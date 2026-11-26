# Deck: Luigi Mifsud

## Slide 1: Luigi Mifsud

Two projects on one question: language models built from scratch to learn far more from far less, and an engine whose AI answers can be re-made bit for bit and checked later.

Malta. luigi28mifsud@gmail.com. Portfolio: https://github.com/luigimifsud. LinkedIn: https://www.linkedin.com/in/luigi-mifsud-a65739293

Notes: I work full time on my own projects.

## Slide 2: The question

> "I want to revolutionize AI learning and do more. ... I want to literally rebuild the way silicon functions ..."

The question under everything I build: how a machine can learn and compute far more with far less, in a way other people can check.

- The learning half: Project Hail Mary.
- The computing half: Project Alpha.

Notes: More of it in my words: "I want to find a way to completely rebuild and reimagine ways of computing. ... I want to cover from the hardware point of view and on the software point of view." And: "we are not working for compression. We are working for EFFICIENCY." My short version is "less for more". The silicon part is still an aim. My tests of computing without binary ran in simulation, most came out negative, and I wrote them down as negative. No chip has been made. Details: https://github.com/luigimifsud/luigimifsud/blob/main/projects/computing-research.md

## Slide 3: The two projects side by side

| | Project Hail Mary | Project Alpha |
|---|---|---|
| The half | Learning | Computing |
| What it is | Language models built from scratch, aimed at learning far more from far less data and memory | An engine that runs open language models so their answers can be re-made bit for bit on other machines and checked later, with a signed receipt and a one-pass audit |
| Since | The research since January 2026; this model since 18 Nov 2026 | 9 Nov 2026 |
| Runs on | My own training stack, written from scratch in Rust and CUDA, on one GPU in my home PC | Five Qwen2.5 open models from 0.5B to 32B, plus one mixture-of-experts model |
| Not done yet | Does not yet match a standard model at equal compute | Nobody outside the project has reproduced a result; no customer yet |

Notes: How they fit, in my words: "We are going to reshape the future of computing no matter what, and we are using this ... product to get the capital for it." Alpha is the part of the research closest to a product.

## Slide 4: Project Hail Mary: building models from scratch

We are building language models from scratch, aimed at learning far more from far less data and memory.

- My own training stack, written from scratch in Rust and CUDA, on one GPU in my home PC.
- The research has run since January 2026; the current English model has trained since 18 Nov 2026.
- By 26 Nov the English model had 37.6 hours of training on the one card.
- A results page of 66 separate lines of work, each with the word its own test printed. A void result is shown as VOID.
- A ledger of 704 ideas. Since 20 Nov, 54 have been put through a test and 28 more are unsure. Tested means tested, not that the idea worked.

Notes: I keep how it works private for now. This slide and the next say what it does and what it has shown.

## Slide 5: Project Hail Mary: early results

- My own training stack, written from scratch in Rust and CUDA, has run about 1,050 clean GPU jobs on one home GPU since 19 Nov.
- A learned forecaster beat its hand-written version in 12 of 27 test cells and was worse in none, on generated test streams.
- In an early preview on one seed, a small model I trained for 58 minutes from nothing got 92 to 97 percent of held-out simple arithmetic questions exactly right, against 0 to 5 percent for the same model trained without arithmetic. On harder forms it got about half right, and it never learned 'which is more'.

It does not yet match a standard model at equal compute. The current model is one week old.

The one equal-time race so far (58 minutes each, from nothing, one card, one run each): a standard model 1.2878 bits per byte on 256 held-out story windows, mine 1.3900, so mine lost by 0.1021 (standard error 0.0026).

Details: https://github.com/luigimifsud/luigimifsud/blob/main/projects/hail-mary.md. Every Hail Mary result, losses included, is in appendix A.

## Slide 6: Project Alpha: the problem, and what I built

AI answers change between runs and machines, so nobody can later prove what an AI said. That matters wherever an AI answer decides money: audits, insurance claims, loans, payouts, evaluation. The EU AI Act asks high-risk systems to keep logs (Article 12).

Since 9 Nov 2026 I've led the research. My dad and I share it, under the name Baseline Technologies.

- The engine: five Qwen2.5 open models from 0.5B to 32B, plus one mixture-of-experts model.
- A pilot server for Windows that answers in the standard chat-completions format and signs every answer. Tested in-house so far.
- A "try it yourself" download. Not yet run on a second machine or sent.
- An audit check that re-reads a logged answer in one pass.

Others publish determinism modes too (SGLang, vLLM and Gensyn). What I build around is the check afterwards: a signed receipt and a one-pass audit.

Notes: In my words: "Like we're building something extremely transparent." A log tells you what an AI said, but it can't re-make the answer, so nobody can check it later. I want the answer itself to be something anyone can re-make and check. The goal I set the project is 100 times more useful AI output from the same bytes of memory moved, with every token the same as an exact reference. That is an aim, not a result, and the earliest milestone toward it, due 18 Nov 2026, was missed.

## Slide 7: Project Alpha: early results

I quote engine results word for word as my project records them, so they read a bit stiff.

Scope today: five Qwen2.5 open models (0.5B to 32B) and one mixture-of-experts model (DeepSeek-V2-Lite), a 512-token window, and a pilot package for Windows only.

- Twelve devices (Windows desktops and laptops, AMD and Intel; Linux cloud servers, AMD EPYC and Intel; two NVIDIA H100 GPUs) gave bit-identical output on every block they shared: 29.8 million rows confirmed on at least two devices, 1.7 million on all twelve; one small open model.
- An NVIDIA RTX 5090 reproduced our CPU engine's output bit for bit on all 106,336 test rows we compared against AMD processors; one small open model.
- A one-pass re-check of a logged answer names the first token that changed. In our tests 40 of 40 honest answers passed with no false alarm, and 40 of 40 altered answers were caught at the exact token, down to a one-bit change.

The re-check works on answers made by this engine, or by one that gives the same bits. Nobody outside the project has reproduced these yet.

Details: https://github.com/luigimifsud/luigimifsud/blob/main/projects/exact-ai.md. Every engine result I can quote, with its limits, is in appendix B.

## Slide 8: How to check this

You can check today: the clinic Jarvis serves is real, and you can message it on WhatsApp from its website, apexdentalmalta.com, and watch Jarvis answer. On a call I can open the log or result file behind a number, with code, design and patient data off screen. Once the portfolio repo is public, its history dates every write-up.

Not checkable yet: nobody outside my projects has reproduced a result. The "try it yourself" download has not been run on a second machine or sent. Hail Mary's design is private and its results come from my own runs. Jarvis's usage numbers come from its own logs. My repos are private.

Not done yet, and what would change that:
- run the "try it yourself" download on a second machine, then send it to people outside the project and publish what they got;
- a short demo video: an answer, its signed receipt, one changed word, and the re-check run on the changed answer;
- a public "check a receipt yourself" page with sample signed answers and the public key, not published yet;
- hashes of Hail Mary's locked pass-rule files and result files, with the design kept private, not published yet.

Check: https://github.com/luigimifsud/luigimifsud/blob/main/VERIFY.md

## Slide 9: Before these two: research that led here

- **Mark One** (20 Apr to Sep 2026; 1,944 commits across the platform and the models): my own small language models, 40M to 295M parameters, trained at home. On 192 held-out code windows cleaned of overlap with the training data, the 40M model scored 1.3615 bits per byte, against 2.8362 for brotli -q 11, the strongest of 9 standard compressors scored on the same windows: 2.08 times smaller (95% confidence interval 2.016 to 2.159). Standard compressors start cold on short windows, so this shows the model learned code, not that it is a better general-purpose compressor.
- **Mark One in Maltese:** 1.2733 bits per byte over 512 windows (95 percent interval 1.2305 to 1.3161), against 3.8010 for the general model on the same Maltese text.
- **Mark One on code, two separate results, not a before and after:** an early 40 million parameter model got 0 of 200 exact matches on completions of real Python test files (26 Jul); my 295 million parameter model solved 164 of 200 small generated Python tasks with 8 tries each, 150 with one greedy try (an earlier model of the same size: 120 and 107). The suite was frozen on 1 Aug and judged by running each program; it is not a public benchmark, and no rival was run on it.
- **The earlier learning models, QMK and AMK:** over about seven weeks, the models I built under strict rules never got past reading back what they had been fed. I changed the rules on 17 Nov, and the learning work went on in Hail Mary.
- **A compression demonstrator**, packaged so a stranger could re-run it, with its losses stated beside its win. Not published yet, so nobody can run it today.
- **LIGHTGAP** (25 Oct to 2 Nov 2026; 440 commits): my own text compressor, written from scratch in Rust. On a development set of 3,653,983 characters of English Wikipedia (enwik8, mapped to 26 letters and the space), it needed 1.152914 bits per character and decoded back exactly, against 1.7694 for 7-Zip PPMd, the best standard compressor on my PC. That set helped choose the settings, so it is not a test; the sealed test, with its pass line written down in advance, had not run as of 2 Nov 2026. Going under 1.3 bits per character is not new: it is a compressor I built from nothing, not a record.
- **Computing without binary:** tests in simulation, mostly negative, written down as negative. No chip has been made.

Details: https://github.com/luigimifsud/luigimifsud/blob/main/projects/mark-one.md, https://github.com/luigimifsud/luigimifsud/blob/main/projects/compression-demo.md, https://github.com/luigimifsud/luigimifsud/blob/main/projects/lightgap.md and https://github.com/luigimifsud/luigimifsud/blob/main/projects/computing-research.md

Notes: Mark One also lost, and those losses are on the dead ends slide. An earlier result from my own model research in August is in appendix B, with the engine results, because it sits in the same record.

## Slide 10: Three more builds

- **QMK World** (late Sep to 7 Oct 2026): an Earth-sized voxel simulator, with Malta rebuilt 1:1: all 112,147 buildings of Malta and Gozo at their measured heights, from the national one-metre height survey (about 20 to 30 parts in deep shadow are wrongly dropped, an estimate). On an exam of 42 physics items on 27 Sep, the world agreed with the real Earth on 10, was wrong on 20 and could not tell on 12: a failing grade, said as one.
- **TETRA mesh** (11 to 14 Sep 2026): an overlay on top of the normal internet, with four layers of encryption, for distributed training. 564 tests, 563 passing, from its status file; never audited outside my projects.
- **Jarvis** (since at least 13 Sep 2026): a WhatsApp booking assistant for Apex Dental, my dad's two clinics in Birkirkara, Malta, live with real patients. From the bot's own logs, not an audit, 12 to 18 Oct 2026: 388 chats with 269 phone numbers; 54 payment holds, 22 of which became bookings.

Details: https://github.com/luigimifsud/luigimifsud/blob/main/projects/qmk-world.md, https://github.com/luigimifsud/luigimifsud/blob/main/projects/tetra.md and https://github.com/luigimifsud/luigimifsud/blob/main/projects/jarvis.md

Notes: TETRA's test count is what its own status file recorded, not re-run. QMK World is paused, and TETRA has been dormant since September 2026. All Jarvis's users are the clinic's patients and staff, and there is no software revenue: the booking fees are clinic income. No patient chat or screenshot is ever shown.

## Slide 11: Dead ends and losses on record

> "A named wall is a result, not a failure."

- **Project Hail Mary:** it lost its one equal-time race, scored 0.000 on name-lookup questions in that race, and is behind my own earlier model of the same size on every story window. Its training runs on the card are not repeatable yet.
- **PhotoLocator** (June 2026): a tool to guess where a photo was taken. An early benchmark claim was later found false, and I stopped it as a dead end.
- **Computing without binary:** a ternary cell lost on transistors per bit, stochastic computing was closed as a negative, and a bit-slicing idea died to both of its controls.
- **An AlphaFold side line:** none of my one-day tests of new ideas passed.
- **Mark One:** an early "beats gzip" claim was retracted in writing; a snapshot of my 295M model lost to Qwen2.5-Coder-7B on 118 of 128 windows of general held-out text; Mark One 295M scored 0.788 bits per byte against 0.593 for Qwen2.5-Coder-0.5B on 256 fixed windows of 2,048 bytes of held-out code, behind by 0.195, winning on 18 of 256 windows (Qwen probably saw similar code, and the holdout is not proven clean); four small pre-registered probes ended KILL.
- **Compressors:** several of my home-built compressors lost to standard tools, 7-Zip PPMd and lzma. QMK-2 lost to 7-Zip PPMd: 1.606522 bits per byte against 1.530961 on a test slice of 1,315,021 bytes.
- **QMK and AMK:** my own written verdict on QMK 3, 2 Oct: real but modest, not yet a capability, ten goals at 0 of 10. QMK-3 added nothing to Jarvis's reader on the meaning label (0.721 with it and 0.721 without, on 86 held-out chat replies).
- **A retraction:** a detection rule of mine, tested against 3,600 matched control runs, had a real false-alarm rate of 0.073611 where it had reported 0.006780, about 10.9 times higher.
- **Project Alpha:** the earliest milestone toward the goal, due 18 Nov 2026, was missed, and one 7B timing did not show a result.

Details: https://github.com/luigimifsud/luigimifsud/blob/main/projects/dead-ends.md

## Slide 12: How I work

- Written rules.
- Pass and fail lines written before each test. In Hail Mary each pass rule is locked with a hash before any result is read; a change is a dated, hashed amendment, never an edit.
- In Hail Mary, tests are checked by planting deliberate errors: three of them caught 15 of 15, 9 of 9 and 26 of 26, and one test reader that caught 84 of 89 was marked not ready.
- A separate check inside my project re-counts a result before I quote it. It is part of my project, so it is not an outside check.
- A result that breaks its own rule is void. A different forecaster race, not the 12 of 27 result, looked good, but one check file's last line broke the locked rule, so the whole race is void and its numbers are never quoted.
- Losses stay on record.

> "Plan, work, research. Plan, work, research. Plan, ideate, find out why it's not working."

Notes: Another line of mine: "If something seems impossible, usually what I used to do was attack it still. ... But the idea is creating multiple variants and testing out new things." I build with AI coding tools; I set the rules, design the tests and decide what counts as done. When a result says "we" or "our", it means the project. I'm applying on my own.

## Slide 13: Not yet

- Nobody outside my projects has reproduced a result.
- No customer and no money raised. No company is incorporated.
- About 70 outreach emails so far, and one investor conversation.
- All real users so far come through Apex Dental.
- Hail Mary's current model is one week old and does not yet match a standard model at equal compute.

## Slide 14: The next two years

The ask: the Thiel Fellowship, $250,000 over two years.

Proposed use: outside reproduction of the main results on machines I don't own, a public benchmark run with pass and fail lines published in advance, a paying pilot where an AI answer decides money, and compute for the engine and for Hail Mary.

Contact: luigi28mifsud@gmail.com. LinkedIn: https://www.linkedin.com/in/luigi-mifsud-a65739293

Notes: This is a proposed plan, not a budget.

# Appendix A: Project Hail Mary in full

Each result says what it was measured on and what it does not show. Lower bits per byte is better. The design stays private.

## Slide A1: The arithmetic result in full

One seed per setup, a preview, not a locked verdict.

- A small model trained for 58 minutes from nothing, with about a tenth of its reading being simple arithmetic, got 92 to 97 percent of 400 held-out near questions exactly right. The questions were sums, differences and next numbers, set in short stories.
- The same model, trained for the same time with no arithmetic, got 0 to 5 percent.
- With one number in a question changed, it gave the old answer 0.2 to 1.6 percent of the time.
- On harder forms (longer sums, and sums told as a story) it got 46 to 54 percent, against chance of 10 and 19 percent.
- It never learned "which is more" (under 2 percent).
- Its English got a little worse.
- The test questions were made on the same PC, and none of them were in the practice set. No other model was tested on them.

## Slide A2: Against a compressor, and a small exact test

On 256 held-out windows of 512 bytes, my 25 million weight model needed 0.8630 bits per byte on stories and 1.2070 on mixed text. An order-12 PPM compressor written in the project, which had counted 170 MB and 400 MB of the training text beforehand, needed 1.0663 and 1.4494. xz, given the training text beforehand, needed 1.4216 and 1.8784. Limits: that PPM is weaker than 7-Zip PPMd, which was not measured here, and its settings were tuned on the same windows.

A small exact test: with 1,985 weights, on 4-byte windows of one corpus (mostly the project's own Python source), scored exactly, my model beat each of four rival models on all 3 seeds, by 4.0, 9.4 and 14.0 percent. The rivals were a Boltzmann machine with 30 hidden units and three pairwise or three-way models of 1,344 to 3,008 weights. A control that destroyed the data's order scored 1.785918. Limits: a small test, on one machine, and not a language-model result. An earlier August claim was narrowed after a check (slide B8).

## Slide A3: Losses

- The equal-time race: a standard model 1.2878 bits per byte on 256 held-out story windows, mine 1.3900, one run each. On name-lookup questions in the same race the standard model got 0.95 to 0.99 and mine 0.000.
- A loss to my own earlier model: on the same 256 story windows the earlier model of the same size needs 0.5804 bits per byte against the new one's 0.8630, so the new one needs about 49 percent more bits (the earlier one about 33 percent fewer), and the earlier one wins on every window. On mixed text it is 0.8678 against 1.2070.
- Training runs on the card are not repeatable yet: the same settings and seed have ended differently on replay. One fix let 4 of the 5 dying runs finish their full hour.
- A different forecaster race, not the 12 of 27 result, looked good, but one check file's last line broke the locked rule, so the whole race is VOID. The earlier notes that treated its numbers as results were corrected, and I never quote them.

## Slide A4: What it writes, and the models before it

The current English model at training step 370,435, picked from a longer sample whose grammar is broken, exactly as printed:

"He was very scared. He did not want to ge up from him in his net."

Before Hail Mary had its name:

- An earlier model of 25 million weights, built in one night (26 to 27 Oct), wrote sentences after about 3 minutes and reached 0.960 bits per byte on unseen simple English after about 10 hours. A picked sample, exactly as printed: "Once upon a time, there was a big spring. In the spring, there was a little fish named Fin. Fin was a very happy fish."
- On 27 Oct I had a Rust trainer built for a text model of about 200 million weights on my own card. I paused it the same day, after about 421 million bytes, at 1.18 bits per byte on held-out science text and still babbling. Earlier in the run it had reached 0.74 on simple stories, a different held-out set. A paused experiment.

Details: https://github.com/luigimifsud/luigimifsud/blob/main/projects/hail-mary.md

# Appendix B: Project Alpha, every engine result I can quote

Word for word as my project records them, with the limits each one carries. My record of results is written in the third person: "Luigi" means me, "this PC" means my home PC, and "the owner's other programs" means other research programs running on the same PC at the time. Nobody outside the project has reproduced any of these yet.

Scope today: five Qwen2.5 open models (0.5B to 32B) and one mixture-of-experts model (DeepSeek-V2-Lite), a 512-token window, and a pilot package for Windows only.

## Slide B1: Exactness across machines

These test whether the same small model gives the same output on different computers, from different makers, on a phone and on GPUs. The twelve-device and RTX 5090 results are on slide 7. Two more:

> In our test, an Arm phone (Google Pixel 10a) produced bit-identical output from our engine on all 2,240 test rows compared with an AMD desktop's reference.

> On Microsoft Azure, an Intel server, two AMD EPYC server types and two NVIDIA H100 GPUs all produced output bit-identical to our AMD desktop's on every row compared, up to 29.8 million rows per machine; one small open model.

## Slide B2: Large models

These run bigger real open models on one PC and compare the CPU's different instruction paths against each other.

> On Qwen2.5-7B-Instruct (7 billion parameters), our exact engine gave bit-identical output on its AVX-512, AVX2 and portable code paths on all 256 rows of an independent test window, on one PC; the engine is the same file used for our smaller models.

(The test window was picked by a separate testing step inside my project, not by anyone outside it.)

> Qwen2.5-14B-Instruct, an open 14-billion-parameter model, runs on our exact engine on this PC: four different CPU instruction paths give bit-identical outputs on every test row we ran (6,336 rows, 1,024 on the two slowest paths), re-checked independently, and its text-prediction quality is within 0.08 % of the same model in full 32-bit precision (the 95 % interval includes zero).

(Re-checked by a separate testing step inside my project, not by anyone outside it.)

> Qwen2.5-32B-Instruct, an open 32-billion-parameter model, runs on our exact engine on this PC: four different CPU instruction paths give bit-identical outputs on every test row run (6,336 rows, 1,024 on the two slowest paths), re-checked independently, and its text-prediction quality is within 0.02 % of the same model in full 32-bit precision on 20 text windows (the 95 % interval, -0.08 % to +0.11 %, includes zero).

(Re-checked by a separate testing step inside my project, not by anyone outside it.)

> On a real open mixture-of-experts model (DeepSeek-V2-Lite), one whole expert layer, its router choosing 6 of 64 experts plus 2 shared experts, computed bit-identically on four different CPU instruction paths, at one and four threads, batched or one token at a time, on 514 real inputs, re-checked independently on the final engine build; a planted tie was broken the same way everywhere, and a one-byte change inside one expert changed exactly the 43 tokens routed to it and nothing else.

(Re-checked by a separate testing step inside my project, not by anyone outside it.)

> We ran a real open mixture-of-experts model, DeepSeek-V2-Lite (27 layers, 64 routed experts per layer), end to end on our exact engine on one PC: four different CPU instruction paths, two thread counts and token-by-token decoding gave bit-identical outputs and identical expert choices on every one of 37,008 output rows, re-checked independently; and its text-prediction quality on 20 text windows is within 1 percent of the same model in full 32-bit precision (+0.14 %, 95 % interval -0.04 % to +0.30 %). Beside it, as pre-registered: an earlier first-layer fidelity check missed its 1 % target at 1.02 %, and 81.7 % of the expert choices match the full-precision model's.

(Re-checked by a separate testing step inside my project, not by anyone outside it.)

## Slide B3: The pilot

The pilot is what a customer would install. These are two separate results: one for the earlier pilot, one for the current package. No customer has installed it yet, and both were measured in-house.

The earlier pilot:

> Our pilot, Exact Server, installs from one zip on a Windows PC, answers in the standard chat-completions form on that PC only, and attaches a signed receipt to every answer; the same question gave the same answer and the same receipt twice, a one-command checker accepted every genuine receipt and rejected every forged one we tried, and an audit pointed to the exact token we had changed.

The current package:

> Our pilot, Exact Server (Windows package v3.1), installs from one zip on a Windows PC and answers in the standard chat-completions form only on that PC's own local address, refusing requests from a web page or under a foreign host name; it attaches a signed receipt to every answer. On a fresh install, the same questions gave the same answers as on our earlier pilot install and a repeated question gave the same answer again, a one-command checker accepted every genuine receipt and rejected every forged one we tried, an audit pointed to the exact token we had changed, all 6,336 fixed test rows matched their reference, and a damaged or missing model file made it refuse to start, naming the file. It ships one small open model (Qwen2.5-Coder-0.5B-Instruct).

## Slide B4: Exactness at very large sizes

These use very large test setups with seed-generated weights, not trained models. They check that output stays exact at that size, and they say nothing about any model's quality or speed. I never describe them as models.

> We pushed one token through a 5-trillion-parameter test network with seed-generated weights (not a trained model) on one RTX 5090, and two CPU implementations matched the GPU bit for bit on every value we compared.

> Two cloud H100 GPUs re-ran our 5-trillion-parameter test network with seed-generated weights (not a trained model) and matched our RTX 5090 on all 584 compared digests.

> We pushed one token through a 20-trillion-parameter test network with seed-generated weights (not a trained model) on one RTX 5090, and two CPU implementations matched the GPU bit for bit on every value we compared.

> Two cloud H100 GPUs ran an endless test network with seed-generated weights (not a trained model) for 6,090 layers, about 104.6 trillion weights, and every layer's output was bit-identical on both machines.

> This PC's RTX 5090 computed bit for bit the same result, layer by layer, as two H100 GPUs in the cloud on 6,090 layers (104.6 trillion seed-generated parameters) of an endless test network with seed-generated weights (not a trained model), and as one of those H100s on all 6,357 layers (109.2 trillion).

## Slide B5: Speed

These are timed runs on one PC. Each sentence names what was compared and the setting it ran in. Nobody outside the project has timed the engine.

> On one NVIDIA RTX 5090, our exact GPU path produced output bit-identical to an exact reference on all 100 held-out test prompts (300 of 300 timed runs), and took 1.26 times the wall time of plain bf16 on the same model and GPU (a 26 % overhead; median of three alternating repeats on a busy PC). Plain bf16 itself differed from the exact output on 44 of the 100 prompts. One small open model (0.5 billion parameters), 128-token answers.

Beside it, word for word from the same entry:

> published determinism modes report overheads of 24 to 55 % (SGLang), 2.4 times (vLLM's bitwise mode for RL) and 58 to 218 % (Gensyn's cross-hardware mode). Those figures are on other models, hardware and workloads; this is not a like-for-like test.

Separately, a timed comparison on the CPU:

> On one PC, in a quiet window beside the owner's other programs, our exact CPU engine produced about 2.19 times the tokens per second of llama.cpp (as built into Ollama, build 740af7a7, a different build from our earlier comparisons) on the same small model (Qwen2.5-Coder-0.5B-Instruct; llama.cpp with Q8_0 weights and its n-gram speculation; 8 threads each), on 57 held-out prompts, the median of three alternating repeats (2.14 to 2.20), with every one of our 342 outputs bit-identical to the exact reference. It was our fourth timed comparison on the same 57 prompts: a later run with a changed loader and drafter rule, the rule chosen on separate development prompts by counts, not by a measured speed; the target set in advance was 2 times.

## Slide B6: Other tools

These are tools around the engine: a converter that brings open Qwen2.5 models into it, and the re-check for logged answers on slide 7, which works on answers made by our engine, or by one that gives the same bits. The converter:

> One command converts an open Qwen2.5 model into our exact engine's format and checks it: the 7-billion-parameter model came out byte-identical to the format we built by hand, and the 0.5-billion one identical array by array; malformed inputs we tried were refused by name, including weights holding invalid numbers and weights the model's settings do not account for.

## Slide B7: A timed comparison on a 32B model, one session

> In our first timed comparison of the 32B, on one PC in a quiet window beside the owner's other programs, our exact CPU engine produced about 2.09 times the tokens per second of llama.cpp (as built into Ollama, build 740af7a7) on Qwen2.5-32B-Instruct, the general model (llama.cpp with matched-precision Q8_0 weights of the same model made on this PC, and its n-gram speculation; 8 threads each), on 19 held-out prompts, a third of the held-out set only, pooled over two alternating repeats (2.10 and 2.09), with every one of our 76 outputs identical, token for token, to the reference made in advance. Our engine's rule and library were those frozen on the 0.5B model, not re-tuned for this one, with a loader written for this model; the bar set in advance was 2 times, for the pooled figure and for each repeat.

Scope of this result: one session, on one desktop PC's CPU, with one model and 19 prompts; it covers no other machine, GPU, model, prompt set or llama.cpp setting.

Notes: This run covers 19 of the 57 held-out prompts. A run on all 57 is still to do.

## Slide B8: Earlier research in the same record

This one comes from my own model research in August 2026, before Project Alpha. It follows the same rules as the rest.

> In August, a variant of Luigi's own model design beat the standard same-size pairwise model (a Boltzmann-family model with no hidden units) on held-out data in every paired trial on record: by 10 to 14 percent in the longer runs and by about 5 to 6 percent in shorter eight-seed runs, though a generic control also beat that model by about a third as much. It is small-scale research, not a compressor, and not yet independently re-run.

This is the August claim in its narrowed wording, after a check; slide A2 mentions the same narrowing.

Details for all of appendix B: https://github.com/luigimifsud/luigimifsud/blob/main/projects/exact-ai.md
