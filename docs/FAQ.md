# Questions a reviewer might have

As of 26 Nov 2026. Short answers, each with a link to the page that has more.

## Has anyone outside reproduced this?

No, nobody outside my projects has reproduced a result yet. Every result on this site was measured inside my own projects. The checks I run before I quote a result catch my mistakes, but they are not an outside check. The next step I want for exact AI is to run the "try it yourself" download on a second machine, then send it to people outside the project and publish what they got, whatever it is. [How to check what this site says](../VERIFY.md) goes claim by claim.

## What can I check today?

A little, and none of it is an outside check of a result. The clinic Jarvis works for is real: you can message it on WhatsApp from [apexdentalmalta.com](https://www.apexdentalmalta.com) and watch Jarvis answer. Once this repo is public at [github.com/luigimifsud/luigimifsud](https://github.com/luigimifsud/luigimifsud), its history dates each write-up, though not the work behind it. On a call I can share my screen, open the log or result file behind a number and re-count commits or run tests while you watch, with code, design details and patient data off screen. The full list is under [What you can check today](../VERIFY.md#what-you-can-check-today).

## Can I see the code?

Not yet. This repo holds write-ups, not code, and the code stays private for now. Jarvis's code, chats and staff portal hold patient data, so they stay private. On a call I can run tests and open result files while you watch, with the code kept off screen. You would see the file, but it is still my file on my machine, as [How to check what this site says](../VERIFY.md#what-you-can-check-today) puts it.

## Why are the exact AI results worded the way they are?

I quote engine results word for word as my project records them, so they read a bit stiff. "We" and "our" mean the project; I'm applying on my own. Where a result says it was re-checked, that was a separate testing step inside my project, not anyone outside it. They are all on [the exact AI page](../projects/exact-ai.md#results), each with its scope.

## Why don't you describe how the Hail Mary models are built?

I keep the design private for now. Each result says what it was measured on and what it does not show, but not how the model works. The same goes for the exact engine and for my earlier learning models. On a call I can open the job log and the result files behind each number, with the design kept off screen. The results, losses included, are on [the Hail Mary page](../projects/hail-mary.md).

## Why do you show your losses?

A result that went against me is still a result. My scoreboard has a line I go by: "A named wall is a result, not a failure." If I showed you just what worked, you would have no way to judge how I handle what does not. So the race Hail Mary lost, Mark One's losses to Qwen and the failing physics exam of QMK World sit on their pages next to the results that went my way, and [Dead ends](../projects/dead-ends.md) gathers the rest.

## How do you work?

I build with AI coding tools; I set the rules, design the tests and decide what counts as done. Before a test runs, I write down what counts as a pass and what counts as a fail. In Hail Mary each pass rule is locked with a hash before any result is read, and tests are checked by planting deliberate errors. A separate testing step inside my project re-counts a result from the files before I quote it. The steps are under [How I check results before I quote them](../VERIFY.md#how-i-check-results-before-i-quote-them).

## Why do commits show "Jonathan Mifsud"?

Commits on Jarvis show "Jonathan Mifsud" because I committed under my dad's git identity. He is Dr Jonathan Mifsud, a dentist who runs Apex Dental, and Jarvis is for its two clinics. I built it, and Jarvis is my project, not his. Mark One's commits show "luigi" with the same email. The repos are private, so on a call I can open the history and recount the commits while you watch ([who made the commits](../VERIFY.md#jarvis)).

## Is there a company?

No company is incorporated, and no money has been raised. Project Alpha started on 9 Nov 2026, and I lead the research. I run it under the name Baseline Technologies. More is under Status on [the exact AI page](../projects/exact-ai.md#status).

## Do you have customers or revenue?

No. There is no customer and no software revenue. Jarvis's users are Apex Dental's patients and staff, and the EUR 20 booking fees it takes are the clinic's income, not mine. For exact AI I have sent about 70 outreach emails and had one investor conversation so far. See [Jarvis](../projects/jarvis.md#not-done-yet) and [exact AI](../projects/exact-ai.md#status).

## Who uses Jarvis, and how is patient safety handled?

Apex Dental's patients and staff. It has talked to real patients since at least 13 Sep 2026, and the bot's own logs, not an audit, show 388 chats with 269 phone numbers in the week 12 to 18 Oct 2026. Every patient message is checked for red-flag symptoms before anything else, in English, with partial cover so far in Italian, Spanish and Maltese. A gateway on the clinic's own phone line fails closed: if Jarvis cannot answer, the patient gets one fixed reply and the staff are flagged. New behaviour runs in shadow mode before it goes live, bookings are cancelled, never deleted, and no patient names, chat text or screenshots are published, on purpose ([the Jarvis page](../projects/jarvis.md)).

## What hardware do you use?

One home PC with an NVIDIA RTX 5090 (32 GB), 32 logical cores and 93.6 GB of memory. Project Hail Mary trains on that one card. Earlier training also used a second PC with an RTX 5070. Some exact AI tests also ran on other devices and on cloud machines, and each result on [the exact AI page](../projects/exact-ai.md#results) names the machines it covers.

## What is not done yet?

Nobody outside my projects has reproduced a result, and there is no customer and no money raised. Project Hail Mary's current model is one week old and does not yet match a standard model at equal compute: in the one equal-time race so far (58 minutes each, one run each), it lost by 0.1021 bits per byte (standard error 0.0026) on 256 held-out story windows. For exact AI, the "try it yourself" download has not been run on a second machine or sent, the pilot server has been tested in-house so far, and the 32B speed test is not yet done on all 57 prompts. Jarvis passed 217 of 477 cases in its evaluation set of 12 Nov 2026 (45 percent, recorded in its own file). Each project page ends with its own "Not done yet" list, and [Where things stand](../README.md#where-things-stand) has the short version.

## How do I reach you?

Message me on [LinkedIn](https://www.linkedin.com/in/luigi-mifsud-a65739293). I'm glad to get on a call, share my screen and open the file behind a number on this site, with code, design details and patient data off screen. The same link is at the end of [the home page](../README.md).
