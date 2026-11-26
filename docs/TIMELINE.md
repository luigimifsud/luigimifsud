# Timeline

As of 26 Nov 2026.

Dated events from my notes and result files, from January 2026 to today: builds started, results, retractions, rule changes and pauses. Where my notes give just a month, so does this page. The results, with their limits, are in [RESULTS.md](RESULTS.md).

## January 2026

- Jan: the research that is now [Project Hail Mary](../projects/hail-mary.md) starts: language models built from scratch. The project gets its name on 19 Nov.

## April 2026

- 20 Apr: earliest commit of Baseline, where I built [Mark One](../projects/mark-one.md), my own small language models.

## June 2026

- 4 Jun: I start PhotoLocator, a tool to guess where a photo was taken.
- 8 Jun: selling PhotoLocator is judged a dead end, and I stop. An early benchmark claim for it had turned out to be false.

## July 2026

- 18 Jul: I commit Forge, my early from-scratch model and the code to train it. Its 85.56 million parameter run wrote code-shaped noise, not working code.
- 23 Jul: I start two training runs of a 104.5 million parameter model on the RTX 5090. I give no score for either.
- 25 Jul: my 40.6 million parameter model reads 3.27 times smaller than gzip on 96 windows.
- 25 to 27 Jul: I find six places where I had set up a rival compressor too weakly, each time in my favour. I now push a rival's settings to the tool's documented limit before I use its number.
- 26 Jul: after I remove the windows that overlapped my training text, the headline falls to 2.49 times.
- 26 Jul: the 40.6 million parameter model gets 0 of 200 completions of Python's own test files exactly right.
- 26 Jul: on 96 held-out windows of web text, the 40.6 million parameter model is 1.2999 times smaller than brotli at its highest setting. The compressors start cold on each short window, so this shows what the model learned, not a better general-purpose compressor.
- By 27 Jul: compared against brotli -q 11, the strongest of nine standard compressors, the headline falls to 2.08 times. This is the number I cite, with the same cold-start limit.
- 27 Jul: my 295 million parameter model finishes 200,000 training steps, and I keep training it.
- 27 Jul: I write that my model's lead over brotli shrinks on longer text, and I name a cause.
- 28 Jul: a third measurement, on 770 KB, puts the lead at 1.450 times, so I withdraw the trend and the cause.
- 28 Jul: I code and decode 769,738 bytes of held-out text with the 40.6 million parameter model and get the same bytes back. The model's own size is not counted.

## August 2026

- Aug: a claim from my small exact test, later narrowed after a check.
- 1 Aug: I freeze a suite of 200 small generated Python tasks, judged by running each program.
- 1 Aug: on 6 very small Python tasks, the 295 million parameter model gets 4 of 6 right within 24 tries. Six tasks are too few for a rate.
- 1 Aug: Qwen2.5-Coder-7B beats a snapshot of the 295 million parameter model on 128 held-out windows of my training mix.
- 1 to 4 Aug: the 295 million parameter model's runs on the 200-task suite end at 164 of 200 with 8 tries each. It is not a public benchmark, and no other model was scored on it.
- 2 Aug: I build a second suite, of 775 Python tasks.
- 4 Aug: on 360 items that need a second variable name, the 295 million parameter model never ranks the right opening byte at the top.
- 8 Aug: I train my Maltese model, 104.5 million parameters.
- 8 Aug: on 512 fixed held-out windows the 295 million parameter model scores 1.3186, not the training log's best of 1.184, so I stop quoting the log's best.
- 9 Aug: a model trained with Maltese as one row in six is 0.0572 worse on general text, over the 0.05 I had registered, so I record that prediction as failed.

## September 2026

- 7 Sep: the compression demonstrator's held-out set: 30 of 30 decoded identical, 1.32 times smaller than lzma -9 (an older version of the compressor). That is on Python; on English it loses to PPMd.
- 8 Sep: earliest commit of [Jarvis](../projects/jarvis.md).
- 8 Sep: on 20 Python standard-library files, my compressor is 1.1411 times smaller than the strongest rival I could run. I could not run lpaq1, paq8, zpaq or cmix, and with its decoder's size counted it needs more than 7-Zip PPMd.
- By 11 Sep: six simulation scripts on computing without binary; a three-level cell loses on transistor count.
- 11 to 14 Sep: TETRA mesh, an overlay network with four layers of encryption (file dates).
- 13 Sep: by this date at the latest, Jarvis is talking to real patients.
- 20 Sep: fixing the bug blamed for holding QMK-1's reasoning back changes its score by exactly zero.
- 20 Sep: a QMK-1 word-pair score grows with the text it reads, but the gain per doubling falls from 0.0087 to 0.0033.
- 21 Sep: three extra parts added to QMK-1 score, together, below its base alone.
- 22 Sep: an audit of QMK-1, which read its files without changing them, answers ten questions about it: 8 NEGATIVE, 2 UNKNOWN, none POSITIVE.
- 22 Sep: a fix makes one step of QMK-1 give the same choice when a run is repeated. That shows repeatability, not a better choice.
- 24 Sep: The Lawyer, a model built on a CPU from 7,503 legal documents, is tested on legal text held back from building.
- 24 Sep: rewiring a copy of QMK-1's code makes its self-check pass on 19 of 40 runs, against 40 of 40 for the original.
- 25 Sep: a count of solved QMK-1 problems is withdrawn, because it counted any output.
- 26 Sep, 17:30: [QMK World](../projects/qmk-world.md) at version 0.2, with a desktop window.
- 27 Sep: QMK World's physics exam: 10 of 42 items agree with the real Earth, a failing grade.
- 29 Sep: QMK-1 is switched off.
- 29 Sep: in QMK World, a weather test passes 29 of 30, a water test 11 of 13 and a rigid-body test 3 of 5.
- 30 Sep: 568 of 568 tiles of the 2012 and 2018 height surveys fetched for QMK World.
- 30 Sep: the d-orbital piece of QMK World's chemistry is merged. No later exam is in my notes.
- Sep: an audit of QMK-1 finds 1,263 confirmed findings in its code, grouped into 27 fixes, and a running copy 43 hours older than the code.
- Sep: QMK-2 is behind 7-Zip PPMd on 124 of 128 held rows, and its ledger withdraws a gap it had carried.
- Sep: a looser version of my detection rule catches no more at the same false-alarm rate, and my result file calls the premise false.
- Sep: Mark One is paused.

## October 2026

- 1 Oct: QMK World's shore check fails at 1 of 12 places.
- 1 Oct, 23:51: a QMK World merge draws all 112,147 Malta and Gozo buildings at their measured heights, against 51,414 in the version before. About 20 to 30 real parts in deep shadow are wrongly dropped (an estimate).
- 2 Oct: my written verdict on QMK 3: real but modest, not yet a capability, ten goals at 0 of 10.
- 2 Oct: QMK World at version 0.19, after 27 merges.
- 3 Oct: the morning's QMK 3 readings do not survive the day. A trivial counting method scores 90 of 96 on the same test, and none of the runs had been on the GPU as I had believed, so every CPU run is stopped.
- 6 Oct: a pre-registered race of four QMK 3 variants against fake-version controls: no variant qualifies at any of four settings.
- 7 Oct: QMK World is paused.
- 12 to 18 Oct: from the bot's own logs, Jarvis has 388 chats with 269 phone numbers; 54 payment holds are created, and 22 become bookings.
- 13 Oct: versions 1 and 2 of Jarvis's small local reader.
- 13 Oct: QMK-3 tested on its own as a reader of replies: on the meaning label, above guessing and below every plain predictor; on the feeling label, no better than guessing.
- 14 Oct: version 3 of the small reader, and its score file.
- 14 Oct: the daily shadow-mode comparison with a larger hosted model starts. It has a line for every day up to 25 Nov.
- 25 Oct to 2 Nov: I write [LIGHTGAP](../projects/lightgap.md), my own text compressor, from scratch in Rust (440 commits). On a development set of 3,653,983 characters of English Wikipedia it needs 1.152914 bits per character and decodes back exactly, against 1.7694 for 7-Zip PPMd. That set helped choose the settings, so it is not a test, and the sealed test had not run as of 2 Nov.
- 26 to 27 Oct: I build a 25 million weight English model in one night. It ends at 0.960 bits per byte (plus or minus 0.050) on a harder held-out set, by its training log's own check.
- 27 Oct: the 25 million weight model is put away.
- 27 Oct: I have a trainer built for a text model of about 200 million weights. In a 5 minute trial its judge's word moves from 'babbling' to 'sentences'.
- 27 Oct: I pause that run the same day, at 1.18 bits per byte on held-out science text and still babbling.

## November 2026

- 9 Nov: [Project Alpha](../projects/exact-ai.md) starts, and I lead the research.
- 9 Nov: AMK stops; it has been resting since.
- 12 Nov: Jarvis's evaluation set: 95 of 114 hand-built cases pass, and 217 of 477 overall. The 363 machine-picked cases have not been checked by a person.
- 12 Nov: I check that evaluation against two bots that do nothing useful. They pass 1 and 7 of the 114 hand-built cases.
- 13 Nov: fixes take Jarvis's exam from 217 to 241 of 477, and its hand-built gate to 114 of 114. The fixes were made to pass known cases, so this is not a score on unseen chats.
- 14 Nov: 16 exam cases for Jarvis's offer check are written before the check exists. 15 fail on that day's code.
- 14 Nov: the clinic's owner reads 25 of the offer check's exam cases, and 3 of his answers change the check.
- 14 Nov, 21:20: Jarvis's red-flag check goes live.
- 17 Nov: I change the rules for the QMK and AMK lines, after about seven weeks in which they never got past reading back what they had been fed.
- 17 Nov: the English model of Project Hail Mary is designed.
- 17 Nov: a review re-opens 21 of my own chip numbers and finds 1 bad, which I fix.
- 17 Nov: my AMK notes record that a 16-byte lookup table beat every version at every size.
- 18 Nov: the English model starts training.
- 18 Nov: Project Alpha's earliest milestone toward its goal, due this day, is not reached.
- 18 Nov: I find that 334 of the 390 items I had drawn from a public reasoning set can be answered by lookup alone.
- 18 Nov: one reading of a new story makes an early snapshot of the English model prefer that story's new names, but it cannot spell them back (0 percent).
- 19 Nov: [Project Hail Mary](../projects/hail-mary.md) gets its name. My training stack has run about 1,050 clean GPU jobs since this day.
- 20 Nov: ideas from my ledger of 704 start going through tests. 54 have been tested since.
- 21 Nov: the one equal-time race so far: a standard model scores 1.2878 bits per byte on 256 held-out story windows and mine 1.3900, so mine loses by 0.1021.
- 21 Nov: Jarvis's exam, now 512 cases, passes 283 with the settings Jarvis runs live. The hosted model is off in this exam, so the paths that reach it are not measured.
- 21 Nov: a Jarvis test run records 12,611 passed and 4 known failures.
- 21 Nov, 16:50: Jarvis's offer check, and a check that answers the patient's question before making an offer, go live.
- 21 Nov: on a live sample of 40 cases, Jarvis passes 32, one fewer than on 13 Nov. No run was made with the new checks off, so the slip cannot be assigned to them.
- 22 Nov: at its third training turn, the English model keeps 25 percent of a story's names into its last three sentences, against 72 percent for real stories. On 10 samples, measured early and not repeated on the later model.
- 23 Nov: the forecaster race on generated streams is read: best in some phases, below a particle filter on erratic-point streams, and about 1,000 times slower than a Kalman filter on the point.
- 23 Nov: Jarvis's live-settings exam score is 288 of 512.
- 25 Nov: my logic test: none of 8 kinds of logic question learned.
- 25 Nov: the last day in the shadow log so far. Over 643 replies, version 2 of the reader agrees with the hosted model on meaning in 77 percent, against a bar of 95 percent (from the bot's own log). Agreement with a hosted model is not accuracy.
- 26 Nov, 06:45: the forecaster is packaged so someone else can run it. It re-makes my race results to within 0.00000000002, not bit for bit. Nobody else has run it yet.
- 26 Nov, 10:12: the English model has 37.6 hours of training and scores 1.1571 bits per byte on 256 held-out story windows. One run, and its curve is flat.
- 26 Nov, 10:13: a larger version of the English model stops early in a short probe, and I do not queue its long run.
- 26 Nov, 11:41: on a small test bench, my model is 0.0169 bits per byte worse than a standard model, and the rule prints 'cannot tell'.
- 26 Nov, 13:41: Project Alpha has 572 logged runs and 560 report files since 9 Nov.
- 26 Nov, 15:44: a re-run of the logic test repeats the 25 Nov result.
- 26 Nov, 16:09: a stability change: 3 of 3 one-hour runs finish with no bad step. One draw each, so luck is not ruled out.
- 26 Nov, 17:27: 22 single changes to a small standard model graded: 12 worse, 6 better, 4 could not be told apart, on tiny models whose results did not always carry to the card.
- 26 Nov: Jarvis has 3,078 commits and is still shipping.
