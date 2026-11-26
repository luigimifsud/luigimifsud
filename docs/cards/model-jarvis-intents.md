# Jarvis intent and answer models

Small models of my own inside Jarvis, built in September 2026, that guess what a patient's message is about and what a reply answers; none has a score on this site.

| | |
|---|---|
| Project | Jarvis |
| Dates | Intent model 12 Sep 2026. Shadow classifier 17 Sep 2026, evaluated 11 to 12 Oct 2026. Answer model 27 Sep 2026. |
| Size | Intent model: a vocabulary of 862 words. Shadow classifier: a model file of 63,434 bytes. |
| Status | The intent model and the answer model shipped, but the live assistant mostly hands the reading to a larger hosted model. The shadow classifier ran in shadow mode and routed nothing; my notes do not say where it stands now. |

## What it was for

- **The intent model** guesses what a patient's message is about.
- **The shadow classifier** was a second, experimental intent classifier. It came out of my QMK-1 work on 17 Sep 2026 and ran in shadow mode beside the shipped one, acting on nothing.
- **The answer model** learns which words in a patient's reply mean which answer to a question Jarvis asked, for example "no preference".

All three are separate from the Jarvis reader, which has its own card.

## What it was trained and tested on

- They were built offline from the assistant's own message logs. The labels came from Jarvis's own rule-based parsers, not from a person.
- The shadow classifier's versions were also tried on a made-up two-spirals task.
- I give no figures for the training messages, and no patient text appears on this card.

## Results

- None on this site. The answer model was never measured. I give no figures for the intent model or for the shadow classifier's October evaluation.

## Where it falls short

- No score for any of the three.
- The live assistant mostly hands the reading to a hosted model, so the intent model does little of the live work.
- The labels come from Jarvis's own parsers, not from people.
- The answer model shipped without being measured.

## Not done yet

- Measuring the answer model.
- A person checking a sample of the labels.

## Check it yourself

- **Today.** Nothing public. The messages are patient data and stay private.
- **On a call.** I can show where each model sits in Jarvis and when each was built, with no patient text on screen.
- [How to check what this site says](../../VERIFY.md#jarvis)

## More

- [Model history](../MODEL_HISTORY.md)
- [The Jarvis page](../../projects/jarvis.md)
- [The Jarvis card](jarvis.md)
- [Jarvis reader](jarvis-reader.md), the small local reader that has scores
- [QMK-1](qmk-1.md), the work the shadow classifier came out of
