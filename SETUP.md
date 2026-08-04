# Math Master v7.3.3 — Split Dashboard Loading

## Why v7.3.2 could still fail

The earlier Parent Dashboard still used one large request for everything:

- student profile;
- mission queue;
- mission progress;
- Weekly Reward Bank;
- all analytics;
- graphs;
- weak questions;
- recent sessions;
- achievements.

That request also refreshed and wrote Mission/MissionProgress rows during a
read-only dashboard load. Concurrent quiz saves or mission changes could make
the dashboard request slower and more fragile.

## v7.3.3 architecture

### Stage 1 — Core dashboard

`getParentDashboardCore`

Loads only:

- student list and cloud profile;
- mission queue view;
- cached MissionProgress rows;
- Weekly Reward Bank;
- mission history and reward status.

It does not read the full Responses or XPHistory sheets and does not write to
any sheet.

The dashboard becomes usable as soon as Stage 1 completes.

### Stage 2 — Detailed analytics

`getParentDashboardAnalytics`

Loads separately:

- verified assessment summary;
- 14-day trend;
- operation performance;
- weak questions;
- recent sessions;
- achievements.

If this stage fails, Mission Builder, mission queue and Weekly Reward Bank stay
visible and usable.

### Server analytics cache

Detailed analytics is cached for 120 seconds using Apps Script CacheService.

The cache key changes automatically when Responses, XPHistory, Achievements or
the student profile changes.

`Retry now` bypasses the cache.

### Retry policy

- The lightweight core request retries network errors and timeouts once.
- The heavy analytics request retries only a network load error.
- A timed-out heavy request is not immediately duplicated, avoiding concurrent
  long-running Apps Script executions.
- Write actions are never automatically replayed.

### Read-only dashboard

Parent Dashboard GET calls no longer write Mission or MissionProgress data.
Queue persistence still occurs during:

- quiz submission;
- mission creation or editing;
- mission archive;
- reward approval and redemption.

## Installation

Install v7.3.3 only.

1. Open the Math Master spreadsheet.
2. Select `Extensions → Apps Script`.
3. Replace the existing `Code.gs` with v7.3.3.
4. Save.
5. Run `setupSheets()` once.
6. Update the existing web-app deployment:
   `Deploy → Manage deployments → Edit → New version → Deploy`
7. Replace the GitHub root files:
   - `index.html`
   - `dashboard.html`
8. Commit the files.

Existing PIN, students, missions, rewards, XP and history remain valid.

## Test URLs

Student:

https://abuubaidahrj.github.io/quiz-app/?version=v7-3-3

Parent Dashboard:

https://abuubaidahrj.github.io/quiz-app/dashboard.html?version=v7-3-3
