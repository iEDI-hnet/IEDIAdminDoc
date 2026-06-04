# Protocols and endpoints

## Protocols

**Route:** `/protocols`

| Column | Description |
|--------|-------------|
| Id | Protocol identifier |
| Type | Protocol type name |
| Description | Text |
| Owner | Owning agreement |
| Created | Created date |

Selecting a row opens a detail **Information** workspace with parameter fields.

| Action | Purpose |
|--------|---------|
| Save | Persist protocol parameters |
| Export | CSV/PDF when enabled |

## Endpoints (iEDI)

**Route:** `/endpoints`

| Column | Description |
|--------|-------------|
| Number | Endpoint number |
| Scheme | URI scheme |
| Name | Display name |
| Owner | Agreement |
| Changed / Synced | Maintenance timestamps |

Detail view includes multiple tabs (routing, documentation, configuration—see endpoint template).

| Action | Purpose |
|--------|---------|
| Change Owner | Reassign endpoint |
| Configure | Open configuration |
| Convert nemhandel | Migration helper |
| Show Changelog | History |
| Old nemhandel | Filter legacy mode |
| Deploy | Deploy endpoint |
| Delete | Remove endpoint |

## AS2

**Route:** `/as2`

Embedded remote desktop / VNC style console in an iframe. No local table.

## Placeholders

| Route | State |
|-------|--------|
| `/duc` | Static placeholder text |
| `/kmd` | No template in repo |
