# Math Master v7.6 — Weekly Mission Planner & Templates

## New Weekly Planner

The Parent Dashboard now includes `Weekly Planner`.

Parents can:

- choose a Monday–Sunday week;
- add blank missions;
- add saved mission templates;
- copy the previous week and shift every date forward seven days;
- reorder missions using up/down controls;
- preview planned credits, questions and potential reward minutes;
- save the entire week as Draft;
- activate the entire week with one confirmation;
- open an existing uncompleted mission in Mission Builder to pause,
  reschedule or edit it.

A weekly plan supports up to 10 missions.

## Mission templates

Running `setupSheets()` creates `MissionTemplates`.

Each planner mission can be saved as a reusable template. Templates store the
requirements, reward and notes, but not fixed dates or student data.

## Duplicate protection

The backend compares the complete mission signature:

- mission name;
- dates;
- requirements;
- reward;
- reward minutes.

Duplicates are reported before saving. The parent can confirm creation of only
the new items; an existing mission is never duplicated silently.

## Fair queue behavior

- missions use the visible preview order;
- old activity is not reused;
- only the Current mission collects progress;
- later missions remain Locked;
- templates do not create activity or rewards by themselves;
- Draft missions are not activated until edited or activated.

## Installation

1. Open the Math Master spreadsheet.
2. Go to `Extensions → Apps Script`.
3. Replace `Code.gs` with v7.6.
4. Save.
5. Run `setupSheets()` once.
6. Update the existing deployment:
   `Deploy → Manage deployments → Edit → New version → Deploy`
7. Replace GitHub root files:
   - `index.html`
   - `dashboard.html`
8. Commit.

Do not run `rebuildProfilesFromHistory()`.

## Test URLs

Student:
https://abuubaidahrj.github.io/quiz-app/?version=v7-6

Parent Dashboard:
https://abuubaidahrj.github.io/quiz-app/dashboard.html?version=v7-6
