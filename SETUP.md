# Math Master v7.3.2 — Resilient Responsive Dashboard

## Which version to install

Install v7.3.2 only.

It replaces both v7.3 and v7.3.1. It contains:

- instant mission handoff;
- responsive iPhone/iOS Parent Dashboard;
- improved Weekly Reward Bank;
- unlimited legitimate progress;
- fair question rotation;
- analytics connection resilience.

## Analytics reliability improvements

### Safe automatic retries

Read-only Parent Dashboard requests retry up to three times when the browser
cannot load the Apps Script JSONP response.

Mission creation, archive, approval and redemption requests are never replayed
automatically, avoiding duplicate write operations.

### Last successful snapshot

The last successful dashboard response is kept in `sessionStorage` for up to
24 hours.

If live analytics temporarily fails:

- the dashboard does not become blank;
- the last successful data remains visible;
- a banner clearly says it is a saved snapshot;
- `Retry now` attempts live synchronization again.

The snapshot remains confined to the current browser tab session.

### Health check

When the full analytics request fails, the dashboard performs a small health
check:

- if health succeeds, Apps Script is online and the issue occurred during the
  heavier analytics request;
- if health fails, the message points to internet, deployment or Apps Script
  execution availability.

### Faster server processing

The earlier dashboard request read the complete `Responses` and `XPHistory`
sheets twice:

1. during mission queue refresh;
2. during analytics construction.

v7.3.2 reads each sheet once and reuses those rows for the queue calculation.

### Stale-response protection

When two dashboard requests overlap, only the latest request is allowed to
update the screen. A slower old response cannot replace newer student data.

## Installation

1. Open the Math Master spreadsheet.
2. Go to `Extensions → Apps Script`.
3. Replace the current `Code.gs` with v7.3.2.
4. Save.
5. Run `setupSheets()` once.
6. Update the same web-app deployment:
   `Deploy → Manage deployments → Edit → New version → Deploy`
7. Replace these files in the GitHub repository root:
   - `index.html`
   - `dashboard.html`
8. Commit the changes.

Existing PIN, students, missions, XP, rewards and history remain valid.

## Test URLs

Student:

https://abuubaidahrj.github.io/quiz-app/?version=v7-3-2

Parent Dashboard:

https://abuubaidahrj.github.io/quiz-app/dashboard.html?version=v7-3-2
