# QMK World

QMK World is a simulator, not a model: an Earth-sized simulated world with Malta rebuilt 1:1, made as a place for my learning models to learn physics in.

| | |
|---|---|
| Project | QMK World, built beside the QMK line |
| Dates | 26 Sep to 7 Oct 2026. Version 0.2, with a desktop window, at 17:30 on 26 Sep; version 0.19, after 27 merges, in my notes of 2 Oct. |
| Size | About 80,000 lines of Rust and 28,000 of Python. That is code, not a model size. |
| Status | Prototype, paused since 7 Oct 2026 |

## What it was for

A world real enough for a learning model to learn physics in: laws go in, outcomes come out, and lessons grade the world against the real Earth. It is an environment. It predicts nothing, so it has no model score and no compression comparison.

## What it was trained and tested on

Nothing was trained: it is a simulator. It was built from public data and graded against the real Earth.

- Malta and Gozo from the national one-metre height survey (2012 and 2018, CC BY 4.0, credit needed). All 568 survey tiles were fetched by 30 Sep.
- New York: 377,822 buildings from OpenStreetMap.
- A survey of public simulation and graphics code, with each repository's licence checked (26 and 27 Sep).
- 13 lessons and an exam of 42 physics items, graded against the real Earth, plus tests for weather, water, rigid bodies and the shore line.

## Results

- **A failing exam.** On 27 Sep 2026 the world agreed with the real Earth on 10 of 42 items, was wrong on 20 and could not tell on 12. That is a failing grade, and I call it one. The tally is from my handover notes, not re-run.
- **Malta, building by building.** The merge of 23:51 on 1 Oct 2026 drew all 112,147 buildings of Malta and Gozo at their measured heights, where the version before drew 51,414. About 20 to 30 real parts in deep shadow are wrongly dropped (an estimate). At that merge the core's tests read 467 passed, 1 known failed and 20 ignored, with the Malta buildings tests at 80 of 80. Limit: counts from my notes, not re-run, and the test totals differ at other merges.
- **Climate.** My notes of 2 Oct record that the main Koppen climate group came out right at 83 percent of unseen places, while the snowline was right in 3 of 10 mountain ranges (high ground came out too green) and the Serengeti came out as forest. Limit: the notes do not say how many places the 83 percent covers or how "unseen" was defined. Nothing re-run.
- **Chemistry.** On 13 exam molecules on 29 Sep, PM7 (a published method) had a median error in heat of formation of 29.6 kJ/mol, against 47.0 for the chemistry tool's earlier method and 440.5 for a quantum method (GFN2-xTB), with signs right on 13 of 13. On a separate 25 items the quantum method missed by a median 390 kJ/mol, with signs right on 18 of 25, so its answers are shown but decide nothing. Limit: at that time 12 of 27 items still read CANNOT TELL (elements that need d orbitals). The d-orbital piece merged on 30 Sep, no later exam is in my notes, and nothing was re-run. The methods are published work.
- **Smaller tests (29 Sep to 1 Oct).** A weather test passed 29 of 30 (one July night came out 5 K warm), a water test 11 of 13 and a rigid-body test 3 of 5. A shore check failed at 1 of 12 places. Counts from my notes, not re-run.
- **Summits.** My notes say 25 of 25 named summits came out within 5 percent. That is the project's own statement, not re-checked.

## Where it falls short

- It failed its physics exam.
- Snowlines and the Serengeti come out wrong, and a shore check failed at 1 of 12 places.
- About 20 to 30 real parts in deep shadow are wrongly dropped, and New York's buildings were drawn, not checked one by one.
- A simulated electrical module (a transistor, a NAND gate and a latch, with 33 checks) was not merged into the running world.
- Every number here is from my notes, not re-run.

## Not done yet

- No exam since the d-orbital piece merged.
- A learning model building its own machines inside the world is still an aim.
- Nobody outside my projects has run it.

## Check it yourself

- **Today.** The inputs are public: the height survey (CC BY 4.0) and OpenStreetMap. The world itself is not.
- **On a call.** I can open the simulator and show Malta in it, and open my notes with the exam tally and the test counts.
- [How to check what this site says](../../VERIFY.md#qmk-world-and-tetra-mesh)

## More

- [Model history](../MODEL_HISTORY.md)
- [QMK World](../../projects/qmk-world.md), the project page
- [QMK and AMK](qmk-and-amk.md), the learning models it was built for
