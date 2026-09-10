# Homeroom — daily use

How the app is actually used once it's set up (see `GETTING-STARTED.md`
if you haven't done that yet). Walks through each tab in the order they
appear across the top of the app.

Also published as a formatted page: see the Artifact link shared alongside
this file, or ask to have it republished if the link's gone stale.

---

## Dashboard

The landing page. One card per student, showing their overall average
and a count of lessons in each stage (To Do / In Progress / Needs Review
/ Done) for the active year. If anything's waiting on your review, a
banner says so right on the card. **Open planner** and **View report**
jump straight to that student's Planner or Reports for the active year.

## Planner

A Kanban board — one student at a time (switch students with the tabs
at the top), one board per active year. Four columns: **To Do → In
Progress → Needs Review → Done**.

- **Add lesson** to create a new assignment (subject, quarter, title,
  optional due date). It starts in To Do.
- Move a card between columns with the status dropdown on the card
  itself, or drag it if that's easier for the student.
- **Needs Review is a real checkpoint, not just another column.**
  Recording a grade — from anywhere in the app — always lands an
  assignment here, never straight to Done. The only way something
  becomes Done is picking it from the status dropdown yourself, which is
  the deliberate "I've looked at this and it's final" step. If a student
  drags a card to Review with no grade yet (common when a parent has to
  grade the test), that's expected — grade it from here whenever you get
  to it.
- **Import** pastes in a batch of assignments at once instead of adding
  them one by one — see `HOW-TO.md` for the format.
- The filter row (Subject / Quarter dropdowns) narrows the board down
  without changing what's actually on it.

## Calendar

A week view of everything with a due date, for the active student and
year. **Prev / Today / Next** move the week; anything without a due date
collects in its own bucket below so it's not just missing. Click a chip
to jump to that lesson. Days in the past with unfinished work are
highlighted.

If you've turned on the reminders bell (top bar, next to the app name),
the browser will notify you about overdue and due-today work — but only
while Homeroom is actually open in a tab; it can't page you otherwise.

## Attendance

One student + one school year at a time (tabs and a dropdown at the
top). Click any weekday cell to check off "instruction conducted" —
weekends are greyed out and can't be clicked by default. Switch the
**Instruction / Holiday** control to **Holiday** to mark breaks instead
— those show an "H" and are shared across all three kids, since you all
follow the same school calendar. **Print / Save PDF** produces the
county-style attendance record for whichever student + year you're
looking at. Works the same way for past years as the current one.

## Grades

Where scores actually get entered — a form, not a spreadsheet.

- **New assignment** records a grade for something that was never
  planned in the Planner (e.g. a pop quiz) — pick subject, quarter,
  title, then Possible/Actual points.
- **Existing lesson** grades something already sitting in the Planner —
  pick it from the dropdown, enter points.
- Either way, saving sends the assignment to **Needs Review** — it does
  *not* mark it Done. (If the on-screen text near the top of this tab
  still says otherwise, that's a known stale label — the actual behavior
  is Review, and Done is always the separate manual step below.)
- Anything currently in Review shows right at the top of this tab so you
  don't have to go hunting for it on the Planner board.
- **Recently graded** is a quick log of the last several scored items,
  with inline edit/delete if you need to fix a typo.

## Reports

The quarterly progress report card for one student, active year only —
every subject, every quarter's percent/letter, a cumulative column, and
an overall GPA. **Export CSV** if you want the raw numbers elsewhere;
**Print / Save PDF** for a physical or PDF copy.

## Transcript

The multi-year academic record for one student — every school year that
exists for them, tracked or historical, side by side. Tracked years pull
live from Planner/Grades; historical years are entered directly here
(one at a time, or in bulk — see `HOW-TO.md`). This is also where you
print the actual transcript document.

---

## The two top-bar toggles

Next to the app name: a **reminders bell** (due-date browser
notifications — see Calendar, above) and a **celebration toggle** 🎉
(the confetti/chime moment when work is sent to Review). Both are
per-device preferences — they live in this browser only and don't travel
with an exported backup or show up on another device.

## Everything else

Setup (adding students/subjects/years, grading scale, school info) is
occasional, not daily — see `GETTING-STARTED.md`. Backing up, restoring,
and both bulk-import flows are covered in `HOW-TO.md`.
