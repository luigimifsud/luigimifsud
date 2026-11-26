# How to check what this site says

As of 26 Nov 2026.

Everything on this site was built and measured inside my own projects, and nobody outside them has reproduced a result yet. So this page goes claim by claim. For each one it says what you can open or run yourself today, and what you can't check yet. When something becomes checkable, I'll move it up and change the date at the top.

## What you can check today

- **Jarvis on WhatsApp.** The clinic Jarvis works for is real, and its website is live at [apexdentalmalta.com](https://www.apexdentalmalta.com). You can message the clinic on WhatsApp from its website and watch Jarvis answer.
- **This repo's own history.** Once this repo is public at [github.com/luigimifsud/luigimifsud](https://github.com/luigimifsud/luigimifsud), its commits show when each write-up was added and changed. That dates the write-ups, not the work behind them.
- **On a call.** I can share my screen and open the log or result file behind a number on this site, and re-count commits or run tests while you watch. Code, design details and patient data stay off screen. You see the file, but it is still my file on my machine.

That is the whole list for now. The rest of this page is about what can't be checked yet.

## Not checkable by an outsider yet

- **Project Hail Mary.** The design is private, and the results come from my own runs.
- **The exact AI results.** They were measured on the project's own test machines and on cloud machines, and re-counted by a separate testing step inside the project. Nobody outside the project has run them.
- **Jarvis's usage numbers.** They come from the bot's own logs, not an audit. Its code is private.
- **Commit and test counts.** The repos are private. Commit counts were re-counted from each project's git history; most test counts are what each project's own files recorded, not re-run.
- **Mark One and the compression demonstrator.** Mark One was trained at home, and the demonstrator's numbers were recorded on my machine. The demonstrator was packaged so a stranger could re-run it, but it isn't published, so nobody can run it today.
- **LIGHTGAP.** Its numbers are development numbers from my own PC, and its code is private. The sealed test had not run as of 2 Nov 2026.
- **The dead ends.** They are in words because they happened. There is nothing to run.

## Project Hail Mary

**What the site says.** The aim, the pace of the work, early results with their limits (arithmetic, a forecaster, a comparison with a compressor, a small exact test), the losses (the equal-time race, and my own earlier model of the same size), two output samples exactly as printed, and that it does not yet match a standard model at equal compute. See [the Hail Mary page](projects/hail-mary.md).

**What you can check today.** Nothing an outsider can run or open. I keep the design private for now. On a call I can open the job log and the result files, with the design kept off screen.

**Not checkable yet.** All of the results. They come from my own runs: the arithmetic result is one seed, a preview, and the race was one run each. Training runs on the card are not repeatable yet: the same settings and seed have ended differently on replay. So even I can't promise the same run twice, which is one more reason none of this is checkable from outside today.

**What would make it checkable.** Nothing is ready yet. SHA-256 hashes of the locked pass-rule files and of the result files behind each Hail Mary result would let this repo's history date them, with the design kept private. They are not published yet.

## Exact AI

**What the site says.** The [exact AI page](projects/exact-ai.md) quotes every engine result I can quote, word for word as my project records them, grouped as exactness across machines, large models, the pilot, speed and other tools, each with the scope or limits that go with it.

**What you can check today.** Nothing you can run or open yourself yet. On a call I can open the record behind a result and the result file it points to. You can't run the engine yourself yet.

**Not checkable yet.** Every number in those results, by you on your own machine. The pilot server has been tested in-house so far. The "try it yourself" download exists, but it has not been run on a second machine or sent to anyone.

**What would make it checkable** (not done yet):
- Run the "try it yourself" download on a second machine, then send it to people outside the project and publish what they got, whatever it is.
- A short demo video: an answer, its signed receipt, one changed word, and the re-check run on the changed answer.
- A "check a receipt yourself" page with sample signed answers and the public key, so a reader can check a signature with a standard tool. It is not published yet.
- A SHA-256 hash of the result file behind each quoted result, so this repo's history dates the evidence and, on a call, you can hash the file I open and compare. The hashes are not published yet.

## Jarvis

**What the site says.** Jarvis is a WhatsApp booking assistant, live with Apex Dental's patients since at least 13 Sep 2026, with usage numbers from the bot's own logs and the size of the codebase. See [the Jarvis page](projects/jarvis.md).

**What you can check today.** The clinic is real and its website is live at [apexdentalmalta.com](https://www.apexdentalmalta.com). You can message the clinic on WhatsApp from its website and watch Jarvis answer.

**Not checkable yet.** The usage numbers, which come from the bot's logs and have not been audited. The evaluation results and the commit and test counts, because the repo is private. Patient chats and screenshots of the bot or the staff portal are never shown. That is a privacy rule, not a gap I plan to close.

**Who made the commits.** Commits on Jarvis show "Jonathan Mifsud" because I committed under my dad's git identity. I build with AI coding tools, and the commit history shows that too.

## Mark One

**What the site says.** My own small language models trained at home, the held-out code result against standard compressors with its caveat, the Maltese result, the coding results, and the losses I keep on record. See [the Mark One page](projects/mark-one.md).

**What you can check today.** Nothing you can run.

**Not checkable yet.** All of it was measured at home, and the scoreboard is private. The coding suite is my own, not a public benchmark, and no rival was run on it.

**What would make it checkable.** Publishing the 192 held-out code windows, so anyone can run brotli -q 11 and the other standard compressors on them and check that side of the comparison. They are not published yet.

## Compression demonstrator

**What the site says.** A compression result on Python files, packaged so a stranger could re-run it, with its limits stated beside it. It is not published yet. See [the demonstrator page](projects/compression-demo.md).

**What you can check today.** Nothing. The package is not published, so nobody outside my projects can run it.

**What would make it checkable.** Publishing the demonstrator, so anyone can re-run it and compare their numbers with mine. It is not published yet.

## LIGHTGAP

**What the site says.** My own text compressor, written from scratch in Rust. On a development set of 3,653,983 characters of English Wikipedia (enwik8, mapped to 26 letters and the space), it needed 1.152914 bits per character and decoded back exactly, against 1.7694 for 7-Zip PPMd. Beside that: a harness run against PPMd, brotli, bzip2, zstd, xz and gzip, a control, a random-data check, and the limits, including that these are development numbers. See [the LIGHTGAP page](projects/lightgap.md).

**What you can check today.** Nothing you can run. enwik8, the text it was measured on, is a public benchmark, but my compressor is not: its code is private.

**Not checkable yet.** Every number. They come from my own runs on my PC, and they are development numbers: the development set helped choose the settings. The test that counts is a sealed 5 MB of enwik8 with its pass line written down before the run (under 1.300 bits per character, decoded exactly), and it had not run as of 2 Nov 2026.

## Computing without binary

**What the site says.** Tests of computing beyond binary, all in simulation, mostly negative and written down as negative. No chip has been made. See [the computing page](projects/computing-research.md).

**What you can check today.** Nothing you can run. Its own README says it plainly: "No watt, no wire, no chip is measured here".

**Not checkable yet.** Every simulation result. A review on 17 Nov re-opened 21 of my own chip numbers and found 1 bad, which was fixed. That review was inside my project too.

## QMK World and TETRA mesh

**What the site says.** What each one is and its status, QMK World's exam result, and TETRA's test count. See [QMK World](projects/qmk-world.md) and [TETRA mesh](projects/tetra.md).

**What you can check today.** Nothing you can open yet. QMK World's Malta is built from public elevation and building-height data, so the inputs are public, but the world itself isn't.

**Not checkable yet.** The repos are private. TETRA's test count is what its own status file recorded, not re-run. Neither has been audited by anyone outside my projects.

**What would make it checkable.** A commit-date record for each project, Jarvis included: earliest and latest date, count and the author name the commits show, with no code and no commit text. It is not published yet.

## Dead ends

**What the site says.** What didn't work and why I stopped, including the earlier learning models (QMK and AMK) with their numbers, and the checks that caught my own mistakes. See [the dead ends page](projects/dead-ends.md).

**What you can check today.** Nothing to run. They are here because they happened, and because a result that went against me is still a result.

## How I check results before I quote them

- Pass and fail lines are written before a test runs. In Project Hail Mary, each pass rule is locked with a hash before any result is read; a change is a dated, hashed amendment, never an edit.
- Tests are checked by planting deliberate errors. In Hail Mary, three of them caught 15 of 15, 9 of 9 and 26 of 26, and one test reader that caught 84 of 89 was marked not ready.
- A separate testing step re-counts a result from the files before I quote it. It is part of my project, so it catches my mistakes, but it is not an outside check.
- When a result breaks its own rule, it is void. A different forecaster race, not the 12 of 27 result, looked good, but one check file's last line broke the locked rule, so the whole race is void and its numbers are never quoted.
- Results that went against me stay on this site, next to the ones that went my way.
- Exact AI results are quoted word for word as my project records them, never reworded or made bigger.
