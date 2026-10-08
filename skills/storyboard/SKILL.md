---
name: storyboard
description: Write or update a slide's page in the storyboard (slides/board/), where a slide of slides/main.pptx is laid out from figures/assets/ SVGs, related to its neighbours, and backed by references linked to papers/. Use when a slide is planned, reorganized, or its sources checked - before it is built in PowerPoint.
---

# A slide's storyboard page

`slides/board/` is where a slide's content is organized before PowerPoint.
One page per slide, three sections:

| Section | Holds |
|---|---|
| **Slide** | a 16:9 mock: `figures/assets/` SVGs placed as they will sit, every one a link to its SVG |
| **Relations** | how the pieces follow from each other and from the neighbouring slides |
| **References** | papers, books, web pages, each linked to the local original where one exists |

```
slides/board/
├── index.html   generated: the index and every page, switched by #anchor
├── pages/       the source, one NN-<slug>.html per slide  <- edit here only
└── utils/       build.sh, serve.py, copy-file, style.css, board.js, assets.js (generated)
```

## Writing a page

Start from `page-template.html` in this skill: copy it to
`slides/board/pages/NN-<slug>.html`, NN = the slide's number in the deck.

- **Keep the head as it is.** `<base href="../">` makes the page resolve its
  paths from `slides/board/` when opened on its own; the three `utils/` lines
  give it the style, the figure data and the viewer. `<title>` is
  `NN · Title`; `description` and `thumb` feed the index card.
- **Paths are relative to `slides/board/`**: figures `../../figures/assets/<topic>/<page>.svg`,
  papers `../../papers/<key>.pdf`. Never absolute, never `file://`.
- **Slide mock.** Figures in `<a class="fig">` (drawings), `<a class="eq">` or
  `<a class="eq2">` (one- or two-line equations), each linking its SVG. Slide
  text in `<span class="note">`, in English, as on the deck.
- **Relations** is a table of linked figures and one sentence each: what the
  second adds to the first, and `→ slide N` where the slide hands over.
- **Page flags** use `<p class="desc"><span class="warn">要確認</span> …</p>`
  under the mock, e.g. a label on the deck that is wrong.

## Citations: key and page only, resolved from references.bib

Cite where the claim is made -- in the slide mock, right after the figure or
line it backs (it renders under it; there is no separate citation line), or in
a Relations row -- with the key, the page of the original that holds it, and
what it backs:

```html
<cite data-key="lowdin1950nonorthogonality" data-page="4" data-note="the orthonormalized set"></cite>
```

`utils/cite.py` (run by `build.sh`) writes the short reference, linked to
`papers/<key>.pdf#page=4` through the entry's `file` field, and fills
`<ol class="bibliography auto"></ol>` in References with every work the page
cites: the full reference from the bib, PDF / full text / DOI, and each
place it is cited with its page and note. Never type a reference by hand.
Books and web pages outside the bib stay as hand-written `<li>` in that list.

**Add `data-quote`** -- a few words copied from the original; several
passages separated by `|`. Each is looked for on the cited page, then
anywhere in the PDF, and boxed where it is (from the text layer,
`pdftotext -bbox-layout`; a word broken at a line end is joined). Clicking
the citation opens the whole PDF in the viewer (vendored pdf.js,
`utils/pdfjs/`) at the cited page, every passage boxed, the note and a
jump link per passage above. That needs the server; from disk the viewer
falls back to the cited page as an image (`utils/pdfpages/`). `build.sh` reports a quote it cannot locate: shorten it, or
take the words exactly as the text layer has them (OCR in old scans).

**A slide that makes choices gets a Choices section** (between Slide and
Relations): one row per decision -- what was chosen, and what each cited
work did to justify it -- so a cluster of citations under one figure is
explained, not just listed.

- **Find the page before citing it**, in the text, not from memory:
  ```sh
  for p in $(seq 1 $(pdfinfo papers/KEY.pdf | awk '/^Pages/{print $2}')); do
    pdftotext -f $p -l $p papers/KEY.pdf - | grep -q 'PHRASE' && echo "p$p"; done
  ```
  Read the context: a value can appear more than once with different
  meanings (Pachucki 2010's abstract quotes r = 1.4011 au; the talk uses
  Table IV's r = 1.40, p.12).
- A key not in `references.bib` renders as `key?` with `bib 未登録`: register
  it through the `references` skill (doiget cite) even before its PDF is
  in hand. An entry without a local PDF renders `未取得`, linked to its DOI:
  that is the list of originals still to fetch. Once a licensed PDF is at
  `papers/<key>.pdf`, run `refs_sync.sh` (it writes the `file` field) and rebuild.

## Build and check

```sh
./slides/board/utils/build.sh
```

It writes `slides/board/index.html` (and `utils/assets.js`, the SVG texts for
copying) and fails on any relative link or `#anchor` that does not resolve.
Then look at the result — render it rather than trusting the markup:

```sh
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new \
  --window-size=1200,900 --screenshot=/tmp/board.png \
  "file://$PWD/slides/board/index.html#NN-<slug>"
```

## The server, for Copy file

In the viewer (click any figure), **Copy file** puts the SVG on the clipboard
the way Finder's Copy does, so PowerPoint pastes a vector. That needs
`slides/board/utils/serve.py` running; a page opened from disk then moves to
the served copy by itself. Start it for the session with both checkouts:

```sh
python3 slides/board/utils/serve.py \
  --root "$HOME/Library/CloudStorage/Dropbox/remotely-save/Review-HartreeFockDMRG" \
  --root "$HOME/orca/workspaces/Review-HartreeFockDMRG/jawfish"
```

It listens on 127.0.0.1:8765 only and refuses paths outside the roots. After
changing `serve.py`, restart it. Keeping it running across logins (launchd)
is the user's decision; do not install it unasked.

## Pitfalls met before

- An id starting with a digit is not a CSS `#id` selector — use `[id="…"]`.
- A figure drawn by a Python page has only a viewBox: give it a width
  (`.fig img{width:100%}`) or a flex column shrinks it to nothing.
- Scripts read from disk may not be decoded as UTF-8: keep `utils/*.js`
  ASCII, non-ASCII as `\uXXXX`.
- An embedded browser pane (Orca) shows local files but will not navigate
  between them, and may refuse a file:// page's `fetch` to http — hence the
  single index with anchors, the in-page viewer, and the `<img>` ping.
