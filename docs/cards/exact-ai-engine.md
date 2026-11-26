# Exact AI engine

An engine that runs open language models so their answers can be re-made bit for bit on other machines and checked later, built in Project Alpha.

| | |
|---|---|
| Project | Project Alpha, where I lead the research |
| Dates | 9 Nov 2026 to now |
| Hardware | My home PC (an NVIDIA RTX 5090 with 32 GB, 32 logical cores, 93.6 GB of memory). The exactness tests also ran on the other devices and cloud machines that each result names. |
| Status | Research, with a Windows pilot tested in-house. No customer yet. |

## What it was for

AI answers change between runs and between machines, so nobody can later prove what an AI said. That matters wherever an AI answer decides money: audits, insurance claims, loans, payouts, evaluation. The EU AI Act asks high-risk systems to keep logs (Article 12). I built the engine, a Windows pilot server that answers in the standard chat-completions format and signs every answer, a "try it yourself" download, and an audit check that re-reads a logged answer in one pass.

## What it was trained and tested on

I did not train these models. The engine runs open models made by others, listed in the scope line below. The tests run the same inputs on different machines and compare the outputs row by row, and they change logged answers on purpose to see whether the re-check catches the change. Each result says how many rows and which machines it covers.

## Results

I quote engine results in one way: word for word as my project records them in its claims register, so they read a bit stiff. "We" and "our" mean the project. They were measured on the project's own machines and on cloud machines, and re-counted by a separate testing step inside the project, not by anyone outside it.

Scope today: five Qwen2.5 open models (0.5B to 32B) and one mixture-of-experts model (DeepSeek-V2-Lite), a 512-token window, and a pilot package for Windows only.

- **Across devices.** "Twelve devices (Windows desktops and laptops, AMD and Intel; Linux cloud servers, AMD EPYC and Intel; two NVIDIA H100 GPUs) gave bit-identical output on every block they shared: 29.8 million rows confirmed on at least two devices, 1.7 million on all twelve; one small open model." Its limit is in the sentence: one small open model.
- **A GPU against the CPU engine.** "An NVIDIA RTX 5090 reproduced our CPU engine's output bit for bit on all 106,336 test rows we compared against AMD processors; one small open model." The same limit: one small open model.
- **The re-check of a logged answer.** "A one-pass re-check of a logged answer names the first token that changed. In our tests 40 of 40 honest answers passed with no false alarm, and 40 of 40 altered answers were caught at the exact token, down to a one-bit change." The re-check works on answers made by this engine, or by one that gives the same bits.

The rest of the results the register allows, each with its own scope (the large models, the pilot packages, the timed runs and the other tools), are on [the exact AI page](../../projects/exact-ai.md#results).

## Where it falls short

- One 7B timing came out without a result.
- The pilot server has been tested in-house so far.
- Every result was measured and re-counted inside my project. That catches my mistakes, but it is not an outside check.

## Not done yet

- Nobody outside the project has reproduced any of these results yet.
- No customer and no money raised. No company is incorporated.
- The earliest milestone toward the project's goal, due 18 Nov 2026, was missed.
- The "try it yourself" download has not been run on a second machine or sent to anyone.

## Check it yourself

Nothing you can run or open yourself yet. On a call I can open the register row behind each sentence and the result file it points to. [How to check what this site says](../../VERIFY.md#exact-ai) goes through what can and can't be checked.

## More

- [The exact AI page](../../projects/exact-ai.md), with every result the register allows and the limits of each
