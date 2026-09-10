# Homeroom — how-to guide

Reference articles for the less-frequent, higher-stakes actions in the app
— backups, restoring, and both bulk-import flows — so you don't have to
rely on memory for these.

One of four docs: `GETTING-STARTED.md` (one-time and per-year setup),
`DAILY-USE.md` (the regular workflow across every tab), this file
(maintenance and special features), and `CHANGELOG.md` (what's shipped,
in plain language).

Also published as a formatted page: see the Artifact link shared alongside
this file, or ask to have it republished if the link's gone stale.

---

## Back up your data

**When:** Periodically, and always before Erase Everything or a Restore.

Your data lives only in this browser's storage — there's no cloud copy. A
backup file is the only way to move it to another device, or to recover if
something goes wrong.

1. Go to **Setup → Data**.
2. Click **Export all data (JSON)**.
3. Your browser downloads a file named `homeroom_backup_<date>.json`. Save
   it somewhere durable — cloud drive, email it to yourself, whatever you'd
   trust with the only copy, because right now it is.

There's no reminder for this — make it a habit, e.g. after finishing a
quarter's grades, or before trying anything you're unsure about.

---

## Restore from a backup

**When:** You want to undo a mistake, move data to another device/browser,
or recover after clearing browser data by accident.

1. Go to **Setup → Data**.
2. Click **Restore from backup**.
3. Click **Choose file** and pick a `.json` file you previously exported.
4. Check the preview — it shows how many years/students/subjects/lessons
   are in that file, so you can confirm it's the one you meant.
5. Click **Replace all data**, then click it again to confirm.

**This replaces everything currently in the app** with the file's contents
— there's no merge, and no undo once you confirm. If you're not sure the
current data is worth keeping, export a backup of *that* first (previous
article) before restoring something else over it.

An invalid or corrupted file is rejected with an error and changes nothing.

---

## Erase everything (start over)

**When:** You genuinely want to wipe the slate — new setup, testing, or
starting fresh with nothing carried over.

1. Go to **Setup → Data**.
2. Click **Erase everything**, then click it again to confirm.

This is *not* a restore to any prior state — it empties the app completely:
no students, no subjects, no years, no school info, nothing. There's no
undo except restoring a backup you made beforehand (see above). If in
doubt, back up first.

---

## Bulk-import assignments (CSV/TSV)

**When:** You have a list of assignments for a subject — e.g. from a
publisher's scope-and-sequence — and don't want to add them one at a time.

**Format:** three columns, in this order, comma- or tab-separated:

```
Subject,Quarter,Title
Algebra II,Quarter 1,Week 1
Algebra II,Quarter 1,Week 2
American History,Quarter 1,Week 1
American History,Quarter 1,Week 2
```

- A header row is optional — it's auto-detected and skipped if present.
- **Subject and Quarter must already exist** for that student (Setup →
  Subjects / Quarters) — the importer matches by name, it doesn't create
  new ones. Set those up first.
- Matching is case-insensitive, but otherwise must match exactly (no
  partial matches).
- This only imports the title. No points, no due date, no status — every
  row lands as an ungraded **To Do** card. Add due dates and grades
  afterward.

**Steps:**

1. Go to **Planner**, select the student, click **Import**.
2. Paste rows in the format above, or click **Choose file** for a `.csv`
   or `.txt` file.
3. Click **Preview**. Rows that matched an existing Subject and Quarter are
   marked ready; unmatched rows show what didn't match (fix the name in
   your source, or add the missing Subject/Quarter in Setup, then re-paste).
4. Click **Import N lessons**.

---

## Printing a clean PDF (Transcript, Report Card, Attendance)

**When:** Any time you click **Print / Save PDF** on one of these three —
they all go through your browser's print dialog, which has a couple of
settings worth checking before you save, or the result can look rougher
than it needs to.

1. Click **Print / Save PDF** on the document you want.
2. In the print dialog, open **More settings**.
3. Uncheck **Headers and footers**. Without this, the browser adds its
   own date/time stamp, the page title, the file's local path, and page
   numbers to every page — none of that is part of the actual document,
   and a raw file path looks unprofessional on something like an official
   transcript.
4. If content looks cramped or spills onto more pages than you'd expect,
   try lowering **Scale** (e.g. from 100% down to 75%) rather than
   leaving it at default — this can pull everything onto fewer, better-
   fitting pages.
5. Save as PDF, or print for real.

These are browser print-dialog settings, not something Homeroom can set
for you automatically — they're per print job (some browsers remember
your last-used settings for next time, some don't).

---

## Add historical course grades (past years)

**When:** Entering a completed year's final grades — a year you're
recording after the fact, not tracking lesson-by-lesson.

Historical years don't use the Planner or individual lessons at all —
just one row per course, with its final grade. You can add courses one
at a time, or paste a whole year's worth at once.

**One at a time:**
1. Go to **Transcript**, select the student.
2. Scroll to the historical year you want (labeled "Historical entry").
3. Click **Add course**.
4. Fill in:
   - **Type** — subject area, e.g. `Math`, `English`, `Elective`.
   - **Course title** — e.g. `Algebra I`.
   - **Grade %** — the final numeric grade.
   - **Credit** — defaults to `1`; adjust for half-credit courses etc.
5. Click **Add course** again to save the row. Repeat for each course in
   that year.

**In bulk:**
1. Go to **Transcript**, select the student, scroll to the historical year.
2. Click **Bulk import** (next to Add course).
3. Paste rows copied from a spreadsheet — one course per line, columns in
   the order `Type, Course Title, Grade %, Credit` — or use **Choose
   file** to load a `.csv`/`.txt` file in the same format. Comma- or
   tab-separated both work.
4. Click **Preview**. Rows with a missing title or a non-numeric Grade %
   or Credit are flagged and won't be imported — fix them in the
   textarea and preview again, or leave them out; the rest still go
   through. A blank Credit defaults to `1`.
5. Click **Import N courses**.

Each row (from either method) can be edited (pencil icon) or deleted
afterward if you need to fix something.
