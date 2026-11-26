# Start here

As of 26 Nov 2026.

This page is for a reviewer with little time. Pick the path that fits the time you have. Each number on it comes with what it was measured on and what it does not show.

## 2 minutes

Read [Where things stand](../README.md#where-things-stand) on the home page, then the numbers below. If you would rather read one page, there is a [one-page summary](../ONE_PAGER.md).

### The numbers that matter most

**Project Hail Mary.** In the one equal-time race so far (58 minutes each, from nothing, one card, one run each), a standard model scored 1.2878 bits per byte on 256 held-out story windows and mine 1.3900, so mine lost by 0.1021 (standard error 0.0026). Lower is better.

- Measured on: 256 held-out story windows, scored with the project's own held-out measure, the same for both models.
- What it does not show: more than this race. It was one race, with one run each.

Hail Mary does not yet match a standard model at equal compute. The current model is one week old. The early results that went my way, each with its limits, are on [the Hail Mary page](../projects/hail-mary.md#results).

**Exact AI (Project Alpha).** I quote engine results word for word as my project records them, so they read a bit stiff.

> Twelve devices (Windows desktops and laptops, AMD and Intel; Linux cloud servers, AMD EPYC and Intel; two NVIDIA H100 GPUs) gave bit-identical output on every block they shared: 29.8 million rows confirmed on at least two devices, 1.7 million on all twelve; one small open model.

Scope today: five Qwen2.5 open models (0.5B to 32B) and one mixture-of-experts model (DeepSeek-V2-Lite), a 512-token window, and a pilot package for Windows only.

- Measured on: the devices and the model the sentence names.
- What it does not show: a check by anyone outside my project. It was measured inside the project and re-counted by a separate testing step inside it. Nobody outside has reproduced it yet.

**LIGHTGAP.** My own text compressor, written from scratch in Rust. On a development set of 3,653,983 characters of English Wikipedia (enwik8, mapped to 26 letters and the space), it needed 1.152914 bits per character and decoded back exactly, against 1.7694 for 7-Zip PPMd, the best standard compressor on my PC. Lower is better.

- Measured on: my development set, VALID27, taken from enwik8, a public benchmark.
- What it does not show: a test result. That set helped choose the settings, so it is not a test, and the sealed test had not run as of 2 Nov 2026. Going under 1.3 bits per character is not new, so this is a compressor I built from nothing, not a record.

## 10 minutes

- [Project Hail Mary](../projects/hail-mary.md#results): the results, including the race it lost, then [where it falls short](../projects/hail-mary.md#where-it-falls-short).
- [Exact AI](../projects/exact-ai.md#start-here): the results under Start here, then [where it falls short](../projects/exact-ai.md#where-it-falls-short).
- [LIGHTGAP](../projects/lightgap.md): the development numbers so far, then [where it falls short](../projects/lightgap.md#where-it-falls-short).
- [The home page](../README.md): both projects, and what else I've built, one line each.
- [What you can check today](../VERIFY.md#what-you-can-check-today). The list is short.
- [Withdrawn](WITHDRAWN.md): claims I took back.

## 30 minutes or more

- [Every result in one place](RESULTS.md), with the losses next to the wins. Its Status column says what backs each number.
- [How I test results before I quote them](METHOD.md).
- [Open problems](OPEN_PROBLEMS.md): what is not solved yet.
- [The plan](PLAN.md): what comes next.
- [Lessons](LESSONS.md): what I took from the work so far.
- [Every model I've built](MODEL_HISTORY.md), from April to November 2026, with the losses.
- [Dead ends](../projects/dead-ends.md): what didn't work and why I stopped.
- [Mark One](../projects/mark-one.md): my earlier models, which lost to Qwen's code models.
- [The compression demonstrator](../projects/compression-demo.md), with its losses stated beside its win.
- [Computing without binary](../projects/computing-research.md): tests in simulation, mostly negative, written down as negative.
- [Jarvis](../projects/jarvis.md): the WhatsApp booking assistant I built for Apex Dental, my dad's two dental clinics in Malta, live with real patients since at least 13 Sep 2026, and [where it falls short](../projects/jarvis.md#where-it-falls-short). You can message the clinic on WhatsApp from [apexdentalmalta.com](https://www.apexdentalmalta.com) and watch it answer.
- [A dated timeline](TIMELINE.md), retractions included.
- [Cards](README.md): a short card for each model and system.
- [What I've built](ALL_BUILDS.md), one line each, and [about me](ABOUT.md).
- [The slides](../DECK.md).

## If you want to check one thing

Read [How to check what this site says](../VERIFY.md). It goes claim by claim: what you can open or run yourself today, and what you can't check yet. Nobody outside my projects has reproduced a result yet, so most of the page is the second part.

If you have time for a call, pick any number on this site and I'll share my screen and open the file behind it. The code and the design stay off screen, and no patient data is shown. You see the file, but it is still my file on my machine.

## If you are technical

- Read [METHOD.md](METHOD.md), then [RESULTS.md](RESULTS.md). The Status column in RESULTS.md says whether a number was measured, recorded, taken from the bot's logs or claimed.
- Lower bits per byte is better. Read each number with the limit beside it. The limit is part of the result.
- Engine results are copied word for word from my project's claims register, with the scope line. Where one says it was re-checked, that was a separate testing step inside my project, not anyone outside it.
- The pages say what each model did and what it was measured on, not how it is built. I keep the design private for now.
- The losses sit on the same pages as the wins, for example Mark One against Qwen under [where it falls short](../projects/mark-one.md#where-it-falls-short).
- I build with AI coding tools; I set the rules, design the tests and decide what counts as done.

## If you are not technical

- The [glossary](GLOSSARY.md) explains the terms these pages use in plain words. The [FAQ](FAQ.md) gives short answers to the questions a reviewer is likely to have.
- Most research numbers here are in bits per byte, where lower is better. The glossary says what that means.
