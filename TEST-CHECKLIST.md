# Math Master v7.2.1 — Test Checklist

## A. Version and setup

- [ ] `setupSheets()` completes successfully.
- [ ] `AssessmentAttempts` contains the new `Selection` column.
- [ ] Existing sessions, profiles, XP and missions remain intact.
- [ ] Existing Parent PIN still works.
- [ ] Student page shows `v7.2.1`.
- [ ] Parent Dashboard shows `v7.2.1`.

## B. Qualification rules

- [ ] Student page shows `How to earn mission assessment credits`.
- [ ] Parent Dashboard shows `Mission credit qualification`.
- [ ] Credit values show 10=1, 20=2, 30=3, 40=4, 50+=5.
- [ ] The rule panel explains 60% accuracy, speed and daily limit.

## C. Fair rotation

- [ ] Complete a 10-question multiplication assessment.
- [ ] Start another 10-question multiplication assessment.
- [ ] The second set is not exactly the same.
- [ ] One or two repeated questions do not cause rejection.
- [ ] The app may briefly show `Rotating questions` when a candidate is too similar.

## D. Fair overlap calculation

Example test using history:

- [ ] A previous 10-question set exists.
- [ ] Start a 50-question assessment.
- [ ] Repeated questions are divided by 50, not by 10.
- [ ] Eight repeated questions show 16%, not 80%.

## E. Credits and notification

- [ ] Eligible 10-question assessment earns 1 credit.
- [ ] Eligible 20-question assessment earns 2 credits.
- [ ] Accuracy below 60% earns 0 credits.
- [ ] An ineligible result displays the exact reason.
- [ ] `View qualification rules` opens the rule panel.
- [ ] `Start a fresh assessment` returns to setup.

## F. All Questions mode

- [ ] First recent full-pool assessment can earn credits.
- [ ] A repeated full-pool assessment is saved for learning.
- [ ] The repeated full-pool assessment displays 0 credit and a clear reason.

## G. Existing v7.2 controls

- [ ] Sequential mission queue still works.
- [ ] Multiple missions can use the same date.
- [ ] Activity from Mission 1 is not reused by Mission 2.
- [ ] Weekly reward minutes are summed correctly.
- [ ] Targeted Practice fair-play remains active.
