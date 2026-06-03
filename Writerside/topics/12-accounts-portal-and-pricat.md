# Portal and Pricat accounts

## iEDI.online (portal)

**Route:** `/portal_accounts`

| Column | Description |
|--------|-------------|
| Account Number | Portal account id |
| Name | Company name |
| Contact Email | Primary contact |
| CVR | Company registration (DK) |
| Endpoint Id | Linked endpoint |

| Action | Purpose |
|--------|---------|
| **Open Account** | SSO into portal context for selected row |
| Edit Account | Toolbar edit flow |

Data comes from the portal API, not the Mongo database.

## iEDI Pricat

**Route:** `/pricat_accounts`

Two tables on one page:

### Accounts table

Subscription, name, email, identification, and related Pricat account fields.

### Receivers table

Receiver configuration: internal id, name, emails, frequency, EAN/CVR, profile.

| Action | Purpose |
|--------|---------|
| Open Account | SSO to Pricat for selected account |
| Company filter | Dropdown on receivers table to narrow by company |

## Placeholder account menus

| Route | UI state |
|-------|----------|
| `/myubl_accounts` | Empty; nav shows **Todo** badge |
| `/gts_accounts` | Empty; nav shows **Todo** badge |

No end-user documentation is required until templates are implemented.
