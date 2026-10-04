# Mathematics

How calculations, statements and proofs are set. In force in every repository
unless its `CLAUDE.md` lists this file under "Rules not in force".

- The text is the calculation. Each step that produces a result is a displayed
  equation, and the prose between two displays is the one sentence that says
  what was used to get from one to the next. A paragraph without a displayed
  equation, in a section that derives something, is a sign that the
  calculation has been replaced by a description of it.
- Put a result first, then its derivation, in one continuous chain of
  equalities where possible.
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
