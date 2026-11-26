# Open problems

As of 26 Nov 2026.

These are the hardest problems I have not solved, project by project. Each one is a research question, then what I have measured so far, with what it was measured on and what it does not show, then what I would count as solved. A line that starts "My aim" is an aim, not a result. Lower bits per byte is better.

Nobody outside my projects has reproduced any of these numbers yet. I keep the design of my models private, so nothing here says how they are built. The full results, losses included, are in [RESULTS.md](RESULTS.md), and [METHOD.md](METHOD.md) says how I test a result before I quote it.

## Project Hail Mary

We are building language models from scratch, aimed at learning far more from far less data and memory. It does not yet match a standard model at equal compute. The current model is one week old. Most numbers below are one run or one seed. Page: [Project Hail Mary](../projects/hail-mary.md).

### The equal-compute gap

**Question.** If I train my model from nothing for the same time as a standard model, on the same card, can it score the same or better on held-out text?

**Measured so far.**

- The one equal-time race so far: 58 minutes each, from nothing, on one card, one run each. On 256 held-out story windows the standard model scored 1.2878 bits per byte and mine 1.3900, so mine lost by 0.1021 (standard error 0.0026). One race cannot show how the gap moves across seeds.
- In the same race, on 256 windows of mixed held-out text, the standard model scored 1.7147 and mine 1.8407. On the whole question set it scored 0.572 exact and mine 0.168. On name-lookup questions it got 0.95 to 0.99 and mine 0.000. That is a loss on every measure in the race. The mixed-text and question figures are means written in my notes; I did not open the raw files.
- After 37.6 hours of training on one RTX 5090, my English model scored 1.1571 on 256 held-out story windows (the project's own held-out measure, one run). That is below the standard model's 1.2878, but the standard model had 58 minutes, so it is not an equal-compute result. Over the last 3.67 hours the score improved by 0.0023, inside one standard error (0.0097). The curve is flat.
- A larger version of my English model, about three times the weights, stopped early in a short probe: 10 of the 497 updates counted in the probe (2.01 percent) were skipped, over the project's 2 percent limit. One short probe says nothing about a long run with other safeguards. It does mean I have no reading yet on whether more size closes the gap.
- On a small test bench (tiny models trained for 3,000 updates, 8 seeds), my model scored 0.0169 bits per byte worse than a standard model (standard error 0.0078), and the project's rule printed "cannot tell". That is under the rule's 0.020 bar, but the spread is too wide to call the two the same, so it is neither a win nor a proven match. It is a tiny bench, not the English model, and results on this bench have not always carried to the card.

**What would count as solved.** My aim: a model that I train from nothing for the same time as a standard model and that scores the same or better on held-out text, then repeated on several seeds and checked by someone outside the project. Not met. I also want that result on a public held-out set with a standard baseline, so someone else can re-run both sides.

**The same question for memory.** My aim: a model with half as many weights as the 25 million weight model that scored 0.8630 bits per byte on held-out stories, that scores better than 0.8630 on the same stories. Not met. That 0.8630 is my model of 18 Nov, scored exactly on 256 held-out windows of 512 bytes. It is a different measure from the 1.1571 above, so the two are not compared here. On the same story windows my earlier one-night model of the same size (26 to 27 Oct) needs 0.5804 and wins on every window, so the newer model is still behind my own earlier one.

### Training runs that do not repeat on replay

**Question.** Can a training run on my card end the same way when I replay it with the same settings and seed, and can I stop runs from dying part-way?

This is the open problem closest to my other project. Project Alpha is about answers that can be re-made bit for bit. My own training runs do not yet end the same way twice on one card.

**Measured so far.**

- The same settings and seed have ended differently on replay. One fix let 4 of the 5 dying runs finish their full hour.
- On 26 Nov I tested one stability change in one-hour runs. With it, all 3 runs finished with no bad step. Without it, the same two setups stopped at step 972 and step 582 after 11 bad steps each, one run each. On a repeat of the second setup, the run without it finished anyway. Counting every run of the two setups without the change, these included, 2 of 4 finished their hour for one setup and 1 of 4 for the other. One draw each, so luck is not ruled out, and it does not show the change is the cure. With the change the held-out score was a little lower, inside 2 percent, against comparison runs from another build, and the runs made fewer updates in the hour.
- In the equal-time race, an earlier attempt of my model stopped at step 243 when a number blew up. The scored run was a second attempt with one setting turned down.
- On the tiny test bench, a change that won on the CPU blew up on the card. In the logic re-run of 26 Nov, one model stopped early at step 654, and its re-run was queued.

**What would count as solved.** A replay with the same settings and seed that ends with the same score, so a single result can be checked by running it again. And the stability change holding over several draws of each setup, with no loss in score. Until then I say one run when it is one run, and I count a difference as real when it is large against its standard error.

### Chains of facts at chance

**Question.** Can a small model trained from nothing learn to follow a chain of facts, and logic more widely, instead of learning the shape of an answer?

**Measured so far.**

- On 25 Nov, and again in a re-run on 26 Nov, a model trained for one hour with about a tenth of its reading being logic examples showed learning on none of the 8 kinds of logic question I tested (comparing, chains, is-a, not, order, if-then, counting, instructions), on 800 held-out questions (100 per kind). It learned the shape of an answer, not the logic. The logic examples cost its held-out English about 0.02 bits per byte against a model trained on English alone, from another night; that figure comes from the verdict, not from a raw file I opened. One seed, and the test was built on the same PC. The project's word is "not shown", which is weaker than "impossible".
- A separate model trained on logic plus arithmetic was read on 25 Nov as learning counting in one answer form. It was not part of the re-run.
- On 18 Nov I found that 334 of the 390 items I had drawn from a public reasoning set could be answered by lookup alone, so 56 test a rule. On a separate reasoning test that lookup alone must fail, an early snapshot of my 25 million weight English model scored at chance on chains, binding, not, counting and reversal, also after 3,000 updates of logic examples. One of these tests had an earlier version that leaked its answers through the length of the gap, and it was rebuilt.
- In an early preview on one seed, a small model trained for 58 minutes from nothing, with about a tenth of its reading being simple arithmetic, got 92 to 97 percent of 400 held-out near questions exactly right, against 0 to 5 percent for the same model trained without arithmetic. On harder forms (longer sums, and sums told as a story) it got 46 to 54 percent, against chance of 10 and 19 percent. It never learned "which is more" (under 2 percent). No other model was tested on these questions. So, in this preview, the model learned this form from a small share of its reading. It does not show that it learns more from the same text than a standard model would.

**What would count as solved.** My aim: a model that follows a chain of facts across 2 links, then 4, then 8, and answers at least 85 percent of questions correctly at each length, and at least 90 percent when the wording is new to it. Not met: chains were at chance when last tested. For arithmetic, I want a standard model trained the same way and tested on the same questions, and "which is more" learned.

### Spelled recall of new names

**Question.** After reading a new story once, can the model spell back the new names in it, without making other text worse?

**Measured so far.**

- On 18 Nov, on an early snapshot (step 7,272) of my 25 million weight English model, one reading of a new story (10 training updates) made it prefer that story's new names over fresh names it had never seen. The preference was 0.41 bits per byte on reworded test sentences and 0.60 on the story's own sentences, z 21 against the same update on unrelated text, with no measurable forgetting at 10 updates. It could not spell the names back: 0 percent. One seed, 40 stories, and I read the note, not the raw file. A preference for names is not recall.
- One setting did spell back 69 percent of names, from repeated sentences after 40 updates, but it made unrelated text clearly worse.
- My current English model, 28.7 million weights, has not been tested this way.

**What would count as solved.** My aim: a model that, after reading a new story once, can spell back at least half of the new names in it, and learns the same skill in half the updates. Not met: spelled recall after one reading was 0 percent when last measured. I also want no measurable forgetting on unrelated text, on more than one seed.

### Writing that keeps names

**Question.** Can the model write at length and keep the same names and the same topic, in complete sentences of real words?

**Measured so far.**

- At its third training turn of 55 minutes (about 3.7 card hours), on 10 check samples, my English model kept 25 percent of the names from a story's earliest named sentence into its last three sentences, against 72 percent for real stories. 4.6 percent of its words were invented, against 0.7 percent. Neighbouring sentences shared a content word 12 percent of the time, against 25 percent. Few samples, measured early, and not repeated on the 37.6 hour model. Between turns 1 and 3, sentence endings were the one measure that moved beyond noise. I read the report, not its raw rows.
- A separate writing test kept names in none of 8 runs.
- The project's judge word for its writing still swings between "babbling" and "sentences". A sample at step 370,435, with broken grammar, is on [the Hail Mary page](../projects/hail-mary.md#what-it-writes).

**What would count as solved.** My aim: a model that writes 12 turns in a row that keep the same names and the same topic, with at least 90 percent of its sentences complete and made of known words, and half as many made-up words. Not met. I also want the names measure repeated on the current model, on more than 10 samples.

## Project Alpha

Project Alpha builds an engine that runs open language models so their answers can be re-made bit for bit on other machines and checked later. I quote its results word for word as my project records them in its claims register, so they read a bit stiff. "We" and "our" mean the project, and "this PC" means my home PC. Where a register sentence says a result was re-checked, that was a separate testing step inside my project, not anyone outside it. Page: [Exact AI](../projects/exact-ai.md).

Scope today: five Qwen2.5 open models (0.5B to 32B) and one mixture-of-experts model (DeepSeek-V2-Lite), a 512-token window, and a pilot package for Windows only.

### Reproduction outside the project

**Question.** If someone outside the project runs the engine on their own machine, do they get the same bits?

**Measured so far,** inside the project:

> Twelve devices (Windows desktops and laptops, AMD and Intel; Linux cloud servers, AMD EPYC and Intel; two NVIDIA H100 GPUs) gave bit-identical output on every block they shared: 29.8 million rows confirmed on at least two devices, 1.7 million on all twelve; one small open model.

> An NVIDIA RTX 5090 reproduced our CPU engine's output bit for bit on all 106,336 test rows we compared against AMD processors; one small open model.

- Nobody outside the project has reproduced these yet. They were measured on the project's own test machines and on cloud machines.
- The "try it yourself" download exists, but it has not been run on a second machine or sent to anyone. The pilot server has been tested in-house so far.

**What would count as solved.** Someone outside the project runs the download on their own machine, compares what they get with our reference, and I publish the result, whatever it is. Before that, the download has to run on a second machine of mine.

### What is outside the scope line

**Question.** Does exactness hold for what the scope line does not name, such as a longer window, another model family or a pilot for another system? And what does it cost there?

**Measured so far.**

- Every exactness result on a trained model that I can quote sits inside that line.
- The test-network results on the exact AI page go to far larger sizes, but their weights are seed-generated, not trained, so they say nothing about any model's quality or speed.
- The timed comparison on the 32B model is not yet done on all 57 held-out prompts. The other speed results I can quote are under [Speed](../projects/exact-ai.md#speed), each with its setting and its limits.
- The earliest milestone toward the project's goal, due 18 Nov 2026, was not reached, and one 7B timing came out without a result.

**What would count as solved.** A register result for each thing outside the line, each with its own scope, marked by the project's separate testing step and then reproduced outside the project. And the 32B timed comparison run on all 57 held-out prompts.

### What the re-check does and does not prove

**Question.** When a logged answer passes the re-check, what has been proved, and against whom?

**Measured so far.**

> A one-pass re-check of a logged answer names the first token that changed. In our tests 40 of 40 honest answers passed with no false alarm, and 40 of 40 altered answers were caught at the exact token, down to a one-bit change.

- It works on answers made by this engine, or by one that gives the same bits.
- The tests in that sentence were made inside the project. They are not a security proof, and nobody outside the project made the altered answers.
- The check finds what changed in a log. It does not stop a server that controls both the engine and the log.
- A match shows that two runs agree. It does not show that the answer is right. A signed receipt shows who signed an answer, not that the answer is right.

Most of the exactness results compare the engine with itself on other machines. How close it stays to the same model in full 32-bit precision is measured by text-prediction quality, not answer by answer:

> Qwen2.5-32B-Instruct, an open 32-billion-parameter model, runs on our exact engine on this PC: four different CPU instruction paths give bit-identical outputs on every test row run (6,336 rows, 1,024 on the two slowest paths), re-checked independently, and its text-prediction quality is within 0.02 % of the same model in full 32-bit precision on 20 text windows (the 95 % interval, -0.08 % to +0.11 %, includes zero).

> We ran a real open mixture-of-experts model, DeepSeek-V2-Lite (27 layers, 64 routed experts per layer), end to end on our exact engine on one PC: four different CPU instruction paths, two thread counts and token-by-token decoding gave bit-identical outputs and identical expert choices on every one of 37,008 output rows, re-checked independently; and its text-prediction quality on 20 text windows is within 1 percent of the same model in full 32-bit precision (+0.14 %, 95 % interval -0.04 % to +0.30 %). Beside it, as pre-registered: an earlier first-layer fidelity check missed its 1 % target at 1.02 %, and 81.7 % of the expert choices match the full-precision model's.

**What would count as solved.** Larger and harder sets of altered answers, made by people outside the project. A written statement of which attacks the check catches and which it does not. And, for each model, a reference that a reviewer can re-make for themselves.

## Earlier lines

Most of my earlier lines are closed, and their walls are on [Dead ends](../projects/dead-ends.md). These problems from them are still open.

### A small model against a large one at equal memory

**Question.** Can a small model I train at home beat a large open model when both get the same memory and the same training? Mark One is paused, and this is the question it left. Page: [Mark One](../projects/mark-one.md).

**Measured so far.**

- On 128 held-out windows of general text from my own training mix, Qwen2.5-Coder-7B (a 4-bit build) was better on 118 of the 128 windows; mine won on at most 10. Mine was a snapshot of my 295M model (step 199,000) at 1.4321 bits per byte. The overlap check on those windows was inconclusive, and any overlap would help my score, not hurt it.
- On 256 fixed windows of 2,048 bytes of held-out code, my 295M model scored 0.788 bits per byte against 0.593 for Qwen2.5-Coder-0.5B, behind by 0.195 and winning on 18 of the 256 windows. Larger Qwen models scored 0.496 at 1.5B and 0.442 at 7.6B. Qwen probably saw similar code, and the holdout is not proven clean.
- Qwen has many times my training, and the 7B many times my parameters, so neither result says whether a small model can beat a large one at equal memory. My 295M model read about 4 percent of its mix (4.17 bytes per parameter), against a reference value of 60 to 80 bytes per parameter for a compute-matched run, so it is far under-trained.

**What would count as solved.** A comparison at equal memory and equal training, on held-out text proven clean of overlap.

### A compression result that counts its own size

**Question.** Can my Python compressor still win once its own decoder is counted, and give back each file exactly as written? Page: [Compression demonstrator](../projects/compression-demo.md).

**Measured so far.**

- On 30 Python files it scored 0.993994 bits per byte against 1.265092 for 7-Zip PPMd at its best order, and all 30 of 30 files came back identical after the round trip. Its limits go with it every time: the margin falls 31 percent when PPMd gets its best setting, on English it loses to PPMd by 0.351291 bits per byte, it is much slower to encode, and its peak memory is 1,751 MiB against 16 MiB.
- On 542,523 bytes of normalised Python standard-library source, counting its decoder program (83,932 bytes), the total is 152,151 bytes. That is more than the 84,957 bytes 7-Zip PPMd needs on the same data.
- It returns a normalised form of each file, not the file as written. Comments and formatting are 20.8 percent of the characters in those files.
- It is not published, so nobody outside my projects can re-run it.

**What would count as solved.** A version that beats PPMd at its best setting with the decoder counted, gives back each file exactly, and is published so a stranger can re-run it and compare.

### Development numbers without a test

**Question.** Does LIGHTGAP, my own text compressor, hold up on text that nothing has read, and not just on the development set that helped choose its settings? Page: [LIGHTGAP](../projects/lightgap.md).

**Measured so far.**

- On my development set, VALID27 (3,653,983 characters of enwik8, the opening 100 MB of English Wikipedia, mapped to the 26 letters and the space), it needed 1.152914 bits per character, and a separate process decoded it back exactly. On the same text 7-Zip PPMd (order 20), the best standard compressor on my PC, scored 1.7694. Lower bits per character is better.
- VALID27 helped choose the settings, so it does not count as a test. The sealed test had not run as of 2 Nov 2026, so there is no test result yet.
- Decoding is slow: 13,116.8 seconds for VALID27, about 279 characters a second, on a busy PC.
- Getting under 1.3 bits per character is not new, so a pass would not be a record. Nobody outside my projects has run it.

**What would count as solved.** The pre-registered test, run: a sealed 5 MB of enwik8 that nothing has read, with the pass line written down before the run. The line is under 1.300 bits per character, decoded exactly.

### Computing without binary

**Question.** Is there a way to compute without binary that wins on a measure written down before the test, in simulation and then in hardware? Page: [Computing without binary](../projects/computing-research.md).

**Measured so far.**

- In simulation, one design needed 7.571 transistors per bit against 2.000 for a binary inverter, so it lost on transistor count. Stochastic computing was closed as a negative, and a bit-slicing idea died to both of its controls.
- A review on 17 Nov re-opened 21 of my own chip numbers and found 1 bad, which I fixed. The review was inside my project too.
- My notes say it plainly: "No watt, no wire, no chip is measured here." No chip has been made.

**What would count as solved.** A design that beats binary in simulation on a measure set before the run, then the same measure taken on a real part.

## Jarvis

Jarvis is the WhatsApp booking assistant I built for Apex Dental, my dad's two clinics. It is live with the clinic's patients and staff. Shadow-mode numbers come from the bot's own logs, not an audit. The exam numbers are recorded in Jarvis's own files and were not re-run for this page. Every number here is an aggregate, with no patient data. Page: [Jarvis](../projects/jarvis.md).

### Paths the offline exam does not measure

**Question.** How does Jarvis do on the parts of a chat that reach the hosted model?

**Measured so far.**

- The offline exam runs sealed, with the hosted model off. It scored 217 of 477 on 12 Nov 2026, and 241 of 477 after the fixes of 13 Nov. By 21 Nov it had 512 cases and passed 283 with the settings Jarvis runs live, and on 23 Nov 288 of 512. A probe of the 477 cases found 344 reach the hosted model somewhere, so those paths are not measured by this exam. The fixes were made to pass known cases, so the rise shows the fixes took, not a score on unseen chats. The case mix also changed from 477 to 512.
- On a fixed live sample of 40 cases that do reach the hosted model, Jarvis passed 34 at the baseline, 33 on 13 Nov and 32 on 21 Nov, with two new checks on. No run with the new checks off was made, so the slip cannot be put down to them. A move of one or two cases on 40 sits inside run-to-run noise.

**What would count as solved.** A measure of the paths that reach the hosted model, on enough cases that a change of one or two is not noise, with a control run for each new check switched off.

### Machine-picked cases nobody has checked

**Question.** Are the machine-picked cases, and the machine judge that scores real offers, right?

**Measured so far.**

- In the 12 Nov evaluation, 61 of 272 machine-picked moments where a chat went wrong passed (22 percent). A bot that hands every message to staff passed 47 of the same 272, a much closer gap than in the other groups. The 363 machine-picked cases have not been checked by a person.
- From 1 to 14 Nov a machine judge found that 143 of 498 real offers (29 percent) went against a limit the patient had given, without saying so. From 14 to 21 Nov, while the offer check was logging what it would change, it found 28 of 212 (13 percent). A person has not checked the judge, and two machine judges disagreed a lot: 23 offers flagged by one alone, 5 by the other alone, 4 by both. Other changes went live in the same week, so the fall is not credited to the check.
- In the same logging week, the check that answers the patient's question before making an offer logged 13 faults in 75 direct questions (17.3 percent), against 12.8 percent before, from a different sample. No improvement is shown.
- When a person did read cases, it changed things. The clinic's owner read 25 of the exam cases for the offer check: 22 were right as written and 3 he answered differently, which changed the check. Those were hand-built cases, not the 363 machine-picked ones.

**What would count as solved.** My 12 Nov evaluation lists two 50-row hand-check sheets still to be answered by a person, and says that if more than about 1 in 10 disagree with the judge, the figures must be redone. Solved means those sheets answered and the figures standing, or redone. Then the 363 machine-picked cases checked by a person the same way.

### The reader below its 95 percent bar

**Question.** Can Jarvis's small local reader reach the bar to become the main reader, and does agreement with the hosted model mean it is right?

**Measured so far.**

- In shadow mode, from October to 25 Nov 2026, version 2 of the reader agreed with the larger hosted model on meaning in 77 percent of 643 replies, the bot's own running total. Its bar for becoming the main reader is 95 percent.
- It did not get closer over the weeks: 79 percent (66 of 84 replies) in the week of 14 to 20 Oct, and 68 percent (68 of 100) in the week of 19 to 25 Nov, with the same version 2 throughout. On samples that small the drop is not far outside what chance could give, so it shows no improvement, not a proven decline. 5 of the 43 days reached 95 percent on their own, each on 1 to 25 replies. Catching upset replies went the other way: 13 of 20 at the start of the log and 24 of 32 at the end.
- In the log's daily rows, which show 593 of those 643 replies, the two agreed on feeling in 60 percent. Of 196 replies the hosted model read as upset, the small reader named the same feeling for 126 (64 percent).
- Agreement with a hosted model is not accuracy, because the hosted model can be wrong, and the log says none is audited yet.
- On fixed test sets, version 3 agreed with the hosted model more often than version 2, but caught fewer of the not-calm replies: 0.64 against 0.88 on 86 chat replies (16 against 22 of 25), and 0.829 against 0.914 on 147 phone replies (29 against 32 of 35). It is built on a larger open model, so the difference is not tuning alone, and it is not the version in shadow mode. The score file reports accuracy and catch rate, not false alarms, so the cost of version 2's higher catch is not shown.

**What would count as solved.** Agreement of 95 percent on meaning held over weeks, not on single days. A sample checked by a person, so agreement can be read as accuracy. And false alarms reported beside the catch rate.
