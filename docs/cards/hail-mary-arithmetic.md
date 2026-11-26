# Hail Mary arithmetic preview

A small Project Hail Mary model, trained for 58 minutes from nothing with some simple arithmetic in its reading.

| | |
|---|---|
| Project | Project Hail Mary |
| Dates | During Project Hail Mary (named 19 Nov 2026); results as of 26 Nov 2026 |
| Hardware | My home PC with one NVIDIA RTX 5090 (32 GB); the test questions were made on the same PC |
| Status | Preview, not a locked verdict |

## What it was for

To see whether a small model picks up simple arithmetic from its reading, and whether that holds on questions it never saw. A check with one number changed in each question shows whether it reads the numbers or gives back an old answer. It is a preview of one skill, not a maths model.

## What it was trained and tested on

- 58 minutes of training from nothing. About a tenth of its reading was simple arithmetic: sums, differences and next numbers, set in short stories. The rest was English text.
- 400 held-out near questions of the kinds it practised, plus harder forms (longer sums, and sums told as a story) and "which is more" questions. The test questions were made on the same PC, and none of them were in the practice set.
- A control: the same model trained for the same time with no arithmetic.
- One seed per setup.

## Results

- **Near questions.** 92 to 97 percent of 400 held-out near questions exactly right. The same model trained for the same time with no arithmetic got 0 to 5 percent. One seed per setup.
- **One number changed.** With one number in a question changed, it gave the old answer 0.2 to 1.6 percent of the time.
- **Harder forms.** On longer sums and sums told as a story it got 46 to 54 percent, against chance of 10 and 19 percent. That is about half: partial, not mastered.
- **"Which is more."** It never learned it (under 2 percent).
- **Its English.** It got a little worse.
- **Logic, a separate run of the same kind (as of 26 Nov 2026, 15:44).** A model trained for 58 minutes from nothing, with about a tenth of its reading being logic examples, showed learning on none of the 8 kinds of logic question I tested (comparing, chains, is-a, not, order, if-then, counting, instructions), on 800 held-out questions (100 per kind). It learned the shape of an answer, not the logic. The logic examples cost its held-out English about 0.02 bits per byte against a model from another night that read English alone. This re-run repeated the 25 Nov result. One seed. The project's word is "not shown", which is weaker than "impossible", and the test was built on the same PC. The 0.02 comes from the project's verdict file, not from a raw file I opened.

## Where it falls short

- One seed per setup, and a preview, not a locked verdict.
- About half right on the harder forms, and "which is more" never learned.
- Its English got a little worse.
- The test questions were made on the same PC, and no other model was tested on them.
- The same kind of run with logic examples learned none of its 8 kinds of question.

## Not done yet

- It has not been repeated on more seeds, and it has no locked verdict.
- No other model has been tested on these questions.
- Nobody outside my projects has run it.

## Check it yourself

- **Today.** Nothing an outsider can run. The model and the questions are private for now.
- **On a call.** I can open the result files with the score for each kind of question, the control and the changed-number check, with the design kept off screen.
- [How to check what this site says](../../VERIFY.md#project-hail-mary)

## More

[The arithmetic result on the Project Hail Mary page](../../projects/hail-mary.md#the-arithmetic-result-in-full)
