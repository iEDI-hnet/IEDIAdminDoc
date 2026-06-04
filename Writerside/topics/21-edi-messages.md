# Messages

**Route:** `/messages`  
**Template:** `messages`

Main message queue for the active dimension.

## Header widgets

| Widget | Filter |
|--------|--------|
| iEDI.com | iEDI.com-related subset |
| iEDI.online & PDF | Online / PDF-related subset |
| Uncommented | Messages without comments |
| Total | Clear widget filter |

Click a widget to filter the table; use Total to reset.

## Toolbar actions

| Action | Purpose |
|--------|---------|
| Show Message | Open detail panel or navigate to full view |
| Edit Account | Jump to owning account |
| Login As | Customer impersonation (controlled) |
| Remove Deleted | Remove soft-deleted from view |
| Open IMU | Mapping utility |
| My Messages | Filter to current logged in user (ticket) |

### Action menu (bulk / row)

| Action | Purpose |
|--------|---------|
| Run Workflow | Re-run processing workflow |
| Move / Run dimension | Move to / Run in W, P, T, etc. |
| Hide Completed | Hide completed rows |
| Comments | Comment workflow |
| Reject email | Send rejection notification |
| Release | Release held message |
| Archive | Send to archive |
| Delete | Delete message |

Account **tags** filter (agreement numbers) may appear in the toolbar when configured.

## Context menus

- Table context menu: row actions
- Single-message context menu: same actions for one message

## Smart search

Document-type smart search may be disabled on this table; use column search and widgets.

## Related

- [Other messages](22-edi-other-messages.md) for NRS-specific queues
- [Message detail and timeline](24-edi-message-detail-and-timeline.md)
