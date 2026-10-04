---
name: cold-read
description: Have a passage of the notes read by a reader who did not write it, before showing it to the author. Use after writing or rewriting any section, subsection or proof - the author reads only what has passed this. Finds where a reader loses the thread, steps that do not follow, and goals that the text announces but does not reach.
---

# Cold read: a first reader before the author

The author should not be the first reader. A passage is shown only after it
has been read twice by others: once by the writer as a reader, once by a
reader with no knowledge of how it was written.

One passage at a time: a subsubsection, a proof, a derivation. A whole section
in one read returns a list too long to act on. Several passages are read by
several readers at once, one per file, each with its own brief.

## 1. Read it yourself first

Print the passage from the source and read it in order, from its first line to
its last, as someone who has to follow it. Do not skim what you remember
writing. Fix what you find before step 2: a cold reader's attention is wasted
on defects you could have seen.

Look for the things the writer cannot feel while writing:

- the opening names a goal, and the calculation that follows reaches a
  different one;
- two displays in a row with nothing saying how the second comes from the
  first;
- a sentence written about the wrong object (a claim that was true of an
  earlier version);
- a symbol whose definition was deleted in an edit, or arrives after its use;
- after a shortening, a display that ends with a period and is followed by
  "which …", or with a comma and is followed by a new sentence.

## 2. The cold reader

Start a fresh agent (general-purpose; it must not inherit this conversation).
Give it only: the path of the passage and where it starts and ends, the
passages it cites and may look up, the approved passage it should read like,
and what the author has said the text must do. Do not tell it what you think
is wrong, and do not give it your own summary of the passage.

Brief, to be filled in:

```
Read-only: do not edit any file. Repository: <path>.

You are <the intended reader: e.g. a first-year graduate student in the field>
reading these notes to learn the material. Read ONE passage in order, without
skipping ahead: <file>, from <first line> to just before <next heading>.
You may look up what it cites: <files / sections>. Read <approved passage>
once: the author approved its style and wants this passage to read like it.
The author's requirement for this passage: <the author's own words>.

Report briefly, most important first:
1. Every place where, reading in order, you did not know why a step was being
   done or where it was going. Quote it.
2. Every step you could not verify within about a minute from what came
   before, or that is wrong. Check the algebra of each displayed equation;
   you may run small numerical checks (<name the formulas worth testing>).
3. Symbols used before they are explained, or never explained.
4. Sentences that say nothing, repeat an equation in words, or talk about the
   document rather than the subject; and places where a needed sentence is
   missing.
5. Whether the passage as a whole does what its opening says it will do, and
   whether it reads like the approved passage. Be specific; do not be polite.
Do not rewrite the passage. Do not comment on other parts of the file.
```

Item 5 is the one that pays. A reader who checks every equation and finds them
correct will still report that the passage announced one thing and derived
another, which the writer does not see.

## 3. Act on the report

- A wrong step, a missing link between the stated goal and the method, a
  conclusion asserted without its last step: fix all of these.
- "Did not know why": add the reason at that point, as one sentence about the
  subject, or reorder so that the reason comes first.
- A request for more explanation is weighed, not obeyed. A cold reader asks
  for everything to be declared and proved in place. Add what removes a
  stopping point, and nothing that only makes the passage longer.
- Rebuild and look at the rendered pages.

If the fixes changed the structure of the passage (a new step, a different
order), run step 2 again with a new agent. If they were local, do not.

## 4. Report to the author

Show the passage together with what the read found and what was changed, in a
few lines. Say what was not fixed and why. The author then reads a passage
whose defects of this kind are already gone, and the report tells them where
to look.

## What this does not replace

A cold read is about following the text. It does not check citations against
their sources, and its algebra check is a reader's, not a referee's. Numerical
verification of new formulas and the check of citations are separate
(`rules/checks.md`).
