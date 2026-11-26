# Baseline Halo

A free Windows guardian with a stalkerware scan and encrypted chat.

**Status:** built, 131 commits. **Last recorded test run:** 26 Aug 2026.

## What it is

A Windows program that scans for stalkerware, the kind of software someone hides on another person's computer to watch them. It also has an encrypted chat built in. It is free.

## Why it exists

Stalkerware is made to stay hidden from the person being watched. I wanted a free tool that someone could run on their own PC to look for it, with an encrypted chat in the same place.

## What I built

- The stalkerware scan.
- The encrypted chat.
- A full test suite.
- A red-team list of attacks against it, each one worked through until it was closed.

## Results

Both recorded in its own plan, not re-run since:

- "Full suite 1230 passed, 2 skipped", recorded on 26 Aug 2026
- a red-team list of 31 of 31 items closed

## Where it falls short

Those are my own tests and my own red-team list. Closing every item on a list I wrote does not mean nobody can break it. Security tools earn trust when people outside try to break them.

## Status

Built. The code is not public.

## Not done yet

- No security review by anyone outside my projects yet. [How to check what this site says](../VERIFY.md#other-builds) goes through what you can and can't check.
- I have no user numbers to report.

## Check it yourself

- **Commit history.** A record of Halo's commit dates and count, with no code and no commit text, is not published yet.
- **On a call.** I can run the test suite and walk through the red-team list.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/halo.md
