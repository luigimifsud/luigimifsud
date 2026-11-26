# QMK World

An Earth-sized voxel simulator, with Malta rebuilt 1:1.

**Status:** prototype, paused. **Dates:** late Sep to 7 Oct 2026.

## What it is

A simulated world built from real data about the Earth. The part I pushed furthest is Malta, where I live: the islands are rebuilt 1:1, building by building, at their measured heights.

## Why it exists

I wanted a world real enough for my learning models to work in, not a game level. I put the idea like this at the time ("he" is the AI that would live in it):

"the idea is we build planet Earth ... if he wants to build a ... rocket to explore a planet for example he has to build the circuits himself, he has to wire them himself, he has to program it himself"

That is the long aim, not something the simulator does today. Malta was the obvious place to start making it exact, because I can go outside and check it.

## What I built

- An Earth-sized voxel world.
- Malta and Gozo rebuilt 1:1: all 112,147 buildings drawn at their measured heights from the national one-metre height survey (2012 and 2018), as of 2 Oct 2026.
- New York: 377,822 buildings from OpenStreetMap.
- 13 lessons that grade the world against the real Earth.
- A simulated electrical module (a transistor, a NAND gate and a latch, with 33 checks).
- About 80,000 lines of Rust and 28,000 of Python.

## Results

- Malta stands in the simulator 1:1, with all 112,147 buildings at their measured heights, apart from about 20 to 30 parts in deep shadow that are wrongly dropped (an estimate).
- The project's own notes say 25 of 25 named summits came out within 5 percent. That is its own statement, not re-checked.
- The exam result, which went against it, is under "Where it falls short".

## Where it falls short

- An AI building its own machines inside the world is still an aim. What exists is the world itself, with Malta in it.
- About 20 to 30 real parts in deep shadow are wrongly dropped (an estimate).
- On an exam of 42 physics items on 27 Sep, the world agreed with the real Earth on 10, was wrong on 20 and could not tell on 12. That is a failing grade, and I call it one.
- New York's buildings were drawn, not checked one by one.
- The electrical module was not merged into the running world.

## Status

Paused since 7 Oct 2026.

## Not done yet

- It is a prototype and it is paused.
- Nobody outside my projects has run it. [How to check what this site says](../VERIFY.md#qmk-world-and-tetra-mesh) goes through what you can and can't check.

## Check it yourself

- **The source data is public.** The buildings come from the national one-metre height survey (2012 and 2018), published under CC BY 4.0, so buildings in the simulator can be compared with the same public record, apart from the parts in deep shadow it drops. The survey is not my work, and none of its data is in this repo.
- **On a call.** I can open the simulator and show Malta in it, and open the exam's result file.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/qmk-world.md
