# Checks

What the writer does before and after writing. These are obligations of the
writer, not contents of the text: their results go in the reply to the author,
never into the document as sentences. In force in every repository unless its
`CLAUDE.md` lists this file under "Rules not in force".

- Know the basis of every claim: derived in the text, taken from a reference,
  or observed numerically. In the text a quoted result carries its citation
  and a numerical one the word "numerically", once, where it is stated.
  Nothing more is written about it. The reply lists which claims are quoted or
  numerical.
- Open the source before citing it and find the passage. A work that could not
  be read supports an attribution ("the theorem is due to …"), not a statement
  of content. The reply lists the citations that could not be checked.
- Before writing a statement with hypotheses, look for a case that breaks it:
  the smallest size, a sign change, a degenerate or zero eigenvalue, a complex
  instead of a real matrix, a set that is not connected. What breaks it
  becomes a hypothesis in the statement.
- Verify every formula before writing it, numerically where possible,
  including the edge cases of its parameters. No "(Checked numerically …)"
  notes in the text.
- A numerical check contains a variant that must fail: one sign changed, one
  term left out, a derivative moved to the other factor. A check that would
  pass for a wrong formula shows nothing. An overall sign, a comparison of an
  expression with itself in another order, and an integral that vanishes by
  symmetry are not controls.
- Before introducing a symbol, search the section and the passages it cites
  for that letter. The clashes to look for are with a symbol defined pages
  earlier, and with a letter the document already uses for another quantity.
- Know the basis of every remainder: derived, or checked numerically by
  watching the error scale with the parameter. The reply says which, and names
  the remainders that are neither.
- After shortening a passage, read it again in order. Shortening cuts
  connectives: a display whose final punctuation no longer fits the sentence
  that follows, a symbol whose definition went with a deleted sentence, a
  conclusion that is no longer drawn.
- A number in a table or in the text comes from a script committed in the
  repository, with fixed seed and sample size, named in a source comment where
  the number appears. That holds for the numbers in the sentences as much as
  for those in the tables, and for a number a reviewer found: the reviewer's
  script is committed first, or the text states the finding without the
  number. A number carried over from an earlier version, or read off a run by
  someone else, is recomputed, or named as such in the reply.
- A measurement is stated with its scope. The sentence that summarises a table
  says no more than the table: which fixtures, which rows, how many of how
  many. A result that goes against the method is written with the same weight
  as one that goes for it.
- A cause given for a number is one that was varied. If an error is put down
  to the truncation, the step or the rounding, the run that changes that one
  thing is in the committed script. Otherwise the candidates are named as
  candidates.
- After a section is written or rewritten, have it read once by a reviewer who
  did not write it (the `cold-read` skill), before the author sees it. The
  reader follows the text, audits it against every rule in force, and checks
  each citation against its TeX source or its PDF. Fix
  what is found, and report in the reply what was found, what was changed and
  what was left.
- A correction is checked like new text. A sentence changed after a review
  states a fact again (a number, an attribution, a hypothesis, a count), and
  that fact is compared with the script output or the source before the
  correction is reported. Corrections made from a reviewer's summary, without
  opening what the reviewer opened, are where the next errors come from.
- Compare the result with the approved sections before showing it: words of
  prose per displayed equation, number of displayed steps against the previous
  version, and sentences about the text itself (there should be none).
