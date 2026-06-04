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
| Writerside IDE setup | [WRITERSIDE_IDE_SETUP.md](https://github.com/iEDI-hnet/iedi3api/blob/master/iedi_project_template/docs/user_docs_repo_setup/WRITERSIDE_IDE_SETUP.md) |
| GitHub Pages setup | [GITHUB_PAGES_SETUP.md](https://github.com/iEDI-hnet/iedi3api/blob/master/iedi_project_template/docs/user_docs_repo_setup/GITHUB_PAGES_SETUP.md) |
| Branch protection | [BRANCH_PROTECTION.md](https://github.com/iEDI-hnet/iedi3api/blob/master/iedi_project_template/docs/user_docs_repo_setup/BRANCH_PROTECTION.md) |

## Related guides

| Product | Repository |
|---------|------------|
| iEDI.app API | [IEDIAppApiDoc](https://github.com/iEDI-hnet/IEDIAppApiDoc) |
| FastProducts | [FastSeriesDoc](https://github.com/iEDI-hnet/FastSeriesDoc) |

## License

Documentation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). See [LICENSE](LICENSE).

Copyright © 2001–2026 [iEDI.com ApS](https://iedi.com).
