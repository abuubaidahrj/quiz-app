# Math Master v7.2.2 — Unlimited Fair Progress

## Why this patch exists

v7.2.1 contained two arbitrary daily caps:

- maximum 8 rewarded assessment credits per day;
- maximum 2 rewarded Targeted Practice sets per day.

Those limits could stop a motivated student even when the work was genuine.
They have been removed.

## New policy

### Assessments

There is no daily assessment-credit limit.

Every assessment can earn credits when it passes:

- server-issued one-time attempt;
- at least 10 completed questions;
- at least 60% first-try accuracy;
- reasonable completion time;
- valid Math Master questions;
- fresh-enough question set;
- no duplicate session;
- current-mission activation window.

Credits remain:

- 10 questions = 1 credit
- 20 questions = 2 credits
- 30 questions = 3 credits
- 40 questions = 4 credits
- 50+ questions = maximum 5 credits per session

### Targeted Practice

There is no daily rewarded-practice limit.

The first Targeted Practice linked to each different source assessment can earn
30 XP and mission credit.

Repeating Targeted Practice from the same source assessment remains saved for
learning, but earns 0 XP and 0 mission credit. This prevents spam without
blocking genuine additional study.

## Eligible-practice counting fix

The patch also:

- validates that the source assessment exists in cloud history;
- counts older eligible rows where Reward Eligible was blank but Session XP
  was positive;
- polls Google Apps Script until the session reward result exists instead of
  assuming the POST completes within 1.5 seconds;
- refreshes the profile and mission only after the eligibility result is
  available.

## Installation

1. Open the Math Master spreadsheet.
2. Go to `Extensions → Apps Script`.
3. Replace the current `Code.gs` with v7.2.2.
4. Save.
5. Run `setupSheets()` once.
6. Update the existing Web App deployment:
   `Deploy → Manage deployments → Edit → New version → Deploy`
7. Replace GitHub root files:
   - `index.html`
   - `dashboard.html`
8. Commit changes.

The existing Parent PIN remains valid.

## Test URLs

Student:

https://abuubaidahrj.github.io/quiz-app/?version=v7-2-2

Parent Dashboard:

https://abuubaidahrj.github.io/quiz-app/dashboard.html?version=v7-2-2
