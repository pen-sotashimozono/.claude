---
name: figure-pages
description: Make or change a figure page - a standalone equation, a TikZ tensor diagram (tikz-tensors) or picture, or a computed plot - under figures/src/, built to figures/generated/ as SVG (and PDF for the documents). Use whenever a slide or a document needs a new formula or schematic picture, or a figure's notation, numbering or folder changes.
---

# Figure pages: one output per source

`figures/src/<topic>/<page>.tex|.py` → `.github/tools/figures/build.sh` →
`figures/generated/<topic>/<page>.svg` (and `.pdf` with `--pdf`).

`figures/` holds only what a writer looks at: pages (`src/`), what they build
into (`generated/`, never edited by hand), figures made one by one outside the
page build (`assets/`, the originals), and other papers' figures (`papers/`,
the `paper-figures` skill). The shared files a page uses — `preamble.tex`, `notation.tex` (what the
shapes of a tensor diagram stand for in this project) and the
`tikz-tensors/` ([pen-sotashimozono/tikz-tensors](https://github.com/pen-sotashimozono/tikz-tensors), a git submodule whose main is the canonical release: `tikz-tensors.sh status` / `pin latest` / `dev <topic>` to change the format in place, as a proposal on a branch) — and the
build's `latexmkrc` live in `.github/tools/figures/`; build.sh puts that
directory on TEXINPUTS, so a page just writes `\input{preamble}`,
`\usepackage{tikz-tensors}` and `\input{notation}` and never names it.

Topics are folders in reading order (`01-model`, `02-method`, …); pages are
numbered inside them (`00-…`, `01-…`, `01b-…`). `figures/src/example/` shows
one page of each kind; delete it once a real topic exists.

## What goes in a page

- **The formula only.** No text labels ("one-body:", "ground state:") and no
  `\underbrace{…}_{\text{…}}` explanations — the slide or the caption carries
  the words. Units are part of a formula.
- **One line per page.** A two-line array is two pages (`01a-…`, `01b-…`).
- **A header comment** saying what the page shows, where its numbers come
  from, and which pages it pairs with (by path).
- **Numbers from a source** — a calculation in the repository, or a paper
  checked in `papers/` — never from memory. Recompute a rounded value before
  writing it.
- **One notation for the whole project.** Decide the symbols once (write them
  into CLAUDE.md) and keep every page to them.

## Kinds of page

- **Equation** (`.tex`): `\documentclass[border=4pt]{standalone}`,
  `\input{preamble}`, one `$\displaystyle … $`.
- **Tensor diagram** (`.tex`): add `\usepackage{tikz-tensors}` and
  `\input{notation}`. The package draws shapes, lines and layouts and says
  nothing about what they mean; the meaning is the project's, in
  `notation.tex` next to build.sh. Read that file before drawing: it names the
  types (`fn` a function of position on `cont` wavy legs, `coef` an array,
  `op` an operator, `canl`/`canr`/`center` the canonical form, …), and a
  project changes it to its own. A meaning it lacks is added there once, never
  styled by hand in a page: a node type, with a comment naming the paper it
  follows, used in every page that draws the object. One figure alone does
  not get its own type. A style is not taken from one paper's picture on a
  guess: name the paper and the figure, show one rendered page, and ask.
  Draw on a layout, not with coordinates: `\tnstack{X}{<sites>}{<layers>}`,
  `\tnlayer{X}{<layer>}{<type>/<label>, …}`, `\tnconnect{X}`,
  `\tnopen[label=…]{down}{X}` for the open indices, `\tnmid` / `\tnput` for
  labels, `\tneq` / `\tnapprox` between blocks, `\tnframe` around a group
  that contracts to one array, `\tnopenswap` to exchange two fermion legs.
  The commands are in the submodule's `docs/reference/commands.md`, and
  `examples/` there has a page for most diagrams (an MPS, a canonical form, an
  effective Hamiltonian, a tree, a PEPS) to start from. Put the coefficients
  on top of the basis functions, so the basis visibly sits between the numbers
  and space.
- **Picture** (`.tex`): plain TikZ with the theme's colours (from tikz-tensors);
  parts a project reuses go in a `.sty` next to build.sh (found on TEXINPUTS).
  Labels are LaTeX math, so they match the equations.
- **Computed plot** (`.py`): a script that writes the SVG path it is given
  (matplotlib with `svg.fonttype = path`, say); run it with `PYTHON=` an
  interpreter that has what it imports.

A figure showing *another paper's* result is never drawn here: extract the
original with the **`paper-figures`** skill.

## Build and look

```sh
.github/tools/figures/build.sh                  # every page that is out of date
.github/tools/figures/build.sh 02-method        # one topic (or a page's path)
.github/tools/figures/build.sh --pdf            # also keep each LaTeX page's PDF
.github/tools/figures/build.sh --force          # rebuild everything
qlmanage -t -s 900 -o /tmp figures/generated/02-method/01-energy.svg   # macOS preview; then look at it
```

- **Slides** paste the SVG (glyphs are paths, so no TeX fonts are needed).
- **Documents** include the PDF: with `\graphicspath{{figures/}}`,
  `\includegraphics{generated/<topic>/<page>}`. The PDF is not committed:
  `latexmk` builds the ones that are missing before it compiles a document.
  After editing a page, build with `--pdf` and commit the SVG; the arXiv bundle
  keeps the path below `figures/`.
- A page is rebuilt when it, or a shared file of its kind in
  `.github/tools/figures/`, is newer than its SVG; slow Python pages run
  under `PYTHON=` an interpreter that has what they need.
- `build.sh` deletes any SVG or PDF whose source is gone, so `generated/`
  mirrors `src/`. It never reads or writes `assets/`.

Always look at the rendered page before reporting it done — a label can
collide, a line can run off, a symbol can come out wrong. Check labels and
lengths on a render at 200 to 300 dpi, not by eye. A label touching a node or
another index is moved one or two millimetres at a time until it is clear.

## Pitfalls

Each of these has cost a failed build or a misdrawn page.

- A triangle (`canl`, `canr`) is placed by its flat-side corner, so its
  flat-side index comes out about twice as long as its apex-side index. To
  even them, shift the neighbouring centre-anchored nodes with a style
  declared inside the `tikzpicture` (declared before `\begin{document}` it
  fails). `xshift` has no effect on a leg-anchored type.
- `\tnframe` and `\tnmid` need real node names, never a dots slot.
- An xcolor mix is at most 100 percent: `canr!120!black` stops the build.
- `build.sh` takes a topic or the path of a page file, not `<topic>/<page>`.

## Moving the tikz-tensors pin

1. Copy `figures/generated/` aside as the baseline (it is not in git).
2. Run `tikz-tensors.sh pin latest` and read the package CHANGELOG between
   the two versions.
3. Take out of `notation.tex` what the package now ships, and rewrite every
   renamed command in the pages with one regex pass.
4. Run `build.sh --pdf-only`, then compare old and new pages by the hash of a
   60 dpi render. Only pages that use a changed shape may differ. Look at
   those pages side by side, and say how many were not looked at.
5. The documents must then build without warnings, and the PR needs
   `bump.sh --affected`.

## Renaming or moving pages

Pages refer to each other by path in their comments, and documents include
them by path. After moving or renumbering, rewrite every reference
(`grep -rn '<old path>' figures/src *.tex notes CLAUDE.md`) and rebuild.
