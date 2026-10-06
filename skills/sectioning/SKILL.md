---
name: sectioning
description: Decide where a physics paper, review or set of notes is divided and what its headings say, by comparing with the tables of contents of published reviews and textbooks on the same subject. Use before writing a new section, when a section has grown, when the author criticizes the structure or the titles of a passage, and before renaming or moving anything. Produces a table of contents for the author to approve; text is moved only after that.
---

# Sectioning: the table of contents before the text

The rules are `rules/sectioning.md`. This skill is the procedure that applies
them. Its product is a table of contents, old beside new, with one line of
reason for each change. Nothing in the document is moved or renamed until
the author has seen it.

## 0. Find out what is being criticized

When the author objects to a passage, say back in one sentence what you take
the objection to be, before changing anything, if it can be read in more
than one way. "The procedure belongs in 2.1.3", "this is repeated too often"
and "the title is wrong" call for three different things. Re-partitioning a
passage is the cheapest response and the one most often wrong: it changes
the look and leaves the content. If the objection is about repetition or
about what is said where, go to step 2 first.

## 1. List the units

Read the passage and its neighbours, and write down, without the headings,
what is there:

- the objects that are defined (with the equation that defines each);
- the operations and procedures (input, output, cost);
- the statements that are proved or quoted;
- the examples.

For each unit note what it needs from before it, and every other place in
the document where the same unit, or a variant of it, appears.

## 2. One home for each unit

Where a unit appears more than once, choose the place where a reader would
look for it, state it there in full, and reduce the others to a citation.
Do this across sections, not only inside the passage. A procedure that is
explained once for the decomposition, again for the canonical form and again
for the truncation is one procedure with three uses. This step usually
shortens the text more than any change of headings, and it is what the
author most often means by "the structure is wrong".

## 3. The published tables of contents

Take two or three published reviews or textbook chapters that cover the same
material, and print their heading trees. For a source in `papers/src`:

```sh
grep -oE '\\(sub)*section\*?\{[^}]*\}' papers/src/<bibkey>.tex \
  | sed -E 's/\\section\*?\{/1 /; s/\\subsection\*?\{/2   /; s/\\subsubsection\*?\{/3     /; s/\}$//'
```

For a book, read its table of contents. Note, for the units of step 1:

- at which level each of them stands there;
- what it is called;
- what its siblings are and by which principle they are divided;
- in which order they come.

Where the sources agree, follow them. Where they differ, the difference is a
real choice: say which one the draft takes and why. Do not copy the habits
that `rules/sectioning.md` excludes.

## 4. Draft the table of contents

Write the new tree, titles only. Then test it, heading by heading:

- **Lookup.** Would a reader who wants this thing find it by this title in
  the table of contents, without having read the text?
- **Principle.** Are the children of each heading divided by one principle?
  Name it.
- **Lone child.** Does any heading have exactly one child?
- **Weight.** Is any child a few lines, or several pages holding two units?
- **Parallel.** Read the sibling titles aloud one after the other. Same
  grammar, same level of detail?
- **Role words.** Any "Introduction", "Remarks", "Details", "Properties",
  "Derivation", "Discussion", a question, or a label before a colon?
- **Order.** Does anything use what comes after it?
- **Depth.** Anything below the subsubsection?

A draft that fails a test is changed in the tree, not explained in the text.

## 5. Show the author

Give the author, in the reply and not in the document:

- the old tree and the new tree side by side;
- for each unit that moved or merged, where it was and where it is now;
- for each renamed heading, the reason in a few words;
- which published tree was followed where, and where the draft departs from
  all of them.

Wait for the answer. Titles and divisions are the author's decision.

## 6. Move the text

After approval: move the text, keep every `\label`, and rebuild. A label
that named a removed heading is kept on the unit that replaced it, so that
references elsewhere do not break. Then run the cold read on the passages
whose text changed, not only on the headings.

## What this does not do

It does not shorten a passage that says too much, and it does not decide
what is displayed and what is inline. Those are `rules/prose.md` and
`rules/mathematics.md`. If the table of contents is right and the passage is
still criticized, the problem is there.
