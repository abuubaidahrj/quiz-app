# Math Master v7.2.1 — Fair Question Rotation

## Which version should be installed?

Install **v7.2.1**.

Do not install the earlier v7.2 package. v7.2.1 contains all v7.2 features plus
the fairness corrections described below.

## Main fairness corrections

### 1. Repeated questions are not automatically a failure

A small number of repeated questions is allowed.

Overlap is now calculated against the size of the **new assessment**:

- Previous quiz: 10 questions
- New quiz: 50 questions
- Repeated questions: 8
- New-set overlap: 8 / 50 = 16%
- Result: allowed

### 2. Fresh sets are checked before the quiz starts

For 10, 20 and 50-question assessments:

1. The browser prefers concepts that the student has not seen recently.
2. It sends the proposed fingerprint and question keys to Apps Script.
3. If overlap is 80% or more within the recent window, Apps Script asks the
   browser to generate another set.
4. Up to eight candidate sets are tried before the quiz begins.

The child is not expected to finish a knowingly duplicated random set and then
discover that it was rejected.

### 3. Reversed facts inside a set

For short assessments, the selector avoids placing both `7 × 8` and `8 × 7`
in the same set.

For All Questions mode, ordered questions remain available. The backend no
longer rejects two different ordered questions as an internal duplicate.

### 4. All Questions mode

All Questions necessarily reuses the full pool. Only the first recent
full-pool completion earns credits. A repeat remains saved for learning and
diagnosis but earns no XP or mission credit.

### 5. Qualification rules are visible

The student page now contains:

`How to earn mission assessment credits`

The Parent Dashboard contains:

`Mission credit qualification`

An ineligible result displays:

- the exact reason;
- a button to view the rules;
- a button to start a fresh assessment.

## Installation — Apps Script

1. Open the existing Math Master spreadsheet.
2. Select `Extensions → Apps Script`.
3. Replace the current `Code.gs` with the supplied v7.2.1 file.
4. Save.
5. Run `setupSheets()` once.
6. Update the existing Web App deployment:
   `Deploy → Manage deployments → Edit → New version → Deploy`

Keep:

- Execute as: Me
- Who has access: Anyone

The existing Parent PIN remains valid.

## Installation — GitHub

Replace both files in the root of the repository:

- `index.html`
- `dashboard.html`

Commit the changes.

## Test URLs

Student quiz:

https://abuubaidahrj.github.io/quiz-app/?version=v7-2-1

Parent dashboard:

https://abuubaidahrj.github.io/quiz-app/dashboard.html?version=v7-2-1

## Important

Do not run `rebuildProfilesFromHistory()` for a normal upgrade.
