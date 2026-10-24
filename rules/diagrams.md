# Diagrams

How tensor diagrams carry the text. In force in every repository unless its
`CLAUDE.md` lists this file under "Rules not in force". How a diagram is
built as a figure page is in the `figure-pages` skill.

- A step that has a diagram is not also written as an SVD, a QR or a matrix
  product in prose or in a display. A diagram is followed by one sentence that
  says what its frames and colours mark, never by its formula restated.
- A tensor keeps the rank and the dimensions it was introduced with, in every
  diagram and on both sides of an equation. Two bonds that a contraction
  leaves open are drawn as one fused (double-line) leg.
- The rows of a multi-row diagram share one grid of the chain's sites. Every
  row has the same number of slots, and unused slots are filled with empty or
  pass-through slots instead of a larger pitch. A tensor's position then
  shows which part of the chain it stands for. Frame labels stand outside the
  frames, above the top row and below the bottom row.
- Index letters the reader cannot place (which sites are $p$ and $q$) are
  drawn on the layout of an existing diagram, as a numbered display right
  after the sentence that names them. Generic sites are drawn inside the
  chain, with dots on both sides. When a display is too wide, scale it with
  the width of `\includegraphics`, not by shrinking the diagram's pitch.
- Before drawing a layout, write in words which object stands at which slot
  and which frame is which part.
