# Superuser
 
**Template:** `superuser`

Restricted to users with the **superuser** role (or configured superuser Meteor ids).

## Page layout

| Area | Content |
|------|---------|
| Count widgets | Team and user counts |
| Account embed | Full account workspace with superuser tabs |

## User Permissions Manager tab

| Control | Purpose |
|---------|---------|
| Team / User choosers | Select team or user to edit |
| Environment matrix | Checkboxes per dimension (P, T, W, …) |
| Feature matrix | Product feature flags |
| Add Permission / Add Team | Create assignments |
| Save / Reset | Persist or discard |
| Remove Access | Revoke access |

Context menu template `user_permissions_context_menu` for row-level actions on permission tables.

## Permissions Overview tab

Read-only grid of effective permissions for auditing.

## Dimensions Management tab

Add, remove, or reorder dimensions available to the agreement. Changes affect which environments appear in the **Change Environment** dialog for all users on that agreement.

See also [Account detail tabs](14-account-detail-tabs.md).
