# Hail Mary forecaster

A forecaster in Project Hail Mary that predicts the next positions of a moving figure or point, tested on generated streams.

| | |
|---|---|
| Project | Project Hail Mary |
| Dates | Race read on 23 Nov 2026; packaged by 26 Nov 2026 |
| Hardware | My home PC; the 23 Nov race ran on the CPU, with no GPU |
| Status | Preview: packaged so someone else can run it, not yet run by anyone else |

## What it was for

A side line of Project Hail Mary: a forecaster for things that move, raced against standard tracking methods. It is not joined to the language model.

## What it was trained and tested on

- Generated streams of two kinds: a stick figure's movement, which has a random part, a switch and a return to its pattern, and an erratic point. The race used 256 held-out streams of each kind.
- No real tracking data.
- The rivals in the race: keep-straight, a Kalman filter, a jump-aware Kalman filter, a particle filter and two learned networks.

## Results

- **Learned settings.** A learned forecaster beat its hand-written version in 12 of 27 test cells and was worse in none, on generated test streams.
- **The race (as read on 23 Nov 2026).** On 256 held-out generated streams of each of two kinds, my forecaster beat every other method in its race (keep-straight, a Kalman filter and two learned networks) in the random part of the stick figure's movement (5 steps ahead) and in its return to the pattern (1 and 5 steps ahead). It was below the bar just after the figure's switch. On the erratic-point streams it was below the best method, a particle filter, in every judged cell, by about 8 to 15 squared units at 5 steps. The project's overall word was "best in some phases". It is about 1,000 times slower than the Kalman filter on the point. The particle filter's own accuracy check is still not met. Recorded in its result files, not re-run since.
- **Packaged (as of 26 Nov 2026, 06:45).** I packaged it so that someone else can run it. It re-makes my race results to within 0.00000000002 (largest difference 1.455e-11): close, but not bit for bit, because of floating-point rounding. 26 of 26 planted errors in its checks were caught. Recorded in the project's notes, not re-run since.
- **VOID.** A different forecaster race, not the 12 of 27 result, looked good, but one check file's last line broke the locked rule, so the whole race is VOID. The earlier notes that treated its numbers as results were corrected, and I never quote its numbers.

## Where it falls short

- All of it is on generated streams. Two kinds of stream cannot show it is the best for tracking in general.
- On the erratic point the particle filter beat it in every judged cell, and just after the figure's switch it was below the bar.
- It is about 1,000 times slower than the Kalman filter on the point.
- One race of it is VOID.

## Not done yet

- It has not been tested on anything but generated streams.
- Nobody has run the package on a clean machine. Its one-click launcher has not been run yet, and its demo page has not been opened in a real browser.
- It is not joined to the language model.

## Check it yourself

- **Today.** Nothing. The package is not public yet.
- **On a call.** I can open the race's result files and the package's re-make check, with the design kept off screen.
- [How to check what this site says](../../VERIFY.md#project-hail-mary)

## More

[Project Hail Mary](../../projects/hail-mary.md)
