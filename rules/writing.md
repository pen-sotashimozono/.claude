# Writing rules for `notes/`

How the text of the notes is written. These are the author's conventions;
apply them to every passage that is added or rewritten.

## Sentences

- No `:` or `;` in the middle of a sentence. A colon is allowed only at the end
  of a sentence, directly before the claim or the displayed equation it
  introduces. Otherwise write two sentences, or join with a conjunction.
- No bullet or numbered lists in running text or in proofs. Write prose
  ("First, … Second, …"). Lists are for genuinely tabular enumerations only.
- No run-in headings (`\paragraph{...}`, "Step 1:", "\emph{Proof.}" labels).
  Use `\subsubsection` / `\subsubsubsection`, or plain text.
- Say what a passage does before doing it ("To diagonalize …", "As in
  Sec. …, …"), and do not introduce a symbol that is used only once.

## Mathematics

- Show the calculation, not a description of it. Each step that produces a
  result is a displayed equation; prose is one sentence of framing.
- Put a result first, then its derivation, in one continuous chain of
  equalities where possible.
- Write matrices out (small explicit cases, e.g. `L = 3`) when a matrix is
  defined by its entries, and say which space a matrix acts on.
- Statements that are proved are `theorem` + `proof`; side definitions are
  `remark`. Before a theorem, say why it matters and where it is used.
  Theorem, Lemma, Proposition, Definition and Remark share one counter per
  section. Inside these environments and inside proofs every displayed equation
  is numbered (`equation`, not `equation*`), and later text refers to a step by
  its equation number. Equation numbers are (section.subsection.number).
- Properties of the Pfaffian that a proof uses are stated in the Pfaffian
  remark of the free-fermion appendix, not re-derived in place.
- Notation must match earlier sections. Kets are tensor products; sums are
  written with their ranges.
- No "(Checked numerically …)" notes in the text unless the author asks. Verify
  every formula before writing it, and report the check in the reply instead.

## Structure

- New or rewritten text goes inside `\begin{draft}…\end{draft}`. Only the
  author removes a draft environment.
- c.f. references go directly under the small subsection they belong to, and
  only when a fitting reference exists. Cite the paper that computes the result,
  with its section or equation.
- Tables and figures are floats with captions, full text width, referred to by
  `Table~\ref` / `Fig.~\ref`. Captions are short.
