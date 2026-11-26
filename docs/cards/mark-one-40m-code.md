# Mark One 40M

My 40.6 million parameter language model, trained at home on code and prose, part of Mark One.

| | |
|---|---|
| Project | Mark One |
| Dates | Tested 25 to 28 Jul 2026. The training dates are not in the files I checked. |
| Size | 40.6 million parameters |
| Hardware | Scored on CPU. The files I checked do not say which GPU trained it. |
| Status | Paused, with the rest of Mark One |

## What it was for

I wanted to know how much a small model trained at home could learn about code and text. I measured that against standard compressors that people actually use, on held-out text the model had not trained on. It is the model behind the code result I cite for Mark One.

## What it was trained and tested on

- Code and prose: 8.07 bytes of training text per parameter. My notes give 60 to 80 bytes per parameter as the reference for a compute-matched run, so this model is far under-trained.
- Its held-out set is 2.2 MB of text kept out of training. The 192 test windows were cleaned of overlap with the training data.
- A second test used 96 windows of web text (FineWeb), also checked against the training text for overlap.
- Every compressor scored exactly the same bytes as the model, checked window by window by hash.
- A separate completion test used 200 items cut from Python's own test files, each checked against the training text by an overlap scan.

## Results

Lower bits per byte is better.

- **Against standard compressors, on its own kind of text.** On 192 held-out windows of code and prose, cleaned of overlap with the training data, it scored 1.3615 bits per byte against 2.8362 for brotli -q 11, the strongest of 9 standard compressors scored on the same windows: 2.08 times smaller (95% confidence interval 2.016 to 2.159). No standard compressor beat it on any of the 192 windows. Limit: standard compressors start cold on short windows, so this shows the model learned code, not that it is a better general-purpose compressor.
- **On web text it was not trained on.** On 96 held-out windows of FineWeb that did not overlap its training text, it needed 2.3845 bits per byte against 3.0996 for brotli at its highest setting: 1.2999 times smaller (95 percent interval 1.282 to 1.319). No standard compressor beat it on any of the 96 windows. Limit: moving to web text cost it 1.02 bits per byte against its own kind of text, and the lead fell from 2.08 to 1.30 times. Brotli ships a built-in web-text dictionary, which my notes give as the reason it comes close. Standard compressors start from nothing on each short window, so this shows what the model learned about web text, not a better general-purpose compressor. Recorded in my scoreboard, not re-run since.
- **A full round trip.** On 28 Jul 2026 I compressed 769,738 bytes of held-out text with the model, decompressed them again and got the same bytes back, checked by hash. The model needed 1.4377 bits per byte, against 2.0843 for brotli, 2.1402 for xz and 2.4656 for gzip on the same bytes. Limit: this does not count the size of the model itself, so it is not a self-contained compression result. With the model's own size counted, my notes record that it loses to gzip on this 2.2 MB held-out set by about two orders of magnitude. The run covers 77 percent of the 1,000,000 bytes I had registered, because the held-out data ran out. One span, one run. Recorded in my scoreboard, not re-run since.
- **Finishing real Python code.** This is a separate result, on a different test. On 200 completions cut from Python's own test files, the model (at step 19,500, on 26 Jul 2026) reproduced 7.95 bytes of the real continuation on average before making a mistake. A baseline built from statistics of the training text alone reached 4.77, one that writes nothing but spaces 5.13, and one that copies the bytes just seen 5.98. That is 1.667 times the statistics baseline, below the 2 times I had registered, and 1.329 times the best of the simple baselines. Counting just the non-space bytes, its edge over the copy baseline was 0.330 bytes, inside its own noise. It got 0 of 200 exactly right. Two mechanical checks scored it, exact match and structure, with no AI judge. Limit: one of the 200 items had its whole 64-byte answer in the training text and passed my overlap rule anyway, so the rule was wrong in kind; no filed score depends on that item. Its edge is early in each answer and falls away later, and extra context did not help it. Recorded in my scoreboard, not re-run since.

The 0 of 200 says nothing about my 295M model, which was not measured on this test. The 295M model's coding suite is a different test on a different model ([Mark One 295M](mark-one-295m.md)). The two are separate results, not a before and after.

## Where it falls short

- **My headline fell twice, both times in writing.** It went from 3.27 times smaller than gzip on 96 windows (25 Jul 2026), to 2.49 times after I removed the windows that overlapped my training text (26 Jul), to 2.08 times once I compared against brotli, the strongest of nine standard compressors on those windows, instead of gzip (by 27 Jul). Before the second measurement I had written down about 2.6 as my expectation. About 35 percent of the fall from 3.27 to 2.49 came from a change in the mix of windows and about 65 percent from removing overlap. Recorded in my scoreboard.
- **I set rivals up too weakly, in my favour.** In my comparisons of this model and my 295M model with standard compressors (25 to 27 Jul 2026), I found six places where I had set up a rival compressor too weakly, each time in my favour, including never running brotli at all. Eight of my written predictions about how strong a rival would be turned out wrong, and all eight were too low, which has a chance of 0.0039 if there were no bias. I now require a rival's settings to be pushed to the tool's documented limit before its number is used. These are my own notes, not a separate testing step.
- **A trend I withdrew.** On 27 Jul 2026 I wrote that the model's lead over brotli was shrinking, from 1.551 times on 8 KB of text to 1.180 times on 100 KB, and I named a cause. On 28 Jul a third measurement, on 770 KB, put the lead at 1.450 times, so I withdrew the trend and the cause, which I had drawn from two points. Recorded in my scoreboard.
- **Shrinking it.** Shrinking this model's weight matrices without retraining made the score worse at every size I tried.
- With its own size counted, it loses to gzip. At 8.07 bytes per parameter it is also far under-trained.

## Not done yet

- The test windows are not published, so nobody else can score the compressors on them.
- Nobody outside my projects has re-run any of this.

## Check it yourself

- **Today.** Nothing you can run. The model and its test windows are private.
- **On a call.** I can open the scoreboard rows behind each number here, the withdrawn ones included, and the result files I can still reach. Some of the result files are on a drive I could not open for this write-up, so those numbers are as my scoreboard recorded them at the time.
- [How to check what this site says](../../VERIFY.md#mark-one) covers what can and can't be checked for Mark One.

## More

- [Mark One](../../projects/mark-one.md)
