# Checks

What the writer does before and after writing. These are obligations of the
writer, not contents of the text: their results go in the reply to the author,
never into the document as sentences. In force in every repository unless its
`CLAUDE.md` lists this file under "Rules not in force".

- Before drafting a section, write its message in at most three sentences and
  the ordered list of its steps. Each step is one claim that needs only
  earlier steps. Every level (sentence, subsection, section) carries one
  message, and neighbouring messages connect. A section's message is not a
  list of its subsections' messages.
- Know the basis of every claim: derived in the text, taken from a reference,
  or observed numerically. In the text a quoted result carries its citation
  and a numerical one the word "numerically", once, where it is stated.
  Nothing more is written about it. The reply lists which claims are quoted or
  numerical.
- Open the source before citing it and find the passage. A work that could not
  be read supports an attribution ("the theorem is due to …"), not a statement
  of content. The reply lists the citations that could not be checked.
- When one claim of a passage is questioned, audit every claim of the passage
  against the source, including claims inherited from an earlier draft. The
  reply says what was wrong, what matched, and what is general knowledge.
  Before concluding that a source does not state something, list all of its
  section headings (Methods included) and search each one.
- When a cited paper contradicts its own definitions or the document's
  derivation, keep the derivable result, leave the paper's number out, and
  say so in the reply.
- Before writing a statement with hypotheses, look for a case that breaks it:
  the smallest size, a sign change, a degenerate or zero eigenvalue, a complex
  instead of a real matrix, a set that is not connected. What breaks it
  becomes a hypothesis in the statement.
- Verify every formula before writing it, numerically where possible,
  including the edge cases of its parameters. No "(Checked numerically …)"
  notes in the text.
- Know the basis of every remainder: derived, or checked numerically by
  watching the error scale with the parameter. The reply says which, and names
  the remainders that are neither.
- After shortening a passage, read it again in order. Shortening cuts
  connectives: a display whose final punctuation no longer fits the sentence
  that follows, a symbol whose definition went with a deleted sentence, a
  conclusion that is no longer drawn.
- A rewrite compresses and restyles. It adds no claim.
- A number in a table or in the text comes from a script committed in the
  repository, with fixed seed and sample size, named in a source comment where
  the number appears. A number carried over from an earlier version is
  recomputed, or named as carried over in the reply.
- Compare the result with the approved sections before showing it: words of
  prose per displayed equation, number of displayed steps against the previous
  version, and sentences about the text itself (there should be none).
- Before showing a section, list its facts and mark every second statement of
  one. Check the text and the figures together, since a diagram can repeat a
  sentence or another diagram.
