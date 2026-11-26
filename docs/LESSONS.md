# What the dead ends taught me

Each lesson on this page is written down in my notes, next to the work that failed.

Under each one: what happened, the lesson, and what changed after, where my notes say. Where I put a lesson in my own plain words, it is marked (paraphrase). Lower bits per byte is better.

## A claim that did not hold: PhotoLocator

**What happened.** In June 2026 I built PhotoLocator, a tool to guess where a photo was taken. An early benchmark claim for it was later found to be false.

**The lesson.** My notes put it in these words: "Core geolocation UNPROVEN on hard imagery".

**What changed after.** Selling it was judged a dead end on 8 Jun, and I stopped. The code is on another machine and was not re-checked for this page, so I give no numbers for it.

Page: [Dead ends](../projects/dead-ends.md#photolocator).

## A best-of-many reading is low by construction (Mark One)

**What happened.** Early in Mark One I had a claim that my model beat gzip by 1.90 times. That figure took the best of 40 evaluations, and I retracted it in writing. Later, my training log reported a best of 1.184 bits per byte for my 295 million parameter model. On 512 fixed, evenly spaced held-out windows of 1,024 bytes, the same saved model scored 1.3186 (95 percent interval 1.2842 to 1.3530).

**The lesson.** (paraphrase) The log keeps the lowest of many noisy readings, so its best is low by construction. That is a measurement of my instrument, not a sign that the model got worse.

**What changed after.** I stopped quoting the training log's best. For two runs of a 104.5 million parameter model that I started on 23 Jul 2026, I give no score at all, because the best held-out lines in their logs are selection-biased.

Card: [Mark One 295M](cards/mark-one-295m.md). Page: [Mark One](../projects/mark-one.md).

## Rivals I had set up too weakly, in my favour (Mark One)

**What happened.** I found six places where I had set up a rival compressor too weakly, each time in my favour, including never running brotli at all. Eight of my written predictions about how strong a rival would be turned out wrong, and all eight were too low, which has a chance of 0.0039 if there were no bias. My headline for the 40.6 million parameter model fell twice, in writing: from 3.27 times smaller than gzip on 96 windows (25 Jul 2026), to 2.49 times after I removed the windows that overlapped my training text (26 Jul), to 2.08 times against brotli, the strongest of nine standard compressors on those windows (by 27 Jul). Before the second measurement I had written down about 2.6 as my expectation.

**The lesson.** (paraphrase) My mistakes in setting up rivals all went my way, so a rival's number is not fit to use until its settings are pushed as far as the tool allows.

**What changed after.** I now require a rival's settings to be pushed to the tool's documented limit before its number is used. The 2.08 against brotli is the figure I cite. Standard compressors start cold on short windows, so it shows the model learned code, not that it is a better general-purpose compressor. These are my own notes, not a separate testing step.

Card: [Mark One 40M](cards/mark-one-40m-code.md#where-it-falls-short). Also: [How I test results](METHOD.md#clean-held-out-sets-and-strong-rivals).

## A trend drawn from two points (Mark One, 27 to 28 Jul 2026)

**What happened.** On 27 Jul 2026 I wrote that my model's lead over brotli was shrinking, from 1.551 times on 8 KB of text to 1.180 times on 100 KB, and I named a cause. On 28 Jul a third measurement, on 770 KB, put the lead at 1.450 times.

**The lesson.** My notes say the cause was wrong to assert from two points. They do not say the third point proved it false.

**What changed after.** I withdrew the trend and the cause.

Card: [Mark One 40M](cards/mark-one-40m-code.md#where-it-falls-short).

## An overlap rule that was wrong in kind (Mark One, 26 Jul 2026)

**What happened.** My 40.6 million parameter model was tested on 200 completions cut from Python's own test files, and it got 0 of 200 exactly right. One of the 200 items had its whole 64-byte answer in the training text and passed my overlap rule anyway.

**The lesson.** My scoreboard says the rule was wrong in kind.

**What changed after.** No filed score depends on that item.

Card: [Mark One 40M](cards/mark-one-40m-code.md#results).

## More of a narrow kind of practice made it worse (Mark One)

**What happened.** On 360 test items where the right next piece of a Python program was a second variable name, such as the q in print(p // q), my 295 million parameter model never ranked the right opening byte at the top (0 of 360) and put a digit there 325 times (90.3 percent). From one checkpoint I then trained 10,000 more steps on a narrow mix: 3.42 million generated transcripts, almost all inline arithmetic and conditional expressions. On a fixed suite of 775 Python tasks with one greedy try, that took the score from 550 down to 526. A wider mix, from the same checkpoint, took it to 565. Every prediction I had registered for the narrow set was falsified.

**The lesson.** My note says the result is about this skill and this model, not about other data.

**What changed after.** I stopped building data for this skill.

Card: [Mark One 295M](cards/mark-one-295m.md).

## Four probes, four KILL verdicts (Mark One, 8 to 10 Aug 2026)

**What happened.** I ran four small pre-registered probes, 4 seeds each, on models of about 4 to 105 million weights trained on a corpus of two textbooks of about 3.2 MB. Each printed the project's own verdict, KILL. In the one with matched sizes, the tested version lost to the plain model by 0.0740 bits per byte on average, on 4 of 4 seeds. One of the four would have read CONFIRM under its original fixed thresholds. It reads KILL under the stricter paired threshold the script uses for its main verdict.

**The lesson.** (paraphrase) The ideas failed at this size, on a small corpus. That does not show they never work. It is not a compression result.

**What changed after.** My notes record the four verdicts and no next step.

Page: [Every model I've built](MODEL_HISTORY.md#mark-one-july-to-september-2026).

## My compressors against standard tools (August to October 2026)

Several of my home-built compressors lost to standard tools (7-Zip PPMd, lzma). Some of the losses:

- **Mark Two**, a very small model of 11,521 parameters, needed 1.996902 bits per byte on 263,040 held-out bytes of book text, against 1.429714 for 7-Zip PPMd given the same training text. It lost by about 0.567. Five of its ten goals were met; beating PPMd on a stream was not. ([Mark Two](cards/model-mark-two.md))
- **QMK-2** needed 1.606522 bits per byte against 1.530961 for 7-Zip PPMd on a registered test slice of 1,315,021 bytes, and was behind on 124 of 128 held rows. ([QMK-2](cards/qmk-2.md))
- **JMK** was below 7-Zip PPMd on 0 of 256 rows. I withdrew it on 2 Oct 2026 and closed its pre-registration unread. ([JMK](cards/model-jmk.md))

The lessons I wrote down from this work:

### Meeting a baseline is not beating it

**What happened.** BMK, a test model of mine (21 to 24 Sep 2026), lost to plain counting on 33-byte windows of English: 2.971336 bits per byte against 2.906112. On 32-byte windows a variant needed 3.489173 against 3.489131 for counting, a tie to 0.00004. Later, a new line I built to beat version 4 of BMK 2 (4 to 5 Oct 2026) needed 1.379028 bits per byte on 256 held-out rows, against 1.385801 for version 4 on the same rows: ahead by 0.006773. A fixed setting of the same line beat it by 0.000112, and three other added side parts bought nothing.

**The lesson.** My note on BMK: meeting counting is not beating it. My verdict on the later line: it does not earn its time.

**What changed after.** My notes don't record a next step.

Card: [BMK and BMK 2](cards/model-bmk.md).

### A gap means nothing across different bytes

**What happened.** QMK-2's ledger had carried a gap of +0.213054 against 7-Zip PPMd. The three early races behind it had compared across different sets of bytes.

**The lesson.** (paraphrase) A gap between two scores means nothing unless both were measured on the same bytes.

**What changed after.** The ledger withdrew the gap. QMK-2's numbers were then read three times on one machine and once on a second, equal to the last digit, and they show a loss. I never say QMK-2 beat or matched PPMd.

Card: [QMK-2](cards/qmk-2.md).

### The verification, not the ratio

**What happened.** My compressor for Python source scored 0.993994 bits per byte on 30 Python files, against 1.265092 for 7-Zip PPMd at its best order, with 30 of 30 round trips. On a different set, 542,523 bytes of normalised Python standard-library source, counting the size of its decoder program (83,932 bytes) makes the total 152,151 bytes. That is more than the 84,957 bytes 7-Zip PPMd needs on the same data. It also returns a normalised form of a Python file, not the file as written, and comments and formatting are 20.8 percent of the characters in those files.

**The lesson.** My written summary of the compressor says the strongest part of the work is the verification, not the ratio. For a buyer who needs the exact original file, it calls the compressor disqualifying today.

**What changed after.** Its limits are always stated with it: the margin falls 31 percent when PPMd gets its best setting, on English it loses to PPMd by 0.351291 bits per byte, it is much slower to encode, and peak memory is 1,751 MiB against 16 MiB.

Page: [Compression demonstrator](../projects/compression-demo.md). Card: [Compression demonstrator](cards/compression-demonstrator.md).

## A log without a verdict line is not a reading (computing without binary, by 11 Sep 2026)

**What happened.** By 11 Sep 2026 I had six small simulation scripts on computing without binary. In one, a three-level circuit that drew no static current needed 7.571 transistors per bit, against 2.000 for a binary inverter, so it lost on transistor count. Stochastic computing was closed as a negative, and a bit-slicing idea died to both of its controls.

**The lesson.** Every script ends with checks that print PASS or FAIL, and a log without those lines does not count as a reading. Its README states the scope plainly: "No watt, no wire, no chip is measured here".

**What changed after.** On 17 Nov 2026 a review re-opened 21 of my own chip numbers and found 1 bad, which I fixed. No chip has been made.

Page: [Computing without binary](../projects/computing-research.md).

## A count that counted any output (QMK-1, 25 Sep 2026)

**What happened.** I kept a count of the problems QMK-1 had solved. Four of its seven solves were one common word.

**The lesson.** My notes give the reason the count was wrong: it counted any output.

**What changed after.** I withdrew the count on 25 Sep 2026.

Card: [QMK-1](cards/qmk-1.md).

## One run of a check is not a verdict (QMK-1, 24 Sep 2026)

**What happened.** I rewired five files in a copy of QMK-1's code and ran its four-part self-check 40 times, each run unseeded. The original passed all four parts on 40 of 40 runs. The rewired copy passed on 19 of 40. That is worse on this check; other counts in the same pass moved the right way. With the original's seeds switched off while it ran, the same check held on 24 of 40.

**The lesson.** (paraphrase) A single run of that check is not a verdict.

**What changed after.** The changes stayed on the copy. None of the 29 live files was written.

Card: [QMK-1](cards/qmk-1.md).

## A detection rule I retracted (QMK line)

**What happened.** A detection rule of mine reported a false-alarm rate of 0.006780. Tested against 3,600 matched control runs, its real rate was 0.073611, about 10.9 times higher.

**The lesson.** In September 2026 I tested whether a looser version of the rule would catch more real structure at the same false-alarm rate. It would not, and my result file calls the premise false.

**What changed after.** I retracted the rule.

Card: [QMK and AMK](cards/qmk-and-amk.md).

## A verdict, then a test that was too easy (QMK 3, 2 to 6 Oct 2026)

**What happened.** On 2 Oct 2026 I wrote my verdict on QMK 3. On 3 Oct the morning's readings were 90, 356 and 1,474 above chance at three sizes, and they did not survive the day. A trivial counting method scored 90 of 96 on the same test, where QMK 3 scored 46.5. None of the runs had been on the GPU as I had believed.

**The lesson.** My verdict of 2 Oct: real but modest, not yet a capability, ten goals at 0 of 10. My notes of 3 Oct: the test was too easy.

**What changed after.** I stopped every CPU run that day. On 6 Oct I read a pre-registered race of four QMK 3 variants, each paired with a fake-version control, 96 trials per setting. No variant qualified at any of four settings. It was a check of my method: the result is that nothing qualified, not that anything was learned about language.

Card: [QMK-3](cards/qmk-3.md).

## Seven weeks of reading back what they were fed (QMK and AMK, to 17 Nov 2026)

**What happened.** Over about seven weeks, the QMK and AMK models I built under strict rules never got past reading back what they had been fed. The best did no better than a plain lookup table on text it had seen. My AMK2 notes of 17 Nov 2026 record, as measured that week, that on text it had been fed, its best version gave back 5.2, 6.0 and 7.7 of 16 bytes at 256 KiB, 1 MiB and 16 MiB of text. That is about what a 12-byte lookup table does, and a 16-byte table beat every version at every size. The "of 16 bytes" measure is my notes' own and is not defined where it is written down.

**The lesson.** (paraphrase) The rules themselves were what kept the line a memory.

**What changed after.** I changed the rules on 17 Nov 2026, and the learning work went on in Project Hail Mary, the research I have run since January 2026. Its current English model was designed on 17 Nov and has trained since 18 Nov 2026, and the project got its name on 19 Nov. It does not yet match a standard model at equal compute: in the one equal-time race so far (58 minutes each, from nothing, one run each), it lost by 0.1021 bits per byte on 256 held-out story windows (standard error 0.0026).

Cards: [QMK and AMK](cards/qmk-and-amk.md), [AMK2](cards/model-amk2.md). Page: [Project Hail Mary](../projects/hail-mary.md).

## A reasoning test that a lookup table could pass (Hail Mary, 18 to 26 Nov 2026)

**What happened.** On 18 Nov 2026 I found that 334 of the 390 items I had drawn from a public reasoning set could be answered by lookup alone, so 56 of them test a rule. An earlier version of that test had leaked its answers through the length of the gap.

**The lesson.** (paraphrase) A reasoning test is worth running when a lookup table must fail it.

**What changed after.** The leaking test was rebuilt. On a separate reasoning test that a lookup table must fail, an early snapshot of my 25 million weight English model scored at chance, also after 3,000 updates of logic examples. On 25 Nov, and again in a re-run on 26 Nov, a model trained for one hour with about a tenth of its reading being logic examples showed learning on none of the 8 kinds of logic question I tested, on 800 held-out questions. It is one seed. The project's word for it is "not shown", which is weaker than "impossible".

Card: [Hail Mary English model](cards/hail-mary-english.md). Also: [How I test results](METHOD.md).
