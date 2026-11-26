# Jarvis

Jarvis is the WhatsApp booking assistant I built for Apex Dental, my dad's two dental clinics in Birkirkara, Malta, and a project of its own.

| | |
|---|---|
| Project | Jarvis |
| Dates | 8 Sep 2026 to now. Talking to real patients since at least 13 Sep 2026, still shipping on 26 Nov 2026. |
| Status | Live with Apex Dental's patients and staff |

## What it was for

Patients message the clinic on WhatsApp. Jarvis answers, finds a slot in the clinic's practice-management diary, takes the EUR 20 booking fee by card (SumUp) inside the chat and books the appointment. It sends reminders with an SMS fallback, and it runs a staff portal with the rota, sales, lab cards and an installable app with alerts.

How it fails safe:

- **Red flags before booking.** A red-flag check reads every patient message before the booking flow starts, in English, with partial cover so far in Italian, Spanish and Maltese. It looks for trouble breathing or swallowing, swelling reaching the eye, neck, throat or tongue, collapse, chest pain, allergic shock, a broken jaw and bleeding that will not stop. It went live on 14 Nov 2026 at 21:20.
- **Fails closed.** A companion gateway on the clinic's own phone line fails closed: if Jarvis cannot answer, the patient gets one fixed reply and the staff are flagged.
- **Shadow mode.** New behaviour runs in shadow mode before it goes live. The offer check, and a check that answers the patient's question before making an offer, logged what they would do from 14 Nov and were switched on on 21 Nov at 16:50.
- **Cancel, never delete.** A standing rule: bookings are cancelled, never deleted.

## What it was trained and tested on

Jarvis is not one trained model. Its small message reader is, and it has [its own card](jarvis-reader.md). Jarvis itself is tested on an offline exam: hand-built cases written from real chats of 7 to 11 Sep 2026 and from known faults, plus 363 cases picked by machine from moments in chats that went wrong or right, which no person has checked. The exam runs offline, with the hosted model switched off and the clock fixed. A separate fixed sample of 40 cases runs with the hosted model on. No patient text appears on this card. Every figure is an aggregate.

## Results

Recorded in the project's own result files and commit messages, not re-run since, unless a bullet says otherwise.

- **Offline exam, 12 Nov 2026.** 95 of 114 hand-built cases passed (83 percent), 61 of 272 machine-picked moments that went wrong (22 percent), and 217 of 477 overall (45 percent). Two bots that do nothing useful, one that never answers and one that hands every message to staff, passed 1 and 7 of the 114, 0 and 47 of the 272, and 0 and 5 of the 91 moments that went right, where Jarvis passed 61. Run twice, the hand-built part gave the same result case for case. Limits: the hand-off bot came close on the went-wrong set (47 against 61), and no person has checked the 363 machine-picked cases. 95 of 114 means chats like these would likely score somewhere between 75 and 89 percent, but the file does not show how that range was worked out.
- **After the fixes.** On 13 Nov, after that day's fixes, the same exam scored 241 of 477 and the hand-built cases 114 of 114. By 21 Nov the exam had 512 cases, 149 of them hand-built: 264 passed with default settings and 283 with the settings Jarvis runs live, and the hand-built part scored 125 and 143 of 149. On 23 Nov the live-settings score was 288 of 512. Limits: the hand-built cases were written from known faults and the fixes were made to pass them, so the rise shows the fixes took, not a score on unseen chats. The hosted model is off in this exam, and a probe found that 344 of the 477 cases reach it somewhere, so those paths are not measured. The case mix changed from 477 to 512, so the counts are not strictly like for like.
- **Live sample, hosted model on.** On 40 fixed cases that reach the hosted model, each run 3 times, Jarvis passed 34 at the baseline, 33 on 13 Nov and 32 on 21 Nov with the offer check and the answer-before-offer check on. Limit: no run with the new checks off was made, so the one-point slip cannot be put down to them, and a move of one or two on 40 cases sits inside run-to-run noise.
- **Red-flag check.** It has 154 tests and 8 exam cases. With the check off, 3 of the 8 exam cases passed; with it on, 8 of 8. Limit: the 8 cases were written with the check, so 8 of 8 shows it does what they ask, not how it does on unseen messages. 154 counts tests, not accuracy.
- **Offer check, tests written before the fix.** On 14 Nov, 16 exam cases for the offer check were written before the check existed, and 15 of them failed on that day's code. The clinic owner then read 25 of its exam cases: 22 were right as written, and 3 he answered differently, which changed the check. With the new checks off, 122 of the 141 hand-built cases passed; with them on, 141 of 141. Limit: those cases were written for the checks, so 141 of 141 is not a score on unseen chats, and the owner read 25 cases, not the 363 machine-picked ones. From commit messages, not re-run since.
- **Offers against the patient's limits.** From 1 to 14 Nov 2026 a machine judge found that 29 percent of real offers went against a limit the patient had given, without saying so. From 14 to 21 Nov, while the offer check was logging what it would change, the same judge found 13 percent. Limits: no person has checked the judge, the two machine judges disagreed a lot, and other changes went live in the same week, so the fall is not credited to the check. In that week the answer-before-offer check logged faults in 17.3 percent of direct questions, against 12.8 percent before (from a different sample), so it shows no improvement.
- **Usage, from the bot's own logs, not an audited dashboard.** In the week 12 to 18 Oct 2026: 388 chats with 269 phone numbers, and 54 payment holds created, 22 of which became bookings.
- **The small reader.** In shadow mode it agreed with a larger hosted model on meaning in 77 percent of 643 replies, from the bot's own logs. It does not become the main reader until it reaches 95 percent. The rest is on [its card](jarvis-reader.md).

## Where it falls short

- In the 12 Nov exam the weakest hand-built groups were "named day kept" (4 of 8), "stops offering when told" (1 of 3) and "a correction taken" (0 of 1). Among the 272 machine-picked moments that went wrong, it got 15 of 30 right when an existing appointment was mishandled and 3 of 30 when one message held several requests. The most common tag on what still went wrong in that set is that Jarvis repeats itself (134 moments), then handing the patient to staff (102). The tags overlap, the groups hold 1 to 30 cases, no person has checked the machine-picked cases, and the 19 failing hand-built cases were fixed on 13 Nov. Recorded in its result files, not re-run since.
- The offline exam does not measure the paths that reach the hosted model.
- The answer-before-offer check shows no improvement so far.

## Not done yet

- No outside customers. Every user so far is a patient or a staff member of Apex Dental. There is no software revenue: the booking fees are the clinic's income.
- Nobody outside has audited the usage numbers.
- No person has checked the 363 machine-picked cases or the machine judge.
- No run of the live sample with the new checks off.

## Check it yourself

The clinic is real: you can message it on WhatsApp from [apexdentalmalta.com](https://www.apexdentalmalta.com) and watch Jarvis answer. Nothing else here can be checked from outside yet: the code, the chats and the staff portal hold patient data, so they stay private, and no screenshots are published. On a call I can share my screen, recount the commits, run the gateway's 238 tests and open the evaluation files, with no patient data on screen. [How to check what this site says](../../VERIFY.md#jarvis) goes through the rest.

## More

- [The Jarvis page](../../projects/jarvis.md)
- [The reader's card](jarvis-reader.md)
