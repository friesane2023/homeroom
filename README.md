# Homeroom

A free lesson planner and gradebook for homeschool families — built to
replace the spreadsheet-plus-sticky-notes setup a lot of us end up with.
I started out with folders and felt like I was so organized, until I had
to keep track of grades for the high schoolers.

**[Open the live app →](https://friesane2023.github.io/homeroom/)**

## What it does

- **Planner** — a To Do / In Progress / Needs Review / Done board per
  student, so lesson planning works like a sprint board instead of a
  static list.
- **Grades** — quick entry for scores, with a review queue for anything a
  student has marked finished but a parent hasn't checked yet.
- **Attendance** — a printable, county-form-style attendance sheet per
  student per school year — click a day to mark it, weekends greyed out.
- **Reports** — a printable quarterly progress report per student,
  calculated from actual/possible points.
- **Transcript** — a multi-year, print-ready high school transcript
  (type, course, grade, credit, GPA), built automatically from tracked
  years, or filled in by hand for years before you started using the app.
- **Diploma** — a printable high school diploma once a student's done.
- **Setup** — students, school years, subjects, grading scale, and school
  info, all editable.

## Your data stays yours

Homeroom runs entirely in your browser, with everything saved to your
device's local storage by default — no account needed, and nothing sent
anywhere unless you turn sync on yourself (see below). That also means
it's per-browser out of the box: switching browsers or devices starts
fresh unless you either export/import a backup (**Setup → Data →
Export**), or set up sync.

**Optional multi-device sync:** if you want the same data to show up on
every phone/tablet/laptop, Homeroom can sync through your own free
Firebase project — not a shared service, and nothing the maintainer of
this repo can see. Entirely opt-in; skip it and everything above still
works exactly the same, fully offline. See
[FIREBASE-SETUP.md](FIREBASE-SETUP.md) for the walkthrough.

## Running your own copy

You don't need to install anything. Options, easiest first:

1. **Use the hosted version** at the link above — nothing to set up.
2. **Fork this repository** on GitHub and turn on GitHub Pages (Settings
   → Pages → Deploy from branch → `main` / `root`) to get your own copy
   at `https://yourusername.github.io/homeroom/`.
3. **Download `index.html`** and open it directly in any browser — it
   works completely offline.

## For other homeschool families

If you'd like to run this for your own kids, forking the repo (option 2
above) gives you a copy that's entirely separate from anyone else's —
your data, your browser, your URL. Want sync across your own family's
devices too? See [FIREBASE-SETUP.md](FIREBASE-SETUP.md) once you're set
up.

## License

MIT — see [LICENSE](LICENSE). Use it, change it, share it.
