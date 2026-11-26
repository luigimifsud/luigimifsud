# Forge

My early from-scratch model and the code to train it, the development model of Mark One.

| | |
|---|---|
| Project | Mark One |
| Dates | Committed 18 Jul 2026 |
| Size | 10.82 million parameters; a second run had 85.56 million |
| Hardware | One RTX 5070 with 12 GB, in my second PC |
| Status | Paused, with the rest of Mark One |

## What it was for

Forge was there to show that my training code learns structure from data. It is not a coding model.

## What it was trained and tested on

- Both runs started from random weights, one run each.
- The 10.82 million parameter run trained on 8 MB for 300 steps.
- The 85.56 million parameter run trained on 40 MB of source code in several programming languages, for 1,500 steps.
- Each run reports a validation loss. My notes do not say how the validation text was chosen, or what unit the loss is in.

## Results

- **10.82 million parameters.** It reached a validation loss of 1.56 on 8 MB, with 0.89 GB of peak memory on the card (recorded in its own notes, not re-run since).
- **85.56 million parameters.** On 40 MB of source code, its validation loss fell from 6.14 to 0.89 and its training loss from 5.65 to 0.73, with 6.76 GB of peak memory on the card. Limit: the samples it wrote were code-shaped noise, not working code, so this shows the training code learns structure, not that it makes a coding model. The unit of the loss is not stated, so these numbers can't be set beside the bits per byte on the other Mark One cards. One run. Recorded in its own notes, not re-run since.

## Where it falls short

- What it wrote was code-shaped noise, not working code.
- Without a stated loss unit, its numbers can't be compared with the later Mark One models.
- One run of each size.

## Not done yet

- Mark One is paused, and Forge with it.
- Nobody outside my projects has re-run it.

## Check it yourself

- **Today.** Nothing you can run. The code is private.
- **On a call.** I can open Forge's notes and its commit history, including the commit of 18 Jul 2026.
- [How to check what this site says](../../VERIFY.md#mark-one) covers what can and can't be checked for Mark One.

## More

- [Mark One](../../projects/mark-one.md)
