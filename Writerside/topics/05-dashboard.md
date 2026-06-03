# Dashboard

**Route:** `/dashboard`  
**Template:** `dashboard`

The dashboard is the landing page after login. It summarizes operational health and quick actions.

## Main areas

| Area | Description |
|------|-------------|
| Stat widgets | High-level counts (errors by document type, portal-related metrics) |
| **Jobqueues** / **Waiting messages** | Toggle between C3 chart views |
| Action widgets | Shortcuts: invite, upload, download (configuration-dependent); invite and upload use the **Agreement** from [Change Environment](03-dimensions-and-environment.md) when set |
| Invitation tables | Sent and received invitations (tabular) |
| Internal blog widget | Recent internal posts |
| GitHub tables | Repository / branch status (when enabled) |

## Actions

| Action | Location |
|--------|----------|
| Toggle Jobqueues vs Waiting messages | Section header control |
| PDF / Event monitor configuration | Cog on relevant widgets |
| Open messages from waiting stats | Links may open `/messages?dim=W` |

## Dimension

Portal statistics subscription uses the active dimension. Some drill-down links set dimension explicitly (for example Waiting → `dim=W`).

## Related pages

- Waiting message detail: [EDI messages](21-edi-messages.md) with dimension **W**
- PDF/events monitoring: [PDFs and reminders](25-edi-pdfs-and-reminders.md)
