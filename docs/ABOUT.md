# About me

## What I work on now

Two projects, side by side:

- [Project Hail Mary](../projects/hail-mary.md): language models built from scratch, aimed at learning far more from far less data and memory.
- [Project Alpha](../projects/exact-ai.md): an engine that runs open language models so their answers can be re-made bit for bit on other machines and checked later. I lead the research. My dad and I share it, under the name Baseline Technologies.

## How I got here

From 20 Apr to Sep 2026 I trained my own small language models at home ([Mark One](../projects/mark-one.md), 40M to 295M parameters). They lost to the Qwen models I compared them against.

On 8 Sep 2026 I started [Jarvis](../projects/jarvis.md), a WhatsApp booking assistant for Apex Dental, my dad's two dental clinics in Birkirkara, talking to real patients since at least 13 Sep 2026.

Alongside it, for about seven weeks, my learning models (the [QMK and AMK lines](../projects/dead-ends.md)), built under strict rules, never got past reading back what they had been fed. On 17 Nov I changed the rules.

Project Alpha started on 9 Nov 2026. Project Hail Mary is the research I have run since January 2026; its current English model was designed on 17 Nov and has trained since 18 Nov 2026. The project got its name on 19 Nov.

## How I work

I go by a line of my own: "attack impossible-looking ideas anyway". Many of those ideas fail, so I write the pass and fail lines before a test runs. In Hail Mary each pass rule is locked with a hash before any result is read. A separate testing step inside my project re-counts a result before I quote it. That catches my mistakes, but it is not an outside check.

Losses stay on record. In Hail Mary's one equal-time race so far (58 minutes each, one run each), a standard model scored 1.2878 bits per byte on 256 held-out story windows and mine 1.3900, so mine lost (lower is better). A detection rule of mine reported a false-alarm rate of 0.006780. Against 3,600 matched control runs it was 0.073611, and I retracted it.

I build with AI coding tools; I set the rules, design the tests and decide what counts as done.

## What is not done yet

- Nobody outside my projects has reproduced a result.
- No customer and no money raised. No company is incorporated.
- All real users so far come through Apex Dental.
- Hail Mary does not yet match a standard model at equal compute. The current model is one week old.

## Where I live and what I use

I live in Malta. I'm 17, and I work on my projects full time.

I use one home PC with an NVIDIA RTX 5090 (32 GB), 32 logical cores and 93.6 GB of memory. Earlier training also used a second PC with an RTX 5070.
