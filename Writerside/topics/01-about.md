# About iEDI Admin

iEDI Admin is the internal web application for operating iEDI customer environments: accounts, EDI traffic, network integrations, and support tooling.

This guide describes **screens, tables, tabs, and actions** as implemented in the Meteor admin UI. It is written for helpdesk staff, operations, and consultants—not for backend developers.

## What this guide covers

- Signing in and choosing an **environment (dimension)**
- Sidebar navigation (Dashboard, Accounts, EDI, Networks, Tools)
- Each major **table page**: filters, columns, toolbar actions, context menus
- **Tabs** on account and message detail views
- **PPF (France)** directory search and create flows

## What this guide does not cover

- Server deployment, secrets, or infrastructure (internal operations documentation only)
- Placeholder menu items marked **Todo** in the UI (myUBL accounts, GTS, D.U.C, KMD, Tieto FI) until those pages are implemented

## Public documentation

This site is published from the public **IEDIAdminDoc** repository. Do not add credentials, customer data, or internal runbooks here. Access to the live Admin application remains protected by sign-in.

## Audience roles

| Role | Typical use |
|------|-------------|
| Helpdesk / support | Messages, archive, accounts, online forms |
| Integration | Protocols, endpoints, nemhandel, PPF |
| Superuser / admin | Permissions, dimensions, superuser workspace |
| Operations | Dashboard job queues, overwatch, PDF/event monitors |
