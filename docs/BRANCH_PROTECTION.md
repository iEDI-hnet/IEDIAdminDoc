# Protect the `master` branch

Use these settings so only reviewed changes reach **master**, and GitHub Pages only updates when the [build workflow](../.github/workflows/build-docs.yml) runs after a **version bump**.

## Prerequisites

- Repository created on GitHub (public)
- At least one commit pushed to **`master`** (the branch must exist before the rule applies)
- You have **Admin** role on the repo (or org owner for org-wide rules)

## Steps (repository settings)

1. Open the repo → **Settings** → **Branches** (under *Code and automation*).
2. Under **Branch protection rules**, click **Add rule** (or **Add branch ruleset** if your org uses rulesets).
3. **Branch name pattern:** `master`  
   (If your default branch is `main`, use `main` and update `branches:` in `.github/workflows/build-docs.yml` to match.)
4. Configure each control as below. (Wording matches **classic branch protection rules**; org **rulesets** use the same ideas with different labels.)

### Pull requests and reviews

| Control | Set to | Notes |
|---------|--------|--------|
| **Require a pull request before merging** | **Checked** | Blocks direct pushes to `master` (except bypass roles, if any). |
| ↳ **Required approvals** | **1** | Use **2** only if your team policy requires two reviewers. |
| ↳ **Require approval from Code Owners** | **Unchecked** | Only enable after you add a [`CODEOWNERS`](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) file. |
| ↳ **Dismiss stale pull request approvals when new commits are pushed** | **Checked** | A new push on the PR clears old approvals so reviewers re-check the latest diff. |
| ↳ **Require approval of the most recent reviewable push** | **Checked** (recommended) | Someone must approve the latest commit, not an older one. |
| ↳ **Require conversation resolution before merging** | **Checked** (recommended) | All review threads on the PR must be marked resolved. |
| ↳ **Allowed merge methods** | Your choice | **Squash merge** keeps `master` history linear; **Merge commit** preserves PR branch commits. Either is fine for docs. |

### Status checks (read before enabling)

The workflow [build-docs.yml](../.github/workflows/build-docs.yml) runs on **`push` to `master` only** — not on `pull_request`. That means:

- Checks appear in the Actions tab **after** something is pushed to `master` (first push, or after a PR is merged).
- They do **not** run on open PRs today, so you **cannot** reliably require `version-check` / `build` / `deploy` **before** merge unless you extend the workflow later.

| Control | Set to | Notes |
|---------|--------|--------|
| **Require status checks to pass before merging** | **Unchecked** (recommended for now) | Turn **on** only if you add a `pull_request` trigger and checks that run on every PR. |
| ↳ **Require branches to be up to date before merging** | Leave off with checks off | Only relevant when status checks are required. |

If you enable status checks later (after workflow runs on PRs):

1. Push to `master` at least once so **Actions** has run **Build documentation**.
2. Edit the rule → **Require status checks** → search the list (names match job ids):
   - **`version-check`** — always runs on qualifying pushes to `master`.
   - **`build`** / **`deploy`** — run only when `version` in `writerside.cfg` changed; **do not** require these on every PR or topic-only merges will never pass the check.

### Bypass, push access, and destructive actions

| Control | Set to | Notes |
|---------|--------|--------|
| **Do not allow bypassing the above settings** | **Checked** | Applies to admins too; use org owners only for emergencies. |
| ↳ **Restrict who can push to matching branches** | **Optional** | If checked, add a team (e.g. docs maintainers). Everyone else must use PRs. Leave **unchecked** if all writers open PRs and you only use “Require a pull request”. |
| **Allow force pushes** | **Unchecked** (nobody) | Prevents rewriting `master` history. |
| **Allow deletions** | **Unchecked** | Prevents deleting `master`. |

### Recommended minimum (this repo, today)

1. **Require a pull request** + **1 approval** + **dismiss stale approvals** + **approve latest push**.
2. **Do not** require status checks until the workflow runs on PRs.
3. **No force push**, **no branch deletion**, **no bypass** for admins.
4. **Save** the rule.

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
