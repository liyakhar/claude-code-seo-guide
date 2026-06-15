# Claude Code SEO Skill

[![GitHub stars](https://img.shields.io/github/stars/liyakhar/claude-code-seo-guide?style=social)](https://github.com/liyakhar/claude-code-seo-guide/stargazers)
[![Live guide](https://img.shields.io/badge/guide-live-brightgreen)](https://liyakhar.github.io/claude-code-seo-guide/)

Agent skill for [Jono Catliff's Claude Code SEO blueprint](https://www.youtube.com/watch?v=4IyJm1i__ag) — programmatic SEO with blog posts at scale, city×service landing pages, on-page checklist, technical SEO, and deploy.

**If this helps you rank, star the repo** — it helps others find it on [skills.sh](https://skills.sh) and GitHub.

## Install

One command (Cursor, Claude Code, Codex, and other agents):

```bash
npx skills add liyakhar/claude-code-seo-guide -y
```

Install a specific skill:

```bash
# Full workflow
npx skills add liyakhar/claude-code-seo-guide --skill claude-code-seo -y

# Blog post generator only
npx skills add liyakhar/claude-code-seo-guide --skill claude-code-seo-blog -y

# Service landing page generator only
npx skills add liyakhar/claude-code-seo-guide --skill claude-code-seo-service -y
```

Global install (all your projects):

```bash
npx skills add liyakhar/claude-code-seo-guide -g -y
```

## Use

1. Clone this repo as your project (or copy blueprint files into an existing Next.js app):

   ```bash
   git clone https://github.com/liyakhar/claude-code-seo-guide.git my-seo-site
   cd my-seo-site
   ```

2. In Cursor or Claude Code, invoke the skill:

   - Type `/claude-code-seo` or ask: *"Run the Claude Code SEO workflow"*
   - For a single blog post: `/claude-code-seo-blog` or *"Create a new SEO blog post"*
   - For a service page: `/claude-code-seo-service` or *"Create a service landing page"*

3. Follow the agent through setup → keywords → content → on-page → technical → deploy.

## What's included

| Skill | What it does |
|-------|----------------|
| `claude-code-seo` | Full workflow: setup, SEMrush, blog, service pages, on-page, technical SEO, deploy |
| `claude-code-seo-blog` | End-to-end blog post from `keywords.csv` with voice + SERP analysis |
| `claude-code-seo-service` | City+service landing page from `Service-keywords.csv` |

## Blueprint files (in this repo)

- `CLAUDE.md` — project rules (SSG, voice, design)
- `on-page-seo.md` — 80+ item checklist
- `prompts.md` — copy-paste prompts v1–v8
- `keywords.csv` / `Service-keywords.csv` — keyword research
- `references/` — voice, humour, stats, stories, opinions
- `slideshow/` — visual SEO guides
- Demo Next.js app (v1–v6 progression pages)

## Live guide

Condensed action guide with timestamp links and blueprint file references:

**https://liyakhar.github.io/claude-code-seo-guide/**

## Credits

- Workflow and blueprint: [Jono Catliff / Automatable](https://github.com/jonocatliff/SEO_brief)
- Skill packaging and guide: [liyakhar/claude-code-seo-guide](https://github.com/liyakhar/claude-code-seo-guide)

## Local dev (demo app)

```bash
npm install
npm run dev
```

Static export:

```bash
npm run build
```

## License

Blueprint content © Jono Catliff. Skill packaging and guide site © contributors. Use and adapt for your own SEO projects.
