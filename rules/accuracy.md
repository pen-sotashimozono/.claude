# Accuracy

What is done before and after writing, so that what is written is true. In
force in every repository unless its `CLAUDE.md` lists this file under "Rules
not in force".

- Every claim has one of three bases, and the text says which: derived here,
  taken from a reference (with its equation or section), or observed
  numerically. A numerical observation is not written as a theorem, and a
  quoted result is not written as if it were derived.
- A citation is written only after the source has been opened and the passage
  found. A work that could not be read supports an attribution ("the theorem
  is due to …"), not a statement of content.
- Before a statement with hypotheses is written, look for a case that breaks
  it: the smallest size, a sign change, a degenerate or zero eigenvalue, a
  complex instead of a real matrix, a set that is not connected. What breaks
  it becomes a hypothesis.
- Verify every formula before writing it, numerically where possible, and
  include the edge cases of its parameters (both sides of a transition, even
  and odd sizes, the limits of each parameter).
- No "(Checked numerically …)" notes in the text unless the author asks.
  Report the check in the reply instead.
- A number in a table or in the text comes from a script committed in the
  repository, with fixed seed and sample size, named in a comment where the
  number appears. A number carried over from an earlier version is recomputed
  or marked as carried over in the reply.
- After a section is written, have it read once by a reviewer who did not
  write it, for the mathematics and for the citations, before it is reported
  as done.
