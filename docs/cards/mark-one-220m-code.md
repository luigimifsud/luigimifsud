# Mark One 295M, step 199,000 snapshot

A saved snapshot of my 295 million parameter language model, part of Mark One, that I scored against Qwen2.5-Coder-7B.

| | |
|---|---|
| Project | Mark One |
| Dates | Measured 1 Aug 2026 |
| Size | 294.7 million parameters, at step 199,000 |
| Hardware | Trained on one RTX 5090. Qwen was scored on CPU. |
| Status | Paused, with the rest of Mark One. The model trained on past this step. |

## What it was for

My notes give this run a different size label. It is my 295M model at step 199,000, and it was trained on a general text mix, not on code alone.

I wanted to see how a small model trained at home compares with a much larger open code model on the same held-out text. Qwen2.5-Coder-7B has many times its parameters and training, so this measures the gap. It does not test whether a small model can beat a large one at equal memory.

## What it was trained and tested on

- Training text: a 29.1 GB mix of Stack Exchange, arXiv papers, Wikimedia, Project Gutenberg books, US government publications and generated logic problems. By step 199,000 it had read 4.17 bytes of text per parameter. A compute-matched run would read about 60 to 80 bytes per parameter (a reference value), so it was far under-trained.
- Test: 128 windows of about 1,000 bytes from the 900 MB held-out part of that same mix, matched by hash between the two models. The test text is general text, not code, and my model was trained on that kind of text.
- My check for overlap between these windows and my training text was inconclusive. If anything, that helps my score.

## Results

Lower bits per byte is better.

- **Against Qwen2.5-Coder-7B.** My snapshot scored 1.4321 bits per byte on these windows. Qwen2.5-Coder-7B (a 4-bit build) was better on 118 of the 128 windows, so I lost, and I won on at most 10 (the result files count 10 wins and 118 losses). Qwen started fresh on each window, and neither model's own size is counted. Limit: Qwen has many times my parameters and training, so this does not say whether a small model can beat a large one at equal memory. The overlap check was inconclusive. My notes hold more than one figure for Qwen's own score on these windows, so I don't quote one here.

## Where it falls short

- It lost to Qwen2.5-Coder-7B on nearly every window.
- It was far under-trained when it was tested.
- The test text is a general mix, so this is not a code result.

## Not done yet

- The overlap check for this snapshot is still inconclusive.
- Nobody outside my projects has re-run it.

## Check it yourself

- **Today.** Nothing you can run. The model and the test windows are private.
- **On a call.** I can open the two result files behind this comparison.
- [How to check what this site says](../../VERIFY.md#mark-one) covers what can and can't be checked for Mark One.

## More

- [Mark One](../../projects/mark-one.md)
- The same model at later steps: [Mark One 295M](mark-one-295m.md)
