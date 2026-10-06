# .claude

The `.claude/` directory shared by the LaTeX repositories made from
[template.tex](https://github.com/pen-sotashimozono/template.tex): the rules
and skills Claude Code reads while working in them. Each repository carries it
as a git submodule at `.claude`.

| Path | Contents |
|---|---|
| `rules/prose.md` | sentences and paragraphs; no sentence about the text itself |
| `rules/mathematics.md` | the text is the calculation; prose measured against approved sections |
| `rules/structure.md` | draft marking, c.f. references, floats |
| `rules/citing.md` | how the text points at a figure, a table or a source: plain sentences, two forms of mention used side by side, no template |
| `rules/checks.md` | what the writer does before and after writing; results go in the reply, not in the text |
| `rules/review-notes.md` | for notes that lay out known results: questions the reader must be able to answer |
| `skills/cold-read/` | a first reader before the author: self-read, then a reader who did not write the passage, who also audits every rule in force and checks each citation against its source |
| `skills/changelog/` | record a change and bump the version |
| `skills/references/` | citations through doiget |
| `skills/figure-pages/` | an equation, tensor diagram or drawing as a figure page |
| `skills/paper-figures/` | a cited paper's own figure, extracted as SVG |

The skills name scripts under `.github/` of the repository they run in
(`bump.sh`, `refs_sync.sh`, `build.sh`, …), so they belong with that template.

## Using it

```sh
git submodule add https://github.com/pen-sotashimozono/.claude .claude
git submodule update --init .claude      # in a clone made without --recurse-submodules
```

Everything in `.claude` is shared. What belongs to one repository only goes in
its `CLAUDE.md`; `.claude/settings.local.json` stays local and untracked.

## How the rules are meant

A rule restricts what is written. It is never met by adding a sentence: rules
phrased as "say X" were tried and produced text in which every result was
followed by a sentence about its status, its use and its limits, with twice
the prose and fewer equations than the sections they were modelled on. The
rules are therefore of three kinds. `prose.md`, `mathematics.md`,
`structure.md` and `citing.md` say what the text looks like. `checks.md` says what the writer
does, and its results are reported to the author in the reply. `review-notes.md`
lists questions the text must answer, by its content and order.

## Which rules are in force

Every file in `rules/` is in force in every repository by default. The files
are split by subject so that a repository can switch one off: it names the
file in its `CLAUDE.md`, in a section headed "Rules not in force", with one
line on why. A file not named there applies. Rules that hold for one
repository only (its own notation, its own running example, which sections to
imitate) are written in that repository's `CLAUDE.md`, not here.

```markdown
## Rules not in force

- `review-notes.md`: this is a research paper, not a set of notes.
```

## Branches: one per repository, `main` for what is common

Each repository works on its own branch of `.claude`, named after it
(`<project>/rules`, or `<project>/<topic>` for a single change), and pins a
commit of that branch. That is the normal state, not a temporary one: a rule
or a skill is changed there, where the need for it appeared, and is tried on
real work for as long as it takes.

```sh
git -C .claude switch -c <project>/rules     # once; later: git -C .claude switch <project>/rules
# edit inside .claude; Claude Code reads the working copy at once
git -C .claude commit -am "feat: ..."
git -C .claude push -u origin <project>/rules
git add .claude                              # pin the pushed commit in the repository
```

Never pin a commit that is not on GitHub: nobody else can check it out.
`git config push.recurseSubmodules check` makes git refuse such a push.

`main` holds only what is common to every repository. It is protected: it
changes only by pull request, merged by squash, and cannot be force-pushed or
deleted. When a change has proved itself in its repository and should hold
everywhere, it is sent as a pull request:

```sh
gh pr create -R pen-sotashimozono/.claude --head <project>/rules
```

A change that has not yet been judged good by the author on real text is not
sent. `main` changing often makes the style of every repository unstable.

To take in what other repositories have made common, merge `main` into the
repository's branch and read the log first, because a changed rule applies to
everything written from then on:

```sh
git -C .claude fetch origin
git -C .claude log --oneline HEAD..origin/main   # what this brings in
git -C .claude merge origin/main
git -C .claude push && git add .claude
```

A repository with no changes of its own may pin `main` directly
(`git submodule update --remote .claude`).

What to put in a pull request:

- **Say why.** A rule records a correction the author made; the pull request
  quotes or describes the case that prompted it, so a later reader can judge
  whether the rule still holds.
- **One rule per bullet, stated as what to do.** If a rule needs an exception,
  write the exception into it rather than adding a second rule that contradicts
  it.
- **Keep it general.** A rule or skill here applies to every repository made
  from the template. What holds for one document only goes in that
  repository's `CLAUDE.md`.
- **Keep skills in step with the template.** A skill names scripts and paths of
  [template.tex](https://github.com/pen-sotashimozono/template.tex). A change
  that needs a script to change goes together with a pull request there, and
  each names the other.
- **Remove what no longer holds.** A rule that is wrong or obsolete is deleted,
  not left in place with a caveat.
