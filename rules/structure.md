# Structure

Where things go in the document. In force in every repository unless its
`CLAUDE.md` lists this file under "Rules not in force".

- New or rewritten text goes inside `\begin{draft}…\end{draft}`. A draft
  environment is taken out only when the author names the passage. A bare
  "ok" does not count: ask once where the boundary falls. Then, in one
  change, close the draft before the passage and reopen it after, so its
  neighbours stay draft.
  Update the status list in the repository's `CLAUDE.md`, if it keeps one, in
  the same commit, rebuild, and look at the page where the colour changes. A
  sentence proposed to the author but not yet in the text goes in only if the
  author agrees. Approval of the draft marking is not approval of those
  sentences.
- c.f. references go directly under the small subsection they belong to, and
  only when a fitting reference exists. Cite the paper that computes the result,
  with its section or equation.
- Citations are dense and varied. Each result gets the source that obtained
  it, the original where it can be read, and the same review is not cited for
  everything.
- An appendix is referred to as an appendix ("Appendix A.1.1",
  `Appendix~\ref{…}`), not as "Sec." or "App.".
- Tables and figures are floats with captions, full text width, referred to by
  `Table~\ref` / `Fig.~\ref`. Captions are short. A caption and the text
  agree: an item the caption names gets a clause in the text. The caption of
  a result figure names the plotted quantity, the axes and every shaded or
  dashed region. No legend of unexplained letters.
- A figure float stands where the text introduces what it shows. Each result
  figure gets its own float, after the paragraph it belongs to. After
  building, find the page each float landed on. If it drifted a page, or left
  a page half empty or a figure alone before a new part, choose one fix:
  shrink it, cut a clause that restates it, or move it ahead of its
  paragraph. Say the cost in the reply.
- Diagrams that make one statement together are one figure, or cells of the
  table that summarises them. A subsection does not get a figure of its own
  because its neighbours have one. How a float is mentioned in the text is in
  `citing.md`.
- When the author removes a subsection, delete its text, its figure pages and
  their built files. Drop its mentions in the section opening and in
  `CLAUDE.md`, check that no `\ref` is left dangling, rebuild, and record the
  topic as an issue with what is known and its sources. The bibliography entry
  the issue cites stays.
- A general subsection (a theory, an operation that several methods use)
  names no method that a later subsection owns.
- Variants of one method are told as a flow, not as parallel papers. A later
  variant says what differs from the earlier one and points at it for the
  rest. It does not repeat the earlier whole-chain display with two rows
  swapped. The step-by-step retelling is cut, but the variant's own sweep
  figure is kept: short text, full figure. Where the variant changes a cost,
  give the two costs side by side, per part and for the whole step. Where its
  novelty is how it chooses, its condition (the cost function) and the cheap
  approximation to it are the centre of the subsection and come before the
  mechanical parts.
