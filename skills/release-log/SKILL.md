---
name: release-log
description: Bring a document's released versions to this machine - each version's PDF and its latexdiff against the one before, in log/<document>/, with a page listing every version, its date, pages and what changed. Use when the author asks what a past version looked like, what changed between versions or since one was handed to someone, or wants the released PDFs at hand instead of downloading them from GitHub one by one.
---

# Released versions, at hand

Every merged PR that bumps a document releases it: the PDF of that version and
a latexdiff against the version before. They sit on GitHub, one page per
version. This brings them here.

```sh
python3 .github/scripts/release_log.py notes              # the last three versions
python3 .github/scripts/release_log.py notes --last 10
python3 .github/scripts/release_log.py notes --all
python3 .github/scripts/release_log.py notes 0.1.2 0.1.5  # these versions
python3 .github/scripts/release_log.py notes --list       # the page only; downloads nothing
```

It writes into `log/<document>/`, which git ignores:

| File | What it is |
|---|---|
| `v<version>-<document>.pdf` | the document as released |
| `diff-v<version>-<document>.pdf` | what changed from the version before, marked in the text |
| `index.md` | every version: date, pages (and the change in pages), the changelog's line, links to the files that are here |

A file already there is not fetched again, so asking for more versions later
only adds to the folder. Needs `gh`, signed in.

## Using it

- **Start from `index.md`.** `--list` costs nothing and shows which version to
  look at. Fetch only the versions the question is about.
- **"What changed in 0.1.5?"** is the diff PDF of 0.1.5, and the changelog's
  line on the page. Read the diff PDF, do not paraphrase the changelog.
- **"What changed since the version I gave to …?"** spans several versions,
  and no single diff PDF covers it. Use the text, which is exact and greppable,
  and render it only if the author wants to read it:

  ```sh
  git diff v0.1.2-notes HEAD -- '*.tex'             # the change itself
  ./.github/scripts/diff.sh v0.1.2-notes            # a rendered latexdiff, tag -> working tree
  ```

- **"What did 0.1.2 say about …?"** is `git show v0.1.2-notes:<file>` for the
  source, or the PDF in `log/` for how it looked.
- A version number without a document means nothing here: each document has
  its own ladder. Ask which document when it is not clear.

## What it is not

- `log/` is a copy. Nothing in it is edited, and nothing there is committed.
- `out/` is the build of the working tree, emptied by a clean. A released PDF
  never goes there.
- The arXiv bundle and the copy without draft marking are not fetched; take
  those from the release page when they are needed.
