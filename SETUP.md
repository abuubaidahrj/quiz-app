# Math Master v7.0 — Read-Only Parent Dashboard

This is Step 1 of the Parent Control Center.

## Included files

- `index.html` — the existing quiz with a Parent Dashboard link.
- `dashboard.html` — the new read-only parent analytics page.
- `Code.gs` — the v7.0 Apps Script backend.
- `SETUP.md` — this guide.

## What the dashboard shows

- Student selector
- Lifetime XP and level
- Current and longest streak
- Assessment count
- Fair-play eligible Targeted Practice count
- Assessment accuracy and response time
- A 14-day trend with visible dates
- Strongest and weakest operations
- Questions needing attention
- Active weekly mission progress
- Recent sessions
- Achievements

The performance calculations use normal assessments. Repeated Targeted Practice
cannot distort the weak-question list or assessment accuracy trend.

## Step 1 — Replace Code.gs

1. Open the existing Math Master Google Spreadsheet.
2. Select `Extensions → Apps Script`.
3. Replace the current `Code.gs` with the supplied v7.0 file.
4. Save.
5. Run `setupSheets()` once.

Do not run `rebuildProfilesFromHistory()` for this normal upgrade.

## Step 2 — Configure the Parent PIN

1. In the function dropdown, choose:
   `configureParentDashboardPin`
2. Click `Run`.
3. Enter a 4 to 8 digit PIN.
4. Approve permissions if Google asks.

The PIN is stored as a SHA-256 hash in Apps Script Properties, not as plain text.

## Step 3 — Update the existing Web App deployment

Use the existing deployment:

`Deploy → Manage deployments → Edit → New version → Deploy`

Keep:

- Execute as: Me
- Who has access: Anyone

Updating the existing deployment keeps the current `/exec` URL.

## Step 4 — Upload to GitHub

Upload both files to the root of the `quiz-app` repository:

- `index.html`
- `dashboard.html`

Commit the changes.

## Test

Student quiz:

https://abuubaidahrj.github.io/quiz-app/?version=v7-0

Parent dashboard:

https://abuubaidahrj.github.io/quiz-app/dashboard.html?version=v7-0

Enter the PIN configured in Apps Script.

## Security note

This PIN is suitable for a private family dashboard, but it is not equivalent
to full Google-account authentication. Do not publish or share the PIN.

## Next phase after verification

v7.1 will add a Mission Builder so missions can be created and edited from the
dashboard instead of typing directly into Google Sheets.
