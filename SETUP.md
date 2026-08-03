# Math Master v6.3 — Fair Play & Math Quest

## Fair-play protection

Targeted Practice can no longer be used to farm XP or finish missions quickly.

Rules:

1. Only the first Targeted Practice set linked to a new assessment can earn XP.
2. Maximum 2 rewarded Targeted Practice sets per student per day.
3. Each eligible set earns a flat 30 XP.
4. Repeated or excess sets are still saved for learning, but:
   - earn 0 XP;
   - do not count as mission practice;
   - do not add mission questions;
   - do not increase lifetime rewarded-question totals.
5. Assessment XP is unchanged.
6. Google Apps Script makes the final reward decision.

## Interface

The new interface uses an original Math Quest platform-game theme with an
original Math Explorer mascot, equation blocks, game-style buttons and a
brighter mobile layout.

It does not include official Mario/Nintendo logos or copyrighted character art.

## Spreadsheet updates

`Sessions` gains:

- Parent Session Label
- Practice Round

`XPHistory` gains:

- Reward Eligible
- Eligibility Reason
- Source Assessment

## Installation

1. Open the Math Master spreadsheet.
2. Go to `Extensions → Apps Script`.
3. Replace the current `Code.gs` with the supplied v6.3 file.
4. Save.
5. Run `setupSheets()` once.
6. Do not run `rebuildProfilesFromHistory()` unless you intentionally want a
   full historical rebuild.
7. Update the existing Web App deployment:
   `Deploy → Manage deployments → Edit → New version → Deploy`
8. Replace the root GitHub `index.html` with the supplied file.

Test URL:

https://abuubaidahrj.github.io/quiz-app/?version=v6-3-fair-play

## Verification

1. Finish an assessment and its first Targeted Practice:
   expected +30 XP and mission credit.
2. Repeat practice from the same assessment:
   expected 0 XP and no mission credit.
3. Finish a second assessment and its first practice:
   expected +30 XP.
4. Finish a third assessment and practice on the same day:
   expected 0 XP due to the 2-set daily limit.
5. Check `XPHistory → Eligibility Reason`.
