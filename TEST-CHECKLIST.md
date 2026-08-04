# Math Master v7.3.3 — Connection Test Checklist

## Core dashboard

- [ ] Unlock the Parent Dashboard.
- [ ] Student profile, mission and Weekly Reward Bank appear first.
- [ ] The message says detailed analytics is loading.
- [ ] Mission Builder can be opened before analytics finishes.
- [ ] Apps Script Executions shows `getParentDashboardCore` completing quickly.

## Detailed analytics

- [ ] Metrics, graph, operations, weak questions and sessions appear afterward.
- [ ] Apps Script Executions shows a separate analytics request.
- [ ] Refresh within two minutes uses `Server cache used`.
- [ ] Retry now forces a fresh analytics calculation.

## Failure isolation

- [ ] If analytics fails, mission and reward panels remain visible.
- [ ] The connection banner says the main dashboard remains usable.
- [ ] A heavy analytics timeout does not start several overlapping executions.
- [ ] The page does not become blank.

## Read-only behavior

- [ ] Refresh Parent Dashboard several times.
- [ ] Missions `Updated At` does not change merely from dashboard reads.
- [ ] MissionProgress is not rewritten by dashboard reads.
- [ ] Completing a quiz still updates mission progress and handoff normally.

## iPhone and desktop

- [ ] No horizontal page overflow on iPhone.
- [ ] Weekly Reward Bank fits correctly.
- [ ] Long wording wraps.
- [ ] Analytics panels update independently without shifting outside the page.
