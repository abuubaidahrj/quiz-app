# Math Master v6.1 — Cloud Progress Sync

## What this version adds

- XP, levels, streaks and badges are stored in Google Sheets.
- The same Student ID can load the same progress on different devices.
- Browser localStorage remains as an offline cache.
- Duplicate session IDs are ignored to prevent double XP.
- Existing quiz history can be converted into cloud XP.
- Targeted Practice still saves to Google Sheets but does not send email.

## Files

- `index.html` — upload to the root of the GitHub `quiz-app` repository.
- `Code.gs` — paste into the Apps Script attached to the Math Master spreadsheet.

## Upgrade the Google Apps Script

1. Open the existing Math Master Google Spreadsheet.
2. Select `Extensions → Apps Script`.
3. Replace the existing `Code.gs` with the supplied `Code.gs`.
4. Save.
5. Set the project timezone to `Asia/Kuala_Lumpur`.
6. Run `setupSheets()` once and approve permissions.
7. Run `rebuildProfilesFromHistory()` once.

The rebuild function creates XP and achievements from the quiz results already
stored in `Sessions` and `Responses`.

## Update the Web App deployment

Use the existing deployment so the `/exec` URL stays unchanged:

1. Select `Deploy → Manage deployments`.
2. Open the active Web App deployment.
3. Select `Edit`.
4. Under Version, choose `New version`.
5. Confirm:
   - Execute as: `Me`
   - Who has access: `Anyone`
6. Select `Deploy`.

Do not create a completely separate Apps Script project unless you intend to
replace the Web App URL inside `index.html`.

## Upload the frontend

Replace the root `index.html` in GitHub with the supplied v6.1 file.

Test URL:

https://abuubaidahrj.github.io/quiz-app/?version=v6-1-cloud

Confirm the page displays:

`Version: v6.1 — Cloud Progress Sync`

## New spreadsheet tabs

- `StudentProfiles`
- `XPHistory`
- `AchievementLog`

The existing sheets remain:

- `Sessions`
- `Responses`
- `StudentSummary`
- `QuestionStats`

## Test

1. Enter a Student ID and complete a short normal quiz.
2. Confirm an email is received.
3. Confirm rows are added to `Sessions`, `Responses`, and `XPHistory`.
4. Confirm the student appears in `StudentProfiles`.
5. Open the quiz on another device or Incognito window.
6. Enter the same Student ID.
7. Wait briefly for the cloud-sync message.
8. Confirm the same XP, level, streak and badges appear.
9. Complete Targeted Practice and confirm:
   - no email is sent;
   - data and XP are still saved.
