# The next two years

As of 26 Nov 2026.

These are aims, not results. None of them is met yet.

For each aim this page gives the aim in plain words, the bar my notes set for it, where it stands today and the next step I have named. Where my notes give no bar or no next step, I say so rather than make one up. My notes set no deadlines for these aims, so this page sets none.

Under each heading, the aim I want most is at the top. Lower bits per byte is better. The results behind the numbers, with their limits, are in [RESULTS.md](RESULTS.md).

## Across both projects

### Someone outside my projects re-makes my results

**Aim.** Outside reproduction of my main results, on machines I don't own. What I want most is an email from someone I've never met, saying they ran my "try it yourself" download on their own machine and got my answers back bit for bit.

**Bar.** One person outside my projects runs the download on their own machine and gets my answers back, bit for bit. For Hail Mary, my written goals ask for the equal-time result below to be checked by someone outside the project.

**Today.** Nobody outside my projects has reproduced a result yet. The engine's download exists, but it has not been run on a second machine or sent to anyone. Hail Mary has nothing public to run. Its forecaster is packaged so someone else can run it: it re-makes my race results to within 0.00000000002, not bit for bit, and 26 of 26 planted errors in its checks were caught. Its one-click launcher has not been run yet, and nobody else has run it.

**Next step.** Run the download on a second machine. Then send it to people outside the project and publish what they got, whatever it is. A short demo video is on the same list: an answer, its signed receipt, one changed word, and the re-check run on the changed answer.

### A public benchmark run, with pass and fail lines published in advance

**Aim.** A run on a public benchmark, with its pass and fail lines published before the run.

**Bar.** My notes name no benchmark and no score to reach, so there is no bar yet.

**Today.** Before a test runs, I write down what counts as a pass and what counts as a fail. In Hail Mary each pass rule is locked with a hash before any result is read. None of those rules is public. My coding and arithmetic tests are my own: the suite of 200 small generated Python tasks I used for Mark One is not a public benchmark, and no rival was run on it. No other model was tested on Hail Mary's arithmetic questions.

**Next step.** None named in my notes.

## Project Alpha

### A paying pilot where an AI answer decides money

**Aim.** A bank or an insurer paying to run its real AI answers through the engine.

**Bar.** One paying customer of that kind. My notes give no size for the pilot.

**Today.** No customer and no money raised. About 70 outreach emails so far, and one investor conversation. The pilot server answers in the standard chat-completions format and signs every answer. It has been tested in-house so far.

**Next step.** I put this after the outside reproduction above. My notes name no separate step for it.

### Goal 1

**Aim.** The goal I set the project: 100 times more useful AI output from the same bytes of memory moved, with every token the same as an exact reference. None of the engine results on this site is a claim of progress toward it.

**Bar.** The 100 times, with every token matching an exact reference.

**Today.** Not met. The earliest milestone toward it, due 18 Nov 2026, was not reached, and one 7B timing came out without a result.

**Next step.** My notes name none after the missed milestone.

### The 32B timed comparison on all 57 prompts

**Aim.** Finish the timed comparison on the 32B model.

**Bar.** All 57 held-out prompts.

**Today.** It is not yet done on all 57. The run so far, with its scope line, is on [the exact AI page](../projects/exact-ai.md).

**Next step.** A run on all 57.

## Project Hail Mary

We are building language models from scratch, aimed at learning far more from far less data and memory. My written goals turn that into the bars below. I keep the design private, so each one says what the model should do, not how.

### Win an equal-time race against a standard model

**Aim.** A model I train from nothing for the same time as a standard model, that scores the same or better on held-out text.

**Bar.** The same or better at equal training time, then repeated on several seeds and checked by someone outside the project. My notes say "several" and give no number.

**Today.** Not met. In the one equal-time race so far (58 minutes each, from nothing, one card, one run each), a standard model scored 1.2878 bits per byte on 256 held-out story windows and mine 1.3900, so mine lost by 0.1021 (standard error 0.0026). After 37.6 hours of training my English model reads 1.1571 on the same measure. That does not count toward this bar, because the standard model had 58 minutes. Over its last 3.67 hours the score improved by 0.0023, inside one standard error, so the curve is flat.

**Next step.** A second equal-time race against the standard model, one that mine doesn't lose.

### Beat 0.8630 with half the weights

**Aim.** A model with half as many weights as my 25 million weight model that scored 0.8630 bits per byte on held-out stories, that scores better than 0.8630 on the same stories.

**Bar.** Under 0.8630 bits per byte on those story windows, with half the weights.

**Today.** Not met. My current English model is larger (28.7 million weights), and its 1.1571 is a different kind of score, so it cannot be set beside 0.8630. The bar is set against the 0.8630 model, not against my earlier one-night model of the same size, which needs 0.5804 on the same story windows.

**Next step.** None named in my notes.

### Follow a chain of facts

**Aim.** A model that follows a chain of facts across 2 links, then 4, then 8.

**Bar.** At least 85 percent of questions right at each length, and at least 90 percent when the wording is new to it.

**Today.** Not met. When last tested, my English model's answers on chains were at chance. Separately, on 26 Nov a model trained for one hour with about a tenth of its reading being logic examples showed learning on none of the 8 kinds of logic question I tested, chains among them, on 800 held-out questions. That is one seed, and the project's word for it is "not shown", which is weaker than "impossible".

**Next step.** None named in my notes.

### Learn new names from one reading

**Aim.** A model that reads a new story once and can then spell back at least half of the new names in it, and learns that in half the updates.

**Bar.** At least half of the new names, spelled back after one reading. For the second part, half the updates, my notes hold no starting count I can quote.

**Today.** Not met. In my early test, on an early snapshot of a 25 million weight model (10 updates on one reading, one seed, 40 stories), spelled recall was 0 percent, although it did prefer the story's new names by 0.41 bits per byte. One setting spelled back 69 percent of names from repeated sentences after 40 updates, but it made unrelated text clearly worse. My current English model has not been tested this way.

**Next step.** None named in my notes.

### Write 12 turns that hold together

**Aim.** A model that writes 12 turns in a row that keep the same names and the same topic.

**Bar.** At least 90 percent of its sentences complete and made of known words, and half as many made-up words.

**Today.** Not met. My English model is on the lowest step of its own eight-step ladder, and the project's judge swings between "babbling" and "sentences" on its writing. In my loop test it kept the names in none of 8 runs. An early check, at about 3.7 card hours and on 10 samples, found 4.6 percent of its words invented, against 0.7 percent in real stories. That check was not repeated on the 37.6 hour model.

**Next step.** None named in my notes.

### Training runs that repeat

**Aim.** Training runs on the card that end the same way when they are replayed with the same settings and seed.

**Bar.** My notes give no number for this.

**Today.** Not met. The same settings and seed have ended differently on replay. The nearest work is on runs that stop early. On 26 Nov one stability change let all 3 of its one-hour runs finish with no bad step, while two of the same runs without it stopped early, and a repeat of one of those finished anyway. That is one draw each, so luck is not ruled out, and it does not show the change is the cure.

**Next step.** None named in my notes.

## LIGHTGAP

### Run the sealed test

**Aim.** A test result for LIGHTGAP, my own text compressor, on text that nothing has read.

**Bar.** The pass line written down before the run: under 1.300 bits per character on a sealed 5 MB of enwik8, decoded exactly. Lower bits per character is better.

**Today.** Not met: the sealed test had not run as of 2 Nov 2026, so there is no test result yet. On my development set, VALID27 (3,653,983 characters of English Wikipedia), it needed 1.152914 bits per character and decoded back exactly, against 1.7694 for 7-Zip PPMd. VALID27 helped choose the settings, so that is not a test. Getting under 1.3 bits per character is not new, so a pass would not be a record. Details: [LIGHTGAP](../projects/lightgap.md).

**Next step.** Run the sealed test.

## Also an aim, with no bar yet

### Computing without binary

**Aim.** A way of computing that does not use binary, and in the end a chip built on it.

**Bar.** None in my notes.

**Today.** All of it is simulation on my PC, mostly negative and written down as negative. No result beats binary, and no chip has been made. A review on 17 Nov re-opened 21 of my own chip numbers and found 1 bad, which I fixed. Details: [computing without binary](../projects/computing-research.md).

**Next step.** None named in my notes.
