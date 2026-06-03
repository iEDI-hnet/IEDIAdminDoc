# Archive

**Route:** `/archive`  
**Template:** `archive`

Search-first view over archived messages (ajax DataTable, not the live Tabular publication).

Archive search uses the **Agreement** from the [Change Environment](03-dimensions-and-environment.md) dialog (`x-iedi-acc`) as the owner context when set; otherwise a default helpdesk agreement applies. Environment (**dim**) does not control which dimension you search within.

## Search form

| Field | Purpose |
|-------|---------|
| Sender | Filter by sender id |
| Receiver | Filter by receiver id |
| Number | Document number |
| Date range | From / to dates |
| Free text | `wsearch` enables `*` wild search |

Submit search to load the results table.

## Results table

Typical columns include Created, Document, message id, Sender, Receiver, and archive metadata. Server-side paging; dimension selector in toolbar.

## Toolbar actions

| Action | Purpose |
|--------|---------|
| Show Message | Open detail with same tabs as Messages |
| Resend / Release | Resend or release archived item |
| Refresh | Reload search results |
| Open IMU | Mapping utility |
| Dimension dropdown | Release within selected dimension |
| Tags filter | Doc. number tag filter when enabled |

## Context menus

Archive table and single-message menus mirror Messages (archive, delete, release, etc.).


## Timeline link

From a message, **Timeline** opens `/timelineTwo` with query parameters preserved.
