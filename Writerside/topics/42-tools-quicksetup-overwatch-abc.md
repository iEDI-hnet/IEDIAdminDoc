# Quick setup, Overwatch, and ABC

## Configuration (quick setup)

**Route:** `/quicksetup`

Vertical **timeline wizard** for onboarding a new customer integration.

| Step (typical) | Purpose |
|----------------|---------|
| Company | Company master data |
| Receive | Inbound channel setup |
| Transmit | Outbound channel setup |
| Format | Document formats |

Each step opens a modal sub-template (`qs_company`, `qs_receive`, `qs_transmit`, `qs_format`). Buttons: **Configure**, **Choose**, etc.

Uses agreement context; may read dimension for defaults.

## Overwatch

**Route:** `/overwatch`

Danish support / billing operations console.

| Area | Content |
|------|---------|
| Customers table | Active customers |
| Billing form | Case billing fields (supporter, time, amount, currency, comment) |
| Latest cases table | Recent cases |

| Action | Purpose |
|--------|---------|
| Nulstil | Reset form |
| Opret sag | Create case |

Default Meteor calls often use dimension **T** (Test)—confirm before production impact.

## ABC

**Route:** `/abc`

Partner lookup (Danish **ABC** registry integration).

| Control | Purpose |
|---------|---------|
| Search form | Partner search criteria |
| Results table | Matching partners |
| Søg Partner | Execute search |
| Opret | Create partner from selection |

Not dimension-scoped.
