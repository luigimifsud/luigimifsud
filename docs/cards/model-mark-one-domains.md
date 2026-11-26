# Mark One subject models

A set of my 104.5 million parameter Mark One language models, each trained from nothing on one subject's text, with runs of the same size on generated logic problems and on a general text mix.

| | |
|---|---|
| Project | Mark One |
| Dates | 23 Jul to 16 Aug 2026; the subject models 13 to 14 Aug |
| Size | 104.5 million parameters each |
| Hardware | One RTX 5090 for the two runs started on 23 Jul; not recorded for the rest |
| Status | Paused, with the rest of Mark One |

## What it was for

I wanted to see how well a mid-size model trained at home learns one subject from that subject's text. I trained one model per subject: law, finance, philosophy, maths, economics, psychology and code, plus one combined run. Models of the same size also ran on generated logic problems and on a general text mix, to test training settings and to compare versions of the model.

## What it was trained and tested on

- One text collection per subject, each read for about one pass.
- A combined run on 9 subjects, 1.74 GB of text.
- On 23 Jul 2026, two runs on one RTX 5090: 20,000 steps on 388 MB of generated logic problems (about 655 MB of text read, 6.3 bytes per parameter), and 50,000 steps on a 29.1 GB general mix (about 1.64 GB read, 15.7 bytes per parameter).
- A model on the general mix was tested at step 120,000 on 96 evenly spaced held-out windows of 1,024 bytes, with gzip and xz scored on the same windows. Scores are in bits per byte, and lower is better.

## Results

- **General text, at step 120,000.** On 96 evenly spaced held-out windows of 1,024 bytes, it needed 1.3929 bits per byte, against 4.2402 for gzip -9 and 4.8945 for xz -9e on the same windows. Limit: gzip and xz start cold on each short window, so they are weak rivals here. Brotli, the strongest of nine standard compressors on my code windows, was not run on this set.
- **The subject models.** I give no score for them on this card.
- **The two runs of 23 Jul.** No score for either. The best held-out lines in their training logs are the lowest of many noisy readings, so they are biased low and I do not cite them.
- **Maltese.** The Maltese model and my test of mixing Maltese into a general model are the same size. They have their own card: [Mark One Maltese](mark-one-maltese.md).

## Where it falls short

- No subject model has a score here, so this card shows what was trained, not how well it learned.
- The general-text result is against weak rivals. The strongest standard compressor was not run on those windows.
- Each subject model read its text about once, and the two runs of 23 Jul read 6.3 and 15.7 bytes of text per parameter.

## Not done yet

- No score for the subject models is on this site.
- Nobody outside my projects has re-run any of this.

## Check it yourself

- **Today.** Nothing you can run. The models and their text are private.
- **On a call.** I can open the training logs and the general-text result file.
- [How to check what this site says](../../VERIFY.md#mark-one)

## More

- [Model history](../MODEL_HISTORY.md)
- [Mark One](../../projects/mark-one.md)
- [Mark One Maltese](mark-one-maltese.md), the same size of model trained on Maltese
