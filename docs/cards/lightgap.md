# LIGHTGAP

My own text compressor, written from scratch in Rust and measured on a standard English benchmark.

| | |
|---|---|
| Project | LIGHTGAP |
| Dates | 25 Oct to 2 Nov 2026, 440 commits. Results as of 2 Nov 2026. |
| Hardware | My PC. The decoding time was taken on a busy PC. |
| Status | Development results; the sealed test had not run as of 2 Nov 2026 |

## What it was for

A text compressor of my own, built from nothing and measured on a public benchmark beside the standard compressors on my PC. The test that counts is pre-registered, and it had not run as of 2 Nov 2026, so every number on this card is a development number.

## What it was trained and tested on

- It is written from scratch in Rust with nothing but the standard library: no outside libraries, and no downloaded model or code. The one download is the test text itself, as data.
- The text is enwik8, the opening 100 MB of English Wikipedia and a standard compression benchmark, mapped to 27 symbols: the 26 letters and the space.
- My development set, VALID27, has 3,653,983 characters. It helped choose the settings, so it does not count as a test.
- Scores are in bits per character, and lower is better.

## Results

- **The whole development set.** It coded all of VALID27 in 526,591 bytes, which is 1.152914 bits per character, and a separate process decoded it back exactly. On the same text, 7-Zip PPMd (order 20), the best standard compressor on my PC, scored 1.7694 bits per character. Limit: a development number, not a test, because VALID27 helped choose the settings.
- **Beside standard compressors.** A harness ran each compressor on the opening 200,000 characters of VALID27 and checked every round trip. Mine needed 1.1572 bits per character (95% interval 1.0901 to 1.2357), against 1.9704 for PPMd, 2.2101 for brotli, 2.2357 for bzip2, 2.3864 for zstd, 2.3918 for xz and 2.6779 for gzip. Limit: this is a shorter piece of text than the full development set, so these are not the same numbers as above.
- **A control.** The same program, with its learned parts left at their untrained starting point, scored 1.364724 bits per character on VALID27. So the learning is what takes it from 1.364724 down to 1.152914.
- **A sanity check.** Random data does not shrink: 1,000,000 bytes of it became 1,000,057 bytes.

## Where it falls short

- These are development numbers. VALID27 helped choose the settings, so it does not count as a test.
- Decoding is slow: 13,116.8 seconds for VALID27, about 279 characters a second, on a busy PC.
- Getting under 1.3 bits per character is not new. Published neural models went under it on similar Wikipedia text in 2016, and large language models report about 0.71 bits per character (LLaMA-7B, 2023). This is a compressor I built from nothing, not a record.
- It does not "beat Shannon's entropy". What it shows is that this one text needs at most 1.152914 bits per character. That tightens Shannon's 1951 estimate of about 1.3 for English, but just on this development text.

## Not done yet

- The test that counts is pre-registered: a sealed 5 MB of enwik8 that nothing has read, with the pass line written down before the run. The line is under 1.300 bits per character, decoded exactly. It had not run as of 2 Nov 2026, so there is no test result yet.
- Nobody outside my projects has run it.

## Check it yourself

- **Today.** enwik8 is a public benchmark, so the source text is public. The code is private, so my side of every number rests on my own runs.
- **On a call.** I can open the records behind these numbers.
- [How to check what this site says](../../VERIFY.md#lightgap)

## More

- [The LIGHTGAP page](../../projects/lightgap.md)
