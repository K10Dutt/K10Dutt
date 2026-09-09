# Profile Docs

Welcome to the documentation for the **KetanDutt** profile README (`K10Dutt/K10Dutt`).

This is a *special* GitHub repository — its `README.md` is displayed on the owner's GitHub profile. The files in `docs/` explain how to customize and maintain it without breaking automation.

## Quick Links

| Doc | What it covers |
|-----|----------------|
| [🛠️ Customization](CUSTOMIZATION.md) | How to edit each section of the README — header, About Me, Demo Projects, Toolbox, Stats, Trophies, and Contact. |
| [⚙️ Maintenance](MAINTENANCE.md) | How the activity auto-update works, what not to edit, and how to troubleshoot the workflow. |
| [🛡️ Security](../SECURITY.md) | Security policy for this profile repository. |

## Repository Layout

```
.
├── README.md                               # Profile README (rendered on github.com/K10Dutt)
├── docs/
│   ├── README.md        ← you are here
│   ├── CUSTOMIZATION.md    # editing guide
│   └── MAINTENANCE.md      # automation guide
├── .github/
│   └── workflows/
│       └── update-activity.yml  # refreshes <!--START_SECTION:activity--> block
└── SECURITY.md
```

## Getting Started

1. **Preview before you push** — GitHub renders the profile README live. Use the "Preview" tab when editing `README.md` on GitHub, or run a local markdown preview.
2. **Keep the activity markers intact** — The block:

   ```html
   <!--START_SECTION:activity-->
   <!--END_SECTION:activity-->
   ```

   is managed by GitHub Actions. Do not remove or rename those comments. See [MAINTENANCE.md](MAINTENANCE.md) for details.

3. **Images are external** — Profile views, follower badges, skillicons, stats cards, and trophies are all loaded from third-party image services. If an image fails to load, check the service URL and your username.

## Editing Tips

- Keep the header's HTML `<h1 align="center">` tags — GitHub's markdown renderer respects them and they center the title.
- Demo Projects table: every row should stay playable — verify the `https://ketandutt.github.io/...` links before committing.
- Toolbox icons come from [skillicons.dev](https://skillicons.dev). Edit the `i=` query param to add/remove icons (e.g. `i=unity,godot,python`).

## Need Help?

- For content changes: see [CUSTOMIZATION.md](CUSTOMIZATION.md)
- For workflow / activity issues: see [MAINTENANCE.md](MAINTENANCE.md)

---

_Back to profile: [README.md](../README.md)_
