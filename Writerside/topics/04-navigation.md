# Navigation

The left sidebar groups all primary modules.

## Menu structure

| Section | Routes (examples) |
|---------|---------------------|
| **Dashboard** | `/dashboard` |
| **Accounts** | `/iedi_accounts`, `/portal_accounts`, `/pricat_accounts`, `/online_forms`, plus Todo entries myUBL / GTS |
| **EDI** | `/messages`, `/other_msg`, `/archive`, `/pdfs`, `/reminders` |
| **Networks** | `/protocols`, `/as2`, `/duc`, `/endpoints`, `/kmd`, `/nemhandel`, `/ppf`, `/tieto`, `/nrs_error_codes` |
| **Tools** | `/superuser`, `/internal-blog`, `/admin/feedback`, `/quicksetup`, `/overwatch`, `/abc` |

## Detail routes (not always in sidebar)

| Route | Purpose |
|-------|---------|
| `/message` | Full-page message workspace (`messageView`) |
| `/timelineTwo` | Document timeline for a specific message type (usually Orders) |
| `/internal-blog/new`, `/edit/...` | Internal blog editor (used for Release Notifications) |

## Active menu highlighting

The sidebar expands the section that contains the current route. Badge labels (for example **Todo** on myUBL, unread count on Online forms) come from configuration in `navigation.js`.

## Environment (dimension)

Switch environment from the **top navigation bar**: click **Environment: …** (database icon) to open the **Change Environment** dialog. This is separate from the sidebar profile dropdown (name / role), which is used for Superuser and Log out.

See [Dimensions and environment](03-dimensions-and-environment.md).

## Collapsed sidebar

The small **iEDI** logo area keeps language and theme switchers when the sidebar is collapsed.
