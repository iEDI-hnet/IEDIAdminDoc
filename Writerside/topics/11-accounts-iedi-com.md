# iEDI.com accounts

**Route:** `/iedi_accounts`  
**Template:** `iedi_accounts` (+ embedded `account` detail)

Primary workspace for iEDI.com **agreements** (customer accounts). The account list is the same regardless of which environment is selected in the top bar **Change Environment** dialog.

## Main table columns

| Column | Description |
|--------|-------------|
| Created | Account creation time |
| Owner | Agreement id (with name when available) |
| Subscription | Product tier |
| Promo | Promotional flag (checkbox column) |
| Description | Account description |
| Helpdesk | Helpdesk reference |
| Changed | Last change |
| Synced | Last sync indicator |

Table features: server-side paging, row selection, page length 25, CSV/PDF export where enabled.

## Open account detail

1. Select **exactly one row** in the table (row select). This enables the toolbar buttons.
2. Click **Edit Account**.

The [account detail](14-account-detail-tabs.md) view opens with tabs for settings, file policies, and optional integrated apps. Selecting a row alone does **not** open the detail panel.

## Toolbar actions

| Action | Purpose |
|--------|---------|
| Edit Account | Open detail view for the single selected row (required after selection) |
| Login As | Impersonate / open customer session (controlled) |
| Create Account / Create User | New account or user flows |
| Add Endpoint | Attach endpoint to account |
| Remove Deleted | Cleanup soft-deleted records |
| Delete / Undelete | Mark account deleted or restore |

## Context menu

Right-click or row menu duplicates several toolbar actions for the selected account (including **Edit Account**).

## Dimension

**Not dimension-sensitive.** The accounts table does not filter by Production, Test, or other environments. Changing environment from the top bar affects EDI message pages and related tools, not which agreements appear here.

If the table reloads after a dimension change, the same account rows are shown; only message-centric screens change their data set.
