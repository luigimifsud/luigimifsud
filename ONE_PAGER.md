# Luigi Mifsud

Malta. luigi28mifsud@gmail.com. Portfolio: https://github.com/luigimifsud. LinkedIn: https://www.linkedin.com/in/luigi-mifsud-a65739293

I work full time on my own projects. I do AI research at home.

> "I want to revolutionize AI learning and do more. ... I want to literally rebuild the way silicon functions ..."

The question under all of it is how a machine can learn and compute far more with far less, in a way other people can check. I work on it through two projects at once, one from each side.

## Project Hail Mary: the learning half

We are building language models from scratch, aimed at learning far more from far less data and memory. The research has run since January 2026; the current English model has trained since 18 Nov 2026, on one GPU in my home PC.

- My own training stack, written from scratch in Rust and CUDA, has run about 1,050 clean GPU jobs on one home GPU since 19 Nov.
- A learned forecaster beat its hand-written version in 12 of 27 test cells and was worse in none, on generated test streams.
- In an early preview on one seed, a small model I trained for 58 minutes from nothing got 92 to 97 percent of held-out simple arithmetic questions exactly right, against 0 to 5 percent for the same model trained without arithmetic. On harder forms it got about half right, and it never learned 'which is more'.

It does not yet match a standard model at equal compute. The current model is one week old. In the one equal-time race so far (58 minutes each, from nothing, on one card, one run each), a standard model scored 1.2878 bits per byte on 256 held-out story windows and mine 1.3900, so mine lost (lower is better). I keep the design private for now. Details: https://github.com/luigimifsud/luigimifsud/blob/main/projects/hail-mary.md

## Project Alpha: the computing half (since 9 Nov 2026)

AI answers change between runs and machines, so nobody can later prove what an AI said. That matters wherever an AI answer decides money: audits, insurance claims, loans, payouts, evaluation. The EU AI Act asks high-risk systems to keep logs (Article 12).

I lead the research on an engine that runs open language models so an answer can be re-made bit for bit on another machine and checked later. My dad and I share it, under the name Baseline Technologies. Others publish determinism modes too (SGLang, vLLM and Gensyn). What I build around is the check afterwards: a signed receipt and a one-pass audit. A Windows pilot server signs every answer; it has been tested in-house so far.

Engine results, word for word as my project records them. "We" means the project; I'm applying on my own.

Scope today: five Qwen2.5 open models (0.5B to 32B) and one mixture-of-experts model (DeepSeek-V2-Lite), a 512-token window, and a pilot package for Windows only.

- Twelve devices (Windows desktops and laptops, AMD and Intel; Linux cloud servers, AMD EPYC and Intel; two NVIDIA H100 GPUs) gave bit-identical output on every block they shared: 29.8 million rows confirmed on at least two devices, 1.7 million on all twelve; one small open model.
- An NVIDIA RTX 5090 reproduced our CPU engine's output bit for bit on all 106,336 test rows we compared against AMD processors; one small open model.
- A one-pass re-check of a logged answer names the first token that changed. In our tests 40 of 40 honest answers passed with no false alarm, and 40 of 40 altered answers were caught at the exact token, down to a one-bit change.

The re-check works on answers made by this engine, or by one that gives the same bits. Details: https://github.com/luigimifsud/luigimifsud/blob/main/projects/exact-ai.md

## Before these, and beside them

My own small language models trained at home (Mark One, 40M to 295M parameters), with their losses on record; a compression demonstrator packaged so a stranger could re-run it, not yet published; computing without binary, all in simulation and mostly negative; an Earth-sized voxel simulator with all 112,147 buildings of Malta and Gozo at measured heights, where about 20 to 30 parts in deep shadow are wrongly dropped, an estimate (QMK World); an encrypted overlay on the internet, for distributed training (TETRA mesh); a WhatsApp booking assistant for Apex Dental, my dad's two clinics in Malta, used by real patients since September 2026 (Jarvis); and the dead ends, PhotoLocator included. Each is written up at https://github.com/luigimifsud.

LIGHTGAP (25 Oct to 2 Nov 2026), my own text compressor written from scratch in Rust, needed 1.152914 bits per character on a development set of 3,653,983 characters of English Wikipedia (26 letters and the space), against 1.7694 for 7-Zip PPMd; it is a development number, and the sealed test had not run as of 2 Nov 2026. Details: https://github.com/luigimifsud/luigimifsud/blob/main/projects/lightgap.md

## What you can check, and what you can't yet

Today: the clinic Jarvis serves is real, and you can message it on WhatsApp from its website and watch Jarvis answer; on a call I can open the log or result file behind a number here, with code and patient data off screen; and the portfolio repo's history will date every write-up once it is public. Not yet: nobody outside my projects has reproduced a result, and the "try it yourself" download has not been run on a second machine or sent to anyone. Claim by claim: https://github.com/luigimifsud/luigimifsud/blob/main/VERIFY.md

## Not yet

- Nobody outside my projects has reproduced a result.
- No customer and no money raised. No company is incorporated.
- All real users so far come through Apex Dental.
- Hail Mary's current model is one week old and does not yet match a standard model at equal compute.

## What $250,000 over two years would buy

A proposed plan, not a budget:

- outside reproduction of the main results, on machines I don't own;
- a public benchmark run, with pass and fail lines published in advance;
- a paying pilot where an AI answer decides money;
- compute for the engine and for Hail Mary.

## How I work

Pass and fail lines are written before each test, and a separate check inside my project re-counts a result before I quote it. Results that go against me stay on record. I build with AI coding tools; I set the rules, design the tests and decide what counts as done. I'm 17 and I work on my projects full time.
