# Claude Code SEO — Condensed Workflow

Source: Jono Catliff masterclass. Full guide: https://liyakhar.github.io/claude-code-seo-guide/

## Strategy

- **Blog posts** → informational keywords at scale
- **Service pages** → commercial keywords (service × city)
- Position 1 ≈ 40% of clicks; rank higher = more leads
- AI search (ChatGPT, Perplexity) pulls from Google — rank on Google first

## Setup

1. VS Code + Claude Code extension
2. Project folder with `CLAUDE.md` at root
3. Clone blueprint: `git clone https://github.com/liyakhar/claude-code-seo-guide.git`

## Build sequence

| Version | Stage | Key output |
|---------|-------|------------|
| v1 | Scaffold | Homepage, blog index, service index |
| v2 | AI blog slop | First draft from keywords.csv |
| v3 | Voice + SERP | Rewrite with references/ + top-3 analysis |
| v4 | Service page | City+service landing from Service-keywords.csv |
| v5 | On-page SEO | on-page-seo.md checklist applied |
| v6 | Technical SEO | sitemap, robots, Lighthouse 100 |

## SEMrush filters (blog)

- Keyword Magic Tool → seed niche term
- KD: 0–30, Volume: 100+
- Intent: Informational
- Prefer keywords with People Also Ask SERP feature
- Rank by Volume / (KD + 1)

## SERP analysis (before writing)

1. WebSearch primary keyword
2. Fetch top 3 organic blog posts (skip forums, Reddit, YouTube)
3. Note format, word count, all H2 topics, FAQ questions
4. Match format and length ±20%
5. Add 1–2 topics competitors missed

## Voice rules (summary)

- Read references/voice.md before writing
- Real numbers only from stats.md
- One story (stories.md), one opinion (opinions.md) per post
- Tell readers when NOT to hire you
- Banned: unlock, leverage, seamless, exclamation marks, emoji

## Deploy

1. GitHub push
2. Vercel import
3. Search Console verification + sitemap submit
4. Google Business Profile for local

## Cadence

- 1 blog/week minimum
- Service pages in city batches (zipper method)
- Never reuse primary keywords
