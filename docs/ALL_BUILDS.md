# What I've built

My own builds in 2026, each with a line on what it is and a link where it has its own page.

## Language models and other research

- **[Project Hail Mary](../projects/hail-mary.md).** Language models built from scratch, aimed at learning far more from far less data and memory: the research since January 2026; the current English model since 18 Nov 2026. The project got its name on 19 Nov 2026 and does not yet match a standard model at equal compute.
- **[My training stack](../projects/hail-mary.md).** My own training stack, written from scratch in Rust and CUDA, has run about 1,050 clean GPU jobs on one home GPU since 19 Nov.
- **[Hail Mary results page and idea ledger](../projects/hail-mary.md).** A page that lists 66 separate lines of work, each with the word its own test printed, beside a ledger of 704 ideas, of which 54 have been put through a test since 20 Nov (tested, which is not the same as worked).
- **[A small exact test](../projects/hail-mary.md).** A model of mine with 1,985 weights raced four rival models on 4-byte windows of one corpus, scored exactly, and beat each of them on all 3 seeds; a small test on one machine, not a language-model result.
- **[A one-night English model](../projects/hail-mary.md).** A model of 25 million weights built in one night (26 to 27 Oct 2026) that wrote sentences after about 3 minutes and reached 0.960 bits per byte on unseen simple English after about 10 hours.
- **[A larger text model](../projects/hail-mary.md).** A Rust trainer I had built for a text model of about 200 million weights on my own card, paused on 27 Oct 2026 after about 421 million bytes, at 1.18 bits per byte on held-out science text and still babbling.
- **[Mark One](../projects/mark-one.md).** My own small language models (40M to 295M parameters), trained at home from 20 Apr to Sep 2026 and measured against standard compressors and against Qwen, whose code models beat them; paused.
- **[Mark One in Maltese](../projects/mark-one.md).** A Mark One model for Maltese that scored 1.2733 bits per byte over 512 windows, against 3.8010 for the general model on the same Maltese text (lower is better; recorded in its result files, not re-run since). About half of that set is parliament, gazette, court and law text, so it is not a score for Maltese prose.
- **[Forge](../projects/mark-one.md).** The earliest Mark One development model, 10.82M parameters, trained on an RTX 5070.
- **[A Python coding suite](../projects/mark-one.md).** 200 small generated Python tasks, frozen on 1 Aug 2026 and judged by running each program; my own suite, not a public benchmark.
- **[Compression demonstrator](../projects/compression-demo.md).** A compression result on Python source, packaged so a stranger could re-run it, with its losses stated beside its win; not published yet, so nobody can run it today.
- **[LIGHTGAP](../projects/lightgap.md).** My own text compressor, written from scratch in Rust from 25 Oct to 2 Nov 2026. On a development set of 3,653,983 characters of English Wikipedia it needed 1.152914 bits per character and decoded back exactly, against 1.7694 for 7-Zip PPMd (lower is better); that set helped choose the settings, so it is not a test, and the sealed test had not run as of 2 Nov 2026.
- **[Computing without binary](../projects/computing-research.md).** Tests in simulation of whether a computer could work on something other than binary; mostly negative, written down as negative, and no chip has been made.

## Exact AI (Project Alpha)

- **[Exact AI engine](../projects/exact-ai.md).** An engine that runs open language models so their answers can be re-made bit for bit on other machines and checked later, with a signed receipt and a one-pass audit; I have led the research since 9 Nov 2026.
- **[Windows pilot server](../projects/exact-ai.md).** A server that answers in the standard chat-completions format and signs every answer; tested in-house so far.
- **["Try it yourself" download](../projects/exact-ai.md).** A package meant to let someone outside the project re-make the engine's answers on their own machine; not yet run on a second machine or sent to anyone.
- **[Audit check](../projects/exact-ai.md).** A check that re-reads a logged answer in one pass.
- **[Model converter](../projects/exact-ai.md).** A converter that brings open Qwen2.5 models into the engine and checks them.
- **A separate testing step.** Re-counts each Project Alpha result from its files, against pass and fail lines written before the test, before I quote it; it is part of my project, not an outside check.
- **A scoring bench.** Scores my own models, Qwen models and standard compressors on the same bytes, with a scan for test text that leaked into training data.
- **[Goal 1 experiments](../projects/exact-ai.md).** Experiments toward the project's aim of 100 times more useful AI output from the same bytes of memory moved, with every token the same as an exact reference; the earliest milestone, due 18 Nov 2026, was not reached.

## Simulation

- **[QMK World](../projects/qmk-world.md).** An Earth-sized voxel simulator with Malta rebuilt 1:1 from public elevation and building-height data; it failed its own physics exam and is paused.
- **QMK World survey.** A survey of public simulation and graphics code for QMK World, with every repository's licence checked and the unclear ones read by hand from the licence text.

## Infrastructure, servers and data

- **[TETRA mesh](../projects/tetra.md).** An overlay network with four layers of encryption, built for distributed training from 11 to 14 Sep 2026; dormant, and never audited outside my projects.
- **[Baseline platform](../projects/mark-one.md).** A local multi-agent platform that runs on my own machines, started on 20 Apr 2026 and built side by side with Mark One.
- **Baseline toolkit.** Installers, a plugin system and a set of small utilities for the Baseline platform.
- **Constellation.** A live web map of the computers in my Baseline setup.
- **GPU chambers.** Packages that borrow a training PC's GPU for a job, then give it back.
- **Keeper.** A watchdog for long research runs that restarts a stopped process, never kills one, and backs off after fast crashes.
- **A watch window.** A live view of a running QMK model, made from files it already writes, that changes nothing in it.
- **A download store with receipts.** A record of each download, covering open models, public protein data and a few software tools, with a checksum receipt for every file.
- **An English and Maltese text pipeline.** Cleans, de-duplicates, licence-checks and splits English and Maltese text for training.
- **A programming teaching pack.** Teaching texts on programming, with a checksum manifest, for training models.
- **Licence-clear text sets.** Text sets for training, kept to sources whose licence allows it.
- **A synthetic text generator.** Makes repeatable synthetic training text, mostly in a legal style, with no real legal text in it.

## Experiments that went nowhere

- **[QMK and AMK](../projects/dead-ends.md).** Earlier learning models built under strict rules, which over about seven weeks never got past reading back what they had been fed; I changed the rules on 17 Nov 2026.
- **[QMK-1](../projects/dead-ends.md).** The earliest QMK model; a September audit found 1,263 confirmed findings in its code, grouped into 27 fixes, and found that the copy running was 43 hours older than the code.
- **[QMK-2](../projects/dead-ends.md).** A QMK model that lost to 7-Zip PPMd, 1.606522 bits per byte against 1.530961 on a registered test slice of 1,315,021 bytes.
- **[QMK-3](../projects/dead-ends.md).** My own written verdict of 2 Oct 2026: real but modest, not yet a capability, ten goals at 0 of 10. It added nothing to Jarvis's reader on the meaning label.
- **[A legal-text test](../projects/dead-ends.md).** On legal text held back from building (24 Sep 2026), a CPU-built model scored 0.7207 on rebuilding word pairs against 0.4947 for a word-frequency baseline, over 7,503 legal documents; not a legal-accuracy score.
- **[Mark One probes](../projects/mark-one.md).** Pre-registered experiments on Mark One, each with its kill rule written in advance; all four ended KILL, at small size.
- **[Home-built compressors](../projects/dead-ends.md).** Several of my home-built compressors lost to standard tools (7-Zip PPMd, lzma).
- **[An AlphaFold side line](../projects/dead-ends.md).** A standard AlphaFold 2 baseline ran bit-identical from run to run on the chains I tested, and none of my one-day tests of new ideas against it passed.
- **A COBOL translation check.** A test harness that checks Python translations of small COBOL programs, made by an open AI model, against a Python reference of what the COBOL should do, using tricky test inputs; the stage meant to run real COBOL was blocked at the compiler.

## Jarvis

- **[Jarvis](../projects/jarvis.md).** A WhatsApp booking assistant for Apex Dental, my dad's two dental clinics in Birkirkara, Malta. It books patients into the clinic's real diary, takes the EUR 20 booking fee in the chat and checks each patient message for red-flag symptoms before anything else; talking to real patients since at least 13 Sep 2026.
- **[Jarvis gateway](../projects/jarvis.md).** A gateway on the clinic's own phone line that fails closed: if Jarvis cannot answer, the patient gets one fixed reply and staff are flagged; about 3,700 lines with 238 tests.
- **[Jarvis's local reader](../projects/jarvis.md).** Three adapters on open models that read each patient message for meaning and feeling; in shadow mode it agreed with a larger hosted model on meaning in 77 percent of 643 replies (from the bot's own shadow log), short of the 95 percent it needs to take over.
- **[Jarvis evaluation set](../projects/jarvis.md).** Hand-built cases plus machine-picked moments where a chat went wrong, to tell whether a change makes Jarvis better or worse; on 12 Nov 2026, 217 of 477 passed (45 percent), as recorded in its own file, and the machine-picked cases have not been checked by a person yet.
