# Nemhandel, NRS, and other networks

## eDelivery DK (nemhandel)

**Route:** `/nemhandel`

Bootstrap-style tabs; each tab loads its own DataTable when selected.

| Tab | Content |
|-----|---------|
| Participants | Nemhandel participants |
| Profiles | Profile definitions |
| Services | Services |
| Business | Business entities |
| Nemhandel Register | Detailed info on registered entries via NemHandel API |
| Tracking | Tracking records (Placeholder) |

Column sets are defined per tab in `nemhandel.js`. Uses `x-iedi-dim` in data calls to switch between production PORS and the related sandbox.

## NRS Error Codes

**Route:** `/nrs_error_codes`

| Widget | Filters table by section |
|--------|--------------------------|
| Header / Lines / Summary / … | Error code category |

| Column (typical) | Description |
|------------------|-------------|
| Created | Timestamp |
| Document Type | EDI document |
| Section | Code section |
| Code | Error code |
| Message | Description |

Global subscription `nrs_error_codes`; not dimension-parameterized the same way as messages.

## Tieto FI

**Route:** `/tieto`

External iframe (Finnish network operator UI). Nav shows **Todo** badge.

## AS2 / D.U.C / KMD

See [Protocols and endpoints](31-networks-protocols-and-endpoints.md).
