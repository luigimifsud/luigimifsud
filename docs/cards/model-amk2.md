# AMK2

AMK2 was a learning program of mine in the QMK and AMK line, written in Rust and named on 27 Oct 2026; on its exam and against plain lookup tables it did no better than the simple baselines.

| | |
|---|---|
| Project | QMK and AMK, the learning work before Project Hail Mary |
| Dates | Named 27 Oct 2026. Read text from 27 to 31 Oct; save packer built 29 to 31 Oct; races against lookup tables 11 to 17 Nov. |
| Status | Resting since 9 Nov 2026. I changed the rules for the line on 17 Nov 2026. A further run plan is written and has not been launched. |

## What it was for

After an earlier attempt failed, I wanted to see whether a program built under strict rules could learn from the text it read and answer exam questions. AMK2 was also meant as the testing ground for the QMK-5 rewrite. From 11 to 17 Nov I raced its simplest form against plain lookup tables.

## What it was trained and tested on

- By 31 Oct 2026, 09:44, it had read 16,885,508,222 bytes of text. Its reading included logic drill files that were later ruled out.
- A 1,000-question exam: true, false or unknown questions, four-word gap filling, and pairs of sentences. A familiarity baseline sat the same items.
- English text it had been fed (256 KiB, 1 MiB and 16 MiB of it) and text it had never been fed, against lookup tables.

## Results

- **The exam.** In its best exam run it did no better than a familiarity baseline on the same items: the project's own check read the difference as "cannot tell". One exam.
- **Against lookup tables.** My AMK2 notes of 17 Nov 2026 record, as measured that week, that on text it had been fed its best version gave back 5.2, 6.0 and 7.7 of 16 bytes at 256 KiB, 1 MiB and 16 MiB of text. That is about what a 12-byte lookup table does, and a 16-byte table beat every version at every size. On text it had never been fed it gave back 2.6 to 4 of 16, the level of a perfect memory (the same notes give 2.6 to 5 of 16 for a perfect memory on new text). Limit: the "of 16 bytes" measure is my notes' own and is not defined where it is written down, and I did not open the check file the notes cite.
- **Its save packer.** I built a lossless packer for AMK2's own hourly saves. Four saves totalling 192.2 GB were stored in 90.784 GB, 47.2 percent of their size, and every byte came back exactly. Limit: no standard compressor was run on the same bytes, and these are saves of my own program.
- **A restart.** About 5 to 6 Nov 2026 I restarted it under stricter rules as AMK3, which has rested since 6 Nov. It has no result.
- **What the line came to.** Over about seven weeks, the QMK and AMK models I built under strict rules never got past reading back what they had been fed. The best did no better than a plain lookup table on text it had seen.

## Where it falls short

- On the exam it did not do significantly better than a familiarity baseline.
- A 16-byte lookup table beat every version at every size.
- Its reading included drill files that were later ruled out.
- The save packer was never compared with a standard compressor.

## Not done yet

- The further run plan has not been launched.
- Nobody outside my projects has run any of it.

## Check it yourself

- **Today.** Nothing you can run. The program and its text are private.
- **On a call.** I can open the exam result, my notes of 17 Nov and the save packer's report, with the design kept off screen.
- [How to check what this site says](../../VERIFY.md#dead-ends)

## More

- [Model history](../MODEL_HISTORY.md)
- [Dead ends](../../projects/dead-ends.md#the-earlier-learning-models-qmk-and-amk)
- [QMK and AMK](qmk-and-amk.md), the card for the whole line
- [QMK-4 and QMK-5](model-qmk-4-and-5.md), the models just before it
- [Project Hail Mary](../../projects/hail-mary.md), where the learning work went after 17 Nov
