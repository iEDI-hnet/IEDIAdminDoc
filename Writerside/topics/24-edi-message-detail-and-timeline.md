# Message detail and timeline

## Full-page message view

**Route:** `/message`  
**Template:** `messageView`

Opened from **Show Message**, timeline links, or deep links with `id` and `owner` query parameters.

### Tabs

| Tab | Purpose |
|-----|---------|
| Document | Primary EDI content |
| Images | Image gallery |
| Attachments | Downloadable files |
| Data | Payload / mapped data |
| Log | Step-by-step log |
| Network | Partner routing details |
| Debug | Technical debug (restricted) |

### Header actions

| Action | Purpose |
|--------|---------|
| Back | Return to timeline or message list |
| Open IMU | Mapping editor |
| Debug / Run Workflow | Technical reprocessing |
| Print | Print-friendly view |
| Timeline | Open case timeline |
| Action menu | Release, Delete, Archive, dimension moves, Ticket, Comments, Download, … |

## Timeline

**Route:** `/timelineTwo`  
**Template:** `timelineTwo`

Vertical timeline of related documents (orders, despatch, invoice, etc.).

| Element | Description |
|---------|-------------|
| Entry | Document type, number, format, archived flag, date |
| Show Message | Opens `/message` for that document |

Used to trace a business case across multiple EDI messages.

## Dimension

Query string preserves `?dim=` when navigating between timeline, messages, and message detail.
