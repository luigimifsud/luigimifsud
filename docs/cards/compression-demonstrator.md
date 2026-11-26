# Compression demonstrator

A compressor for Python source code, packaged so a stranger could re-run it, from the research I did under the name Baseline before Project Alpha.

| | |
|---|---|
| Project | Baseline research, alongside Mark One |
| Dates | Results recorded 7 to 11 Sep 2026 |
| Hardware | My own machine, with CPython 3.14.5 |
| Status | Not published. It runs on my machine. |

## What it was for

I had been wrong about compression before: Mark One's early "beats gzip" claim was retracted in writing, and several of my home-built compressors lost to standard tools. So I wanted one compression claim a stranger could check without trusting me, with the losses in the same place as the win. It compresses Python source and gives back a normalised form of each file, not the file as written. My own notes say the strongest part of this work is the checking, not the ratio.

## What it was trained and tested on

Three sets of Python source:

- 30 Python standard-library files (756,922 bytes). These files are public.
- A held-out set of 30 Python files (524,045 bytes after normalising) that are not published. The compressor's settings were fixed on a different set of 30 files before this set was encoded, and no setting was chosen on it.
- 20 Python standard-library files (542,523 bytes after normalising), joined into one stream.

On each set, every file was decoded back and compared. Normalising drops comments and formatting.

## Results

Lower bits per byte is better. Every number here was recorded on my machine and not re-run since.

- **Standard-library files.** On the 30 standard-library files it needed 0.993994 bits per byte, against 1.265092 for 7-Zip PPMd at its best order, and 30 of 30 files came back identical to their normalised form after the round trip. Limits with it: the margin falls 31 percent when PPMd gets its best setting; on English text it loses to PPMd by 0.351291 bits per byte; it is much slower to encode; its peak memory is 1,751 MiB, against 16 MiB; and it is not published, so nobody outside my projects can run it today.
- **Held-out files.** On the 30 unpublished files it produced 796,328 bits, and all 30 decoded from the compressed file alone back to the same normalised text. 7-Zip PPMd at its best setting needed 966,656 bits, so mine was 1.2139 times smaller. At a weaker PPMd setting the gap looked larger, and I report the smaller one. An older version (837,504 bits, 7 Sep 2026) came out 1.32 times smaller than lzma -9 on this set; the later notes give no lzma row. Limits with it: I ran at least seven versions of the compressor on this set and quote the weakest of them (the best was 767,424 bits); comments and formatting are not kept; nobody else can re-run this set, because the files are not published. The other limits hold here too: the margin falls 31 percent when PPMd gets its best setting, it loses to PPMd on English by 0.351291 bits per byte, it is much slower to encode, and its peak memory is 1,751 MiB against 16 MiB.
- **Against the strongest rival I could run.** On the 20 standard-library files, it needed 1.0060 bits per byte against 1.1479 for a context-mixing compressor built in my own project, which is 1.1411 times smaller (12.36 percent fewer bits). Limits with it: I could not run lpaq1, paq8, zpaq or cmix, and any of them may beat that rival. This is one set of files in one Python version. It still loses to PPMd on English by 0.351291 bits per byte, it is much slower to encode, its peak memory is 1,751 MiB against 16 MiB, and it is not published, so nobody outside my projects can run it today.
- **Counting the decoder.** On the same 542,523 bytes, the decoder program is 83,932 bytes, so the total is 152,151 bytes. That is more than the 84,957 bytes 7-Zip PPMd needs on the same data. It also returns a normalised form of each file, not the file as written: comments and formatting are 20.8 percent of the characters in these files. For anyone who needs the exact original file, that rules it out today. The decoder also needs the same Python version.

## Where it falls short

- On English it loses to PPMd by 0.351291 bits per byte, so I do not call it a general-purpose compressor.
- Counted together with its own decoder, it needs more bytes than 7-Zip PPMd on the 20 standard-library files.
- It gives back a normalised file, not the original.
- It is much slower to encode, and its peak memory is 1,751 MiB against 16 MiB.
- The margin over PPMd falls 31 percent when PPMd gets its best setting.
- I could not run lpaq1, paq8, zpaq or cmix against it, and any of them may beat the rival I did run.
- It is tested on Python source alone, in one Python version.

## Not done yet

- Publishing the package, so someone outside my projects can run it.
- A run by anyone outside my projects.
- A comparison with lpaq1, paq8, zpaq or cmix.

## Check it yourself

Nothing today. The package is not published, so nobody outside my projects can run it, and the held-out files are not published either. If I publish the package, the standard-library result is the part a stranger could re-run, because those files are public. On a call I can open the recorded result files behind each number. [How to check what this site says](../../VERIFY.md#compression-demonstrator) says the same.

## More

- [The compression demonstrator page](../../projects/compression-demo.md)
- [Mark One](../../projects/mark-one.md), the research it came out of
