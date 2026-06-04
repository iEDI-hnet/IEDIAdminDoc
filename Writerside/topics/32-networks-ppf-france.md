# PPF (France annuaire)

**Route:** `/ppf`  
**Shell:** `ppfShell`

French **PPF** integration: search and create entities in the public directory (Code routage, Ligne annuaire, Siren, Siret).

Not scoped by EDI dimension; calls the PPF integration API via Meteor methods.

## Top-level tabs (entity type)

| Tab | Entity |
|-----|--------|
| Code routage | Routing codes |
| Ligne annuaire | Directory lines |
| Siren | French company id (9 digits) |
| Siret | Establishment id (14 digits) |

## Per-entity sub-tabs

Each entity tab has:

| Sub-tab | Purpose |
|---------|---------|
| **Find** | Search form + results table |
| **Create** | Create new entity form |

## Find toolbar

| Control | Purpose |
|---------|---------|
| Find / Search | Run search (`ppf.find*` methods) |
| Advanced filters | Extra criteria (config-driven from `ppf_filters_config.js`) |
| Health | Calls `ppf.state`; shows integration health in a dialog |
| Master-detail back | Return from detail row to list |

## Default load

On first open, **Code routage** runs a default Find with empty filters (typically up to 50 rows).

## Results table

Columns are dynamic per entity (instance id, history, denomination, siret/siren fields, etc.). Select a row for **master-detail** inspection.

## Filter persistence

Last-used filter values per form are stored in `localStorage` under `ppf.filters.<formKey>`.

## Create forms

Each entity type has validation rules (`ppf_constraints.js`, `ppf_form_rules.js`). Submit creates via PPF API.

## Technical reference

Developer notes: `client/views/pages/networks/ppf/README.md` in the iedi-adm repository.
