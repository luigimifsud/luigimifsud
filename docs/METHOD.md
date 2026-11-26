# How I test results before I quote them

Many of my ideas fail when I test them. These are the habits I keep so I don't fool myself, each with a case where it mattered.

## Pass and fail lines before the test

I write them down before a test runs, so the result cannot move them. In Mark One I trained two 104.5 million parameter models with the same seed, one on a general text mix and one on the same mix with Maltese as one row in six. I had registered that adding Maltese would make general text no more than 0.05 bits per byte worse. It came out 0.0572 worse, so I recorded that prediction as failed, although 2 of my 3 registered predictions passed.

## Locked rules in Hail Mary

Each pass rule is written down and locked with a hash before any result is read. A change is a dated, hashed amendment, never an edit. On a small test bench of tiny models (3,000 updates each, 8 seeds), my model scored 0.0169 bits per byte worse than a standard model. That is under the rule's 0.020 bar, but the spread was too wide to call the two the same, so the rule printed "cannot tell". I call it neither a win nor a proven match. It is a tiny bench, not a result for my English model.

## Testing the tests with planted errors

A check that misses a mistake I planted on purpose will miss mine too. In Hail Mary three checks caught 15 of 15, 9 of 9 and 26 of 26 planted errors. The 26 were planted in the checks of my forecaster's package, which I built so someone else can run it; nobody else has run it yet. One test reader caught 84 of 89 and was marked not ready.

## Void results

One forecaster race in Hail Mary looked good. Then one check file's last line broke the locked rule, so the whole race is VOID. The earlier notes that treated its numbers as results were corrected, and I never quote those numbers. It is a different race from the 12 of 27 result I do quote.

## Retractions in writing

Mark One had an early "beats gzip" claim, and I retracted it. A detection rule of mine reported a false-alarm rate of 0.006780. Tested against 3,600 matched control runs, the real rate was 0.073611, about 10.9 times higher, so I retracted that too. An August claim about my own model design was narrowed after a check, and the narrowed wording is the one I quote.

## What may be cited

Mark One's scoreboard marks which numbers I may cite. For my 40.6 million parameter model, the citable row is 1.3615 bits per byte on 192 held-out code windows, against 2.8362 for brotli -q 11, the strongest of 9 standard compressors on the same windows. Standard compressors start cold on short windows, so this shows the model learned code, not that it is a better general-purpose compressor. An older figure stays out, because its held-out set was not checked for leakage.

## Engine results in the project's words

For Project Alpha's exact engine I quote results in one way: word for word as the project's claims register records them, in the form each entry allows, with the limits that belong to it. Where one says a result was re-checked, I add that the re-check was a separate testing step inside my project, not someone outside it.

## Clean held-out sets and strong rivals

My headline for the 40.6 million parameter model fell twice, in writing. It started at 3.27 times smaller than gzip on 96 windows. After I removed the windows that overlapped my training text it was 2.49 times; about 65 percent of that fall was the overlap and about 35 percent a change in the mix of windows. Against brotli, the strongest of nine standard compressors on those windows, instead of gzip, it became 2.08, with the same cold-start limit as above. I also found six places where I had set up a rival compressor too weakly, each time in my favour. Now a rival's settings go to the tool's documented limit before its number is used.

## Equal-time races

After 37.6 hours of training, my English model scored 1.1571 bits per byte on 256 held-out story windows, one run, below the 1.2878 of a standard model. I do not call that a win, because the standard model had 58 minutes. Over my model's last 3.67 hours the score improved by 0.0023, inside one standard error, so its curve is flat. In the one race where both had 58 minutes, from nothing, on the same card, mine scored 1.3900 and lost by 0.1021.

## A separate testing step

Before I quote a number, a separate step inside my project re-counts it from the files. On 17 Nov a review re-opened 21 of my own chip numbers and found 1 bad, which was fixed. That catches my mistakes, but it is not an outside check, and nobody outside my projects has reproduced a result yet. I build with AI coding tools; I set the rules, design the tests and decide what counts as done.

## A named wall is a result, not a failure

That line is on my Mark One scoreboard, and I still go by it. On 25 Nov, and again in a re-run on 26 Nov, a model I trained for one hour with about a tenth of its reading being logic examples showed learning on none of the 8 kinds of logic question I tested, on 800 held-out questions. It learned the shape of an answer, not the logic, and the logic examples cost its English about 0.02 bits per byte against a model trained on English alone from another night. It is one seed. The project's word for it is "not shown", which is weaker than "impossible", and that is the word I use.
