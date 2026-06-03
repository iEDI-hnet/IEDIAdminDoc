# PDFs and reminders

## PDFs & Events

**Route:** `/pdfs`

Two side-by-side tables:

| Table | Purpose |
|-------|---------|
| PDFs | Portal-generated PDF documents |
| Events | Related portal events |

Rows may expand for detail. **View** buttons open portal context.

| Action | Purpose |
|--------|---------|
| Monitor configuration (cog) | PDF/Event monitor setup (shared with dashboard) |
| View | Open PDF or event in portal |

Some API calls pass `x-iedi-dim`; confirm dimension when results look empty.

## Reminders

**Route:** `/reminders`

Single DataTable of scheduled or active reminders (columns defined in `reminders.js`).

Used for follow-ups on customers or messages according to internal reminder rules.

## Dimension

Lower sensitivity than Messages; PDF calls may still reference dimension in methods.
