# Math Master v7.5 — Family Profile Control

## Official profiles

New activity is accepted only for:

- Abu · ABU
- Aisyah · AISYAH
- Maryam · MARYAM

The Student Page and Parent Dashboard show only these three profiles.
Apps Script rejects altered or legacy Student IDs.

## Non-destructive Profile Control

The Parent Dashboard identifies legacy and duplicate StudentProfiles rows.

The parent may:

- link old history to an official child;
- archive a row from the cleanup review;
- return an archived row to review.

No Sessions, Responses, XPHistory or StudentProfiles rows are deleted or
rewritten.

Linked history appears in lifetime profile display, detailed analytics and
Recent Family Activity. It does not count toward active missions or reward
minutes.

Running `setupSheets()` creates a new sheet named `ProfileControl`. It stores
only cleanup decisions. The upgrade no longer clears the existing
`MissionProgress` cache.

## Student Page improvement

`Start Quiz` and `Parent Dashboard` now appear directly under Quiz Type and
Number of Questions. Recent Family Activity is below these buttons.

## Installation

1. Open the Math Master spreadsheet.
2. Select `Extensions → Apps Script`.
3. Replace `Code.gs` with v7.5.
4. Save.
5. Run `setupSheets()` once.
6. Update the same deployment:
   `Deploy → Manage deployments → Edit → New version → Deploy`
7. Replace GitHub root files:
   - `index.html`
   - `dashboard.html`
8. Commit the changes.

Do not run `rebuildProfilesFromHistory()` for this upgrade.

## Test URLs

Student:
https://abuubaidahrj.github.io/quiz-app/?version=v7-5

Parent Dashboard:
https://abuubaidahrj.github.io/quiz-app/dashboard.html?version=v7-5
