# Protect the `master` branch

Use these settings so only reviewed changes reach **master**, and GitHub Pages only updates when the [build workflow](../.github/workflows/build-docs.yml) runs after a **version bump**.

## Prerequisites

- Repository created on GitHub (public)
- You have **Admin** role on the repo (or org owner for org-wide rules)

## Steps (repository settings)

1. Open the repo → **Settings** → **Branches** (under *Code and automation*).
2. Under **Branch protection rules**, click **Add rule** (or **Add branch ruleset** if your org uses rulesets).
3. **Branch name pattern:** `master`  
   (If your default branch is `main`, use `main` and update `branches:` in `.github/workflows/build-docs.yml` to match.)
4. Enable:

| Setting | Recommendation |
|---------|----------------|
| **Require a pull request before merging** | On |
| **Require approvals** | 1 (or 2 for stricter teams) |
| **Dismiss stale pull request approvals when new commits are pushed** | On |
| **Require status checks to pass before merging** | On (after first workflow run exists) |
| **Require branches to be up to date before merging** | On (optional) |
| **Require conversation resolution before merging** | On (optional) |
| **Do not allow bypassing the above settings** | On for admins in production repos |
| **Restrict who can push to matching branches** | Optional — limit to docs maintainers |
| **Allow force pushes** | **Off** |
| **Allow deletions** | **Off** |

5. Save the rule.

## Status checks (after first publish)

Once **Build documentation** has run at least once:

1. Edit the branch rule.
2. Under **Require status checks**, search and select:
   - `version-check` (always runs on push to `master` when paths match)
   - `build` / `deploy` (only when version changed — optional; may block PRs that only edit topics without version bump)

**Note:** Topic-only commits on `master` without a version bump will pass `version-check` but skip `build`. That is intentional. For PRs, you do not need `build` as a required check unless every merge must build.

Practical approach:

- Require **pull request + approval** for merges to `master`.
- Do **not** require `build` on PRs (version often bumped only on release commit).
- Rely on version gate on `master` push for publish.

## Release workflow for editors

1. Edit topics on a feature branch.
2. Open PR → review → merge to `master`.
3. When ready to **publish** the site, bump `version` in `Writerside/writerside.cfg` (e.g. `1.0.0` → `1.0.1`) in a commit on `master` (can be same PR as content or a follow-up commit).
4. Push to `master` → workflow builds and deploys only if `version` changed.

## Org-level rules (optional)

For all doc repos (`IEDIAdminDoc`, `IEDIAppApiDoc`, `FastSeriesDoc`):

**Organization → Settings → Repository → Rulesets** — duplicate the same policy for each repo or use a ruleset target `iEDI-hnet/*Doc`.

## Pages and Actions permissions

Keep:

- **Settings → Pages → Source:** GitHub Actions
- **Settings → Actions → General → Workflow permissions:** Read and write

See [GITHUB_PAGES_SETUP.md](./GITHUB_PAGES_SETUP.md).
