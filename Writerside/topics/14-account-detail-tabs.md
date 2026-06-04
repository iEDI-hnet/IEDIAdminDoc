# Account detail tabs

Account detail appears after **Edit Account** on **iEDI.com accounts** (one row selected).

## Header fields

| Field | Meaning |
|-------|---------|
| Status | Active vs Deactivated |
| Account ID / Agreement ID | Identifiers |
| Helpdesk | Helpdesk link |
| Subscription | Plan name; upgrade badge on Basis |
| Created / Updated | Timestamps |
| Datacenter / Country / Language | Hosting and locale |

Context menu (**⋯**) on the header provides account-level shortcuts (same family as list toolbar).

## Tabs — standard user (non-superuser on detail)

| Tab | Content |
|-----|---------|
| **Account** | Name, description, login (read-only), password reset controls, logo upload, account settings form |
| **File Policies** | Inbound/outbound file policy configuration |
| Dynamic app tabs | One tab per entry in `settings.apps` (embedded iframe or app URL) |

## Tabs — superuser

| Tab | Content |
|-----|---------|
| **User Permissions Manager** | Teams, users, environment and feature permission matrix; Add Permission/Team; Save, Reset, Remove Access |
| **Permissions Overview** | Read-only summary of effective permissions |
| **Dimensions Management** | Configure which dimensions exist for the agreement and user access |

## Common actions on Account tab

| Action | Notes |
|--------|-------|
| Show Password | Reveals stored credential (restricted) |
| Reset Password | May be marked non-functional in UI |
| Save settings | Persists account form fields |
| Logo upload | Company logo for customer branding |

See [Superuser tools](41-tools-superuser.md) for permission tab detail.
