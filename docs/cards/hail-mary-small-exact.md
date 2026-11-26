# Hail Mary small exact test

A small test in Project Hail Mary: a model of mine with 1,985 weights against four rival models, scored exactly on short windows of one corpus.

| | |
|---|---|
| Project | Project Hail Mary |
| Dates | As of 26 Nov 2026; an earlier form of the claim dates from August 2026 |
| Size | 1,985 weights |
| Hardware | One machine |
| Status | Research, small scale |

## What it was for

To compare my model with rival models of a similar size, at a scale small enough to score every window exactly. It also follows up an August claim of mine, which was narrowed after a check.

## What it was trained and tested on

- One corpus, mostly the project's own Python source, cut into 4-byte windows and scored exactly.
- 3 seeds for each model, and a control that destroyed the data's order.
- I make no claim here that the scored windows were held out from training.

## Results

- My model beat each of four rival models on all 3 seeds, by 4.0, 9.4 and 14.0 percent. The rivals were a Boltzmann machine with 30 hidden units and three pairwise or three-way models of 1,344 to 3,008 weights. A control that destroyed the data's order scored 1.785918. Small scale, one machine, and not a language-model result.
- An earlier August claim about this kind of model was narrowed after a check. Its narrowed wording is the August result on the [exact AI page](../../projects/exact-ai.md#earlier-research-in-the-same-register).

## Where it falls short

- Small scale: 1,985 weights, one corpus, one machine, 3 seeds.
- It is not a language-model result, and it says nothing about how the English model does.
- The August form of the claim had to be narrowed.

## Not done yet

- Nobody outside my projects has re-run it.

## Check it yourself

- **Today.** Nothing to run.
- **On a call.** I can open the result file with each model's score on each seed and the control, with the design kept off screen.
- [How to check what this site says](../../VERIFY.md#project-hail-mary)

## More

[A small exact test, on the Project Hail Mary page](../../projects/hail-mary.md#a-small-exact-test)
