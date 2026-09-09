# 🛠️ Customization Guide

How to edit the profile README without breaking layout or automation.

> **File to edit:** [`README.md`](../README.md) at the repository root.  
> **Live preview:** commit to `main` (or your default branch) and visit `https://github.com/K10Dutt`.

## 1. Header & Badges

At the top of `README.md`:

```html
<h1 align="center">Hi 👋, I'm Ketan Dutt</h1>
<h3 align="center">🎮 Game Developer · 💻 Tech Enthusiast · ...</h3>
```

- Change the name/tagline directly in those `<h1>` / `<h3>` lines.
- Portfolio / LinkedIn / Email links are in the next `<p align="center">` block.
- Profile views & follower badges:

  ```html
  <img src="https://komarev.com/ghpvc/?username=ketandutt&style=flat-square&label=Profile+Views" />
  <img src="https://img.shields.io/github/followers/ketandutt?style=social&label=Follow" />
  ```

  Replace `ketandutt` with your username if you fork this template.

## 2. About Me

Section starts at `## 👨‍💻 About Me`.

- Bullet list supports markdown links and bold.
- Keep 5–6 bullets max for readability.
- Example — add a new bullet:

  ```markdown
  - 🌱 **Currently learning:** Procedural generation in Godot 4
  ```

## 3. Demo Projects

```markdown
## 🚀 Demo Projects
...
| Project | Play it | Repo | Built with |
```

- Each row should have a playable WebGL / GitHub Pages link under **Play it**.
- Keep the table to ~7 rows visible; overflow goes into the `<details>` block below.
- **More experiments & tools** — expandable section:

  ```html
  <details>
  <summary><b>🧪 More experiments & tools</b></summary>
  | Project | Notes | Repo |
  ...
  </details>
  ```

  Add new rows there for smaller experiments.

### Adding a New Demo

1. Add a row to the main table.
2. Use the format: `[Name](https://ketandutt.github.io/REPO/) — short description | [▶️ Play](link) | [REPO](https://github.com/KetanDutt/REPO) | Tech`.
3. Ensure the `https://ketandutt.github.io/...` page is published (repo → Settings → Pages).

## 4. Toolbox (Skill Icons)

```markdown
[![My Skills](https://skillicons.dev/icons?i=unity,godot,unreal,cs,python,js,ts,nodejs,html,css,php,mysql,flutter,arduino,git&theme=dark)](https://skillicons.dev)
```

- Edit the `i=` comma-separated list. Full icon list: https://skillicons.dev
- `theme=dark` matches the profile's dark stats cards. Use `theme=light` for light mode.
- Keep to ~15 icons max or the row wraps poorly on mobile.

## 5. Recent GitHub Activity

```markdown
## 📈 Recent GitHub Activity
_Refreshed automatically ..._
<!--START_SECTION:activity-->
<!--END_SECTION:activity-->
```

- **Do not edit between the markers** — it's overwritten by the workflow.
- You *can* edit the heading or the italic description above it.
- To trigger a manual refresh: Actions → *Update GitHub Activity* → Run workflow.

See [MAINTENANCE.md](MAINTENANCE.md) for full details.

## 6. GitHub Stats

```html
<p align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=ketandutt&theme=gruvbox" />
</p>
<p align="center">
  <img src="https://github-readme-stats-fast.vercel.app/api?username=ketandutt&show_icons=true&theme=gruvbox" />
  <img src="https://streak-stats.demolab.com/?user=ketandutt&theme=gruvbox" />
  ...
</p>
```

- All cards use `username=ketandutt` and `theme=gruvbox`. Change theme to `dark`, `tokyonight`, etc. if you prefer.
- Services used:
  - `github-profile-summary-cards.vercel.app`
  - `github-readme-stats-fast.vercel.app` (fork of `anuraghazra/github-readme-stats`)
  - `streak-stats.demolab.com`
  - `github-profile-trophy.screw-hand.vercel.app`

If a card shows errors (rate-limited), wait a few hours or change the service domain.

## 7. GitHub Trophies

```markdown
## 🏆 GitHub Trophies
<img src="https://github-profile-trophy.screw-hand.vercel.app/?username=ketandutt&theme=gruvbox&row=1&no-bg=true&no-frame=true" />
```

- `row=1` keeps trophies on one row — increase to `2` if they overflow.
- `no-bg=true&no-frame=true` makes it blend on dark GitHub themes.

## 8. Get in Touch

```markdown
[![LinkedIn](https://img.shields.io/badge/...)](https://www.linkedin.com/in/...)
[![Gmail](https://img.shields.io/badge/...)](mailto:...)
[![Website](https://img.shields.io/badge/...)](https://ketandutt.github.io/)
```

Replace URLs/emails as needed. Badges use [shields.io](https://shields.io).

## 9. Footer

```markdown
_Profile docs: [📖 Docs home](docs/README.md) · [🛠️ Customization](docs/CUSTOMIZATION.md) · ..._
```

Keep these links — they help collaborators discover how to edit safely.

---

## Style Tips

- Use emojis sparingly in headings (`👨‍💻`, `🚀`, `🛠️`) — they render well on GitHub but avoid in plain-text contexts.
- Keep centered HTML (`align="center"`) only for header/stats — everything else should be standard markdown for accessibility.
- Test links after every edit — broken demo links are the most common profile issue.

## Rebranding for a Different User

If you fork this template:

1. Replace all `ketandutt` → your username (README.md, docs, workflow).
2. Replace `KetanDutt` / `Ketan Dutt` display names.
3. Update `komarev.com/ghpvc/?username=...`, stats card URLs, and trophy URLs.
4. Update `.github/workflows/update-activity.yml` env var `GITHUB_USERNAME`.

Back: [Docs home](README.md) · [Maintenance](MAINTENANCE.md)
