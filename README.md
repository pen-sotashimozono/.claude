# .claude

The `.claude/` directory shared by the LaTeX repositories made from
[template.tex](https://github.com/pen-sotashimozono/template.tex): the rules
and skills Claude Code reads while working in them. Each repository carries it
as a git submodule at `.claude`.

| Path | Contents |
|---|---|
| `rules/prose.md` | sentences and paragraphs; nothing used before it is declared |
| `rules/mathematics.md` | calculations, statements, proofs, numbering |
| `rules/structure.md` | draft marking, c.f. references, floats |
| `rules/accuracy.md` | the basis of each claim, citations, checks before and after writing |
| `rules/review-notes.md` | for notes that lay out known results: motivation, conditions and their failure, mapping to references |
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

## Updating

A repository stays at the commit it pinned and moves only when it chooses to.

```sh
git submodule update --remote .claude    # move to the newest main
git diff --submodule=log .claude         # the commits this brings in
git add .claude                          # then commit the new pin
```

Read the log before committing: a changed rule applies to everything written
in that repository from then on.

## Improving a rule or a skill

`main` is protected: it changes only by pull request, merged by squash, and
cannot be force-pushed or deleted. A change is made where the need for it
appeared, inside the `.claude` of that repository, so it is tried on real work
before it is proposed.

```sh
git -C .claude switch -c <project>/<topic>   # a branch named after the repository it comes from
# edit inside .claude; Claude Code reads the working copy at once
git -C .claude commit -am "fix: ..."
git -C .claude push -u origin <project>/<topic>
gh pr create -R pen-sotashimozono/.claude --head <project>/<topic>
```

Until the pull request is merged, the repository may pin the pushed branch
commit (`git add .claude`). Never pin a commit that is not on GitHub: nobody
else can check it out. `git config push.recurseSubmodules check` makes git
refuse such a push. After the merge, update as above.

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
