# Sign-in and access

## Login

Access is through the organisation Google sign-in flow tied to Meteor accounts. A valid **JWT** is stored locally (`x-iedi-jwt`) after authentication.

Routes without a valid session redirect to `/login`.

## Authorization

| Check | Effect |
|-------|--------|
| Logged in | Required for all pages except login |
| Admin (`isAdmin`) | Required for standard secure routes |
| Role: `superuser` | Required for `/superuser` and superuser tabs on accounts |
| Per-dimension role `run_P`, `run_T`, … | Limits which environments appear in the **Change Environment** dialog |

Unauthorized users are sent to `/unauthorized`.

## Profile menu (top of sidebar)

From the account block at the top of the left navigation (name / role dropdown):

| Entry | Action |
|-------|--------|
| **Superuser** | Opens `/superuser` (superuser role only) |
| **Log out** | Clears session and returns to login |

Switching **environment (dimension)** is not done from this menu. Use the top bar **Environment: …** link and the **Change Environment** dialog — see [Dimensions and environment](03-dimensions-and-environment.md).

## Top bar

| Control | Action |
|---------|--------|
| **Environment: …** (database icon) | Opens **Change Environment** dialog |
| **Sync** | iEDICOM online archive status (when installed) |
| **Log out** | Same as sidebar logout |

## Language and theme

- **Language**: switcher in the sidebar header (TAPi18n; typically EN / DA).
- **Theme**: light / dark switcher beside language.

Settings follow the logged-in Google user when configured on the agreement.

## URL parameters

| Parameter | Meaning |
|-----------|---------|
| `?dim=` | Active **environment** (P, T, W, I, D, A)—used across dimension-scoped modules |
| `?acc=` | **Agreement** (customer owner id) for a **limited** set of helpdesk tools—archive, upload, invitations—not a global app filter |
| `jwt=` | One-time token hand-off |

Internal links usually preserve `?dim=`. `?acc=` is kept when present but only affects the workflows described under **Agreement (`acc`) — limited scope** in [Dimensions and environment](03-dimensions-and-environment.md).
