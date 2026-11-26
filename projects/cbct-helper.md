# CBCT helper

A 3D Slicer add-on for dental implant planning that runs the public DentalSegmentator model.

**Status:** prototype, awaiting clinical checks. **Dates:** 23 Oct to 24 Nov 2026.

## What it is

Implant planning at the clinic starts from a CBCT scan, a 3D X-ray of the jaw. The add-on runs inside 3D Slicer, a free medical imaging program, and uses DentalSegmentator, a public model, to mark up the scan so planning can start from that.

## Why it exists

The clinic plans implants from these scans. I wanted the marking-up step to happen inside the program the planning is done in.

## What I built

- The add-on for 3D Slicer, which wraps the public DentalSegmentator model.
- About 14 builds so far.

I did not train a model of my own for this. The model is DentalSegmentator, as published.

## Results

It runs as an add-on inside 3D Slicer. There is no clinical result to report yet.

## Where it falls short

The hard part, the model that marks up the scan, is someone else's published work. My part is getting it into the clinic's planning step. Until a clinician has checked it, I would not ask anyone to rely on it.

## Status

Prototype, waiting on clinical checks.

## Not done yet

- The clinical checks. [How to check what this site says](../VERIFY.md#other-builds) goes through what you can and can't check.
- No patient data or scans are shown here, on purpose.

## Check it yourself

- **The model.** DentalSegmentator and 3D Slicer are both public, so anyone can look at what the add-on builds on.
- **On a call.** I can show the add-on running inside 3D Slicer on a public scan, never a patient's.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/cbct-helper.md
