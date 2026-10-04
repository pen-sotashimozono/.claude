# claude-tex

The `.claude/` directory shared by the LaTeX repositories made from
[template.tex](https://github.com/pen-sotashimozono/template.tex): the rules
and skills Claude Code reads while working in them. Each repository carries it
as a git submodule at `.claude`.

| Path | Contents |
|---|---|
| `rules/writing.md` | how the text of `notes/` is written (sentences, mathematics, structure) |
| `skills/changelog/` | record a change and bump the version |
| `skills/references/` | citations through doiget |
| `skills/figure-pages/` | an equation, tensor diagram or drawing as a figure page |
| `skills/paper-figures/` | a cited paper's own figure, extracted as SVG |

The skills name scripts under `.github/` of the repository they run in
(`bump.sh`, `refs_sync.sh`, `build.sh`, …), so they belong with that template.

## Using it

```sh
git submodule add https://github.com/pen-sotashimozono/claude-tex .claude
git submodule update --init .claude      # in a clone made without --recurse-submodules
git submodule update --remote .claude    # move to the newest main; then git add .claude
```

To change a rule or a skill, edit inside `.claude`, commit and push there
first, then `git add .claude` in the repository that uses it.

Everything in `.claude` is shared. What belongs to one repository only goes in
its `CLAUDE.md`; `.claude/settings.local.json` stays local and untracked.
