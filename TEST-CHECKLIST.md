# Math Master v7.3.2 — Test Checklist

## Basic analytics

- [ ] Unlock the dashboard.
- [ ] Analytics loads and the synchronization timestamp appears.
- [ ] Server processing time is displayed.
- [ ] Changing students loads the correct student.
- [ ] Repeated fast student changes do not show stale data.

## Retry and snapshot

- [ ] Load the dashboard successfully once.
- [ ] Temporarily disconnect the device from the internet.
- [ ] Tap Refresh.
- [ ] The last successful dashboard remains visible.
- [ ] A connection banner explains that a snapshot is being shown.
- [ ] Reconnect the internet and tap Retry now.
- [ ] Live analytics replaces the snapshot.
- [ ] The banner disappears after success.

## Safe writes

- [ ] Save one new mission.
- [ ] Only one mission row is created.
- [ ] Archive, approve and redeem actions are not duplicated.
- [ ] Read-only retries do not replay write operations.

## Performance

- [ ] Open Apps Script → Executions.
- [ ] Check `getParentDashboard` duration before and after the patch.
- [ ] Confirm a normal refresh has only one execution.
- [ ] Confirm there is no repeated full-sheet read caused by the frontend.

## Responsive dashboard

- [ ] iPhone portrait has no horizontal page scrolling.
- [ ] Weekly Reward Bank wording and cards fit correctly.
- [ ] Long mission and reward names wrap.
- [ ] Tables scroll inside their own panels.

## Existing functions

- [ ] Mission 2 activates immediately after Mission 1.
- [ ] Unlimited valid assessment credits remain active.
- [ ] Unlimited legitimate Targeted Practice remains active.
- [ ] Fair question rotation still works.
