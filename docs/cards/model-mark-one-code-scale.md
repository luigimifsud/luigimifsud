# Mark One large code runs

Later training runs of my largest Mark One model, 295 million parameters, started fresh on large sets of code, plus one English run overnight; none of them has a score I can give.

| | |
|---|---|
| Project | Mark One |
| Dates | 14 Aug to 7 Sep 2026. Attempts to restart the Python run are logged up to 26 Oct 2026. |
| Size | 294.7 million parameters in each run |
| Hardware | Not recorded for these runs |
| Status | Stopped. The 41 GB code run collapsed, the English run was stopped early, and the Python run was my last large Mark One training campaign. |

## What it was for

The main run of my 295 million parameter model was on a general text mix, and it finished 200,000 steps on 27 Jul 2026. These later runs started fresh models of the same size on code at a much larger scale, to see how far it would go. The English run tried the same size overnight on English.

## What it was trained and tested on

- 14 to 18 Aug 2026: a fresh model on 41 GB of open code under permissive licences.
- 19 Aug to 7 Sep 2026: a fresh model trained for 700,000 steps on 34 GB of Python code, kept to licences that allow training.
- 3 Sep 2026, 21:27 to 23:55: an English run overnight, stopped by a stop file after about 7,600 steps.
- No test of these runs is on this card.

## Results

- **The 41 GB code run collapsed** during training. I have no score from it.
- **The Python run and the English run** have no score on this card either.

## Where it falls short

- Three large runs and no number to show for them.
- One collapsed, and one was stopped after about 7,600 steps.
- The coding results I do have come from a different run: the 295 million parameter model trained further on code from its general-text checkpoint. They are on the [Mark One 295M](mark-one-295m.md) card.

## Not done yet

- None of these runs has been re-run or scored. Mark One is paused.
- Nobody outside my projects has run them.

## Check it yourself

- **Today.** Nothing you can run.
- **On a call.** I can open the training logs of these runs, including the one that collapsed, and the stop file that ended the English run.
- [How to check what this site says](../../VERIFY.md#mark-one)

## More

- [Model history](../MODEL_HISTORY.md)
- [Mark One](../../projects/mark-one.md)
- [Mark One 295M](mark-one-295m.md), the same size of model trained further on code, with its coding results
