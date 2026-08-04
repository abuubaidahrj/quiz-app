# Math Master v7.4 — Family Student Selector

## Main student-page changes

### One approved-student dropdown

The two editable fields for Student ID and Student Name have been removed.

The only available profiles are:

- Abu · ABU
- Aisyah · AISYAH
- Maryam · MARYAM

The page remembers the last selected student on that device.

A quiz cannot start until one of these approved profiles is selected.

### Recent Family Activity

The student page displays the latest activity for each student:

- student name and ID;
- Assessment or Targeted Practice;
- question count;
- relative time;
- exact date and time.

Example:

`Maryam · MARYAM — Targeted Practice — 4 Aug 2026, 3:30 PM`

## Performance design

Recent Family Activity does not block the quiz page.

1. The setup page renders immediately.
2. A saved browser copy is shown first when available.
3. The live request starts during browser idle time.
4. Apps Script reads only the latest 600 XPHistory rows.
5. The server response is cached for 90 seconds.
6. The activity panel has a separate 10-second timeout.
7. A failure only affects the activity panel—not profile, mission or quiz use.
8. After a successful quiz save, the activity panel refreshes with `force=1`.

No new Google Sheets are required.

## Installation

Install v7.4 over v7.3.3.

1. Open the Math Master spreadsheet.
2. Go to `Extensions → Apps Script`.
3. Replace the existing `Code.gs` with v7.4.
4. Save.
5. Run `setupSheets()` once.
6. Update the existing web-app deployment:
   `Deploy → Manage deployments → Edit → New version → Deploy`
7. Replace these GitHub root files:
   - `index.html`
   - `dashboard.html`
8. Commit the changes.

Existing student profiles, missions, XP, history and Parent PIN remain valid.

## Test URLs

Student:

https://abuubaidahrj.github.io/quiz-app/?version=v7-4

Parent Dashboard:

https://abuubaidahrj.github.io/quiz-app/dashboard.html?version=v7-4
