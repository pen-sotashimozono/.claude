# Sectioning

Where a document is divided and what the headings say. In force in every
repository unless its `CLAUDE.md` lists this file under "Rules not in force".

The measure is the table of contents of a published review or textbook on the
same subject. Read alone, the table of contents is an outline of the objects
of the field and of what is done with them. A rule here restricts what is
written. None of them is met by adding a heading.

## Dividing

- A heading marks a unit that a reader looks up by its name: an object
  ("Matrix product operators"), an operation on it ("Applying an MPO to an
  MPS"), a method with an established name ("Time-evolving block decimation
  (TEBD)"), a class of systems. A step of an argument, a paragraph that is
  long, or the place where the writer changed topic is not such a unit.
- Dividing is not editing. A passage that repeats itself, or that mixes a
  definition with a procedure and its consequences, is not repaired by
  headings between the parts. Remove the repetition and settle where each
  thing is said once, across the neighbouring sections too. Then decide the
  division. If the criticism of a passage is about its content, a new
  partition is not an answer.
- One principle divides the children of a heading: by object, or by
  operation, or by method, or by case (finite and infinite, pure and mixed,
  left and right). Do not mix principles among siblings.
- A heading has no single child. A lone subsubsection is the body of its
  parent, or the parent has a second unit that was not named.
- Three levels below the part: section, subsection, subsubsection. A fourth
  level is a sign that a subsection should have been a section, or that
  steps are being given headings.
- Siblings have comparable weight. A unit of a few lines is merged into its
  neighbour or its parent. A unit that runs over several pages and holds two
  things that are looked up separately is split.
- The order of siblings is the order of dependence: the object before the
  operations on it, the exact form before its approximation, the general
  statement before its cases, the method before its variants.
- A parent's own text, before its first child, states what the children
  share: the setting and the notation. It does not preview them.
- A thing has one home. A definition, a procedure or a cost is given under
  one heading and cited from the others, even when two sections both need
  it.

## Naming

- A title is a noun phrase that names the content: the object, the
  operation as a noun or a gerund ("Truncation", "Compressing an MPS by
  SVD"), the method by its established name. It is not a role
  ("Derivation", "Discussion", "Remarks", "Generalities", "Some
  properties", "Basics", "Details"), not a sentence, and not a question.
- A title carries no label in front of a colon ("TDVP: one-site
  integrator"). The method is the parent, and its parts are the children.
  A colon is allowed where the second half narrows the first to a case
  ("Conventional time evolution: pure states") and the siblings are built
  the same way.
- Sibling titles are parallel in grammar and in the level of detail:
  "Generation of a left-canonical MPS" beside "Generation of a
  right-canonical MPS", not beside "How to go the other way".
- A title is short, about two to six words, and never more than one line of
  the table of contents. A condition, a hypothesis or a result belongs in the
  text.
- A method is named in full where it gets its heading, with its abbreviation
  in parentheses if the abbreviation is used afterwards. A title contains no
  symbol that is defined only inside the section, and no citation.
- The same title does not appear twice under one parent. Under different
  parents it may, when the two parents are built in parallel ("Sweep" under
  the one-site and under the two-site integrator).
- Capitalization follows one convention through the document. The default
  is sentence case.

## Where the measure comes from

The rules were read off the heading trees of published reviews and long
papers on tensor networks: Schollwöck, Ann. Phys. 326, 96 (2011);
Verstraete, Murg and Cirac, Adv. Phys. 57, 143 (2008); Orús, Ann. Phys. 349,
117 (2014); Eisert, Cramer and Plenio, Rev. Mod. Phys. 82, 277 (2010);
Perez-Garcia et al., Quantum Inf. Comput. 7, 401 (2007); Stoudenmire and
White, New J. Phys. 12, 055026 (2010). In them a title has a median of four
or five words; sections are objects or tasks, subsections operations or
methods, subsubsections variants; three levels are used and a fourth is not.
They also contain what these rules exclude (question titles, "Some
properties", a lone subsubsection, conversational colons). Those are the
habits of single authors, not the common practice, and the notes of a thesis
do not copy them. The `sectioning` skill says how to compare a draft with
such a tree.
