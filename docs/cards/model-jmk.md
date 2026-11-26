# JMK

JMK was a two-day experiment of mine in October 2026: a text predictor that lost to 7-Zip PPMd on every row and was withdrawn, then a tool that looks for repeating structure in text.

| | |
|---|---|
| Project | My compressor work of early October 2026, raced against BMK 2 |
| Dates | 2 to 3 Oct 2026 |
| Size | The predictor: 135,036 to 435,600 weights |
| Status | Withdrawn as a predictor on 2 Oct 2026 at 21:05. The second version closed on 3 Oct 2026. |

## What it was for

I wanted to know whether a new predictor could beat BMK 2, my strongest compressor model at the time, and 7-Zip PPMd on the same text. When it lost, I tried a second version: a tool that finds repeating structure in text and uses it to write new sequences, instead of predicting text.

## What it was trained and tested on

- The same fixed text sample as BMK 2, on three of its slices, with 256 held rows across two of them.
- 7-Zip PPMd and BMK 2 scored on the same slices.
- Scores are in bits per byte, and lower is better.

## Results

- **It lost to PPMd on every row.** On its best slice it needed 2.013916 bits per byte against 1.502068 for 7-Zip PPMd, still about 0.51 behind. Across the 256 rows of two slices it was below PPMd on none. On a third slice it needed 9.629322.
- **It was far behind BMK 2.** On a development slice it needed 2.196494, against 1.342128 for version 3 of BMK 2 and 1.326882 for version 4: about 0.85 to 0.87 bits per byte behind.
- **Withdrawn.** I withdrew it as a predictor on 2 Oct 2026 at 21:05 and closed its registered test without reading it. Limit: I have the race rows themselves, but the PPMd and BMK 2 figures are quoted from my notes for the race.
- **The second version.** It predicts nothing, so it has no score. I closed it on 3 Oct 2026.

## Where it falls short

- It was below PPMd on none of the rows it was raced on.
- It was far behind BMK 2.
- The second version produced no result.

## Not done yet

- Both versions are closed. Nobody outside my projects has run either.

## Check it yourself

- **Today.** Nothing you can run. The text sample and the code are private.
- **On a call.** I can open the race rows and the note where I withdrew it.
- [How to check what this site says](../../VERIFY.md#dead-ends)

## More

- [Model history](../MODEL_HISTORY.md)
- [Dead ends](../../projects/dead-ends.md#home-built-compressors-that-lost), with my other home-built compressors that lost
- [BMK and BMK 2](model-bmk.md), the models JMK was raced against
