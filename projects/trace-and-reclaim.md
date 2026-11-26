# Baseline Trace and Baseline Reclaim

Two tools for checking crypto addresses. Trace screens addresses against the US sanctions list and keeps a signed record. Reclaim checks a Bitcoin address's exposure and never touches funds.

**Status:** both built, no customers. **Dates:** Trace's handoff is dated 11 Jul 2026.

## What it is

**Baseline Trace** is a desktop tool for small EU crypto firms. It checks addresses against the US sanctions list and writes a signed, tamper-evident record of each check, offline.

**Baseline Reclaim** is a Bitcoin exposure checker. It looks at an address and never touches the funds behind it.

## Why it exists

A firm that screens addresses has to be able to show later what it checked and what the answer was. I wanted a tool a small firm could run on its own computer, offline, that leaves a record which shows if anyone changes it afterwards. It is the same question as my exact AI work, earlier and on a smaller problem: can you prove later what a machine said?

## What I built

- Trace: the screening tool, the signed records and the offline mode.
- Reclaim: the exposure checker, built so it never touches funds.

## Results

- Trace: 703 commits (counted on 26 Nov 2026) and 4,347 tests (recorded in its 11 Jul 2026 handoff, not re-run).
- Reclaim: 91 commits (counted on 26 Nov 2026) and 73 of 73 tests passing (recorded in its changelog, not re-run).

## Where it falls short

By 8 Jul 2026 there had been no customer conversations about Trace at all.

## Status

Both built. No customers, no revenue.

## Not done yet

- No customer for either tool.
- No outside review of Trace's records or Reclaim's checks. [How to check what this site says](../VERIFY.md#other-builds) goes through what you can and can't check.

## Check it yourself

- **Commit history.** A record of each repo's commit dates and count, with no code and no commit text, is not published yet.
- **On a call.** I can run both test suites and recount the commits.
- **What you cannot check yet.** The code is not public.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/trace-and-reclaim.md
