# Prose

How sentences and paragraphs are written. In force in every repository unless
its `CLAUDE.md` lists this file under "Rules not in force".

A rule here restricts what is written. None of them is met by adding a
sentence. When a passage breaks a rule, rewrite or delete it.

- No `:` or `;` in the middle of a sentence. A colon is allowed only at the end
  of a sentence, directly before the claim or the displayed equation it
  introduces. Otherwise write two sentences, or join with a conjunction.
- No bullet or numbered lists in running text or in proofs. Write prose
  ("First, … Second, …"). Lists are for genuinely tabular enumerations only.
- No run-in headings (`\paragraph{...}`, "Step 1:", "\emph{Proof.}" labels).
  Use `\subsubsection` / `\subsubsubsection`, or plain text.
- No sentence about the text itself. Do not write what a section will do, has
  done, does not do, or leaves out ("This subsection computes …", "What is
  missing is …", "This is derived here", "It does not yet give …", "not
  evaluated here"). Say the thing, or leave it out. The one exception is a
  single clause of purpose at the start of a calculation ("To diagonalize
  $H$, …").
- A symbol is declared in the phrase that introduces it, not in a sentence of
  its own: "the $L \times L$ matrix $U$", "for a set $S \subseteq K_s$ of
  modes". A symbol defined in a displayed equation that is cited needs no
  second definition. Do not follow an equation with a "Here … is …, … is …"
  sentence that lists its symbols.
- Do not introduce a symbol that is used only once. Write the expression.
- One symbol means one thing within a section, and one thing has one symbol
  and one name throughout the document.
- After writing, read each sentence and ask what the reader loses if it is
  deleted. If nothing, delete it.
