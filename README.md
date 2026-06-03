# IEDIAdminDoc

Stakeholder user guide for **iEDI Admin** (Meteor). Built with [JetBrains Writerside](https://www.jetbrains.com/writerside/) and published to GitHub Pages — same pattern as [FastSeriesDoc](https://github.com/iEDI-hnet/FastSeriesDoc).

**Published site (after setup):** `https://iEDI-hnet.github.io/IEDIAdminDoc/`

Application source code lives in the private **iedi-adm** repository; edit documentation here only.

**Public repo:** CI deploys only on **`master`** when `version` in `writerside.cfg` changes.

## Layout

```text
Writerside/
  writerside.cfg
  iedi-adm.tree
  topics/*.md
  cfg/buildprofiles.xml
  images/
```

## Edit and build

| Task | Where |
|------|--------|
| Topic content | `Writerside/topics/` |
| Table of contents | `Writerside/iedi-adm.tree` |
| Branding / footer | `Writerside/cfg/buildprofiles.xml` |
| Guide version (triggers CI) | `version="…"` on `<instance>` in `writerside.cfg` |
| WebStorm setup | [docs/WEBSTORM_WRITERSIDE_SETUP.md](docs/WEBSTORM_WRITERSIDE_SETUP.md) |
| GitHub Pages setup | [docs/GITHUB_PAGES_SETUP.md](docs/GITHUB_PAGES_SETUP.md) |
| Branch protection | [docs/BRANCH_PROTECTION.md](docs/BRANCH_PROTECTION.md) |

## Related guides

| Product | Repository |
|---------|------------|
| iEDI.app API | [IEDIAppApiDoc](https://github.com/iEDI-hnet/IEDIAppApiDoc) |
| FastProducts | [FastSeriesDoc](https://github.com/iEDI-hnet/FastSeriesDoc) |
