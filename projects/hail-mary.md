# Project Hail Mary

Long-term research into language models that learn far more from far less.

**Status:** research, early. **Dates:** the research since January 2026; this model since 18 Nov 2026.

## What it is

The aim, in one sentence: we are building language models from scratch, aimed at learning far more from far less data and memory.

It runs on my own training stack, written from scratch in Rust and CUDA, on one GPU in my home PC. The research has run since January 2026; the current English model has trained since 18 Nov 2026. By 26 Nov that model had 37.6 hours of training on the one card, added up from the logged seconds.

## Why it exists

The exact engine is about trusting what a model says. Hail Mary goes after a different problem: how much data and memory a model needs in order to learn at all. If a model could learn the same things from much less of both, far more people could build their own.

In my own words: "I want to revolutionize AI learning and do more." This is the project where that work is heading.

Before this model, I spent about seven weeks on earlier learning models built under strict rules. They never got past reading back what they had been fed, and the best did no better than a plain lookup table on text it had seen. On 17 Nov I changed the rules. That earlier work is on the [dead ends](dead-ends.md) page.

I keep the design private for now. This page has what it does and what it has shown, not how it works.

## What I built

- My own training stack, written from scratch in Rust and CUDA, running on the home GPU.
- A results page that lists 66 separate lines of work, each with the word its own test printed. A void result is shown as VOID.
- A ledger of 704 ideas. Since 20 Nov, 54 of them have been put through a test, and 28 more are unsure. Tested means tested, not that the idea worked.
- A written record for each line of work. In the 74 work folders counted so far (of 75) there are 99 rule files, 242 check files, 46 verdict files and 25 re-derivation files, counted by file name.

## Results

These are early results. Each one says what it was measured on and what it does not show. Lower bits per byte is better.

### The three I lead with

> My own training stack, written from scratch in Rust and CUDA, has run about 1,050 clean GPU jobs on one home GPU since 19 Nov.

> A learned forecaster beat its hand-written version in 12 of 27 test cells and was worse in none, on generated test streams.

> In an early preview on one seed, a small model I trained for 58 minutes from nothing got 92 to 97 percent of held-out simple arithmetic questions exactly right, against 0 to 5 percent for the same model trained without arithmetic. On harder forms it got about half right, and it never learned 'which is more'.

It does not yet match a standard model at equal compute. The current model is one week old.

### The race it lost

The one equal-time race so far: 58 minutes each, from nothing, on one card, one run each. A standard model scored 1.2878 bits per byte on 256 held-out story windows. Mine scored 1.3900, so mine lost by 0.1021 (standard error 0.0026). On name-lookup questions in the same race, the standard model got 0.95 to 0.99 and mine got 0.000.

### The arithmetic result in full

One seed per setup, a preview, not a locked verdict.

- A small model trained for 58 minutes from nothing, with about a tenth of its reading being simple arithmetic, got 92 to 97 percent of 400 held-out near questions exactly right. The questions were sums, differences and next numbers, set in short stories.
- The same model, trained for the same time with no arithmetic, got 0 to 5 percent.
- With one number in a question changed, it gave the old answer 0.2 to 1.6 percent of the time.
- On harder forms (longer sums, and sums told as a story) it got 46 to 54 percent, against chance of 10 and 19 percent.
- It never learned "which is more" (under 2 percent).
- Its English got a little worse.
- The test questions were made on the same PC, and none of them were in the practice set. No other model was tested on them.

### Against a compressor

On 256 held-out windows of 512 bytes, my 25 million weight model needed 0.8630 bits per byte on stories and 1.2070 on mixed text. An order-12 PPM compressor written in the project, which had counted 170 MB and 400 MB of the training text beforehand, needed 1.0663 and 1.4494. xz, given the training text beforehand, needed 1.4216 and 1.8784.

Limits: that PPM is weaker than 7-Zip PPMd, which was not measured here, and its settings were tuned on the same windows.

### A loss to my own earlier model

On the same 256 story windows, my earlier model of the same size needs 0.5804 bits per byte against the new one's 0.8630, and it wins on every window. On mixed text it is 0.8678 against 1.2070. So the new model is still behind my own earlier one.

### A small exact test

With 1,985 weights, on 4-byte windows of one corpus (mostly the project's own Python source), scored exactly, my model beat each of four rival models on all 3 seeds, by 4.0, 9.4 and 14.0 percent. The rivals were a Boltzmann machine with 30 hidden units and three pairwise or three-way models of 1,344 to 3,008 weights. A control that destroyed the data's order scored 1.785918.

Limits: a small test, on one machine, and not a language-model result. An earlier August claim was narrowed after a check; its narrowed wording is the August result on the [exact AI page](exact-ai.md#earlier-research-in-the-same-register).

### What it writes

The current English model at training step 370,435, picked from a longer sample whose grammar is broken, exactly as printed:

"He was very scared. He did not want to ge up from him in his net."

### Before Hail Mary had its name

- An earlier model of 25 million weights, built in one night (26 to 27 Oct), wrote sentences after about 3 minutes and reached 0.960 bits per byte on unseen simple English after about 10 hours. A picked sample, exactly as printed: "Once upon a time, there was a big spring. In the spring, there was a little fish named Fin. Fin was a very happy fish."
- On 27 Oct I had a Rust trainer built for a text model of about 200 million weights on my own card. I paused it the same day, after about 421 million bytes, at 1.18 bits per byte on held-out science text and still babbling. Earlier in the run it had reached 0.74 on simple stories, a different held-out set. A paused experiment.

## Where it falls short

- It does not match a standard model at equal compute. It lost the one equal-time race, and on name lookup it scored 0.000.
- It is behind my own earlier model of the same size, on every story window.
- Training runs on the card are not repeatable yet: the same settings and seed have ended differently on replay. One fix let 4 of the 5 dying runs finish their full hour.
- The arithmetic result is one seed, and a preview.
- The forecaster result comes from generated test streams.
- A different forecaster race, not the 12 of 27 result, looked good, but one check file's last line broke the locked rule, so the whole race is VOID. The earlier notes that treated its numbers as results were corrected, and I never quote them.
- The compressor it beat is a PPM written in the project, weaker than 7-Zip PPMd, with settings tuned on the same windows.

## How I check results before I quote them

- Pass rules are written down and locked with a hash before any result is read. A change is a dated, hashed amendment, never an edit.
- Tests are checked by planting deliberate errors. Three of them caught 15 of 15, 9 of 9 and 26 of 26. One test reader caught 84 of 89 and was marked not ready.
- Each result gets a separate re-check inside my project before I quote it.

## Status

Active research. The current model is one week old.

## Not done yet

- It does not match a standard model at equal compute yet.
- Its training runs are not repeatable on the card yet.
- Nothing here has been reproduced by anyone outside my projects. [How to check what this site says](../VERIFY.md#project-hail-mary) is plain about that.
- There is nothing to download yet. The design stays private for now.

## Check it yourself

- **On a call.** I can share my screen and open the job log behind the job count, the results page with its 66 lines of work, the idea ledger, the locked rule files with their hashes, and the result files behind each number on this page, with the design kept off screen.
- **What you cannot check yet.** There is nothing public to run. Until there is, these results rest on my own measurements.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/hail-mary.md
