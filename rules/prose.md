# Prose

How sentences and paragraphs are written. In force in every repository unless
its `CLAUDE.md` lists this file under "Rules not in force".

A rule here restricts what is written. None of them is met by adding a
sentence. When a passage breaks a rule, rewrite or delete it.

- No `:` or `;` in the middle of a sentence. A colon is allowed only at the end
  of a sentence, directly before the claim or the displayed equation it
  introduces. Otherwise write two sentences, or join them with the word that
  states their relation ("so that", "which", "therefore", "because"). A limit
  followed by what still holds is two sentences joined by "however", not one
  joined by "and".
- A display is introduced by a sentence and ends with the punctuation that
  sentence needs. Text after a display that continues the sentence starts in
  lowercase ("with", "where", "which gives"). After a display that ends the
  sentence, a new sentence starts. No "so" between two displays.
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
  letter stands for one object. A symbol is not borrowed from a section the
  reader is not in. Distinct symbols go only to objects the reader must tell
  apart, not to every variant. A name that clashes with the literature ($N$ as
  a count of sites) is flagged to the author.
- After writing, read each sentence and ask what the reader loses if it is
  deleted. If nothing, delete it.
- A section does not open with a rhetorical question or with a sentence on
  why the topic matters. It opens with the object, what is asked of it, and
  who solved it. An opening carries information: the general object first,
  then the route taken, then what changes and at what cost or with what
  consequence. A new opening over an unchanged body is not a revision.
- A motivation is true of its subject and of nothing else. A motivation that
  would fit a neighbouring concept is cut. A section that several later
  sections use is opened for all of them, not for the first, and may end with
  one clause on where its applications are. A roadmap of its subsections is
  still not written.
- A word of judgment ("important", "useful", "in practice", "usually") is
  written only where a cited source says it, with the number or the range of
  that source.
- A report of another paper's work opens with the problem before the result.
  It says what the data are (what one sample is), what is wanted from them,
  and why that is hard, with the cost or the scaling the paper gives. Then it
  gives the idea and the one fact that makes it plausible, what was done, in
  order, the quantity measured, the dependence that decides whether the idea
  helps, the comparison at equal resources, the result with the scope the
  paper gives it, and its figure. Each stage is a few sentences carrying the
  paper's numbers. The paper's own cautions, advice and side observations
  stay out unless the text uses them later. What can be done with a result is
  said only as the paper says it, and what the paper proposes as future work
  is left out.
- A measured quantity in such a report is introduced with what it decides:
  what depends on it, and for which values the method wins. Each case is then
  read against that criterion, including any case the paper says the method
  does not win. A quantity used as a criterion first says what each of its
  values means for the object.
- When a paper writes a field object as an MPS, the report says how the array
  gets its indices, how the chain follows, what a bond separates, and which
  measured quantity is the bond dimension that bond needs.
- Write for the reader named in the repository's `CLAUDE.md`, and assume
  nothing else. A term from another field ("multi-configuration", "active
  space") is introduced by the problem it solves, in plain words. An
  abbreviation is spelled out at first use. A system from another field opens
  with its governing equation, what its control parameter measures and which
  direction of it is hard. A data set is named by what happens in it before
  its name is used.
- A rule names what a sentence must contain, not its wording. Do not turn a
  rule's shorthand ("what it is after") into a sentence. Write a plain verb
  whose object is what is achieved (enlarges, replaces, reaches, finds), and
  read every new opening for grammar before building.
