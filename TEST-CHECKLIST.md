# Math Master v7.4 — Test Checklist

## Student selector

- [ ] Student page has one dropdown only.
- [ ] No editable Student ID field is present.
- [ ] No editable Student Name field is present.
- [ ] Dropdown options are Abu, Aisyah and Maryam.
- [ ] Start Quiz is disabled until a student is selected.
- [ ] Selecting Abu loads profile ABU.
- [ ] Selecting Aisyah loads profile AISYAH.
- [ ] Selecting Maryam loads profile MARYAM.
- [ ] Reloading the page restores the last selected student.
- [ ] Submitted sessions use the correct ID and normalized name.

## Recent Family Activity

- [ ] All three students appear in the activity panel.
- [ ] The latest session type is displayed.
- [ ] Targeted Practice is shown correctly.
- [ ] Exact date/time and relative time are shown.
- [ ] Students without history display `No saved activity yet`.
- [ ] Manual refresh button works.
- [ ] Completing a quiz refreshes the activity panel.
- [ ] Activity failure does not prevent Start Quiz.

## Performance

- [ ] Quiz controls are usable before activity finishes loading.
- [ ] A second load within 90 seconds uses the server cache.
- [ ] Browser-cached activity appears immediately on reload.
- [ ] Apps Script only reads the recent XPHistory tail for this endpoint.
- [ ] Parent Dashboard split loading still works.
