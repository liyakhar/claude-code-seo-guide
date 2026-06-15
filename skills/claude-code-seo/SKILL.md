---
name: claude-code-seo
description: >-
  Runs the full Claude Code SEO workflow from Jono Catliff's 50k-clicks blueprint:
  SSG site setup, SEMrush keyword research, voice-matched blog posts, service
  landing pages, on-page checklist, technical SEO, and deploy. Use when the user
  wants Claude Code SEO, programmatic SEO, rank on Google, build SEO blog posts at
  scale, service pages by city, on-page SEO checklist, technical SEO, Lighthouse
  100, or deploy an SEO site to Vercel.
---

# Claude Code SEO

End-to-end programmatic SEO with Claude Code. Based on [Jono Catliff's blueprint](https://github.com/jonocatliff/SEO_brief) — blog posts at scale (informational keywords) plus service pages (service × city money keywords).

**Live guide:** https://liyakhar.github.io/claude-code-seo-guide/

## Before you start

Verify the blueprint files exist in the project root:

```
CLAUDE.md
on-page-seo.md
prompts.md
keywords.csv
Service-keywords.csv
references/voice.md
references/humour.md
references/stats.md
references/stories.md
references/opinions.md
references/used-keywords.md
```

If missing, bootstrap:

```bash
git clone https://github.com/liyakhar/claude-code-seo-guide.git .
# or clone upstream: git clone https://github.com/jonocatliff/SEO_brief.git .
```

Read `CLAUDE.md` first. Every content task must use **SSG only** (`output: 'export'` in Next.js). Google must receive fully rendered HTML at crawl time.

## Four pillars

1. **Keywords** — SEMrush data, not AI guesses. Blog = informational; service = commercial.
2. **On-page SEO** — `on-page-seo.md` (80+ items).
3. **Technical SEO** — sitemap, robots.txt, Lighthouse, Core Web Vitals.
4. **Off-page SEO** — backlinks, citations, Google Business Profile.

## Workflow checklist

Copy and track progress:

```
- [ ] 1. Setup VS Code + Claude Code + CLAUDE.md
- [ ] 2. Scaffold site (v1 prompt)
- [ ] 3. Confirm SSG / static export
- [ ] 4. SEMrush keyword research → keywords.csv + Service-keywords.csv
- [ ] 5. Blog post v2 → v3 (voice) → v5 (on-page) → v6 (technical)
- [ ] 6. Service landing pages (v4 + on-page)
- [ ] 7. npm run build — all routes static
- [ ] 8. Deploy GitHub + Vercel
- [ ] 9. Google Search Console + sitemap submit
```

## Phase 1 — Setup

1. Install VS Code and the Claude Code extension.
2. Open the blueprint project folder.
3. Ensure `CLAUDE.md` is at the root — SSG rules, voice rules, design rules.

## Phase 2 — Build site (v1)

1. Attach a Dribbble screenshot as design reference.
2. Run **prompts.md v1**: homepage + blog index + service index.
3. Preview at localhost. Confirm blog index and service index exist.

## Phase 3 — Static site generation

**Required.** No client-side rendering for SEO pages.

- Next.js: `output: 'export'` in `next.config.mjs`
- Every route must pre-render to HTML at build time
- No `cookies()`, `headers()`, `searchParams`, or `dynamic = 'force-dynamic'`

See `slideshow/rendering-pizza.html` for the visual explainer.

## Phase 4 — Keyword research (SEMrush)

**Blog keywords** → `keywords.csv`:

1. SEMrush → SEO → Keyword Magic Tool
2. Seed: your niche (e.g. "plumber")
3. Filters: KD 0–30, Volume 100+, Intent = Informational
4. Export; dedupe primaries; track used keywords in `references/used-keywords.md`

**Service keywords** → `Service-keywords.csv`:

1. Pattern: `[service] [city] [state/country]`
2. Intent = Commercial
3. One primary per landing page; never reuse a primary

## Phase 5 — Blog workflow (prompts v2–v6)

Use skill `claude-code-seo-blog` for the full blog generator, or run prompts manually:

| Step | Prompt | What it does |
|------|--------|--------------|
| v2 | prompts.md v2 | Draft from keywords.csv (AI slop baseline) |
| v3 | prompts.md v3 | Rewrite with voice files + SERP top-3 analysis |
| v5 | prompts.md v5 | Apply `on-page-seo.md` checklist, keep voice |
| v6 | prompts.md v6 | Lighthouse 100 + robots.txt + sitemap.xml |

**v3 SERP rules:** Match top-3 format and length (±20%). Cover all their H2 topics. Add 1–2 topics they missed. FAQ from People Also Ask. Direct answer in first paragraph.

**Voice files** (read before any writing): `references/voice.md`, `humour.md`, `stats.md`, `stories.md`, `opinions.md`. Never invent stats or stories.

## Phase 6 — Service pages

Use skill `claude-code-seo-service` or **prompts.md v4**: one landing page per row in `Service-keywords.csv`. Same design as homepage, localized NAP + schema.

## Phase 7 — On-page SEO

Read `on-page-seo.md` before shipping any page. Key items:

- Title 50–60 chars, primary keyword near start
- Meta description 150–160 chars
- FAQ + FAQPage schema, Breadcrumbs, Person/Author schema
- 3–5 internal links, 2–3 authoritative external links
- TOC with anchor links on long posts

Visual checklist: `slideshow/onpage-seo-checklist.html`

## Phase 8 — Technical SEO

- `app/sitemap.ts` and `app/robots.ts` (or static `sitemap.xml` / `robots.txt`)
- Canonical URLs on every page
- OG images 1200×630
- Run Lighthouse — target 100 across Performance, Accessibility, Best Practices, SEO
- `npm run build` — confirm all routes show `○ (Static)`

## Phase 9 — Deploy

1. Push to GitHub (prompts.md v7)
2. Import to Vercel; connect repo
3. Add Google Search Console verification snippet (prompts.md v8); redeploy
4. Submit sitemap in Search Console

## Phase 10 — Publishing cadence

- **Blog:** 1 post/week minimum for momentum
- **Service pages:** batch by city cluster ("zipper" — same service, many cities)
- Track used primaries in `references/used-keywords.md` — never reuse

## Sub-skills

| Skill | Use when |
|-------|----------|
| `claude-code-seo-blog` | `/blog` or new blog post from keywords.csv |
| `claude-code-seo-service` | `/service` or new city+service landing page |

Install individually:

```bash
npx skills add liyakhar/claude-code-seo-guide --skill claude-code-seo-blog -y
npx skills add liyakhar/claude-code-seo-guide --skill claude-code-seo-service -y
```

## Additional resources

- Condensed action guide: [references/workflow.md](references/workflow.md)
- Copy-paste prompts: [references/prompts.md](references/prompts.md)
- Full transcript + links: https://liyakhar.github.io/claude-code-seo-guide/
- Official upstream: https://github.com/jonocatliff/SEO_brief

## Anti-patterns

- Do not guess keywords — use SEMrush CSV data
- Do not reuse a primary from `used-keywords.md`
- Do not ship without `npm run build` passing
- Do not use client-side rendering for SEO pages
- Do not invent stats, stories, or opinions — pull from reference files only
- Do not skip `on-page-seo.md` for v5+ content
