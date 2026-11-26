# Mark One Maltese

My 104.5 million parameter language model, trained on Maltese text alone, part of Mark One.

| | |
|---|---|
| Project | Mark One |
| Dates | Trained 8 Aug 2026; mixing test 9 Aug 2026 |
| Size | 104.5 million parameters |
| Hardware | Trained at home. Scored on CPU; the scoring is deterministic. |
| Status | Paused, with the rest of Mark One |

## What it was for

I wanted to see how well a small model trained on Maltese alone predicts Maltese prose it has never seen. Then I tested whether adding Maltese to a general training mix gets the same result.

## What it was trained and tested on

- A frozen 1.08 GB Maltese corpus. Training read 85.0 percent of it once and 15 percent twice, so it was not one clean pass.
- Whole files were kept out of training, with no random draw. The prose test uses 512 evenly spaced windows of 1,024 bytes from 24 held-out prose files, mostly blogs, press articles and Wikipedia.
- Each window had to pass a Maltese check, and 489 did. The other 23 came from six non-Maltese scans (Guernesiais, Polish and Urdu OCR) and are left out. The model read 3.8044 on them.
- The split and four predictions were registered before any checkpoint was scored.

## Results

Lower bits per byte is better.

- **Maltese prose.** On the 489 held-out windows that passed the Maltese check, it needed 1.3999 bits per byte (95 percent interval 1.3771 to 1.4228), against 2.824 for DEFLATE given 64 KB of earlier text on the same windows. Limit: the rival is DEFLATE, not a tool made for Maltese. One model, one run.
- **The whole held-out set.** Over 512 windows of the whole held-out set, it scored 1.2733 bits per byte (95 percent interval 1.2305 to 1.3161), against 3.8010 for the general model on the same Maltese text (recorded in its result files, not re-run since). Limit: that set includes 51.8 percent parliament, gazette, court and law text, so my scoreboard says this number must not be quoted as how well the model compresses Maltese. For prose, the number is the 1.3999 above.
- **Mixing Maltese into a general model.** I trained two more 104.5 million parameter models from random weights for 80,000 steps each with the same seed, one on a general text mix and one on the same mix with Maltese as one row in six. On the 489 Maltese prose windows, the model that saw Maltese needed 1.6809 bits per byte against 3.8797 for the other. On general text it needed 1.4105 against 1.3534, which is 0.0572 worse. I had registered that it would be no more than 0.05 worse, so I recorded that prediction as failed; 2 of my 3 registered predictions passed. Limit: the model trained on Maltese alone scored 1.3999 on the same windows, so mixing did not match it. One seed per model.

## Where it falls short

- The prose rival is DEFLATE, not a tool made for Maltese.
- Mixing Maltese into a general model did not match the model trained on Maltese alone, and it cost more on general text than I had predicted.
- Training did not read the corpus in one clean pass.

## Not done yet

- No language model from outside my projects has been scored on these windows.
- Nobody outside my projects has re-run any of this.

## Check it yourself

- **Today.** Nothing you can run. The model and the test windows are private.
- **On a call.** I can open the result files and the predictions I registered before scoring.
- [How to check what this site says](../../VERIFY.md#mark-one) covers what can and can't be checked for Mark One.

## More

- [Mark One](../../projects/mark-one.md)
