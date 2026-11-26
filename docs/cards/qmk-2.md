# QMK-2

QMK-2 was a model in the QMK line, the learning work before Project Hail Mary, scored as a text compressor against 7-Zip PPMd, and it lost.

| | |
|---|---|
| Project | QMK and AMK, the learning work before Project Hail Mary |
| Dates | September 2026; its notes are dated 24 Sep 2026 |
| Hardware | Two machines: its numbers were read three times on one and once on a second |
| Status | Retired, with the rest of the QMK and AMK line |

## What it was for

I scored QMK-2 the way a compressor is scored: the bits it needs for each byte of a fixed test text, where lower is better. 7-Zip PPMd is a standard compressor and the rival I measured it against.

## What it was trained and tested on

Two sets of test bytes, with 7-Zip PPMd scored on the same ones: a registered test slice of 1,315,021 bytes, and a whole draw of 19,417,730 bytes.

## Results

- **It lost to 7-Zip PPMd.** QMK-2 needed 1.606522 bits per byte against 1.530961 for 7-Zip PPMd on the registered test slice of 1,315,021 bytes, and 1.581544 against 1.459873 on 19,417,730 bytes. Lower is better, so it lost on both. One of my notes gives the slice as 1,314,944 bytes instead, a 77 byte difference I cannot explain from the notes.
- **The loss was broad.** In September 2026 it was behind PPMd on 124 of 128 held rows. Its numbers were read three times on one machine and once on a second, equal to the last digit. My notes do not say which version of QMK-2 the 124 of 128 is for. Recorded in QMK-2's own notes, not re-run since.
- **A simpler version lost by more.** A simpler version of QMK-2 scored 1.786743 against 1.530961 for PPMd on the registered slice (0.255782 behind), and 1.744015 against 1.459873 on the whole draw. Recorded in QMK-2's own notes, not re-run since.
- **A gap I withdrew.** My QMK-2 notes withdraw a gap of +0.213054 they had carried, because three early races had compared across different sets of bytes.

## Where it falls short

- It lost to 7-Zip PPMd on both test sets, and was behind on 124 of 128 held rows.
- My own records needed fixing: a gap had to be withdrawn because races compared different bytes, and two notes give the slice size 77 bytes apart.

## Not done yet

- Nothing here has been re-run since September 2026, and nobody outside my projects has run it.

## Check it yourself

7-Zip PPMd is a public tool, but the test bytes and QMK-2 are private, so there is nothing you can run. On a call I can open QMK-2's notes and the result lines behind these numbers. [How to check what this site says](../../VERIFY.md#dead-ends) covers it under dead ends.

## More

- [Dead ends](../../projects/dead-ends.md), where QMK-2's loss sits with my other home-built compressors that lost
- [QMK and AMK](qmk-and-amk.md), the card for the whole line
