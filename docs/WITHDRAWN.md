# Claims I withdrew

These are the claims I took back or narrowed in writing, from June to November 2026, in date order.

## PhotoLocator's benchmark claim

**What I claimed.** An early benchmark claim for PhotoLocator, a tool I built to guess where a photo was taken.

**What I found.** A later check found the claim false. Its verdict reads: "Core geolocation UNPROVEN on hard imagery". An honest measure showed the tool could often narrow a photo down to the right country, which is a long way from knowing where it was taken.

**What I did.** I dropped the claim. Selling the tool was judged a dead end on 8 Jun, and I stopped. I give no numbers for it, because the code is on another machine and was not re-checked for this page.

**Date.** 4 to 8 Jun 2026.

More: [Dead ends](../projects/dead-ends.md#photolocator).

## The early "beats gzip" claim

**What I claimed.** That my 40.6 million parameter Mark One model beat gzip, by 1.90 times.

**What I found.** The 1.90 came from taking the best of 40 evaluations.

**What I did.** I retracted it in writing. The code result I cite now is a different measurement, on held-out code cleaned of overlap with the training data, and it is in the next section. An older gzip figure of mine stays out too, because its held-out set was not checked for leakage.

**Date.** July 2026, from the model's scoring of 25 to 27 Jul. My notes as I checked them do not give the day of the retraction.

More: [Mark One 40M card](cards/mark-one-40m-code.md).

## My headline for the 40.6 million parameter model

**What I claimed.** On 25 Jul 2026, that the model was 3.27 times smaller than gzip on 96 windows.

**What I found.** Some of those windows overlapped my training text. Once I removed them, on 26 Jul, the figure was 2.49 times. Before that measurement I had written down about 2.6 as my expectation. About 65 percent of the fall from 3.27 to 2.49 was the overlap, and about 35 percent was a change in the mix of windows. Also, gzip was not the strongest rival. Against brotli, the strongest of nine standard compressors on those windows, the figure was 2.08 times.

**What I did.** I corrected the headline in writing, twice. The number I cite now: on 192 held-out code windows cleaned of overlap with the training data, the model scored 1.3615 bits per byte against 2.8362 for brotli -q 11, which is 2.08 times smaller (95% confidence interval 2.016 to 2.159). Lower bits per byte is better. Standard compressors start cold on short windows, so this shows the model learned code, not that it is a better general-purpose compressor. The 3.27 and the 2.49 are recorded in my scoreboard, not re-run since.

**Date.** 25 Jul 2026 for the 3.27, 26 Jul for the 2.49, and by 27 Jul for the 2.08.

More: [Mark One 40M card](cards/mark-one-40m-code.md).

## Rival compressors I had set up too weakly

**What I claimed.** Leads for my Mark One models over standard compressors, measured with some of the rivals set up too weakly.

**What I found.** Six places where I had set up a rival compressor too weakly, each time in my favour, including never running brotli at all. Eight of my written predictions about how strong a rival would be turned out wrong, and all eight were too low, which has a chance of 0.0039 if there were no bias.

**What I did.** I now require a rival's settings to be pushed to the tool's documented limit before its number is used. These findings are my own notes, not a separate testing step.

**Date.** July 2026.

More: [Mark One 40M card](cards/mark-one-40m-code.md).

## A trend and its cause

**What I claimed.** On 27 Jul 2026, that my 40.6 million parameter model's lead over brotli was shrinking, from 1.551 times on 8 KB of text to 1.180 times on 100 KB. I also named a cause.

**What I found.** On 28 Jul a third measurement, on 770 KB, put the lead at 1.450 times. I had drawn the trend and the cause from two points.

**What I did.** I withdrew the trend and the cause. The third point is a different, larger span, so it shows the cause should not have been asserted from two points, not that the cause is false. I leave the cause off this page. All three measurements are recorded in my scoreboard, not re-run since.

**Date.** 27 and 28 Jul 2026.

More: [Mark One 40M card](cards/mark-one-40m-code.md).

## The training log's best for my 295 million parameter model

**What I claimed.** My training log reported a best of 1.184 bits per byte for the model.

**What I found.** On 512 fixed, evenly spaced held-out windows of 1,024 bytes, the same saved model scored 1.3186 (95 percent interval 1.2842 to 1.3530). The log draws random windows and keeps the lowest of many noisy readings, so its best is low by construction. That is a measurement of my instrument. It does not say the model got worse.

**What I did.** I stopped quoting the training log's best. For the same reason I give no score for two runs of a 104.5 million parameter model that I started on 23 Jul 2026: the best held-out lines in their logs are selection-biased.

**Date.** Summer 2026, on the 295 million parameter model, which trained from 24 Jul to 12 Aug 2026.

More: [Mark One 295M card](cards/mark-one-295m.md).

## The Maltese score

**What I claimed.** That my Maltese model (104.5 million parameters) scored 1.2733 bits per byte over 512 windows (95 percent interval 1.2305 to 1.3161), against 3.8010 for the general model on the same Maltese text (recorded in its result files, not re-run since).

**What I found.** Of those 512 windows, 51.8 percent are parliament, gazette, court and law text. So the number does not say how well the model compresses Maltese prose.

**What I did.** I narrowed it in writing: my scoreboard says the 1.2733 must not be claimed as how well the model compresses Maltese. For prose I use a separate test. On 489 held-out windows of 1,024 bytes of Maltese prose, mostly blogs, press articles and Wikipedia, the model needed 1.3999 bits per byte (95 percent interval 1.3771 to 1.4228), against 2.824 for DEFLATE given 64 KB of earlier text on the same windows. The rival is DEFLATE, not a tool made for Maltese.

**Date.** August 2026. The prose result file is dated 8 Aug.

More: [Mark One Maltese card](cards/mark-one-maltese.md).

## The August claim about my tiny models

**What I claimed.** In August 2026 I wrote up a result for tiny models of my own, of about 2,000 to 4,500 weights, against rival models of the same size, scored exactly on short windows of bytes.

**What I found.** A check narrowed it. I don't repeat the wording from before the check.

**What I did.** I quote the narrowed wording, as my project's register keeps it, in the third person:

> In August, a variant of Luigi's own model design beat the standard same-size pairwise model (a Boltzmann-family model with no hidden units) on held-out data in every paired trial on record: by 10 to 14 percent in the longer runs and by about 5 to 6 percent in shorter eight-seed runs, though a generic control also beat that model by about a third as much. It is small-scale research, not a compressor, and not yet independently re-run.

The test at 1,985 weights against four rival models on 3 seeds, with its limits, is on its card.

**Date.** August 2026. The runs are dated 25 to 28 Aug. My notes as I checked them do not date the check that narrowed the claim.

More: [Hail Mary small exact test card](cards/hail-mary-small-exact.md), and [the exact AI page](../projects/exact-ai.md#earlier-research-in-the-same-register).

## A stream figure from my compression work

**What I claimed.** A bits-per-byte figure for coding a stream of text.

**What I found.** It compared two different sets of text.

**What I did.** I retired it. It is not quoted anywhere on this site.

**Date.** September 2026.

More: [Compression demonstrator card](cards/compression-demonstrator.md).

## A ratio against 7-Zip PPMd

**What I claimed.** A ratio for my Python compressor against 7-Zip PPMd, on 20 Python standard-library files (542,523 bytes after normalising them).

**What I found.** My notes mark that form superseded. The rival I compare with now is the strongest one I could run on those files, a context-mixing compressor built in my own project.

**What I did.** I stopped quoting the ratio against PPMd. The form I quote: my compressor needed 1.0060 bits per byte against 1.1479 for that rival, which is 1.1411 times smaller (12.36 percent fewer bits). I could not run lpaq1, paq8, zpaq or cmix, and any of them may beat that rival. With its 83,932-byte decoder counted, my compressor's total on the same files is 152,151 bytes, more than the 84,957 bytes 7-Zip PPMd needs.

**Date.** September 2026, in my compressor work of 2 to 11 Sep.

More: [Compression demonstrator card](cards/compression-demonstrator.md).

## QMK-2's gap to 7-Zip PPMd

**What I claimed.** My QMK-2 notes carried a gap of +0.213054 bits per byte behind 7-Zip PPMd.

**What I found.** Three early races had compared across different sets of bytes, with PPMd measured on different bytes from QMK-2.

**What I did.** I withdrew the gap in those notes. On the same bytes, QMK-2 lost to PPMd: 1.606522 bits per byte against 1.530961 on a registered test slice of 1,315,021 bytes, and 1.581544 against 1.459873 on 19,417,730 bytes. It was behind PPMd on 124 of 128 held rows (my notes do not say which version of QMK-2 that count is for).

**Date.** 23 to 24 Sep 2026.

More: [QMK-2 card](cards/qmk-2.md).

## QMK-1's count of solved problems

**What I claimed.** A count of problems QMK-1 had solved, with seven solves.

**What I found.** The count took any output as a solve. Four of its seven solves were one common word.

**What I did.** I withdrew the count on 25 Sep 2026. The measure I keep: in two snapshots taken part-way through a run, on problems whose answers I knew and had not shown it, the right word was among those it reached in 217 of 2,686 tries (0.0808), and it declined to guess in 1,784. On a mixed set built from text it had fetched itself, at problem 505 of 2,000, the right word was among those it reached in 106 of 476 tries (0.2227), and it declined in 83. These are snapshots, not final runs, and no chance rate is recorded. QMK-1 was switched off on 29 Sep.

**Date.** 25 Sep 2026.

More: [QMK-1 card](cards/qmk-1.md).

## The false-alarm rate of my detection rule

**What I claimed.** A detection rule of mine, which I used to tell real structure from chance, reported a false-alarm rate of 0.006780.

**What I found.** Tested against 3,600 matched control runs, its real false-alarm rate was 0.073611, about 10.9 times higher.

**What I did.** I retracted it. I also tested whether a looser version of the rule would catch more real structure at the same false-alarm rate. It would not, and my result file calls that premise false.

**Date.** September 2026.

More: [QMK and AMK card](cards/qmk-and-amk.md).

## QMK-3's morning readings

**What I claimed.** On the morning of 3 Oct 2026, readings for QMK-3 of 90, 356 and 1,474 above chance at three sizes.

**What I found.** A trivial counting method scored 90 of 96 on the same test, where QMK-3 scored 46.5, so the test was too easy. None of the runs had been on the GPU as I had believed.

**What I did.** I took the readings back that day, in my notes, and stopped every CPU run. On 6 Oct I read a pre-registered race of four QMK-3 variants, each against a fake version of itself, and no variant qualified at any of four settings.

**Date.** 3 Oct 2026.

More: [QMK-3 card](cards/qmk-3.md).

## Numbers from my chip research

**What I claimed.** The numbers in my older simulation files on computing without binary.

**What I found.** On 17 Nov 2026 a review inside my project re-opened 21 of those numbers and found 1 bad. The same review, describing my older files, listed the ideas that had already died, among them superconducting logic, which was withdrawn once cooling was counted.

**What I did.** I fixed the bad number. The review was inside my project, so it is not an outside check. No chip has been made.

**Date.** 17 Nov 2026.

More: [Computing without binary](../projects/computing-research.md).

## The VOID forecaster race

**What I claimed.** A forecaster race in Project Hail Mary that looked good. Earlier notes of mine treated its numbers as results.

**What I found.** One check file's last line broke the race's locked rule.

**What I did.** The whole race is VOID by its own rule. I corrected the earlier notes that treated its numbers as results, and I never quote those numbers. It is a different race from the 12 of 27 result I do quote.

**Date.** November 2026, during the forecaster work of 22 to 26 Nov.

More: [Hail Mary forecaster card](cards/hail-mary-forecaster.md).
