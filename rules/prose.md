# Prose

How sentences and paragraphs are written. In force in every repository unless
its `CLAUDE.md` lists this file under "Rules not in force".

- No `:` or `;` in the middle of a sentence. A colon is allowed only at the end
  of a sentence, directly before the claim or the displayed equation it
  introduces. Otherwise write two sentences, or join with a conjunction.
- One claim per sentence. A sentence that needs "and so … which … because" is
  several sentences.
- No bullet or numbered lists in running text or in proofs. Write prose
  ("First, … Second, …"). Lists are for genuinely tabular enumerations only.
- No run-in headings (`\paragraph{...}`, "Step 1:", "\emph{Proof.}" labels).
  Use `\subsubsection` / `\subsubsubsection`, or plain text.
- Say what a passage does before doing it ("To diagonalize …", "As in
  Sec. …, …").
- Nothing is used before it is declared. A symbol, an abbreviation or a named
  object is introduced in the sentence where it first appears, with what it is
  (a number, a vector, an $N \times N$ matrix, an operator on which space) and
  what its indices run over. A symbol defined far back is recalled with a
  reference to its definition.
- Do not introduce a symbol that is used only once. Write the expression.
- One symbol means one thing within a section, and one thing has one symbol
  and one name throughout the document.
- No step is left as "clearly" or "it follows". If a step takes the reader more
  than a line to check, write that line.
