# GitHub Pages setup — IEDIAdminDoc

Public documentation repository. GitHub Pages on **public** repos does not require GitHub Enterprise.

## One-time setup

1. Create repository **`IEDIAdminDoc`** (Public) under your org.
2. Push this repository; default branch **`master`** recommended.
3. **Settings → Pages → Build and deployment → Source:** **GitHub Actions**.
4. **Settings → Actions → General → Workflow permissions:** Read and write.
5. **Settings → Branches:** protect `master` — see **[BRANCH_PROTECTION.md](./BRANCH_PROTECTION.md)**.
6. Merge to `master` with a **version bump** in `Writerside/writerside.cfg` to trigger the first publish.

Site URL: `https://<org>.github.io/IEDIAdminDoc/`  
`web-path="/IEDIAdminDoc/"` must match the repository name.

## When the site is built and published

| Condition | Result |
|-----------|--------|
| Push to **`master`** and `version` in `writerside.cfg` **changed** | Build + deploy to Pages |
| Push to **`master`** with only topic edits (same `version`) | Workflow may run; **no** build/deploy (version gate) |
| Push to other branches | No workflow |
| Pull request | No workflow (merge via PR to `master`) |

### Release a content update

1. Merge topic changes to `master` (via PR).
2. Bump `version` on `<instance>` in `Writerside/writerside.cfg`, for example `1.0.0` → `1.0.1`.
3. Commit and push to `master` — CI publishes the site.

## Security

Review **[PUBLIC_AUDIT.md](./PUBLIC_AUDIT.md)** before each release.

## Local build

```bash
docker run --rm -v "$(pwd)":/data jetbrains/writerside-builder:243.22562 \
  --instance Writerside/iedi-adm
```

See [WEBSTORM_WRITERSIDE_SETUP.md](./WEBSTORM_WRITERSIDE_SETUP.md).
