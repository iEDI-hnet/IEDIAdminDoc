# Dimensions and environment

A **dimension** is the runtime environment for EDI data in Admin. Message and many network pages filter by the active dimension. **Account lists do not** (including iEDI.com accounts).

## Standard dimensions

| Code | Name | Typical use |
|------|------|-------------|
| **P** | Production | Live customer traffic |
| **T** | Test | Test agreements and partners |
| **W** | Waiting | Messages held before production |
| **I** | Integration | Integration testing |
| **D** | Development | Developer sandboxes |
| **A** | Archiving | Archive-oriented views |

The agreement may define additional or renamed dimensions. The **Change Environment** dialog lists only environments your user is allowed to run.

## How to switch dimension

Use the **top navigation bar** (not the sidebar profile menu):

1. Click **Environment: …** in the top bar — the link with the database icon (`Environment: Production`, `Environment: Test`, and so on).
2. The **Change Environment** dialog opens.
3. Select the environment with the radio buttons (for example **Production**).
4. Optionally set the **Agreement** id (customer agreement / owner) when you need helpdesk scope for the tools listed below—not for everyday browsing of Messages or Accounts.
5. Click **OK**.

### Environment (`dim`) — applies broadly

- **OK** updates `?dim=` in the URL and stores `x-iedi-dim` in `sessionStorage` and `localStorage` so new tabs and refreshes keep the same environment.
- Dimension-scoped pages (Messages, Protocols, Endpoints, and similar) reload their data for the selected environment.

While the dialog is open, choosing an environment radio button already updates `x-iedi-dim` so dimension-scoped lists can refresh before you click **OK**.

### Agreement (`acc`) — limited scope

The **Agreement** field is for helpdesk workflows that act **on behalf of** a specific customer agreement. It is **not** a global filter for the whole application.

| Typically uses `acc` | Does **not** use `acc` as a global scope |
|----------------------|------------------------------------------|
| [Archive](23-edi-archive.md) search (owner context) | iEDI.com account list |
| File **Upload** from the [Dashboard](05-dashboard.md) | Portal / Pricat account lists |
| Partner **Invitations** (invite / edit invite) | Message tables (filtered by **dimension**, not by agreement) |
| Related dashboard invitation context | PPF, internal blog, ABC |

**OK** stores `x-iedi-acc` in `sessionStorage` and adds `?acc=` to the URL when a value is set; clearing the field removes it. Changing agreement does **not** replace environment selection—set **dim** and **acc** independently when both are needed (for example Production + a customer agreement id for an archive search).

## Which pages respect dimension

| Sensitive to `dim` | Not dimension-scoped |
|--------------------|----------------------|
| Messages, Other messages, Archive, Message detail, Protocols, Endpoints, nemhandel, Overwatch | **iEDI.com accounts**, Portal accounts, Pricat, Online forms, PPF (France API), Internal blog, Feedback admin, ABC partner search |

When a page shows no rows after switching dimension, confirm the correct environment is selected before assuming data is missing.

## Permissions

Non-admin users need the role `run_<dimensionId>` (for example `run_P`) to see an environment in the dialog. Superuser and admin roles see all dimensions configured on the agreement.
