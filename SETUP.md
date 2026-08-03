# Math Master v7.0.1 — Parent Dashboard Performance Fix

## Cause of the timeout

The v7.0 read request ran `setupSheets()` more than once.

That setup function formats every tab and runs `autoResizeColumns()`. It is
appropriate during installation, but too expensive to run before every
dashboard read. The browser stopped waiting after 15 seconds.

## Fixes

- Removed `setupSheets()` from read-only GET requests.
- Avoided a second StudentProfiles read.
- Reused loaded XP and response data for mission calculations.
- Increased the browser's initial wait from 15 to 45 seconds.
- Added server processing time to the dashboard status line.

## Install

1. Open the Math Master spreadsheet.
2. Go to `Extensions → Apps Script`.
3. Replace the current `Code.gs` with the supplied v7.0.1 file.
4. Save.
5. Do not run `setupSheets()` for this patch.
6. Update the existing Web App:
   `Deploy → Manage deployments → Edit → New version → Deploy`
7. Replace GitHub files:
   - `index.html`
   - `dashboard.html`
8. Commit the changes.

## Test

Quiz:

https://abuubaidahrj.github.io/quiz-app/?version=v7-0-1

Dashboard:

https://abuubaidahrj.github.io/quiz-app/dashboard.html?version=v7-0-1

A successful dashboard load displays:

`Server processing: X.Xs`

## If it still times out

Open Apps Script → Executions and inspect the latest `doGet`:

- Completed: browser or deployment/cache issue
- Failed: open the execution to see the exact error
- Running: spreadsheet reads are still taking too long
