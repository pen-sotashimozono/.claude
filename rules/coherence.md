# Coherence across scales

Viewpoints for planning and auditing a document as a whole. Unlike the other
rule files these are **recommendations, not requirements**: a text is better
the more of them hold, and an audit reports where they do not, but none of
them is met by adding a sentence, and none overrides the rules on prose and
mathematics. In force in every repository unless its `CLAUDE.md` lists this
file under "Rules not in force".

## One message per block, at every level

- A document is coherent at several scales at once: equation to equation,
  paragraph to paragraph, subsection to subsection, section to section. Good
  connection at the smallest scale does not give it at the larger ones.
- Each block at each level (subsubsection, subsection, section) has one
  message that can be said in a sentence. The message of a parent is not the
  list of its children.
- Each section has a view that suits it best: its organizing question. A new
  section is easiest to place by what it removes from, or adds to, the one
  before ("what did translation invariance protect, what holds without it,
  what appears without it").
- Do not reduce a section to one summary and then write from the summary. A
  summary keeps one aspect. What makes the section's own view the right one is
  lost with the others.

## Connections

- The message of each block follows from the one before it and leads to the
  next, at each level separately. Check subsection against subsection and
  section against section, not only line against line.
- Blocks on different topics may say the same thing. Look for it: the same
  object under two names, the same question answered in several places ("how
  does the smallest energy close with the size"), one construction that is a
  special case of another. Where it is found, say it once and let the later
  place build on the earlier one instead of deriving it again.
- Text the author has approved defines the views already in use. New text
  builds on them, with their notation and their names. Where new text needs a
  different view, that is a decision for the author, raised in the reply.
- A statement that promises something elsewhere ("derived in Sec. …") is
  checked against what that place now contains.

## Messages before text

- Decide the messages of a section before writing it, and propose them to the
  author in the reply: the organizing question, a few messages, and for each
  the calculation that carries it.
- Test a candidate message with a small calculation before building text on
  it. Expectations fail, and what replaces them is often the better message.
  A result that goes against the expectation is kept and stated.
- Known facts are the starting point of a section, not its content. The
  question is what follows from them, or what happens just outside them.
- How much of a calculation is shown depends on the role of the section.
  Where the section is the foundation, the details are the content. Where it
  generalizes an earlier one, show what differs and say that the rest carries
  over.
- Work in two passes. First fix the messages, with results and numbers enough
  to know that they stand. Then follow the calculations through. The reply
  after the first pass lists the derivations still owed.

## Form

- Titles of sections and subsections state the claim, not the topic.
- A line-by-line correspondence between two cases is a table.

## Auditing

An audit against this file reads the document level by level and reports, in
the reply and not in the text: the message of each block; where two adjacent
blocks do not connect; where two distant blocks say the same thing without
saying so; where new text departs from the approved text in view, notation or
promise. It distinguishes what is a defect from what is a choice for the
author.
