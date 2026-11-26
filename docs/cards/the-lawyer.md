# The Lawyer

The Lawyer was a model built on a CPU from 7,503 legal documents, part of the QMK line, the learning work before Project Hail Mary.

| | |
|---|---|
| Project | QMK and AMK, the learning work before Project Hail Mary |
| Dates | 24 Sep 2026 (one cycle) |
| Hardware | A CPU |
| Status | Retired, with the rest of the QMK and AMK line |

## What it was for

I wanted to see whether a model built from legal text alone could learn which words go together in it, and whether that reached two standing legal questions. The two questions stay private.

## What it was trained and tested on

7,503 legal documents, 12,699,381 bytes. The build used 18,439 words and kept 2,142,995 tokens; 198,783 tokens were held back and never built from. The word-pair score below is on that held-back text.

## Results

- **Word pairs on held-back text.** On legal text held back from building, the model scored 0.7207 (plus or minus 0.0046) on rebuilding word pairs, against 0.4947 (plus or minus 0.0048) for a word-frequency baseline. It is not a legal-accuracy score, and it says nothing about whether a legal answer is right.
- **The two questions.** In the same cycle I tested whether the model could link pairs of words from its two legal questions, against matched control pairs. All 4 links on one question held (for example by 0.1057 against a spread of 0.0115, and by 0.1276 against 0.0494). None of the 3 links on the other question did: on one, the control beat the model by 0.0520 (spread 0.0011). My note says the model reaches the one question and not one half of the other, that this is an early reading and not a verdict, and that it measures reach, not a legal answer. It puts the missing half down to English case law not being in the text. One cycle, 7 word pairs, recorded in its result file and not re-run since.

## Where it falls short

- It reached one of its two questions. On the other, none of the 3 links held, and on one the control beat it.
- It is a word-pair score, not a legal-accuracy score.
- It is one cycle: an early reading, not a verdict.

## Not done yet

- Nothing here has been re-run, and nobody outside my projects has run it.

## Check it yourself

Nothing you can run: the model and the two questions stay private. On a call I can open the result file, with the two questions kept off screen. [How to check what this site says](../../VERIFY.md#dead-ends) covers it under dead ends.

## More

- [Dead ends](../../projects/dead-ends.md)
- [QMK and AMK](qmk-and-amk.md), the card for the whole line
