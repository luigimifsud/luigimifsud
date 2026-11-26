# BMK and BMK 2

BMK and BMK 2 were text compressors of mine from September 2026, built as a test bed for Mark Two and raced against plain counting and then against 7-Zip PPMd.

| | |
|---|---|
| Project | Baseline, as the test bed for Mark Two |
| Dates | BMK: 21 to 24 Sep 2026. BMK 2: versions 1 to 3 on 22 to 24 Sep 2026; version 4, built on 24 Sep, was the model to beat until 5 Oct. |
| Size | No neural network. The main BMK version held 1,143,900 stored numbers. |
| Hardware | Not recorded on this card. The raw logs are on another of my machines. |
| Status | Superseded. BMK gave way to BMK 2, begun on 22 Sep 2026, and BMK 2's version 4 stayed the model to beat until 5 Oct. |

## What it was for

BMK tested ideas for Mark Two: could a new kind of text model beat plain counting on short windows of English? BMK 2 was a larger model of the same kind, raced against 7-Zip PPMd, a standard compressor. It went through four versions in three days. There was also a portable build that runs on standard Python libraries alone and checks that its arithmetic agrees; it scores no text.

This BMK is a compressor. It has nothing to do with Jarvis, the booking assistant.

## What it was trained and tested on

- BMK: short windows of one fixed English test text, 33 bytes each at the main setting and 32 bytes at a smaller one, with plain counting scored on the same windows.
- BMK 2: slices of one fixed text sample, a mix of medical, scientific and web text. Each slice is scored on 128 held rows of 2,055 bytes, 263,040 bytes in all. Each new version was graded on fresh slices.
- In the graded tests, 7-Zip PPMd was scored on the same bytes at its best order for each slice, picked on the held bytes themselves. That choice helps the rival.
- Scores are in bits per byte, and lower is better.

## Results

**BMK (21 to 24 Sep 2026)**

- **It lost to plain counting.** On 33-byte test windows of English text, its best fitted form needed 2.971336 bits per byte against 2.906112 for plain counting on the same windows, so it lost by 0.065. A variant reached 2.936104, still 0.030 above counting, and the earlier form scored 3.060156. At the smaller setting (32-byte windows) a variant needed 3.489173 against 3.489131 for counting: a tie to 0.00004, not a win. Meeting counting is not beating it. Limit: one fixed English text with short windows, so this is not a compression result. The logs are on another of my machines; I read my written notes for this card.

**BMK 2, versions 1 and 2 (22 to 24 Sep 2026)**

- **Two early losses.** Version 1 lost to PPMd on its slice, 1.617074 against 1.530961. Version 2 lost on another slice, 1.680668 against 1.495681, in a run whose fitting stalled. I kept it in the record.
- **A small lead on four fresh slices.** On 512 pooled held rows of four fresh slices, the better form of version 2 needed 1.493499 bits per byte against 1.506394 for PPMd on the same bytes: 0.012896 in its favour, ahead on 364 of 512 rows. Limit: the gap is small, and on the 128 pooled rows where PPMd spends the most bits it lost, 1.920634 against 1.907968.

**BMK 2, version 3 (24 Sep 2026)**

- **Ahead of PPMd on four more fresh slices.** On 512 pooled held rows of four fresh slices, version 3 was 0.052619 bits per byte below PPMd. Per slice it needed 1.386065, 1.386375, 1.266320 and 1.272638, against 1.442275, 1.443765, 1.315633 and 1.320164 for PPMd, and it was ahead on 482 of 512 rows. The test was registered before its bytes were read. Limit: one test on one fixed text sample, with the rival's order picked on the held bytes. It needs far more computing time than PPMd.

**BMK 2, version 4 (24 Sep to 5 Oct 2026)**

- **The model to beat.** On a development slice it needed 1.326882 bits per byte against 1.399240 for PPMd. Limit: that figure is quoted from my notes for the later races, not from a registered test of this version, and I found none. In the race below, on 256 held rows of two more slices, it needed 1.385801 against 1.453406 for PPMd, a PPMd figure measured earlier. My notes of 5 Oct record a defect that costs it 1,802.5 bits more than a variant of version 3 on one of those slices.

**A later line raced against version 4 (4 to 5 Oct 2026)**

- **A lead too small to keep.** A new line I built to beat version 4 needed 1.379028 bits per byte on the same 256 held rows (526,080 bytes), ahead of version 4 by 0.006773. My own verdict was that it does not earn its time: a fixed setting of the same line beat it by 0.000112, three added side parts bought nothing, and a related version, ahead of version 4 by 0.003257, read "cannot tell yet". I closed it after one graded race. The raw race log is on another of my machines; the verdict text is what I read.

**On English text**

- **The same compressor work loses there.** On a different English test text, my notes record that my Baseline compressor work loses to 7-Zip PPMd by 0.351291 bits per byte. A later note in my list of defects reads PPMd stronger there and puts the gap at 0.370242. BMK 2 itself was not measured on that text like for like.

## Where it falls short

- BMK lost to plain counting, and at best tied it.
- BMK 2's leads over PPMd are on one fixed text sample. Version 2's lead was small, and it lost on the rows where PPMd spends the most bits.
- It needs far more computing time than PPMd.
- On English text my compressor work loses to PPMd, and BMK 2 was not measured there.
- Version 4's best figure is second-hand, from my notes, not a registered test.
- The raw logs are on another machine. I read the verdict notes for this card.

## Not done yet

- A like-for-like test of BMK 2 against PPMd on English text.
- Nobody outside my projects has re-run any of it.

## Check it yourself

- **Today.** Nothing you can run. The models and the text sample are private. 7-Zip PPMd is public.
- **On a call.** I can open the verdict notes with each registered test and its per-slice figures. The raw logs are on another of my machines.
- [How to check what this site says](../../VERIFY.md#mark-one)

## More

- [Model history](../MODEL_HISTORY.md)
- [Mark One](../../projects/mark-one.md), the Baseline programme BMK belongs to
- [Dead ends](../../projects/dead-ends.md#home-built-compressors-that-lost), with my other home-built compressors
- [Mark Two](model-mark-two.md), the model BMK was a test bed for
- [JMK](model-jmk.md), raced against BMK 2 in October
- [QMK-2](qmk-2.md), raced against PPMd on the same kind of slice
