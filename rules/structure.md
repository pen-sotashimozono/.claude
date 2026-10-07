# Structure

Where things go in the document. In force in every repository unless its
`CLAUDE.md` lists this file under "Rules not in force".

- New or rewritten text goes inside `\begin{draft}…\end{draft}`. Only the
  author removes a draft environment.
- c.f. references go directly under the small subsection they belong to, and
  only when a fitting reference exists. Cite the paper that computes the result,
  with its section or equation. The location is given as it stands in the copy
  under `papers/`: an equation number of that copy, or the title of the
  section when the copy is a preprint whose numbers differ from the published
  ones.
- Citations are dense and varied. Each result gets the source that obtained
  it, the original where it can be read, and the same review is not cited for
  everything.
- An appendix is referred to as an appendix ("Appendix A.1.1",
  `Appendix~\ref{…}`), not as "Sec." or "App.".
- Tables and figures are floats with captions, full text width, referred to by
  `Table~\ref` / `Fig.~\ref`. Captions are short.
