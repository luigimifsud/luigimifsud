# Hail Mary English model

My English text model in Project Hail Mary, trained from nothing on one GPU in my home PC.

| | |
|---|---|
| Project | Project Hail Mary |
| Dates | The research since January 2026; this model since 18 Nov 2026 (designed 17 Nov). The project got its name on 19 Nov. Results as of 26 Nov 2026. |
| Size | 28.7 million weights today; an earlier version had 25 million |
| Hardware | One NVIDIA RTX 5090 (32 GB) in my home PC |
| Status | Preview: research; this model is one week old |

## What it was for

This is the current model of Project Hail Mary. The aim: we are building language models from scratch, aimed at learning far more from far less data and memory. I hold it to a standard model trained for the same time and scored on the same held-out text. It does not yet match a standard model at equal compute. The current model is one week old.

## What it was trained and tested on

- It reads English text and is trained from nothing.
- Most scores are on 256 windows of 512 bytes from held-out files kept out of training: simple stories, and a mix of stories, history and Simple Wikipedia. Scores are in bits per byte, and lower is better.
- Other tests: name-lookup questions, reasoning questions, a test of reading a new story once, and counts of names, invented words and shared words in what it writes.
- Two versions appear on this card. The earlier one had 25 million weights. The current one, 28.7 million weights, began as my side of the 58 minute race below and has trained on since, in rounds of about an hour.

## Results

**The current version (28.7 million weights)**

- **Training so far (as of 26 Nov 2026, 10:12).** After 37.6 hours of training on one RTX 5090, added up from the logged seconds, it scored 1.1571 bits per byte on 256 held-out story windows, down from 1.3900 after 58 minutes. Over its last 3.67 hours it improved by 0.0023, which is inside one standard error (0.0097), so the curve is flat. One run, one seed, scored with the project's own held-out measure. That measure is not the exact scoring behind the compressor results further down, so the two sets of numbers cannot be compared. The standard model in the race scored 1.2878 (plus or minus 0.0099) after its 58 minutes. Mine has had 37.6 hours, so a lower number here is not a win at equal compute.
- **The equal-time race it lost (21 Nov 2026).** 58 minutes each, from nothing, on one card, one run each. On 256 held-out story windows a standard model scored 1.2878 bits per byte and mine 1.3900, so mine lost by 0.1021 (standard error 0.0026). On 256 windows of mixed held-out text the standard model scored 1.7147 and mine 1.8407. On name-lookup questions the standard model got 0.95 to 0.99 and mine 0.000, and on the race's whole question set the standard model scored 0.572 exact and mine 0.168. Mine lost on every measure here, in one race. The mixed-text and whole-question-set numbers are means recorded in the project's notes, not re-run since, and I did not open their raw files.
- **What it writes.** At training step 370,435, picked from a longer sample whose grammar is broken, exactly as printed: "He was very scared. He did not want to ge up from him in his net."
- **Its writing, checked early (22 Nov 2026).** After its third training round of 55 minutes (about 3.7 hours on the card), on 10 check samples against 40 real stories: it kept 25 percent of the names from the earliest sentence that names someone into its last three sentences, against 72 percent for real stories. 4.6 percent of its words were invented, against 0.7 percent. Neighbouring sentences shared a content word 12 percent of the time, against 25 percent. Few samples, measured early, and not repeated on the 37.6 hour model (recorded in its result files, not re-run since).
- **A larger version (26 Nov 2026).** In a short probe, a larger version of the model stopped early: 10 of the opening 497 updates (2.01 percent) were skipped, over the project's 2 percent limit. A standard model of the same size kept training in the same probe. I did not queue the larger version's long run. One short probe and one run, so it says nothing about a long run with other safeguards.
- **A stability change (26 Nov 2026).** I tested one change meant to stop training runs from breaking. With it, all 3 one-hour runs finished with no bad step. Without it, the same runs stopped at step 972 and step 582, after 11 bad steps each, and on a repeat of the second setup the run without it finished anyway. One run each, so luck is not ruled out: earlier runs of the same two setups without the change finished their hour 2 of 4 times and 1 of 4 times. The held-out scores differed by less than 2 percent, a little lower with the change, against runs from another build, and the runs with the change made fewer updates in the hour. It does not show the change is the cure.

**The earlier version (25 million weights)**

- **Against a compressor.** On 256 held-out windows of 512 bytes, it needed 0.8630 bits per byte on stories and 1.2070 on mixed text, against 1.0663 and 1.4494 for an order-12 PPM compressor written in the project, which had counted 170 MB and 400 MB of the training text beforehand. xz, given the training text beforehand, needed 1.4216 and 1.8784. Limits: that PPM is weaker than 7-Zip PPMd, which was not measured, and its settings were tuned on the same windows.
- **A loss to my own earlier model.** On the same 256 story windows, my one-night model of 26 to 27 Oct, of the same size, needs 0.5804 bits per byte against this version's 0.8630. This one needs about 49 percent more bits, and the older model wins on every window. On mixed text it is 0.8678 against 1.2070. The older model has its own card: [earlier English models](earlier-english-models.md).
- **Reading a new story once (18 Nov 2026).** On an early snapshot (step 7,272), one reading of a new story (10 training updates) made it prefer that story's new names over fresh names it had never seen, by 0.41 bits per byte on reworded test sentences (0.60 on the story's own sentences), z 21 against the same update on unrelated text, with no measurable forgetting at 10 updates. It could not yet spell the names back (0 percent). One seed, 40 stories. It is a preference for names, not recall, and the current version was not tested this way (recorded in its result files, not re-run since).
- **Reasoning questions (18 Nov 2026).** I found that 334 of the 390 items I had drawn from a public reasoning set could be answered by lookup alone, so 56 of them test a rule. On a separate reasoning test that a lookup table must fail, an early snapshot scored at chance on chains, binding, not, counting and reversal, also after 3,000 updates of logic examples. An earlier version of one of these tests had leaked its answers through the length of the gap, and I rebuilt it. The check on the logic-examples run printed FAIL on one instrument, although every number reproduced bit for bit. The logic examples taught logic text (0.59 against 1.75 bits per byte) and cost the stories 0.0105. Early model, not the current version (recorded in its result files, not re-run since).

**On a bench of tiny models (not the English model)**

- **My model against a standard one, at tiny scale (as of 26 Nov 2026, 11:41).** Tiny models trained for 3,000 updates on the CPU, 8 seeds: mine scored 0.0169 bits per byte worse than a standard model, about 1.1 percent of the gap between an untrained model and the standard one (standard error 0.0078). The project's rule printed "cannot tell": the gap is under the rule's 0.020 bar, and the spread is too wide to call the two the same. It is neither a win nor a proven match. The later rounds of this test have not been run (60 runs missing).
- **Single changes to a standard model (as of 26 Nov 2026, 17:27).** I graded 22 single changes to a small standard language model, one at a time, each on 4 or 8 seeds of tiny models (3,000 updates each): 12 made it worse, 6 made it better and 4 could not be told apart. A separate re-derivation reproduced all 141 answer lines. The counts are mine, from the graded table. Results on this bench did not always carry to the card: a change that won on the CPU blew up on the card. Every change ran with one shared training setting, so a change that wants a different setting looks worse here than it may be. A further group of changes has not been run.

## Where it falls short

- It does not yet match a standard model at equal compute. It lost the one equal-time race on every measure, and scored 0.000 on name lookup there.
- The earlier version is behind my own one-night model of the same size on every story window.
- Training runs on the card are not repeatable yet: the same settings and seed have ended differently on replay. One fix let 4 of the 5 dying runs finish their full hour, and the 26 Nov stability change rests on one run each.
- The current version's score went flat over its last 3.67 hours of training.
- Its grammar is broken, and in the early check it kept fewer names and invented more words than real stories do.
- The larger version went over the 2 percent limit in its short probe.

## Not done yet

These are aims. None of them is met yet.

- A model I train from nothing for the same time as a standard model, that scores the same or better on held-out text, repeated on several seeds and checked by someone outside the project. Not met: the one equal-time race so far was lost by 0.1021 bits per byte.
- A model with half as many weights as the 25 million weight model that scored 0.8630 bits per byte on held-out stories, that scores better than 0.8630 on the same stories. Not met.
- A model that follows a chain of facts across 2 links, then 4, then 8, and answers at least 85 percent of questions correctly at each length, and at least 90 percent when the wording is new to it. Not met: the English model's chain answers were at chance when last tested.
- A model that, after reading a new story once, can spell back at least half of the new names in it, and learns the same skill in half the updates. Not met: in my early test (10 updates on one reading), spelled recall was 0 percent, and the one setting that spelled back 69 percent of names from repeated sentences after 40 updates made unrelated text clearly worse.
- A model that writes 12 turns in a row that keep the same names and the same topic, with at least 90 percent of its sentences complete and made of known words, and half as many made-up words. Not met: the judge's word for its writing swings between "babbling" and "sentences", and the loop test kept names in none of 8 runs.

Also not done: training runs that end the same way when replayed, and any check by someone outside my projects.

## Check it yourself

- **Today.** Nothing an outsider can run or open. The design is private, and every number here comes from my own runs.
- **On a call.** I can share my screen and open the training log behind the 37.6 hours, the locked pass rules with their hashes, and the result file behind each number on this card, with the design kept off screen.
- What would make it checkable: [How to check what this site says](../../VERIFY.md#project-hail-mary).

## More

[Project Hail Mary](../../projects/hail-mary.md)
