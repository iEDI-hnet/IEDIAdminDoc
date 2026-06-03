# Online forms

**Route:** `/online_forms`

Inbox for customer submissions from online forms (support / onboarding).

## Main table

| Column | Description |
|--------|-------------|
| Status | Read / unread (badge) |
| Created | Submission time |
| Company | Submitter company |
| Message | Summary text |
| Comments | Internal comments (may include hidden columns) |

## Workflow

1. Select a row to open the **detail panel** below or beside the table.
2. Review form fields and the embedded **form data** sub-table.
3. Add or update an internal comment.
4. Close the detail panel when done.

Unread count appears as a **label** on the sidebar menu item (polled periodically).

## Dimension

Not filtered by EDI dimension; tied to notification / form submission services.
