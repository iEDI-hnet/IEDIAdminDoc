# EDI messages overview

The **EDI** section covers operational message handling: live queues, exceptions, archive search, PDFs/events, and reminders.

| Page | Route | Role |
|------|-------|------|
| Messages | `/messages` | Primary production/test queue |
| Other messages | `/other_msg` | NRS / workflow exceptions |
| Archive | `/archive` | Historical search |
| PDFs & Events | `/pdfs` | Portal PDF and event monitors |
| Reminders | `/reminders` | Scheduled reminders |

## Shared message table (Messages / Other messages)

Both use **Tabular** `Messages` with the same core columns:

| Column | Description |
|--------|-------------|
| Created | Message timestamp |
| Owner | Agreement |
| Document | Document type (INVOIC, ORDERS, …) |
| Number | Document number |
| Sender / Receiver | Party ids and names |
| Network | Timeline / network indicators |
| Workflow | State (completed, error, waiting, …) |
| Comments | Inline comment field |
| Log | Log summary |

## Shared detail tabs (selected message)

When a message is selected (inline panel or `/message`):

| Tab | Content |
|-----|---------|
| Document | EDI document view |
| Images | Attached images |
| Attachments | File attachments |
| Data | Raw / structured data |
| Log | Processing log |
| Network | Network JSON / routing |
| Debug | Debug tools (role-dependent) |

## Dimension

All EDI list pages require the correct **environment** selected in the top bar (**Change Environment** dialog). Archive adds an in-page dimension dropdown for cross-environment archive search where permitted.

## Deep links

| Route | Opens |
|-------|--------|
| `/message?id=…&owner=…` | Full-page [message detail](24-edi-message-detail-and-timeline.md) |
| `/timelineTwo` | [Timeline](24-edi-message-detail-and-timeline.md) for related documents |
