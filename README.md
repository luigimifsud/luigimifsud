# Luigi Mifsud

I'm Luigi Mifsud. I live in Malta and work full time on my own projects.
I do AI research at home.

## The question

In my own words:

> "I want to revolutionize AI learning and do more. ... I want to literally rebuild the way silicon functions ..."

The question under everything I build is how a machine can learn and compute far more with far less, in a way other people can check.

I work on it through two projects at once. Project Hail Mary is the learning half: language models built from scratch. Project Alpha is the computing half: AI answers that come out exact, so they can be checked later.

The silicon part is still an aim. My tests of computing without binary ran in simulation, most of them came out negative, and I wrote them down as negative. No chip has been made.

## Project Hail Mary: the learning half

We are building language models from scratch, aimed at learning far more from far less data and memory. The research has run since January 2026; the current English model has trained since 18 Nov 2026, on one GPU in my home PC. By 26 Nov the model had 37.6 hours of training on that one card. Each pass rule is written down and locked with a hash before any result is read.

- My own training stack, written from scratch in Rust and CUDA, has run about 1,050 clean GPU jobs on one home GPU since 19 Nov.
- A learned forecaster beat its hand-written version in 12 of 27 test cells and was worse in none, on generated test streams.
- In an early preview on one seed, a small model I trained for 58 minutes from nothing got 92 to 97 percent of held-out simple arithmetic questions exactly right, against 0 to 5 percent for the same model trained without arithmetic. On harder forms it got about half right, and it never learned 'which is more'.

It does not yet match a standard model at equal compute. The current model is one week old. In the one equal-time race so far (58 minutes each, from nothing, one card, one run each), a standard model scored 1.2878 bits per byte on 256 held-out story windows and mine 1.3900, so mine lost by 0.1021 (standard error 0.0026).

I keep how it works private for now. Every result, the losses included: [the Hail Mary page](projects/hail-mary.md).

## Project Alpha: the computing half

Since 9 Nov 2026 I've led the research on an engine that runs open language models so their answers can be re-made bit for bit on other machines and checked later. I run it under the name Baseline Technologies.

AI answers change between runs and machines, so nobody can later prove what an AI said. That matters wherever an AI answer decides money: audits, insurance claims, loans, payouts, evaluation. Others publish determinism modes too (SGLang, vLLM and Gensyn). What I build around is the check afterwards: a signed receipt and a one-pass audit.

I quote engine results word for word as my project records them, so they read a bit stiff. "We" and "our" mean the project; I'm applying on my own.

Scope today: five Qwen2.5 open models (0.5B to 32B) and one mixture-of-experts model (DeepSeek-V2-Lite), a 512-token window, and a pilot package for Windows only.

- Twelve devices (Windows desktops and laptops, AMD and Intel; Linux cloud servers, AMD EPYC and Intel; two NVIDIA H100 GPUs) gave bit-identical output on every block they shared: 29.8 million rows confirmed on at least two devices, 1.7 million on all twelve; one small open model.
- An NVIDIA RTX 5090 reproduced our CPU engine's output bit for bit on all 106,336 test rows we compared against AMD processors; one small open model.
- A one-pass re-check of a logged answer names the first token that changed. In our tests 40 of 40 honest answers passed with no false alarm, and 40 of 40 altered answers were caught at the exact token, down to a one-bit change.

The re-check works on answers made by this engine, or by one that gives the same bits. Nobody outside the project has reproduced these yet.

The 32B and mixture-of-experts runs, the pilot, the timed runs against llama.cpp and the limits of each: [the exact AI page](projects/exact-ai.md).

## Everything else I've built

**Research that led here**
- [Mark One](projects/mark-one.md): my own small language models (40M to 295M parameters), trained at home from 20 Apr to Sep 2026. On 192 held-out code windows cleaned of overlap with the training data, the 40M model scored 1.3615 bits per byte against 2.8362 for brotli -q 11, the strongest of 9 standard compressors on the same windows (lower is better). Standard compressors start cold on short windows, so this shows the model learned code, not that it is a better general-purpose compressor. It lost to Qwen's code models. Paused.
- [Compression demonstrator](projects/compression-demo.md): a compression result on Python source, packaged so a stranger could re-run it, with its losses stated beside its win. Not published yet, so nobody can run it today.
- [LIGHTGAP](projects/lightgap.md): my own text compressor, written from scratch in Rust from 25 Oct to 2 Nov 2026. On a development set of 3,653,983 characters of English Wikipedia (enwik8, mapped to 26 letters and the space), it needed 1.152914 bits per character and decoded back exactly, against 1.7694 for 7-Zip PPMd, the best standard compressor on my PC (lower is better). That set helped choose the settings, so it is not a test; the sealed test had not run as of 2 Nov 2026. Going under 1.3 bits per character is not new, so this is a compressor I built from nothing, not a record.
- [Computing without binary](projects/computing-research.md): tests of computing beyond binary, all in simulation. Mostly negative, written down as negative.
- [Dead ends](projects/dead-ends.md): what didn't work and why I stopped, including about seven weeks of earlier learning models (QMK and AMK) that never got past reading back what they had been fed, and PhotoLocator.

**Other builds**
- [QMK World](projects/qmk-world.md): an Earth-sized voxel simulator, with all 112,147 buildings of Malta and Gozo at their measured heights (about 20 to 30 parts in deep shadow are wrongly dropped, an estimate). On its physics exam it agreed with the real Earth on 10 of 42 items, a failing grade. Paused.
- [TETRA mesh](projects/tetra.md): an overlay on top of the normal internet, with four layers of encryption, for distributed training. Prototype, dormant, never audited outside my projects.
- [Jarvis](projects/jarvis.md): a WhatsApp booking assistant for Apex Dental, my dad's two dental clinics in Malta, used by real patients since September 2026. You can message the clinic on WhatsApp from [apexdentalmalta.com](https://www.apexdentalmalta.com) and watch it answer.

Model cards, method, results and a timeline: [docs](docs/README.md).
- [Start here](docs/START_HERE.md): what to read in 2, 10 or 30 minutes.
- [Claims I withdrew](docs/WITHDRAWN.md), [open problems](docs/OPEN_PROBLEMS.md), [what the dead ends taught me](docs/LESSONS.md) and [the next two years](docs/PLAN.md).

## Where things stand

- Nobody outside my projects has reproduced a result yet. [How to check what this site says](VERIFY.md) goes claim by claim: what you can check today, and what you can't yet.
- No customer and no money raised. No company is incorporated.
- All real users so far come through Apex Dental.
- Hail Mary's current model is one week old and behind a standard model at equal compute.
- Before a test runs, I write down what counts as a pass and what counts as a fail. In Hail Mary each rule is locked with a hash before any result is read, and any change is a dated, hashed amendment, never an edit. A separate check inside my project re-counts a result before I quote it. That catches my mistakes, but it is not an outside check.
- I build with AI coding tools; I set the rules, design the tests and decide what counts as done.
- This repo holds write-ups, not code. The code stays private for now.

A one-page summary is in [ONE_PAGER.md](ONE_PAGER.md) and the slides are in [DECK.md](DECK.md).

Contact: [LinkedIn](https://www.linkedin.com/in/luigi-mifsud-a65739293)

Copyright (c) 2026 Luigi Mifsud. All rights reserved. See LICENSE.
