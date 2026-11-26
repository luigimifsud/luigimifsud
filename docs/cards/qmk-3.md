# QMK-3

QMK-3 was a model in the QMK line, the learning work before Project Hail Mary; in October 2026 I raced it against fake versions of itself and tested it as an extra reader for Jarvis.

| | |
|---|---|
| Project | QMK and AMK, the learning work before Project Hail Mary |
| Dates | Results on record from 2 to 13 Oct 2026 |
| Hardware | One GPU for the 6 Oct race. The 13 Oct reader test ran offline, with the network off and the GPU hidden from it. |
| Status | Retired, with the rest of the QMK and AMK line |

## What it was for

I tested two things. One was whether QMK-3 had learned anything real, by racing it against fake versions of itself. The other was whether it could help the reader Jarvis uses on chat replies, on the meaning label and on the feeling label.

## What it was trained and tested on

For the reader test, QMK-3 was trained on 3,572 anonymised replies and tested on 86 held-out chat replies and 147 held-out phone replies. The answers it was scored against are the labels a larger hosted model gave, not a person's. For the race, variants were paired with fake versions of themselves, 96 trials per setting, at four settings.

## Results

- **My verdict of 2 Oct.** My own written verdict on QMK-3, on 2 Oct 2026: real but modest, not yet a capability, ten goals at 0 of 10. It was written before the 3 Oct check below.
- **Readings that did not survive the day.** On 3 Oct 2026 the morning's readings (90, 356 and 1,474 above chance at three sizes) did not hold. A trivial counting method scored 90 of 96 on the same test, where QMK-3 scored 46.5, so the test was too easy. None of the runs had been on the GPU as I had believed, so I stopped every CPU run. Recorded in my notes of that day, not re-run since.
- **A race against fake versions.** On 6 Oct 2026 I read a pre-registered race of four QMK-3 variants, each paired with a fake version as its control, 96 trials per setting. At one setting two variants were favoured in 23 and 21 trials against 46 and 47 for their controls (27 and 28 ties), and every version raced at that setting failed a registered check. At a second setting one variant beat its control by 35 trials to 34 but failed two other registered checks, one lost 31 to 42, one lost 29 to 30, and one tied its control in 96 of 96. Two more settings read the same way, and no variant qualified at any of the four. This was a check of my method: the result is that nothing qualified, not that anything was learned about language.
- **On its own, on the meaning label.** On 13 Oct 2026, QMK-3 on its own agreed with the larger hosted model's meaning labels on 0.477 of 86 held-out chat replies, against 0.337 for always guessing the commonest label and 0.674 to 0.733 for three plain predictors. On 147 held-out phone replies it agreed on 0.401, against 0.374 for the commonest label and 0.585 to 0.619 for the plain predictors. Small test sets, one run. It is above always guessing and below every plain predictor, so it is not a working reader.
- **In the mix, on the meaning label.** In the same offline test, QMK-3 added nothing to Jarvis's meaning reader: on the 86 chat replies the mix scored 0.721 with it and 0.721 without, and gave it a weight of 0.001. On the 147 phone replies it scored 0.585 with it and 0.578 without, with a weight of 0.0. A plain byte predictor scored 0.733 on the chats. These come from an offline test copy, not from the reader scores on the Jarvis page.
- **On the feeling label.** In the same test, QMK-3 on its own scored 0.709 on the 86 chat replies and 0.762 on the 147 phone replies, exactly what always guessing the commonest label scored (0.709 and 0.762), so it showed no skill there. The mix gave it a weight of 0.948 on the chat set, yet accuracy was 0.698 with it and 0.709 without it. On the phone set the mix scored 0.721 with and without it, with a weight of 0.523. The plain byte predictor scored 0.674 on the chats and 0.741 on the phone replies. Small sets, one run.

## Where it falls short

- On the feeling label it showed no skill: on its own it matched always guessing the commonest label, and where the mix leaned on it, accuracy went down.
- On the meaning label it was below every plain predictor on its own, and it added nothing to the mix.
- No variant qualified in the race, and the readings of 3 Oct came from a test that was too easy.
- The labels it was scored against came from a hosted model, not a person, and the test sets are small.

## Not done yet

- Ten goals at 0 of 10, by my own verdict.
- Nothing here has been re-run since October 2026, and nobody outside my projects has run it.

## Check it yourself

Nothing you can run: the replies and the model stay private. On a call I can open the score file and the race reading, with the data and the design kept off screen. [How to check what this site says](../../VERIFY.md#dead-ends) covers it under dead ends.

## More

- [Dead ends](../../projects/dead-ends.md)
- [Jarvis](../../projects/jarvis.md), whose meaning reader QMK-3 was tested with
- [QMK and AMK](qmk-and-amk.md), the card for the whole line
