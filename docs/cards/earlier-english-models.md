# Earlier English models

Two English text models from late October 2026, built and trained on my own RTX 5090 before Project Hail Mary had its name.

| | One-night model | Big Voice |
|---|---|---|
| Project | Early English work, before Project Hail Mary | Early English work, before Project Hail Mary |
| Dates | 26 Oct 2026, 23:49, to 27 Oct, 09:42 (about 10 hours) | 27 Oct 2026 |
| Size | 25 million weights | About 200 million weights |
| Hardware | One NVIDIA RTX 5090 | One NVIDIA RTX 5090, my own card |
| Status | Retired: put away on 27 Oct | Paused the same day, 27 Oct |

## What it was for

Both were early tries at an English model of my own. The one-night model was built and trained in one night. For Big Voice I had a Rust trainer built for a text model of about 200 million weights. The one-night model is the earlier model that a later Hail Mary version lost to on every story window.

## What it was trained and tested on

- The one-night model read 5.75 billion bytes of English text in training. Its training log checked it on held-out stories, and at the end on a harder held-out set of stories, history and Simple Wikipedia. Later it was scored exactly on 256 held-out windows of 512 bytes, of stories and of mixed text.
- Big Voice read about 421 million bytes before it was paused. It was checked on held-out stories and on held-out science text.
- The project's judge reads samples and gives a word such as "babbling" or "sentences". It counts known words and pairs, not meaning.

## Results

**One-night model**

- It wrote sentences after about 3 minutes of training.
- On the training log's own held-out check of stories: 1.4735 bits per byte after 4.48 million bytes of training, when the judge called its writing "babbling"; 1.2365 after 8.96 million bytes, when the judge's word became "sentences"; and 0.6587 after 327 million bytes.
- Its final 0.960 (plus or minus 0.050), after 5.75 billion bytes and about 10 hours, is on the harder held-out set of stories, history and Simple Wikipedia. It is the log's own check on a 24,576 byte slice, a figure from a verification file that I did not re-derive.
- Scored exactly on 256 held-out windows, it needed 0.5804 bits per byte on stories and 0.8678 on mixed text. On those story windows it beat my later 25 million weight Hail Mary version (0.8630) on every window.
- A picked sample, exactly as printed: "Once upon a time, there was a big spring. In the spring, there was a little fish named Fin. Fin was a very happy fish."
- Limits for all of these: one seed, no outside re-run, the samples are picked ones, and the judge counts words, not meaning.

**Big Voice**

- In a 5 minute trial on 27 Oct, the trainer took the held-out story score from 1.3397 bits per byte at update 256 to 1.0055 at update 626, after 14.4 million bytes of training (standard errors 0.0147 and 0.0121), and the judge's word moved from "babbling" to "sentences". A 5 minute trial, one run.
- The full run was paused the same day after about 421 million bytes, at 1.18 bits per byte on held-out science text and still babbling. Earlier in the run it reached 0.74 on simple stories, a different held-out set. Its check set is not the same size as the one-night model's, so none of this is a comparison with it.

## Where it falls short

- The one-night model is one seed with picked samples, and nobody outside my projects has re-run it. I did not re-derive its 0.960.
- Big Voice was still babbling on harder text when I paused it, and its trial was 5 minutes and one run.

## Not done yet

- Big Voice's full run stays paused.
- Neither model has been checked by anyone outside my projects.

## Check it yourself

- **Today.** Nothing to run.
- **On a call.** I can open both training logs with each held-out check and the samples as they were written.
- [How to check what this site says](../../VERIFY.md#project-hail-mary)

## More

- [Before Hail Mary had its name, on the Project Hail Mary page](../../projects/hail-mary.md#before-hail-mary-had-its-name)
- [The Hail Mary English model](hail-mary-english.md)
