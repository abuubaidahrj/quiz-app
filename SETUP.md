# Math Master v7.1 — Mission Builder

## What this phase adds

Parents can now manage weekly missions from `dashboard.html`:

- Create a mission
- Edit a mission
- Save as Draft or Active
- Archive a mission
- Review mission history and live progress
- Prevent overlapping active missions for the same student

The mission is still manually created by the parent. Automatic weekly mission
generation will be added only after this builder is verified.

## Backend installation

1. Open the Math Master spreadsheet.
2. Go to `Extensions → Apps Script`.
3. Replace the existing `Code.gs` with the supplied v7.1 file.
4. Save.
5. Run `setupSheets()` once.
6. Update the existing Web App deployment:
   `Deploy → Manage deployments → Edit → New version → Deploy`

Your existing Parent PIN remains valid.

## GitHub installation

Replace these files in the root of `quiz-app`:

- `index.html`
- `dashboard.html`

Commit the changes.

## Test URLs

Quiz:

https://abuubaidahrj.github.io/quiz-app/?version=v7-1

Dashboard:

https://abuubaidahrj.github.io/quiz-app/dashboard.html?version=v7-1

## Recommended first mission

- Mission name: Nintendo Weekend Mission
- Start/end: Monday to Sunday
- Assessments: 3
- Eligible practice: 2
- Questions: 50
- Minimum accuracy: 80%
- Mission-period XP: 0
- Reward: Nintendo this weekend
- Reward minutes: 60
- Status: Active

Only fair-play eligible Targeted Practice counts.

## Important behavior

- Lifetime historical XP does not complete a new mission.
- Only activity inside Start Date and End Date is counted.
- Active missions for the same student cannot overlap.
- Archive an old active mission before creating another mission over the same
  date range.
- Archived missions remain in Google Sheets for history.

## Next phase

v7.2 will add:

- automatic weekly mission templates;
- automatic Monday mission creation;
- parent approval and reward redemption states.
