# Getting help

## In-application help

Some routes set a help context id (for example iEDI accounts uses context `1000`) for contextual help integration when enabled.

## Support channels

| Channel | URL |
|---------|-----|
| iEDI Helpdesk | https://iedi.com/customer-portal/ |
| Corporate site | https://iedi.com |
| Email | info@iedi.com |

## Escalation checklist

When reporting an Admin UI issue, include:

1. **Route** (for example `/messages`, `/ppf`)
2. **Environment** (`?dim=` value, for example `P` or `T`) and, if relevant, **Agreement** (`?acc=` — archive, upload, invitations only)
3. Message or account **id**
4. Screenshot of table filters and error text
5. **Time**

Do not send JWT tokens or customer passwords in tickets.

### Filters feel wrong or the page is slow?

Colleagues often report that table filters “do nothing” or that Admin feels sluggish. In many cases the UI is still using **old data or scripts** cached in the browser—not a server outage.

Before opening a ticket, try this (takes a few minutes):

1. **Sign out** of Admin (top bar or sidebar **Log out**).
2. Clear **cached images and files** and **site data** for `admin.iedi.net` in your browser (or use a private/incognito window and sign in again).
3. Sign back in, set the correct **Environment** in the top bar, and retry the filter.

If it works after that, note “resolved after cache clear” in any follow-up. If it still fails, use the checklist above and include which filter / action you used and what you expected to see.

## Related documentation

| Guide | Link |
|-------|------|
| iEDI.app API (user guide) | [IEDIAppApiDoc](https://iEDI-hnet.github.io/IEDIAppApiDoc/) |
| FastProducts (end users) | [FastSeriesDoc](https://iEDI-hnet.github.io/FastSeriesDoc/) |
| iEDI.app API reference (ReDoc) | [api.iedi.app/redoc](https://api.iedi.app/redoc) |

For any detail not covered here, contact iEDI development team.
