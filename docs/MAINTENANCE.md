# ⚙️ Maintenance Guide

How the profile README stays up-to-date automatically and what not to break.

## Overview

The **Recent GitHub Activity** section in `README.md` is the only auto-managed part of the profile:

```markdown
## 📈 Recent GitHub Activity

_Refreshed automatically from public activity a few times a day by GitHub Actions — learn more in [docs/MAINTENANCE.md](docs/MAINTENANCE.md)._

<!--START_SECTION:activity-->
<!--END_SECTION:activity-->
```

A GitHub Actions workflow (`.github/workflows/update-activity.yml`) fills the block between the two marker comments with a list of recent public events (commits, PRs, issues, stars, etc.).

> **Golden rule:** never delete or rename `<!--START_SECTION:activity-->` / `<!--END_SECTION:activity-->`. If the markers disappear, the workflow has nowhere to write and will fail.

## Workflow File

**Path:** `.github/workflows/update-activity.yml`

```yaml
name: Update GitHub Activity
on:
  schedule:
    - cron: "0 */6 * * *"   # every 6 hours
  workflow_dispatch:         # + manual "Run workflow" button
permissions:
  contents: write
jobs:
  update-readme:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: jamesgeorge007/github-activity-readme@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
        with:
          COMMIT_MSG: "chore: update recent activity"
          MAX_LINES: 10
```

- **Scheduler:** `cron: "0 */6 * * *"` → runs at 00:00, 06:00, 12:00, 18:00 UTC. Adjust as needed.
- **Manual trigger:** `workflow_dispatch` lets you run it on demand from the Actions tab.
- **Action used:** [`jamesgeorge007/github-activity-readme`](https://github.com/jamesgeorge007/github-activity-readme) — reads public GitHub events via the API and rewrites the marked section.
- **Token:** uses the built-in `GITHUB_TOKEN` — no extra secrets required. Ensure workflow permissions are `contents: write` (Repo → Settings → Actions → General → Workflow permissions → *Read and write permissions*).

### Customizing

| Want to… | Edit… |
|----------|-------|
| Change frequency | `cron:` line (use https://crontab.guru) |
| Show more/fewer lines | `MAX_LINES:` |
| Change commit message | `COMMIT_MSG:` |
| Track a different user | add `USERNAME: ketandutt` under `with:` (defaults to repo owner) |

## What to Avoid

- ❌ Deleting or editing the marker comments (including extra spaces: `<!-- START_SECTION:activity -->` ≠ `<!--START_SECTION:activity-->`).
- ❌ Adding content *between* the markers manually — it will be overwritten on the next run.
- ❌ Renaming the workflow file without updating the comment in `README.md` (the comment points to `.github/workflows/update-activity.yml`).

## Safe Edits

You **can** safely:

- Edit the heading `## 📈 Recent GitHub Activity` or the italic description above the markers.
- Move the whole block (heading + markers) elsewhere in `README.md` — the workflow finds markers by text, not line number.
- Temporarily disable the workflow by adding `if: false` under the job or by disabling Actions in repo settings.

## Troubleshooting

| Symptom | Fix |
|---------|-----|
| Activity not updating | Check Actions tab for failed runs → ensure `GITHUB_TOKEN` has write permission and markers exist. |
| Workflow commits but README shows no change | Public activity may be sparse — `MAX_LINES: 10` shows up to 10 recent events; if none in last 90 days, section stays empty. |
| `Resource not accessible by integration` | Repo → Settings → Actions → General → *Allow GitHub Actions to create and approve pull requests* is not needed; ensure *Read and write permissions* is enabled. |
| Images in stats/trophies broken | Third-party service downtime — check `https://github-profile-summary-cards.vercel.app` or `streak-stats.demolab.com` directly. Not related to the activity workflow. |
| PR from workflow triggers infinite loop | Workflow commits with `GITHUB_TOKEN` do **not** trigger new workflow runs by design — safe. |

### Manual Refresh

1. Go to **Actions** → **Update GitHub Activity** → **Run workflow** → Run.
2. Wait ~30s, refresh `README.md` — activity should appear between the markers.
3. If it still fails, check the workflow logs for API rate-limit errors.

### Local Test

```bash
# Dry run without pushing (requires GitHub CLI)
gh workflow run update-activity.yml
gh run watch
```

## Docs & Links

- Workflow source: `.github/workflows/update-activity.yml`
- Action docs: https://github.com/jamesgeorge007/github-activity-readme
- Related doc: [CUSTOMIZATION.md](CUSTOMIZATION.md) — how to edit other sections safely.
- Profile README: [`README.md`](../README.md)

---

_Keep the markers intact and the profile stays fresh automatically._
