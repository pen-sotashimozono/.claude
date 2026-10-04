# Mathematics

How calculations, statements and proofs are set. In force in every repository
unless its `CLAUDE.md` lists this file under "Rules not in force".

- The text is the calculation. Each step that produces a result is a displayed
  equation, and the prose between two displays is the one sentence that says
  what was used to get from one to the next. A paragraph without a displayed
  equation, in a section that derives something, is a sign that the
  calculation has been replaced by a description of it.
- Put a result first, then its derivation, in one continuous chain of
  equalities where possible. A derivation opens with one sentence of goal and
  the target equation, and says why that form can be reached, by the property
  or the earlier result that guarantees it ("$M$ is real and antisymmetric, so
  as shown in Appendix A.1.1 it can be brought to …").
- Each step is a display, introduced by a short phrase that says what the step
  is for or what it uses ("The rows of $iMv = -\epsilon v$ are", "With the
  projector onto $P = p$,"). A bare imperative with no purpose, or two displays
  with nothing between them, leaves the reader following a calculation without
  knowing where it goes.
- What can be said by an equation is said by an equation. A distinction of
  cases (phases, limits, parities) is a `cases` display or a table, not a
  paragraph. Numbers quoted for a formula stand in a display next to it, not
  inside a sentence.
- No `\simeq`, `\approx` or `\sim` in a displayed equation. Write what is
  meant: an equality with its remainder ($= a + O(L^{-3})$,
  $= a \, [1 + O(x^{-1})]$), a limit ($\lim_{r \to \infty} \dots = a$), or a
  bound. Name the limit and what is held fixed. Intermediate steps stay exact
  for as long as they can, and the remainder enters at the step that creates
  it. A leading-order statement that is quoted or only observed numerically is
  marked as such.
- A revision does not remove displayed steps. If the prose grows and the number
  of displays falls, the revision went the wrong way.
- The amount of prose is measured against the sections the author has
  approved (named in the repository's `CLAUDE.md`). Count the words of prose
  per displayed equation in those sections and in the new text. New text that
  needs more than about one and a half times as many is cut before it is
  shown.
- Write matrices out (a small explicit case) when a matrix is defined by its
  entries, and say which space a matrix acts on.
- Kets are tensor products; sums are written with their ranges.
- Statements that are proved are `theorem` + `proof`; side definitions are
  `remark`. Theorem, Lemma, Proposition, Definition and Remark share one
  counter per section.
- Inside these environments and inside proofs every displayed equation is
  numbered (`equation`, not `equation*`), and later text refers to a step by
  its equation number. Equation numbers are (section.subsection.number).
- A statement lists every hypothesis it needs, in the statement itself.
- An identity that several proofs use is stated once, in a remark, and cited
  from there. It is not re-derived in place.
