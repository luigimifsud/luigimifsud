# Compression demonstrator

A compression result on Python source code, packaged so a stranger could re-run it. The package is not published yet, so nobody outside my projects can run it today. Every number below was recorded on my machine and not re-run for this page.

**Status:** working on my machine, not published.

## What it is

A small package meant to let someone check one claim about compressing Python source code without trusting me.

## Why it exists

I had been wrong about compression before. Mark One had an early "beats gzip" claim that I retracted in writing, and several of my home-built compressors lost to standard tools. So for this result I wanted something a stranger could run, where the losses are stated in the same place as the win.

## What I built

- The compressor and its decoder.
- A held-out test set.

## Results

- On 30 Python files it scored 0.993994 bits per byte, against 1.265092 for 7-Zip PPMd at its best order. All 30 of 30 files came back identical after the round trip.
- On a held-out set, 30 of 30 decoded identical, and the output was 1.32 times smaller than lzma -9.

## Its limits

These limits go with the result every time I state it:

- The margin falls 31 percent when PPMd gets its best setting.
- On English text it loses to PPMd by 0.351291 bits per byte.
- It is much slower to encode.
- Peak memory is 1,751 MiB, against 16 MiB.

Its wins are on Python source code. On English it loses, so I do not call it a general-purpose compressor.

## Not done yet

- The package is not public, so nobody outside my projects has run it. [How to check what this site says](../VERIFY.md#compression-demonstrator) goes through what you can and can't check.

## Check it yourself

- **Today.** Until the package is public, these numbers are my own measurements.
- **Publishing it.** Publishing the package would let anyone re-run it and compare what it prints with the numbers on this page. It is not published yet.
- **On a call.** I can open the recorded result files behind these numbers.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/compression-demo.md
