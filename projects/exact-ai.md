# Exact AI (Project Alpha)

An engine that runs open language models so their answers can be re-made bit for bit on other machines and checked later, with a signed receipt and a one-pass audit.

**Status:** research and a working pilot, no customer yet. **Dates:** 9 Nov 2026 to now.

## What it is

Project Alpha started on 9 Nov 2026, and I lead the research. I run it under the name Baseline Technologies. No company is incorporated yet.

The engine runs open models: five Qwen2.5 models from 0.5B to 32B, plus one mixture-of-experts model. The aim: ask the same question on another computer and get the same answer, down to the bit. The results below say which computers that has been tested on.

Other tools have determinism modes as well, and three of them are named under Speed below, with their published overheads. What I am building around is the check afterwards: each answer can carry a signed receipt, and a logged answer can be checked again later in one pass.

## Why it exists

AI answers change between runs and between machines, so nobody can later prove what an AI said. That matters wherever an AI answer decides money: audits, insurance claims, loans, payouts, evaluation. The EU AI Act asks high-risk systems to keep logs (Article 12). A log tells you what was said. I want the answer itself to be something anyone can re-make and check.

The goal I set the project is 100 times more useful AI output from the same bytes of memory moved, with every token the same as an exact reference. That is an aim, not a result. The earliest milestone toward it, due on 18 Nov 2026, was not reached.

## What I built

- **The engine.** It runs the five Qwen2.5 models and the mixture-of-experts model. The results below say exactly which models and machines each exactness test covered.
- **A pilot server for Windows.** It answers in the standard chat-completions format and signs every answer. Tested in-house so far.
- **A "try it yourself" download.** Not yet run on a second machine, and not sent to anyone.
- **An audit check.** It re-reads a logged answer in one pass.

## Results

I quote results about the engine in one way: word for word as my project records them in its claims register, in the form each entry allows, with the limits that belong to it. The register is written in the third person. "Luigi" means me, "this PC" means my home PC, and "the owner's other programs" means other research programs running on the same PC at the time.

Where a register sentence says a result was re-checked, or that a test window was set apart for checking, that was done by a separate testing step inside my project, not by anyone outside it.

Scope today: five Qwen2.5 open models (0.5B to 32B) and one mixture-of-experts model (DeepSeek-V2-Lite), a 512-token window, and a pilot package for Windows only.

### Start here

Four results to start with. Everything else the register allows is grouped after them.

The same small model on twelve devices:

> Twelve devices (Windows desktops and laptops, AMD and Intel; Linux cloud servers, AMD EPYC and Intel; two NVIDIA H100 GPUs) gave bit-identical output on every block they shared: 29.8 million rows confirmed on at least two devices, 1.7 million on all twelve; one small open model.

A GPU against the CPU engine:

> An NVIDIA RTX 5090 reproduced our CPU engine's output bit for bit on all 106,336 test rows we compared against AMD processors; one small open model.

The current pilot package:

> Our pilot, Exact Server (Windows package v3.1), installs from one zip on a Windows PC and answers in the standard chat-completions form only on that PC's own local address, refusing requests from a web page or under a foreign host name; it attaches a signed receipt to every answer. On a fresh install, the same questions gave the same answers as on our earlier pilot install and a repeated question gave the same answer again, a one-command checker accepted every genuine receipt and rejected every forged one we tried, an audit pointed to the exact token we had changed, all 6,336 fixed test rows matched their reference, and a damaged or missing model file made it refuse to start, naming the file. It ships one small open model (Qwen2.5-Coder-0.5B-Instruct).

The re-check of a logged answer:

> A one-pass re-check of a logged answer names the first token that changed. In our tests 40 of 40 honest answers passed with no false alarm, and 40 of 40 altered answers were caught at the exact token, down to a one-bit change.

### Exactness across machines

These test whether the same small model gives the same output on different computers, from different makers, and on a GPU. The twelve-device and RTX 5090 results are under Start here. Two more:

> In our test, an Arm phone (Google Pixel 10a) produced bit-identical output from our engine on all 2,240 test rows compared with an AMD desktop's reference.

> On Microsoft Azure, an Intel server, two AMD EPYC server types and two NVIDIA H100 GPUs all produced output bit-identical to our AMD desktop's on every row compared, up to 29.8 million rows per machine; one small open model.

### Large models

These run bigger real open models on one PC and compare the CPU's different instruction paths against each other.

> On Qwen2.5-7B-Instruct (7 billion parameters), our exact engine gave bit-identical output on its AVX-512, AVX2 and portable code paths on all 256 rows of an independent test window, on one PC; the engine is the same file used for our smaller models.

> Qwen2.5-14B-Instruct, an open 14-billion-parameter model, runs on our exact engine on this PC: four different CPU instruction paths give bit-identical outputs on every test row we ran (6,336 rows, 1,024 on the two slowest paths), re-checked independently, and its text-prediction quality is within 0.08 % of the same model in full 32-bit precision (the 95 % interval includes zero).

> Qwen2.5-32B-Instruct, an open 32-billion-parameter model, runs on our exact engine on this PC: four different CPU instruction paths give bit-identical outputs on every test row run (6,336 rows, 1,024 on the two slowest paths), re-checked independently, and its text-prediction quality is within 0.02 % of the same model in full 32-bit precision on 20 text windows (the 95 % interval, -0.08 % to +0.11 %, includes zero).

> On a real open mixture-of-experts model (DeepSeek-V2-Lite), one whole expert layer, its router choosing 6 of 64 experts plus 2 shared experts, computed bit-identically on four different CPU instruction paths, at one and four threads, batched or one token at a time, on 514 real inputs, re-checked independently on the final engine build; a planted tie was broken the same way everywhere, and a one-byte change inside one expert changed exactly the 43 tokens routed to it and nothing else.

> We ran a real open mixture-of-experts model, DeepSeek-V2-Lite (27 layers, 64 routed experts per layer), end to end on our exact engine on one PC: four different CPU instruction paths, two thread counts and token-by-token decoding gave bit-identical outputs and identical expert choices on every one of 37,008 output rows, re-checked independently; and its text-prediction quality on 20 text windows is within 1 percent of the same model in full 32-bit precision (+0.14 %, 95 % interval -0.04 % to +0.30 %). Beside it, as pre-registered: an earlier first-layer fidelity check missed its 1 % target at 1.02 %, and 81.7 % of the expert choices match the full-precision model's.

### The pilot

The pilot is what a customer would install. There are two results and they are separate. The current package is under Start here. This one is for the earlier pilot:

> Our pilot, Exact Server, installs from one zip on a Windows PC, answers in the standard chat-completions form on that PC only, and attaches a signed receipt to every answer; the same question gave the same answer and the same receipt twice, a one-command checker accepted every genuine receipt and rejected every forged one we tried, and an audit pointed to the exact token we had changed.

### Speed

These are timed runs on one PC. Each sentence names what was compared and the setting it ran in.

> On one NVIDIA RTX 5090, our exact GPU path produced output bit-identical to an exact reference on all 100 held-out test prompts (300 of 300 timed runs), and took 1.26 times the wall time of plain bf16 on the same model and GPU (a 26 % overhead; median of three alternating repeats on a busy PC). Plain bf16 itself differed from the exact output on 44 of the 100 prompts. One small open model (0.5 billion parameters), 128-token answers.

Beside it, as the register requires:

> published determinism modes report overheads of 24 to 55 % (SGLang), 2.4 times (vLLM's bitwise mode for RL) and 58 to 218 % (Gensyn's cross-hardware mode). Those figures are on other models, hardware and workloads; this is not a like-for-like test.

Separately, a timed comparison on the CPU against llama.cpp:

> On one PC, in a quiet window beside the owner's other programs, our exact CPU engine produced about 2.19 times the tokens per second of llama.cpp (as built into Ollama, build 740af7a7, a different build from our earlier comparisons) on the same small model (Qwen2.5-Coder-0.5B-Instruct; llama.cpp with Q8_0 weights and its n-gram speculation; 8 threads each), on 57 held-out prompts, the median of three alternating repeats (2.14 to 2.20), with every one of our 342 outputs bit-identical to the exact reference. It was our fourth timed comparison on the same 57 prompts: a later run with a changed loader and drafter rule, the rule chosen on separate development prompts by counts, not by a measured speed; the target set in advance was 2 times.

### Other tools

These are tools around the engine: a converter that brings open Qwen2.5 models into it, and a check for logged answers. The check works on answers made by our engine, or by one that gives the same bits. The check itself is the last result under Start here. The converter:

> One command converts an open Qwen2.5 model into our exact engine's format and checks it: the 7-billion-parameter model came out byte-identical to the format we built by hand, and the 0.5-billion one identical array by array; malformed inputs we tried were refused by name, including weights holding invalid numbers and weights the model's settings do not account for.

### A timed comparison on a 32B model, one session

This is one session on a 32B model. Its scope line comes straight after it.

> In our first timed comparison of the 32B, on one PC in a quiet window beside the owner's other programs, our exact CPU engine produced about 2.09 times the tokens per second of llama.cpp (as built into Ollama, build 740af7a7) on Qwen2.5-32B-Instruct, the general model (llama.cpp with matched-precision Q8_0 weights of the same model made on this PC, and its n-gram speculation; 8 threads each), on 19 held-out prompts, a third of the held-out set only, pooled over two alternating repeats (2.10 and 2.09), with every one of our 76 outputs identical, token for token, to the reference made in advance. Our engine's rule and library were those frozen on the 0.5B model, not re-tuned for this one, with a loader written for this model; the bar set in advance was 2 times, for the pooled figure and for each repeat.

Scope of this result: one session, on one desktop PC's CPU, with one model and 19 prompts; it covers no other machine, GPU, model, prompt set or llama.cpp setting.

### Exactness at size, on test networks

These use test networks with seed-generated weights, not trained models. They check that results stay exact when the network is very large. They say nothing about any model's quality or speed.

> We pushed one token through a 5-trillion-parameter test network with seed-generated weights (not a trained model) on one RTX 5090, and two CPU implementations matched the GPU bit for bit on every value we compared.

> Two cloud H100 GPUs re-ran our 5-trillion-parameter test network with seed-generated weights (not a trained model) and matched our RTX 5090 on all 584 compared digests.

> We pushed one token through a 20-trillion-parameter test network with seed-generated weights (not a trained model) on one RTX 5090, and two CPU implementations matched the GPU bit for bit on every value we compared.

> Two cloud H100 GPUs ran an endless test network with seed-generated weights (not a trained model) for 6,090 layers, about 104.6 trillion weights, and every layer's output was bit-identical on both machines.

> This PC's RTX 5090 computed bit for bit the same result, layer by layer, as two H100 GPUs in the cloud on 6,090 layers (104.6 trillion seed-generated parameters) of an endless test network with seed-generated weights (not a trained model), and as one of those H100s on all 6,357 layers (109.2 trillion).

### Earlier research in the same register

This one comes from my own model research in August 2026, before Project Alpha. It follows the same rules as the rest.

> In August, a variant of Luigi's own model design beat the standard same-size pairwise model (a Boltzmann-family model with no hidden units) on held-out data in every paired trial on record: by 10 to 14 percent in the longer runs and by about 5 to 6 percent in shorter eight-seed runs, though a generic control also beat that model by about a third as much. It is small-scale research, not a compressor, and not yet independently re-run.

This is the August claim in its narrowed wording, after a check; the [Hail Mary page](hail-mary.md#a-small-exact-test) mentions the same narrowing.

## Where it falls short

- The earliest milestone toward the goal, due 18 Nov 2026, was missed, and one 7B timing came out without a result.
- Two side lines inside Project Alpha are written up on their own pages, as they came out. An AlphaFold side line passed none of its tests of new ideas ([dead ends](dead-ends.md)). A review of my older chip research re-opened 21 of my numbers and found 1 bad, now fixed, in research that is mostly negative ([computing research](computing-research.md)).
- Every result above was measured inside my own project and re-checked by a separate testing step inside it too.

## Status

- No customer and no money raised yet. The company is not incorporated.
- About 70 outreach emails sent, and one investor conversation so far.
- On 26 Nov 2026 at 13:41, Project Alpha had 572 logged runs and 560 report files since 9 Nov 2026.

## Not done yet

- Nobody outside the project has reproduced any of these results yet. That is the next thing I want. [How to check what this site says](../VERIFY.md#exact-ai) goes through what you can and can't check.
- The 32B timed comparison covers 19 of the 57 held-out prompts. A run on all 57 is still to do.
- The pilot server has been tested in-house so far. The "try it yourself" download has not been run on a second machine or sent.

## Check it yourself

- **The register rows.** Every engine result on this page is copied word for word from my claims register. Each row names its result file and the testing step that marked it. On a call I can open any row and the file behind it.
- **Check a receipt yourself.** A page with sample signed answers, the public key and a standard signature check that runs in a browser is not published yet.
- **Run it on your own machine.** The "try it yourself" download exists, but it has not been run on a second machine or sent to anyone.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/exact-ai.md
