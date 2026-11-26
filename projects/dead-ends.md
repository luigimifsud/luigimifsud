# Dead ends

Things that did not work, kept here on purpose. All of them are stopped, and each one is written up as it came out.

My scoreboard has a line I go by: "A named wall is a result, not a failure." If I showed you just what worked, you would have no way to judge how I handle what does not. A result I had to take back tells you more about how I work than one more success.

## The earlier learning models (QMK and AMK)

Over about seven weeks, the learning models I built under strict rules, QMK and AMK, never got past reading back what they had been fed. The best did no better than a plain lookup table on text it had seen. On 17 Nov I changed the rules. My learning work now goes on in [Project Hail Mary](hail-mary.md).

What they showed on the way, starting with the losses:

- **QMK-2 lost to 7-Zip PPMd.** 1.606522 bits per byte against 1.530961 on a registered test slice of 1,315,021 bytes, and 1.581544 against 1.459873 on 19,417,730 bytes. Lower is better.
- **QMK-3 added nothing to Jarvis's reader.** On the meaning label, on 86 held-out chat replies, the reader scored 0.721 with it and 0.721 without, and gave it a weight of 0.001. On 147 phone replies it scored 0.585 with it and 0.578 without, with a weight of 0.0. A plain byte predictor scored 0.733 on the chats.
- **My own verdict on QMK 3, written on 2 Oct:** real but modest, not yet a capability, ten goals at 0 of 10.
- **A test on legal text (24 Sep).** On legal text held back from building, a model built on the CPU scored 0.7207 (plus or minus 0.0046) on rebuilding word pairs, against 0.4947 (plus or minus 0.0048) for a word-frequency baseline, over 7,503 legal documents. It is not a legal-accuracy score.

Two checks that caught my own mistakes:

- **A detection rule of mine.** Tested against 3,600 matched control runs, its real false-alarm rate was 0.073611, where it had reported 0.006780. I retracted it.
- **A September audit of QMK-1.** It found 1,263 confirmed findings in its code, grouped into 27 fixes, and found that the copy running was 43 hours older than the code.

## PhotoLocator

In June I built PhotoLocator, a tool to guess where a photo was taken. An early benchmark claim for it turned out to be false: a later check found the core of it unproven on hard photos. An honest measure showed it could often narrow a photo down to the right country, which is a long way from knowing where it was taken. Selling it was judged a dead end, and I stopped. The code is on another machine and was not re-checked for this page, so I give no numbers for it.

## The AlphaFold side line

Inside Project Alpha I tried a side line on protein structure. A standard AlphaFold 2 baseline ran bit-identical from run to run on the chains I tested. Then I tried new ideas against it in one-day tests, and none of them passed. I closed it there.

## Home-built compressors that lost

Several of my home-built compressors lost to standard tools, 7-Zip PPMd and lzma. QMK-2's loss is above. Even the compressor that held up on Python source loses on English text, to PPMd by 0.351291 bits per byte. Its win, with all its limits, is on the [compression demonstrator](compression-demo.md) page.

## The "beats gzip" claim

Early in Mark One I had a "beats gzip" claim. It did not hold up, and I retracted it in writing. The code result I cite now is a different measurement, on held-out code cleaned of overlap with the training data, and it carries its own caveat. It is on the [Mark One](mark-one.md) page.

## More walls, on the pages they belong to

- Mark One lost to the Qwen models it was compared against ([Mark One](mark-one.md)).
- Project Hail Mary lost its one equal-time race against a standard model, and is behind my own earlier model ([Project Hail Mary](hail-mary.md)).
- QMK World failed its physics exam ([QMK World](qmk-world.md)).
- Computing without binary is mostly negative, in simulation ([computing research](computing-research.md)).
- Project Alpha missed its earliest milestone, due 18 Nov 2026 ([exact AI](exact-ai.md)).

## Check it yourself

- **On a call.** I can open the written verdicts and retractions behind each of these, except PhotoLocator, whose files are on another machine.
- **What you cannot check yet.** These are in words because they happened, and there is nothing to run. [How to check what this site says](../VERIFY.md#dead-ends) says the same.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/dead-ends.md
