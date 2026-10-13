---
name: cold-read
description: Have a passage of a document read by a reader who did not write it, before showing it to the author. The reader follows the passage in order, audits it against every rule in force, and checks each claim against what it rests on - a derived step against the steps before it, a citation against its source, a number against what produced it. Use after writing or rewriting a section, subsection or proof, where the rules in force ask for a reader before the author. Finds where a reader loses the thread, steps that do not follow, and goals that the text announces but does not reach.
---

# Cold read: a first reader before the author

The author should not be the first reader. A passage is shown only after it
has been read twice by others: once by the writer as a reader, once by a
reader with no knowledge of how it was written.

One passage at a time: a subsubsection, a proof, a derivation. A whole section
in one read returns a list too long to act on. Several passages are read by
several readers at once, one per file, each with its own brief.

What differs from one repository to the next is not written here: who the
intended reader is, which passage the author has approved, and how a number
of the document is reproduced. The brief takes these from the repository's
`CLAUDE.md`. `rules/checks.md` says when a passage is sent to a reader, and a
repository that has switched that rule off does not send one.

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
passages it cites and may look up, the approved passage it should read like
if the repository names one, the rules in force, and what the author has said
the text must do. Do not tell it what you think is wrong, and do not give it
your own summary of the passage.

The reader audits the passage against **every rule in force**, not a
selection. The rules in force are all files in `.claude/rules/`, minus those
the repository's `CLAUDE.md` lists under "Rules not in force", plus its "Rules
of this repository only". Give the reader the paths and have it read them
itself. Do not paraphrase the rules into the brief, because a paraphrase drops
the ones the writer already tends to forget. Do not narrow the brief either. A
line such as "mathematics only" or "no comments on style" removes the rules
from the read, and the reader then reports every equation correct in a passage
that breaks half of them.

The reader also checks **every claim of the passage against what it rests
on**. A claim is derived in the text, taken from a reference, or observed
numerically (`rules/checks.md`), and each kind is checked where its basis
lies.

- Derived: the reader redoes each displayed step from the ones before it, and
  may test a formula numerically.
- Taken from a reference: the reader opens the source, which is the TeX source
  `papers/src/<bibkey>.tex` or the PDF `papers/<bibkey>.pdf`. A
  `papers/src/<bibkey>.txt` is an extraction of the PDF that loses symbols: it
  serves to find the place, and the PDF page is then read. For each `\cite`
  the reader finds the section or equation the text names and confirms that it
  says what the passage attributes to it, in the stated notation.
- Observed numerically: the reader runs what the repository names as the
  origin of the numbers and compares each number in the tables and in the
  sentences with the output. A number that nothing in the repository reproduces is reported
  as such, whether or not it is right. A computation too slow to repeat is
  named, and its numbers are reported as not verified.

A kind of claim the passage does not make is left out of the brief. Notes
that lay out known results may hold no number of their own, and a calculation
may cite little.

Brief, to be filled in:

```
Read-only: do not edit any file. Repository: <path>.

You are <the intended reader: e.g. a first-year graduate student in the field>
reading this document for the first time. Read ONE passage in order, without
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
6. Rules. Read CLAUDE.md (sections "Rules", "Rules not in force", "Rules of
   this repository only") and every file of .claude/rules/ that is in force.
   Go through the rules one by one and list every violation in the passage,
   quoted, with the rule it breaks. Say explicitly which rule files you
   checked and found no violation of.
7. Citations. For every \cite in the passage, open the TeX source
   papers/src/<bibkey>.tex or the PDF papers/<bibkey>.pdf (a .txt in
   papers/src is only an extraction: use it to locate the page, then read the
   PDF), and find the section or equation the passage names. Report per
   citation: confirmed (with the location you found), wrong or imprecise
   (what the source actually says), or could not be checked (why). A source
   that is missing or unreadable is reported, not passed.
8. Numbers. <Leave this item out if the passage has none of its own.> Run
   <what the repository names as their origin; how to run it; what is too
   slow to run>. For every number in a table or a sentence, say whether the
   output contains it, to the digits quoted. List the numbers that nothing in
   the repository reproduces.
Judge by the standard of the approved passage, not a stricter one. Where a
rule is broken throughout, say so once and give the worst cases.
Do not rewrite the passage. Do not comment on other parts of the file.
```

Item 5 is the one that pays. A reader who checks every equation and finds them
correct will still report that the passage announced one thing and derived
another, which the writer does not see.

## 3. Act on the report

- A wrong step, a missing link between the stated goal and the method, a
  conclusion asserted without its last step: fix all of these.
- A rule violation is fixed, or the rule is wrong for this case and that goes
  to the author as a question. It is not left standing silently.
- A citation that is wrong or imprecise is corrected from the source. One
  that could not be checked supports an attribution only, and is named in the
  report to the author.
- "Did not know why": add the reason at that point, as one sentence about the
  subject, or reorder so that the reason comes first.
- A request for more explanation is weighed, not obeyed. A cold reader asks
  for everything to be declared and proved in place. Add what removes a
  stopping point, and nothing that only makes the passage longer.
- What the reader found is not yet something the text can rest on. A number
  or a result that exists only in the reader's own working does not go into
  the text: reproduce it from what the repository holds and quote that, or
  state the finding without the number.
- Rebuild and look at the rendered pages.

If the fixes changed the structure of the passage (a new step, a different
order), run step 2 again with a new agent. If they were local, do not run it
again, but check each corrected statement of fact against what it rests on
yourself. In a second read of a passage that was corrected, name the corrected
lines to the reader as lines to check, without saying what was wrong with
them.

## 4. Report to the author

Show the passage together with what the read found and what was changed, in a
few lines. Say what was not fixed and why. The author then reads a passage
whose defects of this kind are already gone, and the report tells them where
to look.

## What this does not replace

Its algebra check is a reader's, not a referee's. Numerical verification of
new formulas, and of the order of every remainder, stays with the writer
(`rules/checks.md`). The citation check confirms that a cited passage exists
and says what is claimed; whether a better or earlier source should be cited
instead is the writer's question.
