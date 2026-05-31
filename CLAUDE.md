# CLAUDE.md

This file provides guidance for AI assistants working in this repository.

## Repository Overview

This is **lbruster/lbruster** — a GitHub special profile repository. The single file `README.md` is automatically rendered as the profile page at [github.com/lbruster](https://github.com/lbruster). There is no source code, build system, tests, or CI/CD pipeline.

**Owner**: Leroy Bruster — Full Stack Developer, portfolio at deadlinestudio.net  
**Contact**: info@deadlinestudio.net

---

## Repository Structure

```
lbruster/
└── README.md     # GitHub profile page (the only tracked file)
```

---

## README.md Conventions

The README mixes Markdown and raw HTML. Follow these patterns precisely when making changes.

### Section Order

1. Animated header (typing SVG)
2. Role subtitle and bullet-point bio
3. `### Skills` — SVG icon grid
4. `### 🛠 &nbsp;Tech Stack` — flat badge grid
5. `### ⚙️ &nbsp;GitHub Analytics` — stats widgets
6. `### Socials` — social link icons

### Animated Header

Uses `readme-typing-svg.herokuapp.com`. Parameters: `font=Time+New+Roman`, `color=cyan`, `size=25`, `center=true`, `vCenter=true`, `width=600`, `height=100`. Lines are `+`-separated in the `lines=` query param.

```html
<p align="center">
  <a href="https://github.com/DenverCoder1/readme-typing-svg">
    <img src="https://readme-typing-svg.herokuapp.com?font=Time+New+Roman&color=cyan&size=25&center=true&vCenter=true&width=600&height=100&lines=Line+One;Line+Two">
  </a>
</p>
```

### Skills Section

Skill icons come from `danielcranney/readme-generator`. All icons are **36×36** SVGs, inside a `<p align="left">` block with no whitespace between `<a>` tags. Each link must include `target="_blank" rel="noreferrer"`.

```html
<p align="left">
  <a href="https://..." target="_blank" rel="noreferrer">
    <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/<name>-colored.svg" width="36" height="36" alt="<Name>" />
  </a>
</p>
```

Icon slug pattern: `<technology-name>-colored.svg`. Special cases observed:
- Visual Studio Code → `visualstudiocode.svg` (no `-colored` suffix)
- .NET → `dot-net-colored.svg`

### Tech Stack Badges

Uses shields.io with a consistent dark style. Background is always `05122A`. Badges are placed inline with `&nbsp;` separators; use `\` (backslash) for a visual line break (renders as `<br>` on GitHub).

```markdown
![Label](https://img.shields.io/badge/-Label-05122A?style=flat&logo=<logo-name>)&nbsp;
```

For colored logos, append `&logoColor=<hex>`:
```markdown
![Java](https://img.shields.io/badge/-Java-05122A?style=flat&logo=Java&logoColor=FFA518)&nbsp;
```

### GitHub Analytics

Embeds from `github-readme-stats-eight-theta.vercel.app`. Always centered, both images side by side at `height="180em"`.

```html
<p align="center">
<a href="https://github.com/AVS1508">
  <img height="180em" src="https://github-readme-stats-eight-theta.vercel.app/api?username=lbruster&show_icons=true&theme=algolia&include_all_commits=true&count_private=true"/>
  <img height="180em" src="https://github-readme-stats-eight-theta.vercel.app/api/top-langs/?username=lbruster&layout=compact&langs_count=8&theme=algolia"/>
</a>
</p>
```

### Socials Section

Social icons are 32×32 and use `<picture>` for dark/light mode support. All icons come from `danielcranney/readme-generator/main/public/icons/socials/`. Each platform has a `-dark.svg` and a plain `.svg` variant.

```html
<p align="left">
  <a href="https://www.<platform>.com/lbruster" target="_blank" rel="noreferrer">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/<name>-dark.svg" />
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/<name>.svg" />
      <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/<name>.svg" width="32" height="32" />
    </picture>
  </a>
</p>
```

Current social links: GitHub (`/lbruster`), LinkedIn (`/in/lbruster`), X/Twitter (`/LeroyBruster`).

---

## Development Workflow

### Branching

- Default branch: `main`
- Feature/AI branches follow the pattern: `claude/<description>-<id>`
- Always develop on the designated feature branch and push before the session ends.

### Making Changes

All changes are edits to `README.md`. There is no build step, no linting, and no test suite. After editing:

```bash
git add README.md
git commit -m "Description of change"
git push -u origin <branch-name>
```

### What to Avoid

- Do not add build tooling, package managers, or CI/CD unless explicitly requested.
- Do not create additional files beyond `README.md` and `CLAUDE.md` unless requested.
- Do not change badge colors or icon sizes — consistency across the profile matters visually.
- Do not alter the `username=lbruster` parameter in analytics URLs.

---

## Key External Services Used

| Service | Purpose |
|---|---|
| `readme-typing-svg.herokuapp.com` | Animated header typewriter effect |
| `raw.githubusercontent.com/danielcranney/readme-generator` | Skill and social icon SVGs |
| `img.shields.io` | Tech stack flat badges |
| `github-readme-stats-eight-theta.vercel.app` | GitHub stats and top-languages widgets |
