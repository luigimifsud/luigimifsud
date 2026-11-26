# Mark One

My own small language models, trained at home, plus a local multi-agent platform. This is the research I did under the name Baseline before Project Alpha.

**Status:** paused. **Dates:** 20 Apr to Sep 2026.

## What it is

Two things, built side by side over 1,944 commits:

- a local multi-agent platform that runs on my own machines;
- my own small language models, from 40M to 295M parameters, trained at home on about 1.46 TB of data and runs, and benchmarked against standard compressors and against Qwen.

## Why it exists

The aim, in my words from that summer, was to "make the entirety of the Internet fit onto one computer" and to "make large-scale AI processing not needed." That is an aim, not a result. I wanted to know how far a small model trained on home hardware could get, measured against tools and models that people actually use. The way to find out was to train them myself and measure them.

## What I built

- Forge, the earliest Mark One development model.
- The training and benchmark setup for models from 40M to 295M parameters.
- Benchmarks against 9 standard compressors and against Qwen models.
- A coding suite of 200 small generated Python tasks, frozen on 1 Aug 2026 and judged by running each program.
- A Mark One model for Maltese.
- A scoreboard that marks which numbers may be cited and keeps the retractions in writing.

Hardware: one home PC with an NVIDIA RTX 5090 (32 GB), 32 logical cores and 93.6 GB of memory. Earlier training also used a second PC with an RTX 5070.

## Results

Lower bits per byte is better.

**Code.** On 192 held-out code windows, cleaned of overlap with the training data, the 40M model (8.07 bytes of training data per parameter) scored 1.3615 bits per byte, against 2.8362 for brotli -q 11, the strongest of 9 standard compressors scored on the same windows. That is 2.08 times smaller (95% confidence interval 2.016 to 2.159). This is the row my scoreboard marks as the citable number.

Standard compressors start cold on short windows, so this shows the model learned code. It does not show that it is a better general-purpose compressor.

**Coding tasks.** My 295 million parameter model solved 164 of 200 small generated Python tasks with 8 tries each, and 150 with one greedy try. An earlier model of the same size got 120 and 107. The suite was frozen on 1 Aug and judged by running each program. It is my own suite, not a public benchmark, and no rival was run on it. A different coding result, on a different model and a different test, is under "Where it falls short", below. The two are separate results, not a before and after.

**Maltese.** Mark One's Maltese model scored 1.2733 bits per byte over 512 windows (95 percent interval 1.2305 to 1.3161), against 3.8010 for the general model on the same Maltese text (recorded in its result files, not re-run since).

**Forge.** The development model had 10.82M parameters and trained on an RTX 5070, with 0.89 GB peak memory on the card (recorded in its own notes, not re-run since).

## Where it falls short

My scoreboard has a line I still go by: "A named wall is a result, not a failure." These are the walls Mark One hit.

- An early "beats gzip" claim was retracted in writing.
- My earliest 40 million parameter model got 0 of 200 exact matches on completions of real Python test files (26 Jul).
- Mark One 295M scored 0.788 bits per byte against 0.593 for Qwen2.5-Coder-0.5B, on 256 fixed windows of 2,048 bytes of held-out code. It was behind by 0.195 and won on 18 of the 256 windows. Larger Qwen models scored 0.496 at 1.5B and 0.442 at 7.6B. Qwen probably saw similar code, and the holdout is not proven clean.
- The 220M code model lost to Qwen2.5-Coder-7B on 118 of 128 windows.
- Qwen2.5-Coder-7B (a 4-bit build) scored 0.985 bits per byte against Mark One's 1.432 on 128 windows.
- Shrinking weight matrices without retraining made every size worse.
- Four small pre-registered probes (4 seeds each, small models on a corpus of two textbooks) each ended KILL. The ideas failed at that size, which is not the same as never working.
- Separately, several of my home-built compressors lost to standard tools (7-Zip PPMd, lzma). They are on the [dead ends](dead-ends.md) page. A compression result that did hold up, with its limits stated, has its own page: the [compression demonstrator](compression-demo.md).

I keep these here because they are part of the result.

## Status

Paused since September 2026.

## Not done yet

- None of these home models beat the Qwen models they were compared against in the results above.
- None of it has been reproduced by anyone outside my projects. [How to check what this site says](../VERIFY.md#mark-one) goes through what you can and can't check.

## Check it yourself

- **The compressor side of the code result.** Publishing the 192 held-out code windows would let anyone run brotli -q 11 and the other standard compressors on them and check that side of the comparison. They are not published yet.
- **Commit history.** A record of Mark One's commit dates and count, with no code and no commit text, is not published yet.
- **On a call.** I can open the result files behind each number and recount the commits.
- **What you cannot check yet.** The models themselves are not public, so the model side of each result rests on my own measurements.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/mark-one.md
