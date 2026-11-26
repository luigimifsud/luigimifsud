# Mark Two

Mark Two was a very small language model of mine, trained from nothing in September 2026 and raced against 7-Zip PPMd on held-out book text, and it lost.

| | |
|---|---|
| Project | Baseline: Mark Two was the research line beside Mark One |
| Dates | 29 Aug to 24 Sep 2026. Named Mark Two on 5 Sep; the last training log is from 24 Sep. |
| Size | 11,521 parameters in the core model; the largest runs had about 299,403 |
| Hardware | The GPU in my home PC |
| Status | Paused since 24 Sep 2026 |

## What it was for

Mark One's main models had 40 million to 295 million parameters. With Mark Two I asked whether a far smaller model, trained from nothing at home, could beat a standard compressor on text it had never seen. It ran under strict written test rules. 7-Zip PPMd was the rival.

## What it was trained and tested on

- Public-domain books. The test bytes are the held-out ending of each of 128 book streams, 2,055 bytes each, 263,040 bytes in all.
- 7-Zip PPMd was given the same training text before it coded the same held-out bytes, at its best setting.
- Mark Two was scored exactly, in bits per byte. Lower is better.
- Before the name: three tiny models of about 1,100 weights each (25 Aug), trained on a 2,000,000 byte text file to test whether a claimed gain was real or came from something generic; and small English and Maltese runs, including one that kept training on 20 English books and Maltese Wikipedia from 29 to 31 Aug, with no registered test and no verdict. I give no results for these.

## Results

- **It lost to 7-Zip PPMd on held-out book text.** Its best run needed 1.996902 bits per byte against 1.429714 for 7-Zip PPMd, so it lost by about 0.567. The mean of four paired seeds was 2.097066, a loss of 0.667352. Limit: 128 streams of one kind of text is a small test. One summary in my notes gives PPMd 1.429471 at a different setting; the log itself reads 1.429714 at PPMd's best setting, which is the figure I use.
- **It lost on whole books too.** Scored on whole books, it needed 2.536562 against 1.273195 for PPMd.
- **Half its goals.** Of the ten goals I set for it, five were met. The goal of beating PPMd on a stream of text was not.
- **Two longer runs that did not finish (23 Sep 2026).** One reached 2.314667 at pass 3 of 20 over the book text. The other reached 2.789596 at pass 5 on a different text sample, then the GPU ran out of memory. Neither saved a checkpoint and no compressor was scored beside them, so neither is a comparison.

## Where it falls short

- It lost to 7-Zip PPMd on every comparison on record.
- The test is small: 128 streams, all books.
- The two longer runs of 23 Sep did not finish.

## Not done yet

- Its main goal, beating PPMd on a stream of text, is not met.
- Nobody outside my projects has re-run it.

## Check it yourself

- **Today.** Nothing an outsider can run. The model and the test bytes are private. 7-Zip PPMd is public.
- **On a call.** I can open the training logs and the result file behind each number, with the design kept off screen.
- [How to check what this site says](../../VERIFY.md#mark-one)

## More

- [Model history](../MODEL_HISTORY.md)
- [Mark One](../../projects/mark-one.md), the programme Mark Two grew out of
- [Dead ends](../../projects/dead-ends.md#home-built-compressors-that-lost), with my other home-built work that lost to standard compressors
- [BMK and BMK 2](model-bmk.md), the test bed I built for Mark Two's ideas
- [Hail Mary small exact test](hail-mary-small-exact.md), which follows up an August claim from the tiny models before Mark Two
