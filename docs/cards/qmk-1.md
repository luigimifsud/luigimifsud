# QMK-1

QMK-1 was a learning model in the QMK line, the work before Project Hail Mary.

| | |
|---|---|
| Project | QMK and AMK, the learning work before Project Hail Mary |
| Dates | Results on record from 20 to 25 Sep 2026; switched off on 29 Sep 2026 |
| Hardware | My home PC, as recorded for the 20 Sep reasoning test |
| Status | Retired. Switched off on 29 Sep 2026. |

## What it was for

QMK-1 learned from plain text. I tested how well it linked words that go together, and asked it questions and problems whose answers I knew and had not shown it. Like the rest of the line, it never got past reading back what it had been fed.

## What it was trained and tested on

Plain text, including text it fetched itself. In one test I measured it after reading from 100 MB up to 4,800 MB. The tests used held-out word pairs (978,478 in one test, 2,420 in another, where 0.5 is chance), 60 questions of 40 steps each scored on text it had never seen, and problems whose answers I had not shown it.

## Results

- **The audit.** An audit of QMK-1 on 22 Sep 2026, which changed nothing it read, found 1,263 confirmed findings in its code, grouped into 27 fixes, and found that the copy running was 43 hours older than the code. On ten questions I had asked about QMK-1 it gave 8 NEGATIVE, 2 UNKNOWN and none POSITIVE. It also found one loop that had written nothing for 10 hours, and that 39 of 3,888,333 recorded entries carried a verdict. Who ran the audit is not recorded. These come from the audit report, not re-run since, and describe QMK-1 on 22 Sep, before it was switched off.
- **The bug that was blamed.** On 20 Sep 2026 I tested what was really holding QMK-1's reasoning back, on 60 questions of 40 steps each, scored on text it had never seen. Fixing the bug that was blamed changed its score by exactly zero (0 of 60 questions changed). A different change lifted the score from 0.3189 to 0.5761 (better on 43 of 60 questions, 5.10 standard errors). The part that was expected to matter added 0.0163 (plus or minus 0.0474) on top, and a matched control version scored 0.6089 against its 0.5924. My own questions, not an outside benchmark, and one run. The result file does not define the score in the lines that give it. This does not show that part is worthless; it shows this way of using it added nothing measurable.
- **More text, smaller gains.** On 20 Sep 2026 I measured how a QMK-1 word-pair score grows with the amount of text read, on 978,478 held-out word pairs where 0.5 is chance (a control scored 0.5034). It scored 0.63726 at 100 MB, 0.64598 at 200, 0.65325 at 400, 0.66054 at 800, 0.66612 at 1,600, 0.66943 at 3,200 and 0.67098 at 4,800 MB, with uncertainty about 0.0003. The gain per doubling fell from 0.0087 to 0.0033, and from 3,200 to 4,800 MB the gain was 0.0016. Each size is the best of seven settings, picked on the same pairs, so it is slightly optimistic, and there is one run per size. This is a word-pair score, not a language-model score. A second file from the same work gives 0.66265 at 4,800 MB for the full 45,066-word vocabulary, and the two files do not say how they differ, so this is one setup, not a settled curve.
- **Adding parts made it worse.** On 21 Sep 2026 I tested three extra parts added to QMK-1's base, on 2,420 held-out word pairs where chance is 0.5. The base alone scored 0.7029 (plus or minus 0.0093), and each extra part scored above chance on its own (0.5789 to 0.6777). All three together scored 0.6657 with equal weights and 0.6864 with weights set by what each part earned, both below the base alone. My note records that no compounding was observed. Noise on these comparisons is about 0.013. A word-pair score, not a language-model score, recorded in its result file and not re-run since.
- **A repeatability fix.** On 22 Sep 2026, in a scratch copy of QMK-1, I tested a fix to one step where it makes a choice. With the new rule, two runs gave the same choice at all 200 positions; with the old one, 194 of 200 differed. For a second such step, the new rule differed on 0 of 90 pairs across 3 seeds, and the old rule on 90 of 90. This is a repeatability check from one scratch run: it shows the same input gives the same choice, not that the choice is better. How often the two rules would choose differently on live runs was not measured.
- **A rewiring that failed its own check.** On 24 Sep 2026 I rewired five files in a copy of QMK-1's code and ran its four-part self-check 40 times, each run unseeded. The original passed all four parts on 40 of 40 runs; the rewired copy passed on 19 of 40 (0.4750 plus or minus 0.0790), a drop of 0.5250 that is outside its own spread. That is worse on this one check; other counts in the same pass moved the right way. With the original's seeds switched off while it ran, the same check held on 24 of 40 (0.6000 plus or minus 0.0775), so a single run of it is not a verdict. The changes stayed on the copy: none of the 29 live files was written.
- **Problems with known answers.** On 25 Sep 2026, in two snapshots taken part-way through a run, I asked QMK-1 problems whose answers I knew and had not shown it. On one set, the right word was among those it reached in 217 of 2,686 tries (0.0808), and it declined to guess in 1,784. On a mixed set built from text it had fetched itself, at problem 505 of 2,000, the right word was among those it reached in 106 of 476 tries (0.2227), and it declined in 83. These are snapshots, not final runs, and no chance rate is recorded, so they cannot be read against chance. The same day I withdrew an earlier count of solved problems from this work, because it counted any output: four of its seven solves were one common word.

## Where it falls short

- Fixing the bug that was blamed changed nothing, and adding three parts to it lowered its score.
- More text kept helping less: from 3,200 to 4,800 MB its word-pair score rose by 0.0016.
- The audit's ten verdicts had none positive, and the copy running was 43 hours older than the code.
- Every test here is my own, on my own questions, word pairs or problems, and most are one run. None is an outside benchmark.

## Not done yet

- It was switched off on 29 Sep 2026. None of these results has been re-run since, and nobody outside my projects has run them.

## Check it yourself

Nothing you can run: QMK-1 is switched off and its code is private. On a call I can open the audit report and the result files behind each number, with the design kept off screen. [How to check what this site says](../../VERIFY.md#dead-ends) covers it under dead ends.

## More

- [Dead ends](../../projects/dead-ends.md)
- [QMK and AMK](qmk-and-amk.md), the card for the whole line
