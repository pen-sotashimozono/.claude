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
- The same object is written with the same symbol and called by the same
  name wherever it appears in the document. This is the rule, and it is about
  objects: it does not forbid a letter from standing for a different object
  in a section where the first one does not occur. Within one passage a
  letter stands for one object.
- After writing, read each sentence and ask what the reader loses if it is
  deleted. If nothing, delete it.
- A section does not open with a rhetorical question or with a sentence on
  why the topic matters. It opens with the object, what is asked of it, and
  who solved it.
- A word of judgment ("important", "useful", "in practice", "usually") is
  written only where a cited source says it, with the number or the range of
  that source.
- A report of another paper's work gives what was done, in order, the result
  with the scope the paper gives it, and its figure. The paper's own cautions,
  advice and side observations stay out unless the text uses them later.
