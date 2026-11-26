# Jarvis reader

A small local reader inside Jarvis, the clinic's WhatsApp booking assistant, that reads each patient reply for what it means and how the patient feels.

| | |
|---|---|
| Project | Jarvis |
| Dates | Versions 1 and 2 existed by 13 Oct 2026, version 3 by 14 Oct 2026 (file dates). Compared with a hosted model every day from 14 Oct to 25 Nov 2026. |
| Hardware | Runs locally. The larger model it is compared with is hosted. |
| Status | Shadow mode (version 2). Not the main reader yet. |

## What it was for

Jarvis has to know what a patient's reply means, for example whether it says yes to an offer, and whether the patient is calm. A larger hosted model does that reading today. I want a small reader that runs locally to take it over. It does not become the main reader until it agrees with the hosted model on meaning in 95 percent of replies.

## What it was trained and tested on

I give no figures for its training data here: the score file covers the test sets. The labels it is scored against are the larger hosted model's readings, not a person's, so every score here is agreement with that model, not accuracy. There are two fixed test sets: 147 anonymised patient answers to reception offers on the clinic's phone line (35 of them not calm), and 86 anonymised patient replies to offers and payment links in Jarvis chats (25 not calm). My notes call both sets held out from training; the score file itself does not say so, and I have not re-checked it. Every figure here is an aggregate. No patient text appears.

## Results

From the reader's score file (one run per version, on the test sets, not live) and from the bot's own shadow log. Higher is better.

- **Phone set, version 3.** On the 147 phone answers it agreed with the hosted model on meaning in 0.844 of cases and on feeling in 0.946. The same open model before tuning agreed in 0.565 and 0.803. Always answering yes would agree on meaning in 0.374, and always answering calm on feeling in 0.762. Of the 35 not-calm replies, version 3 named the same feeling as the hosted model for 29 (0.829), against 11 (0.314) before tuning. Limits: 35 not-calm replies is a small set, this is one run, and version 3 is not the version in shadow mode.
- **Chat set, version 3.** On the 86 chat replies it agreed on meaning in 0.872 and on feeling in 0.86, against 0.686 and 0.686 for the same open model before tuning. Always answering yes would agree on meaning in 0.337, and always answering calm on feeling in 0.709. Of the 25 not-calm replies, it named the same feeling for 16 (0.64), against 3 (0.12) before tuning. Limits: 25 is a very small set, and 0.64 is the lowest of the three versions on this set (version 2 got 0.88).
- **Version 2 against version 3.** Version 3 agreed with the hosted model more often on meaning and feeling, but named the right feeling for fewer of the not-calm replies: 16 against 22 of 25 on the chat set (0.64 against 0.88), and 29 against 32 of 35 on the phone set (0.829 against 0.914). Version 3 starts from a larger open model than versions 1 and 2, so the difference is not tuning alone. On the chat set, versions 1 and 2 and the untuned model agreed on feeling less often than always answering calm would (0.593, 0.698 and 0.686 against 0.709). On the phone set, version 1 agreed on meaning in 0.565, the same as the untuned model. Limit: the score file reports agreement and catch rate, not false alarms, so the cost of version 2's higher catch is not shown.
- **Shadow mode, version 2, from the bot's own log.** From October to 25 Nov 2026 version 2 read the same patient replies as the hosted model. They agreed on meaning in 77 percent of 643 replies, the log's own running total. In the log's daily rows, which cover most of those replies, they agreed on feeling in 60 percent, and of the replies the hosted model read as upset, the small reader named the same feeling for 64 percent. Limits: agreement with a hosted model is not accuracy, because the hosted model can be wrong; the log says none of it has been audited yet; the log does not say what the replies outside its daily rows are; and the sums of the daily rows are mine.
- **No rise over the weeks.** Version 2 did not agree with the hosted model more often on meaning as the weeks went on. The log's daily rows show 79 percent in the week of 14 to 20 Oct and 68 percent in the week of 19 to 25 Nov, with the same version 2 throughout. The log's running figure fell from 84 percent on 15 Oct to 77 percent on 25 Nov. 5 of the 43 days reached 95 percent on their own, each on a small number of replies. Limits: on weekly samples this small, a drop of about 11 points is not far outside what chance could give, so this shows no improvement, not a proven decline. Catching upset replies went the other way over the same weeks.

## Where it falls short

- It is at 77 percent agreement on meaning in shadow mode, against the 95 percent it needs to become the main reader.
- Every score is agreement with a hosted model, not accuracy, and nobody has audited the readings yet.
- The version that agrees most often, version 3, catches fewer of the not-calm replies than version 2.
- The not-calm sets are small: 35 and 25 replies.
- Its agreement in shadow mode has not risen over the weeks.
- False alarms are not counted.

## Not done yet

- Reaching 95 percent agreement on meaning, so it can become the main reader.
- A person checking a sample of its readings, and the hosted model's.
- Counting false alarms next to the catch rate.
- Version 3 is not the version in shadow mode, so its scores come from the fixed test sets alone.

## Check it yourself

Nothing public yet: the replies are patient data and stay private. On a call I can open the score file and the shadow log's totals, with no patient text on screen. [How to check what this site says](../../VERIFY.md#jarvis) covers Jarvis as a whole.

## More

- [The Jarvis card](jarvis.md)
- [The Jarvis page](../../projects/jarvis.md)
