# Structure

Where things go in the document. In force in every repository unless its
`CLAUDE.md` lists this file under "Rules not in force".

- New or rewritten text goes inside `\begin{draft}…\end{draft}`. Only the
  author removes a draft environment.
- c.f. references go directly under the small subsection they belong to, and
  only when a fitting reference exists. Cite the paper that computes the result,
  with its section or equation.
- Citations are dense and varied. Each result gets the source that obtained
  it, the original where it can be read, and the same review is not cited for
  everything.
- An appendix is referred to as an appendix ("Appendix A.1.1",
  `Appendix~\ref{…}`), not as "Sec." or "App.".
- Tables and figures are floats with captions, full text width, referred to by
  `Table~\ref` / `Fig.~\ref`. Captions are short.
- Diagrams that make one statement together are one figure, or cells of the
  table that summarises them. A subsection does not get a figure of its own
  because its neighbours have one. How a float is mentioned in the text is in
  `citing.md`.
