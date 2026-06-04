# Accounts overview

The **Accounts** section manages customer and portal identities across iEDI products.

| Menu item | Route | Status |
|-----------|-------|--------|
| iEDI.com | `/iedi_accounts` | Full table + account detail |
| iEDI.online | `/portal_accounts` | Portal client table |
| iEDI Pricat | `/pricat_accounts` | Accounts + receivers tables |
| myUBL.com | `/myubl_accounts` | Placeholder (Todo) |
| GTS | `/gts_accounts` | Placeholder (Todo) |
| Online Forms | `/online_forms` | Submitted forms inbox |

## Common patterns

- **List + detail**: On iEDI.com, select one row and click **Edit Account** to open the detail workspace (see [Account detail tabs](14-account-detail-tabs.md)).
- **SSO / Open account**: Portal and Pricat tables include actions to open the customer context in the target product.
- **Dimension**: Account lists (including iEDI.com) are **not** filtered by environment dimension. Dimension applies to EDI messages, protocols, endpoints, and similar modules (see [Dimensions](03-dimensions-and-environment.md)).

## Count widgets (iEDI.com)

On `/iedi_accounts`, header widgets filter the main table:

| Widget | Filter intent |
|--------|----------------|
| Customers | Customer-type accounts |
| Portal | Portal-related accounts |
| Shared | Shared accounts |
| Total | All (reset filter) |

Click a widget to filter; click again or use Total to clear.
