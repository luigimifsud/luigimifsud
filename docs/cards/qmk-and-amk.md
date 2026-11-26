# QMK and AMK

QMK and AMK were the lines of learning models I built before Project Hail Mary; they are retired and sit with my dead ends.

| | |
|---|---|
| Project | QMK and AMK, the learning work before Project Hail Mary |
| Dates | September to 17 Nov 2026 |
| Hardware | My own PCs; each model card gives what is recorded for that model |
| Status | Retired. I changed the rules on 17 Nov 2026. QMK-1 was switched off on 29 Sep; AMK2 has been paused since 9 Nov. |

## What it was for

For about seven weeks these were my learning models, built under strict rules I set for them. The aim was a model that does more than read back what it was fed. None of them got there. On 17 Nov 2026 I changed the rules, and the learning work went on in Project Hail Mary.

Most of what is on these cards is negative. I keep it on record because a result that went against me is still a result.

## What it was trained and tested on

Plain text. AMK2 was tested on English, both on text it had been fed (256 KiB, 1 MiB and 16 MiB of it) and on text it had never been fed, against plain lookup tables. The QMK models were tested on held-out word pairs and questions (QMK-1), on fixed test bytes against 7-Zip PPMd (QMK-2), on held-out chat and phone replies for Jarvis (QMK-3), and on legal text held back from building (The Lawyer).

## Results

- **What the line came to.** Over about seven weeks, the QMK and AMK models I built under strict rules never got past reading back what they had been fed. The best did no better than a plain lookup table on text it had seen.
- **AMK2 against lookup tables.** My AMK2 notes of 17 Nov 2026 record that on English text it had been fed, its best version gave back 5.2, 6.0 and 7.7 of 16 bytes at 256 KiB, 1 MiB and 16 MiB of text. That is about what a 12-byte lookup table does, and a 16-byte table beat every version at every size. On text it had never been fed it gave back 2.6 to 4 of 16, the level of a perfect memory (the same notes give 2.6 to 5 of 16 for a perfect memory on new text). The "of 16 bytes" measure is my notes' own and is not defined where it is written down. Recorded in my notes, not re-run since, and not re-checked against the check file they cite.
- **A detection rule I retracted.** A rule I used to tell real structure from chance reported a false-alarm rate of 0.006780. Tested against 3,600 matched control runs, its real false-alarm rate was 0.073611, about 10.9 times higher. I retracted it.
- **A looser version of that rule did no better.** In September 2026 I tested whether a looser version of the same rule would catch more real structure at the same false-alarm rate. It would not. Worked out exactly, the widest looser rule gained at most 1.34 times at one setting and lost by 19 times at another. Measured on planted structure, it caught 1.06 times as much at best and 0.42 times as much at the weakest signal. My result file calls the premise false. One test setup, with planted structure.

## Where it falls short

- None of these models got past reading back what it had been fed.
- The tests are my own: my questions, word pairs, test slices and replies, most of them one run. None is an outside benchmark.
- Some of my own measurements had to be taken back: the detection rule above, a QMK-1 count of solved problems that counted any output, a QMK-2 gap that compared different sets of bytes, and QMK-3 readings from a test that was too easy.

## Not done yet

- Nothing here has been reproduced by anyone outside my projects.
- Project Hail Mary, where the learning work went next, has not yet matched a standard model at equal compute either.

## Check it yourself

Nothing you can run today: the models, their code and their data stay private. On a call I can open my notes, the result files, the audit report and the retraction behind each number on these cards, with the design kept off screen. [How to check what this site says](../../VERIFY.md#dead-ends) says the same.

## More

- [Dead ends](../../projects/dead-ends.md), where these lines sit with my other stopped work
- [Project Hail Mary](../../projects/hail-mary.md), where the learning work went after 17 Nov
- The model cards: [QMK-1](qmk-1.md), [QMK-2](qmk-2.md), [QMK-3](qmk-3.md) and [The Lawyer](the-lawyer.md)
- [QMK World](../../projects/qmk-world.md) is a separate build: a simulator I made as a world for my learning models to work in, not one of these models.
