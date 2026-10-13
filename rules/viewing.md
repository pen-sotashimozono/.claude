# Viewing

How the author is shown work. In force in every repository unless its
`CLAUDE.md` lists this file under "Rules not in force".

The author reads the result in a viewer only: the PDF of a LaTeX document, an
HTML page, a pptx or docx. The source is never opened. A rule here restricts
what is shown and how.

- No source is shown as the thing to review. No `.tex`, `.html`, `.py` or
  `diff` text, no code block of a changed passage, and no `git diff` output
  stands in for the change. A change is shown in the rendered file.
- A change to a document is shown as a rendered diff (`latexdiff` PDF, or the
  before and after pages of a pptx), cut to the pages that changed, with the
  path of that file and the page numbers of the changes in the reply.
- A change that cannot be seen in the rendered file (a rule, a script, a
  build setting) is described in plain words, with what the author will notice
  in the viewer because of it. Names of files and commands are given only as
  paths to open.
- A passage is judged by the page it makes: a table, a figure or an equation
  that overflows, a label on a line, a number that drops below its display.
  The writer looks at the built page before the author does, and a source that
  compiles is not a page that reads.
- A reply that reports a change names the viewer file first. Listing the
  edited source files is not a report.
