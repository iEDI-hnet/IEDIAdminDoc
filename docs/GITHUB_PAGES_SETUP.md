# GitHub Pages setup — IEDIAdminDoc

Public documentation repository. GitHub Pages on **public** repos does not require GitHub Enterprise.

## One-time setup

1. Create repository **`IEDIAdminDoc`** (Public) under your org.
2. Push this repository; default branch **`master`** recommended.
3. **Settings → Pages → Build and deployment → Source:** **GitHub Actions** (not “Deploy from a branch”). See [GitHub Actions vs branch deploy](#github-actions-vs-deploy-from-a-branch) below.
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

## GitHub Actions vs deploy from a branch

| Source | Fits Writerside? | Why |
|--------|------------------|-----|
| **GitHub Actions** | **Yes — use this** | CI runs the Writerside Docker builder, then `deploy-pages` publishes the HTML zip. Matches `.github/workflows/build-docs.yml`. |
| **Deploy from a branch** (`main` / `master` + folder) | **No** | GitHub serves static files (or Jekyll) from git. It does **not** run Writerside. You would have to commit built `webHelp*` HTML into the repo and keep it in sync by hand. |

**FastSeriesDoc** also uses the **Build documentation** workflow (`JetBrains/writerside-github-action` + `deploy-pages`). If the Pages UI still says “built from the `main` branch”, that is an old or secondary setting. The line that matters is: *“Your site was last deployed to the `github-pages` environment by the Build documentation workflow.”* — that is the correct path.

**What to do**

1. **Settings → Pages → Build and deployment → Source** → select **GitHub Actions**.
2. Do **not** rely on “Deploy from a branch” for live updates.
3. Do **not** commit `webHelp*/` or `Writerside/out/` (`.gitignore` already excludes them).
4. Align branch names: this workflow triggers on **`master`**. If the repo default branch is **`main`**, either rename the default branch to `master` or change `branches: [master]` in `build-docs.yml` to `[main]`.

The “Learn how to add a Jekyll theme” hint on the Pages settings page applies only to branch/Jekyll publishing — ignore it for Writerside.
