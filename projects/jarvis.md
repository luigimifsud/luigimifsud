# Jarvis

A WhatsApp booking assistant for Apex Dental, my father's two dental clinics in Birkirkara, Malta. It talks to real patients and books them straight into the clinic's diary.

**Status:** live with patients and staff. **Dates:** 8 Sep 2026 to now, still shipping on 26 Nov 2026.

## What it is

Patients message the clinic on WhatsApp. Jarvis answers them, finds a slot, takes the booking fee and puts the appointment in the clinic's real diary. It checks every message for red-flag symptoms before anything else, and if it can't answer, the patient gets one fixed reply and the staff are flagged.

## Why it exists

A clinic lives on its diary. I wanted patients to be able to book in the chat they already use, and I never wanted the bot to be the reason a patient with a real problem gets missed.

## What I built

- **Booking in the real diary.** Jarvis reads and writes the clinic's practice-management diary, so what it books is what reception sees.
- **Payment inside the chat.** It takes the EUR 20 booking fee by card (SumUp) without the patient leaving WhatsApp.
- **Reminders.** It sends appointment reminders, with an SMS fallback.
- **Red-flag check.** Every patient message is checked for red-flag symptoms before anything else, in English, Italian, Spanish and Maltese.
- **A small local reader of its own.** Three adapters on open models read every patient message for what it means and how the patient feels. It runs in shadow mode next to a larger hosted model.
- **A staff portal.** Rota, sales, lab cards, and an installable app with alerts.
- **A gateway that fails closed.** A companion gateway sits on the clinic's own phone line. If Jarvis cannot answer, the patient gets one fixed reply and the staff are flagged.
- **Shadow mode.** New behaviour runs in shadow mode before it goes live.
- **Cancel, never delete.** A standing rule: bookings get cancelled, never deleted.
- **An evaluation set.** Hand-built cases plus cases picked by machine, most of them moments where a chat went wrong, so I can measure whether a change makes Jarvis better or worse.

## Results

Jarvis has been talking to real patients since at least 13 Sep 2026.

Usage, from the bot's own review logs (not an audited dashboard), for the week 12 to 18 Oct 2026:

- 388 chats with 269 phone numbers
- 54 payment holds created, 22 of which became bookings

The local reader, from its own score files (aggregate figures, not re-run since):

- on 147 clinic phone messages it scored 0.844 on meaning and 0.946 on feeling, and caught 0.829 of the messages that were not calm
- on 86 chats, it caught 0.64
- in shadow mode it agreed with the larger hosted model on meaning in 77 percent of 643 replies

Size of the work:

- 3,078 commits (counted on 26 Nov 2026)
- about 187,000 lines of application code
- about 150,000 lines of tests, with 8,984 test functions
- the gateway: about 3,700 lines with 238 tests
- a test run on 21 Nov 2026 recorded 12,611 passed and 4 known failures (from that run's log, not re-run since)

The commits show the name Jonathan Mifsud because I committed under my father's git identity.

## Where it falls short

My evaluation set of 12 Nov 2026 shows how far Jarvis still has to go (recorded in its own file, not re-run since):

- 95 of 114 hand-built cases pass (83 percent)
- on 272 machine-picked moments where a chat went wrong, 61 pass (22 percent)
- 217 of 477 pass overall (45 percent)
- the 363 machine-picked cases have not been checked by a person yet

The local reader is not the main reader yet. The bar for that is 95 percent agreement with the hosted model on meaning, and in shadow mode it is at 77 percent.

## Status

Live. Patients book through it and staff work in the portal.

## Not done yet

- Every user so far comes through Apex Dental: its patients and its staff. There are no outside customers.
- There is no software revenue. The booking fees are the clinic's income, not mine.
- The usage numbers come from the bot's logs. Nobody outside has audited them. [How to check what this site says](../VERIFY.md#jarvis) goes through what you can and can't check.
- No patient data, chat text or screenshots of the bot or the staff portal are published here, on purpose.

## Check it yourself

- **The clinic.** Jarvis is the clinic's live WhatsApp line, and the clinic is real: [apexdentalmalta.com](https://www.apexdentalmalta.com). You can message the clinic on WhatsApp from its website and watch Jarvis answer.
- **Commit history.** A record of Jarvis's commit dates and count, with no code and no commit text, is not published yet.
- **The numbers, on a call.** The code, the chats and the portal stay private because they hold patient data. On a call I can share my screen, recount the commits, run the gateway's tests and open the evaluation and reader score files, with no patient data on screen.
- This page: https://github.com/luigimifsud/luigimifsud/blob/main/projects/jarvis.md
