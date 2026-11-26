# TETRA mesh

An overlay on top of the normal internet, with four layers of encryption, built for distributed training.

**Status:** prototype, dormant. **Dates:** 11 to 14 Sep 2026 (from the file dates).

## What it is

A private overlay that sits on top of the normal internet. Traffic between machines passes through four layers of encryption. I built it so that training jobs could one day be spread over several machines without trusting the connections in between.

## Why it exists

Training on one home PC has a ceiling. Spreading the work over more machines needs links between them that you can trust, and I wanted to understand that part by building it.

## What I built

- The overlay itself, with all four encryption layers.
- About 51,000 lines of code, plus 26,000 lines of tests.

## Results

From its own status file (not re-run since):

- 564 tests, 563 passing

## Where it falls short

- Not every test passed: 563 of 564.
- The test count comes from its own status file. I have not re-run it.

## Status

Dormant since September 2026.

## Not done yet

- Not audited by anyone outside my projects. Encryption means little until someone outside has tried to break it, so I would not ask anyone to rely on it yet. [How to check what this site says](../VERIFY.md#qmk-world-and-tetra-mesh) goes through what you can and can't check.

## Check it yourself

- **On a call.** I can run the test suite and open the status file the numbers come from.
- **What you cannot check yet.** The code is private.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/tetra.md
