# Mathematics

How calculations, statements and proofs are set. In force in every repository
unless its `CLAUDE.md` lists this file under "Rules not in force".

- Show the calculation, not a description of it. Each step that produces a
  result is a displayed equation; prose is one sentence of framing.
- Put a result first, then its derivation, in one continuous chain of
  equalities where possible.
- Write matrices out (a small explicit case) when a matrix is defined by its
  entries, and say which space a matrix acts on.
- Kets are tensor products; sums are written with their ranges.
- Statements that are proved are `theorem` + `proof`; side definitions are
  `remark`. Theorem, Lemma, Proposition, Definition and Remark share one
  counter per section.
- Inside these environments and inside proofs every displayed equation is
  numbered (`equation`, not `equation*`), and later text refers to a step by
  its equation number. Equation numbers are (section.subsection.number).
- A statement lists every hypothesis it needs, in the statement itself. A
  hypothesis used only inside the proof is still a hypothesis.
- An identity that several proofs use is stated once, in a remark, and cited
  from there. It is not re-derived in place.
