# Glossary

As of 26 Nov 2026.

Plain explanations of the terms this portfolio uses, for readers who do not work in AI or software. The examples come from the portfolio's own pages, with the limits that go with them. This page explains words, not designs: it says nothing about how the exact AI engine or my learning models are built.

Where an entry quotes a result about the exact AI engine, the quote is word for word from my project's claims register, and this scope line goes with it:

Scope today: five Qwen2.5 open models (0.5B to 32B) and one mixture-of-experts model (DeepSeek-V2-Lite), a 512-token window, and a pilot package for Windows only.

## A

**Adapter.** A small add-on trained on top of an open model to teach it one job, without retraining the whole model. Jarvis's local reader is three adapters on open models that read each patient message for what it means and how the patient feels. On 147 clinic phone messages, version 3 scored 0.844 on meaning and 0.946 on feeling, and caught 0.829 of the messages that were not calm, counted as agreement with a larger hosted model's labels (aggregate figures from its own score files, not re-run since).

**AlphaFold 2.** A well-known published model that predicts the 3D shape of a protein from its sequence. A chain is one protein strand. Inside Project Alpha, a standard AlphaFold 2 baseline ran bit-identical from run to run on the chains I tested, and none of my one-day tests of new ideas against it passed.

**Audit.** A careful check of a system by someone looking for problems in it. A September audit of QMK-1, one of my earlier learning models, found 1,263 confirmed findings in its code, grouped into 27 fixes, and found that the copy running was 43 hours older than the code. In Project Alpha, the one-pass audit is the check of a logged answer described under One-pass re-check.

## B

**Baseline.** A simple or standard method used as a point of comparison, so a result has something to be measured against. In Project Alpha's AlphaFold side line, a standard AlphaFold 2 baseline was what new ideas were tested against, and none of those one-day tests passed. Baseline is also a name I have used for my own work, such as the research I did under the name Baseline before Project Alpha; there it is just a name.

**Benchmark.** A fixed test used to compare systems on the same task. A public benchmark is one that other people use too, so results can be compared across groups. My Mark One coding suite is my own, not a public benchmark, and no rival was run on it.

**Beside-item.** A sentence that the claims register requires to be printed next to a result, so the result is never read without it. On the exact AI page, the GPU timing result is followed by the sentence the register requires beside it.

**Binary.** Computing with two states, on and off, which is how the computers we use work today. My tests of computing without binary all ran in simulation, most came out negative, and I wrote them down as negative. No chip has been made.

**Bit and byte.** A bit is the smallest piece of information a computer stores, a yes or a no. A byte is a small group of bits, enough for one letter of plain English text. File sizes and test windows are counted in bytes.

**Bit-identical output.** Two outputs are bit-identical when every bit is the same, so there is no difference at all, however small. "Bit for bit", "byte-identical" and "token for token" mean much the same, counted in bytes or in tokens. In my project's words:

> An NVIDIA RTX 5090 reproduced our CPU engine's output bit for bit on all 106,336 test rows we compared against AMD processors; one small open model.

**Bit-slicing.** Handling a number as separate slices of its bits, worked on side by side. A bit-slicing idea of mine, tested in simulation, died to both of its controls.

**Bits per byte.** A score for how well a model or a compressor predicts text: the number of bits it needs, on average, to store each byte. Lower is better. On 256 story windows, my earlier model of the same size needs 0.5804 bits per byte against the new Hail Mary model's 0.8630, so the new one is still behind, and the earlier one wins on every window.

**Block.** As the claims register uses the word, a group of test rows. The devices did not all run the same blocks, so the twelve-device result compares the blocks that two or more devices had in common:

> Twelve devices (Windows desktops and laptops, AMD and Intel; Linux cloud servers, AMD EPYC and Intel; two NVIDIA H100 GPUs) gave bit-identical output on every block they shared: 29.8 million rows confirmed on at least two devices, 1.7 million on all twelve; one small open model.

**Boltzmann machine, pairwise and three-way models.** Standard kinds of small model from earlier AI research, used on my pages as rivals. A pairwise model scores data by how pairs of its parts go together, a three-way model by how groups of three go together, and a Boltzmann machine can add hidden units, extra parts that pick up patterns not seen directly in the data. In Hail Mary's small exact test the rivals were a Boltzmann machine with 30 hidden units and three pairwise or three-way models of 1,344 to 3,008 weights.

**brotli.** A compressor made by Google and much used on the web; -q 11 is its strongest setting. On 192 held-out code windows cleaned of overlap with the training data, my 40M Mark One model scored 1.3615 bits per byte against 2.8362 for brotli -q 11, the strongest of 9 standard compressors scored on the same windows. Standard compressors start cold on short windows, so this shows the model learned code, not that it is a better general-purpose compressor.

## C

**CC BY 4.0.** A public licence that lets anyone reuse data as long as they credit the source. The national one-metre height survey that QMK World's Malta is built from is published under it, so its credit line has to go with any picture made from it.

**Chance.** The score you would expect from guessing. On harder arithmetic forms (longer sums, and sums told as a story) my Hail Mary model got 46 to 54 percent, against chance of 10 and 19 percent; that is one seed per setup, a preview.

**Chat-completions format.** A common standard way for a program to send a conversation to an AI server and get the reply back. Project Alpha's pilot server for Windows answers in this format.

**Claims register.** The record where my project writes down each result about the exact AI engine, in fixed wording, with the limits that belong to it. I quote those results word for word, so they read a bit stiff; the register is in the third person, and "we" and "our" mean the project. Each row of the register names its result file and the testing step that marked it.

**Cloud server.** A computer in a data centre, rented and used over the internet. Some exact AI results were measured on cloud machines, as their register sentences say. Microsoft Azure, named in one of them, is Microsoft's cloud.

**Commit.** A saved step in a project's history, recorded by git, the most common tool for tracking changes to code. Jarvis had 3,078 commits, counted on 26 Nov 2026. Commits on Jarvis show "Jonathan Mifsud" because I committed under my dad's git identity, the name and email git writes on each commit. I build with AI coding tools, and the commit history shows that too.

**Compressor.** A program that makes a file smaller and can give back the exact original. How small it gets text, measured in bits per byte, shows how well it predicts that text, which is why I compare language models with compressors. The ones named on these pages are gzip, brotli, lzma, xz, 7-Zip PPMd and PPM, each explained on this page, and several of my home-built compressors lost to 7-Zip PPMd and lzma.

**Confidence interval.** A range that shows how sure a measured number is; with a 95 percent interval, the true value is very likely inside it. Mark One's Maltese model scored 1.2733 bits per byte over 512 windows (95 percent interval 1.2305 to 1.3161), against 3.8010 for the general model on the same Maltese text, recorded in its result files and not re-run since; about half of that held-out set is parliament, gazette, court and law text, so it is not a score for Maltese prose. When an interval for a difference includes zero, the measurement cannot tell that difference apart from none at all.

**Control.** A comparison run with the key ingredient taken out or scrambled, to check that a result really comes from that ingredient. In Hail Mary's arithmetic test the control was the same model trained for the same time with no arithmetic, which got 0 to 5 percent (one seed per setup, a preview). Matched control runs are runs where there is nothing to find, used to measure how often a detector raises a false alarm.

**Corpus.** A body of text collected for training or testing. Hail Mary's small exact test used 4-byte windows of one corpus, mostly the project's own Python source.

**CPU.** The main processor of a computer, made by companies such as AMD and Intel. Several exact AI results compare the engine's output across CPUs from different makers.

## D

**Dated amendment.** When a locked rule has to change, the change is written as a new amendment, dated and locked with its own hash, and the original rule stays as it was. In Hail Mary a change is a dated, hashed amendment, never an edit. The record then shows what the rule was when a test ran, and what changed after.

**DeepSeek-V2-Lite.** An open mixture-of-experts model published by DeepSeek. It is the mixture-of-experts model in the exact AI scope line.

**Determinism mode.** A setting in some AI software that makes the same request give the same answer each time. Others publish determinism modes too (SGLang, vLLM and Gensyn). What I build around is the check afterwards: a signed receipt and a one-pass audit.

**Distributed training.** Training one model on several machines at once, with the work shared between them. I built TETRA mesh so training jobs could one day be spread over several machines without trusting the network in between.

## E

**Encryption.** Scrambling data so that it can be read with the right key and not without it. TETRA mesh encrypts the traffic between machines, and it has not been reviewed by anyone outside my projects.

**Engine.** In Project Alpha, the program that runs open language models so their answers can be re-made bit for bit on other machines and checked later. This page says nothing about how it works.

**Equal compute or equal time.** Equal compute means two models get the same amount of computer work; equal time means the same minutes on the same card. The one equal-time race so far gave each model 58 minutes from nothing on one card, one run each: a standard model scored 1.2878 bits per byte on 256 held-out story windows and mine 1.3900, so mine lost by 0.1021 (standard error 0.0026). Hail Mary does not yet match a standard model at equal compute. It is one week old.

**EU AI Act.** The European Union's law on AI. It asks high-risk systems to keep logs (Article 12), which is part of why a record of what an AI said matters.

**Evaluation set.** A fixed set of test cases used to measure whether a change makes a system better or worse. On Jarvis's evaluation set of 12 Nov 2026, 95 of 114 hand-built cases passed (83 percent); on 272 machine-picked moments where a chat went wrong, 61 passed (22 percent); and 217 of 477 passed overall (45 percent), recorded in its own file. The 363 machine-picked cases have not been checked by a person yet.

**Exact AI.** The name I use for AI whose answers can be re-made bit for bit on other machines and checked later. It is what Project Alpha works on, and nobody outside the project has reproduced its results yet.

**Exact match.** Output that equals the expected text exactly, with no credit for being close. My earliest 40.6 million parameter model got 0 of 200 exact matches on completions of real Python test files (26 Jul), where a completion is the model carrying on a file from where it stops.

**Exact reference.** An output made in advance and kept as the answer that later runs must match exactly. Several register sentences compare the engine's output with an exact reference.

## F

**Fails closed.** A system fails closed when, if something goes wrong, it falls back to a safe fixed behaviour instead of guessing. Jarvis's companion gateway on the clinic's own phone line does this: if Jarvis cannot answer, the patient gets one fixed reply and staff are flagged.

**False alarm.** When a check flags a problem that is not there; the false-alarm rate is how often that happens. A detection rule of mine, tested against 3,600 matched control runs, had a real false-alarm rate of 0.073611 where it had reported 0.006780, about 10.9 times higher, and I retracted it.

**Forecaster.** A program that makes predictions; a learned one is trained from data, and a hand-written one follows fixed rules written into its code. In Hail Mary: "A learned forecaster beat its hand-written version in 12 of 27 test cells and was worse in none, on generated test streams." A test cell is one combination of the settings a test varies, and generated test streams are test data made by a program, so the result says nothing yet about real data.

**From scratch and from nothing.** From scratch means built new, rather than on top of someone else's code or model. A model trained from nothing starts blank and learns everything it knows in that run, as in Hail Mary's 58-minute runs.

**Frozen.** Fixed on a date and not changed afterwards, so results stay comparable. My Mark One coding suite was frozen on 1 Aug 2026.

## G

**GPU.** A graphics processing unit: a chip built to do many small calculations at once, which is why it is used to train and run AI models. "The card" means the GPU; mine is one NVIDIA RTX 5090 (32 GB) in my home PC, and earlier training also used a second PC with an RTX 5070.

**Greedy try.** One attempt where the model always picks its most likely next token. My 295 million parameter model solved 164 of 200 small generated Python tasks with 8 tries each, and 150 with one greedy try (an earlier model of the same size: 120 and 107). The suite was frozen on 1 Aug and judged by running each program; it is not a public benchmark, and no rival was run on it.

**gzip.** An old and very common compressor, used across the web and in many file tools. Early in Mark One I had a "beats gzip" claim; it did not hold up, and I retracted it in writing.

## H

**Hardware names.** AMD and Intel make CPUs, and NVIDIA makes GPUs. The RTX 5090 and RTX 5070 are NVIDIA cards sold for home PCs, the H100 is NVIDIA's GPU for data centres, AMD EPYC is AMD's line of server CPUs, and Arm is the chip design inside most phones.

**Hash and hash lock.** A hash is a short fingerprint worked out from a file; change one character of the file and the fingerprint comes out completely different. A digest is another word for a hash. Locking a rule with a hash means recording that fingerprint before any result is read, so a later edit to the rule would show. In Hail Mary each pass rule is locked with a hash before any result is read.

**Held-out.** Data kept apart from training, so a model is tested on text it has not seen. Mark One's code result was measured on 192 held-out code windows cleaned of overlap with the training data, because overlap would make the score look better than it is. In my 295M comparison with Qwen, the holdout is not proven clean, since Qwen probably saw similar code.

**Hosted model.** A model that runs on someone else's servers and is reached over the internet. Jarvis's local reader runs in shadow mode next to a larger hosted model, and becomes the main reader at 95 percent agreement with it on meaning.

## I

**Idea ledger.** A running list of ideas to test. Hail Mary's has 704 ideas; since 20 Nov, 54 have been put through a test and 28 more are unsure. Tested means tested, not that the idea worked.

**In-house.** Inside my own project, not by anyone outside it. The Windows pilot server has been tested in-house so far.

**Instruction paths.** Modern CPUs offer extra sets of instructions for doing many sums at once; AVX-512 and AVX2 are two of them, and a portable path uses neither. Programs often take a different path on a different chip, which is one reason AI output can differ between machines. Several register sentences report tests of the engine's output on different instruction paths of one PC.

## K

**KILL.** The verdict word for a pre-registered test whose result lands on the line, written down in advance, for stopping the idea. A probe is a small, quick test of one idea. Two pre-registered probes in Mark One ended KILL, and they stay on record as losses.

## L

**Language model.** A program that has learned the patterns of a language from a large amount of text, so it can predict and write text. The Qwen2.5 models and my own Mark One and Hail Mary models are language models.

**Line of work.** One separate question in Hail Mary, with its own written rules, tests and verdict. Hail Mary's results page lists 66 separate lines of work, each with the word its own test printed. In the 74 work folders counted so far (of 75) there are 99 rule files, 242 check files, 46 verdict files and 25 re-derivation files, counted by file name; a re-derivation works a result out a second time.

**llama.cpp and Ollama.** llama.cpp is a widely used open program for running language models on ordinary computers, and Ollama is an app with llama.cpp built in. The exact AI page has timed comparisons against llama.cpp, each sentence naming what was compared and the setting it ran in.

**Local address.** An address a computer uses to reach itself, so a program listening there can be reached from programs on the same PC and not from other machines. The register sentence for the current pilot package, on the exact AI page, uses this term.

**Logged answer.** An answer saved in a log at the time it was given, so it can be looked at again later. A log tells you what was said; the exact AI work is about making the answer itself something anyone can re-make and check.

**Lookup table.** A plain store of what has been seen, which answers by looking it up rather than by having learned anything general. Over about seven weeks, my earlier QMK and AMK models never got past reading back what they had been fed, and the best did no better than a plain lookup table on text it had seen. On 17 Nov I changed the rules, and my learning work went on in Project Hail Mary.

**lzma and xz.** lzma is a strong general-purpose compression method, and -9 is its strongest preset; xz is a common file tool that uses it. Several of my home-built compressors lost to standard tools, lzma among them. In Hail Mary's comparison with a compressor, xz was given the training text beforehand, so it had read the same text the model learned from.

## M

**Memory and data units.** MB (megabytes), GB (gigabytes) and TB (terabytes) are units of data, each much larger than the one before, and MiB is a close cousin of MB counted the way computers prefer. Peak memory is the most memory a program uses at any one moment. My home PC has 93.6 GB of memory, and my compression demonstrator's peak memory is 1,751 MiB against 16 MiB, which is one of its limits.

**Mixture-of-experts.** A kind of language model made of many smaller parts called experts. For each token, a part called the router picks a few experts to do the work, so just part of the model runs each time. DeepSeek-V2-Lite, in the exact AI scope line, is one.

**Multi-agent platform.** Software in which several AI programs, called agents, each take part of a task and pass work between them. Mark One included one that ran on my own machines.

## N

**Narrowed claim.** A claim cut back after a check to what the evidence supports, without taking it back entirely. An earlier August claim of mine was narrowed this way, and the exact AI page carries its narrowed wording.

**Near questions.** In Hail Mary's arithmetic test, the simpler group of held-out questions, as against the harder forms: sums, differences and next numbers, set in short stories. A small model trained for 58 minutes from nothing, with about a tenth of its reading being simple arithmetic, got 92 to 97 percent of 400 held-out near questions exactly right; one seed per setup, a preview. It never learned "which is more" (under 2 percent).

**Number formats.** A model is a very large set of numbers, and they can be stored at different lengths. Full 32-bit precision keeps them at full length and is the usual yardstick for how well a model predicts text; bf16 is a common shorter format that GPUs often run models in; a 4-bit build is much shorter still, saving memory at some cost in quality. Some register sentences compare the engine's text-prediction quality with the same model at full 32-bit precision, one compares its timing with plain bf16, and Mark One was compared with a 4-bit build of Qwen2.5-Coder-7B.

## O

**One-metre height survey.** Malta's national survey of land and building heights, from 2012 and 2018, published under CC BY 4.0. QMK World draws all 112,147 buildings of Malta and Gozo at their measured heights from it, as of 2 Oct 2026, apart from about 20 to 30 real parts in deep shadow that are wrongly dropped (an estimate).

**One-pass re-check.** The audit check in Project Alpha: it re-reads a logged answer in one pass, and it works on answers made by the engine, or by one that gives the same bits. It is also called the one-pass audit. In my project's words:

> A one-pass re-check of a logged answer names the first token that changed. In our tests 40 of 40 honest answers passed with no false alarm, and 40 of 40 altered answers were caught at the exact token, down to a one-bit change.

**Open model.** A model whose weights are published, so anyone can download it and run it on their own machine. The exact AI engine runs five Qwen2.5 open models from 0.5B to 32B, plus one mixture-of-experts model.

**OpenStreetMap.** A free map of the world, made and kept up by volunteers. QMK World's New York, 377,822 buildings, comes from it; they were drawn, not checked one by one.

**Overlay network.** A private network that runs on top of the ordinary internet. TETRA mesh is one, built for distributed training; it is a dormant prototype, never audited outside my projects.

## P

**Parameter or weight.** The numbers inside a model that training adjusts; a model's size is counted in them, with M for million and B for billion. Mark One's models went from 40M to 295M parameters, the Hail Mary model in the compressor comparison has 25 million weights, and the engine runs Qwen2.5 models from 0.5B to 32B. In Jarvis's reader, "weight" also means how much the reader leans on one input: on the meaning label, on 86 held-out chat replies, it gave QMK-3 a weight of 0.001 and scored 0.721 with it and 0.721 without.

**Pass and fail lines.** Written down before a test runs: what result counts as a pass and what counts as a fail, so the bar cannot move once the result is in. Jarvis's local reader has a line like this: it becomes the main reader at 95 percent agreement with the hosted model on meaning, and in shadow mode it agreed in 77 percent of 643 replies, so it is not the main reader yet.

**Pilot.** An early version of a product, meant for a customer to install and try. Project Alpha's pilot is a server for Windows that answers in the standard chat-completions format and signs every answer; it has been tested in-house so far, and no customer has installed it yet.

**Planting errors.** Putting deliberate mistakes into test material to see whether the test catches them; a test that misses planted errors cannot be relied on to catch real ones. In Hail Mary, three tests checked this way caught 15 of 15, 9 of 9 and 26 of 26, and one test reader that caught 84 of 89 was marked not ready.

**Plus or minus.** A short way to give a number together with its uncertainty. On legal text held back from building, a model I built on the CPU scored 0.7207 (plus or minus 0.0046) on rebuilding word pairs, against 0.4947 (plus or minus 0.0048) for a word-frequency baseline, which just uses how often each word appears, over 7,503 legal documents. It is not a legal-accuracy score.

**PPM and 7-Zip PPMd.** PPM, short for prediction by partial matching, is a family of compressors that predict each next byte from the bytes just before it, and its order is how many bytes back it looks. 7-Zip is a free archiving program and PPMd is its PPM method, strong on text; QMK-2, one of my earlier learning models, lost to it, 1.606522 bits per byte against 1.530961 on a registered test slice of 1,315,021 bytes. Hail Mary's comparison used an order-12 PPM written in the project, which is weaker than 7-Zip PPMd (not measured there), and its settings were tuned on the same windows.

**Practice-management diary.** The software a clinic keeps its appointments in, where reception sees the bookings. Jarvis reads and writes the clinic's diary, so what it books is what reception sees.

**Pre-registered.** Written down before a test runs: what will be measured and what counts as a pass. A registered test slice is a piece of test data fixed and recorded the same way, before the test. Two pre-registered probes in Mark One ended KILL.

**Preview and locked verdict.** A locked verdict is a result read against a pass rule that was written down and locked with a hash before the result existed. A preview is an earlier look that has not been through that, so it can still change. My Hail Mary arithmetic result is one seed per setup, a preview, not a locked verdict.

**Prompt.** The text given to a language model to answer or carry on. Held-out prompts are kept apart from any tuning, like other held-out data, so a timing or a check on them is fair.

**Python.** A widely used programming language; source code is the readable text of a program. Several of my tests use Python source code, such as Mark One's 200 small generated Python tasks.

## Q

**Qwen2.5.** A family of open language models published by Alibaba's Qwen team, in many sizes. Instruct versions are tuned to follow instructions and chat, and Coder versions are tuned for code. The exact AI engine runs five of them, from 0.5B to 32B, and my Mark One models lost to the Qwen code models they were compared against.

## R

**Red-flag symptoms.** Signs in a patient's message that something may be urgent. Jarvis checks every patient message for them before anything else, in English, with partial cover so far in Italian, Spanish and Maltese.

**Repo.** Short for repository: a project's code together with its full history of commits. My repos are private, and the portfolio's own repo holds write-ups, not code.

**Reproduction.** When someone else runs the same test on their own machines and gets the same result. Nobody outside my projects has reproduced a result yet; outside reproduction of the main results, on machines I don't own, is part of my proposed plan. [How to check what this site says](../VERIFY.md) goes claim by claim.

**Retraction.** Taking a claim back in writing after it turns out wrong, and keeping the record of it. Mark One's early "beats gzip" claim was retracted in writing, and so was the detection rule under False alarm.

**Round trip.** Compressing a file and decompressing it again, to check that exactly the original comes back. A compressor that fails a round trip is broken, however small its output.

**Row.** In a register sentence, a test row is one unit of output that a test compares exactly, between machines or against a reference, and results count how many rows matched. The twelve-device result under Block counts rows. The claims register itself is also made of rows, one per result, and each names its result file and the testing step that marked it.

**Rust and CUDA.** Rust is a programming language designed to catch many memory mistakes before a program runs. CUDA is NVIDIA's way of writing programs that run on its GPUs, and my Hail Mary training stack is written in both.

## S

**Scope line.** A sentence that says what a result covers, so nobody reads it as covering more. The exact AI results carry the scope line given at the top of this page, and the 32B timed comparison on the exact AI page carries one of its own.

**Scoreboard.** My Mark One record that marks which numbers may be cited and keeps the retractions in writing. It has a line I still go by: "A named wall is a result, not a failure."

**Seed.** A number that sets the random choices in a run, such as a model's starting values. Running several seeds shows whether a result holds beyond one lucky draw, so "one seed" means that has not been shown yet; my Hail Mary arithmetic result is one seed per setup. Training runs on the card are not repeatable yet: the same settings and seed have ended differently on replay.

**Separate testing step.** A step inside my project that re-counts a result from the files before I quote it. It catches my mistakes, but it is not an outside check. Where a register sentence says a result was re-checked, or that a test window was set apart for checking, that was done by this step, not by anyone outside the project.

**Shadow mode.** New behaviour runs next to the live system and its output is recorded and compared, but not used. In Jarvis, new behaviour runs in shadow mode before it goes live, and the local reader agreed with a larger hosted model on meaning in 77 percent of 643 replies in shadow mode.

**Signed receipt.** A small record attached to an answer and signed with a secret key, so anyone holding the matching public key can check that the answer has not been changed since. Project Alpha's pilot server for Windows signs every answer; it has been tested in-house so far. A forged receipt is a fake one made to look genuine.

**Simulation.** Working something out on a computer instead of building it and measuring it in the real world. My tests of computing without binary all ran in simulation, and the project's own notes say "No watt, no wire, no chip is measured here."

**Standard error.** A measure of how much a number would likely shift if the measurement were repeated on other, similar samples. In Hail Mary's equal-time race mine lost by 0.1021 bits per byte, with a standard error of 0.0026, so the gap is much larger than the wobble from chance in the measuring. It was still one run each, so it does not show how a second run would go.

**Standard model.** In Hail Mary's race, a language model of the ordinary, widely used kind, trained on the same card for the same time. It is the yardstick Hail Mary has to beat, and Hail Mary does not yet match it at equal compute.

**Start cold.** A compressor starts cold when it begins each file knowing nothing and learns its patterns as it goes. On short windows it has little room to learn, which favours a model trained beforehand. That is why my Mark One code result shows the model learned code, not that it is a better general-purpose compressor.

**Stochastic computing.** Computing with streams of random bits, where a number is carried by how often a bit is on. I tested it in simulation and closed it as a negative.

## T

**Tamper-evident.** Built so that any later change shows. A signed receipt is tamper-evident, and so is a rule locked with a hash: change one character and the check no longer matches.

**Ternary.** Computing with three states instead of two. A ternary cell I tested in simulation lost to binary on transistors per bit.

**Test network with seed-generated weights.** A network built for testing whose weights are made from a seed rather than learned, so it knows nothing and is not a trained model. Project Alpha uses such networks to check that output stays exact when a network is very large; they say nothing about any model's quality or speed.

**Test suite.** The full set of automated tests for a program, where each test function checks one thing. Jarvis has about 150,000 lines of tests with 8,984 test functions, and a test run on 21 Nov 2026 recorded 12,611 passed and 4 known failures, from that run's log, not re-run since. A known failure is a test already known to fail and logged as such.

**Threads and cores.** A thread is one stream of work a program runs, and a core is one part of a processor that runs it. My home PC has 32 logical cores, and some register sentences name how many threads a run used.

**Timing terms.** Wall time is the real time on a clock that a job takes, and tokens per second is how many tokens a model writes each second. Overhead is the extra time a method costs compared with running without it. With alternating repeats, the two systems being timed take turns, run after run, so a busy moment on the PC hits both alike; the median is the middle result.

**Token.** The small pieces of text a language model reads and writes, one at a time; a token is often a short word or part of a word. A model's answer is a string of tokens, so a check can point to the exact token where two answers part ways.

**Token window.** In the exact AI scope line, "a 512-token window" is the length of text, counted in tokens, that today's results cover. Longer text is outside that scope as it stands.

**Training data.** The text a model learns from. A test is fair when none of its questions were in it: in Hail Mary's arithmetic test, the questions were made on the same PC, and none were in the practice set the model learned from. No other model was tested on them.

**Training stack.** The set of programs that trains models: it reads the data, runs the training on the GPU and records the results. In my words: "My own training stack, written from scratch in Rust and CUDA, has run about 1,050 clean GPU jobs on one home GPU since 19 Nov." A GPU job is one piece of work sent to the card, such as a training run or a test.

**Training step.** One update of a model during training, so progress is counted in steps. At training step 370,435, Hail Mary's current English model wrote this, picked from a longer sample whose grammar is broken, exactly as printed: "He was very scared. He did not want to ge up from him in his net."

**Transistors per bit.** How many transistors, the tiny switches chips are made of, a circuit needs for each bit it handles; fewer is cheaper. The ternary cell I tested lost to binary on this measure.

**Tuning.** Trying different settings on some data and keeping the ones that do best. A result is most trustworthy when the settings were tuned on separate data and the result was then measured on held-out data. In Hail Mary's comparison with a compressor, the PPM's settings were tuned on the same windows, one of the limits stated with it.

## V

**VOID.** The verdict for a result that broke its own locked rule, so its numbers are not used as results. A forecaster race in Hail Mary looked good, but one check file's last line broke the locked rule, so the whole race is VOID; it is a different race from the 12 of 27 result, and the earlier notes that treated its numbers as results were corrected. Hail Mary's results page shows a void result as VOID.

**Voxel.** The 3D version of a pixel: a small piece of space that a simulator fills with what is there. QMK World is an Earth-sized voxel simulator with Malta rebuilt 1:1, at full size; on an exam of 42 physics items it agreed with the real Earth on 10, was wrong on 20 and could not tell on 12, a failing grade.

## W

**Window.** A stretch of text of fixed length, cut from a larger file and scored on its own. Hail Mary's comparison with a compressor used 256 held-out windows of 512 bytes, and Mark One's comparison with Qwen used 256 fixed windows of 2,048 bytes of held-out code. The word has two other uses here: "a quiet window" is a stretch of time when the PC was less busy, and in a register sentence a test window is a set of test rows set apart for checking.
