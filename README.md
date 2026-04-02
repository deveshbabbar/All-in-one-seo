# All-in-One SEO Skill

**Complete SEO + GEO + AEO audit & optimization skill for AI coding agents.**

Works with Claude Code, Cursor, Windsurf, Cline, Antigravity, Amp, and any agent that supports markdown skills.

---

## What's Inside

A single, comprehensive skill that covers:

- **SEO Audit** — Meta tags, Schema.org, sitemap, robots.txt, technical SEO, content SEO
- **GEO (Generative Engine Optimization)** — Get cited by Google AI Overviews, Perplexity, ChatGPT
- **AEO (AI Engine Optimization)** — Structured data, AI crawler access, content patterns
- **Google-Compliant Ad Placement** — Better Ads Standards, safe formats, Adsterra-specific rules
- **Next.js Patterns** — Metadata for client components, sitemap templates, next.config optimization

Based on **2025-2026 Google guidelines** and the **Coalition for Better Ads Standards**.

---

## Installation

### Claude Code (CLI)

```bash
npx skills add https://github.com/deveshbabbar/All-in-one-seo --skill seo-audit
```

### Claude Code (Manual)

```bash
git clone https://github.com/deveshbabbar/All-in-one-seo.git /tmp/seo-skill
cp /tmp/seo-skill/skills/seo-audit.md .claude/skills/seo-audit.md
```

### Cursor

```bash
mkdir -p .cursor/skills
curl -o .cursor/skills/seo-audit.md https://raw.githubusercontent.com/deveshbabbar/All-in-one-seo/main/skills/seo-audit.md
```

### Windsurf

```bash
mkdir -p .windsurf/skills
curl -o .windsurf/skills/seo-audit.md https://raw.githubusercontent.com/deveshbabbar/All-in-one-seo/main/skills/seo-audit.md
```

### Cline

```bash
mkdir -p .cline/skills
curl -o .cline/skills/seo-audit.md https://raw.githubusercontent.com/deveshbabbar/All-in-one-seo/main/skills/seo-audit.md
```

### Antigravity / Amp

```bash
npx skills add https://github.com/deveshbabbar/All-in-one-seo --skill seo-audit
```

### Any Agent (Universal)

```bash
curl -O https://raw.githubusercontent.com/deveshbabbar/All-in-one-seo/main/skills/seo-audit.md
```

---

## Usage

Once installed, just tell your AI agent:

```
/seo-audit
```

Or ask naturally:

- *"Run an SEO audit on my website"*
- *"Optimize my site for Google and AI search engines"*
- *"Add structured data and fix SEO issues"*
- *"Make my website rank higher on Google"*
- *"Set up GEO optimization for AI search"*

The skill guides the agent through a complete **5-phase optimization**:

1. **SEO Audit** — Find all issues
2. **GEO Optimization** — AI search engine visibility
3. **AEO Optimization** — Structured data & AI crawlers
4. **Ad Compliance** — Google-safe ad placement
5. **Framework Patterns** — Next.js specific fixes

---

## What It Covers

### SEO Checklist
| Check | Details |
|-------|---------|
| Meta Tags | title, description, OG, Twitter, canonical |
| Schema.org | Organization, Article, FAQ, HowTo, BreadcrumbList, ItemList |
| Sitemap | All static + dynamic pages with priority |
| robots.txt | Crawlers + AI bots access |
| Technical | 404 page, error boundary, image optimization, security headers |
| Content | H1 hierarchy, alt tags, internal linking, citations |

### GEO (AI Search Optimization)
| Pattern | Purpose |
|---------|---------|
| Structured Answer Blocks | AI engines extract these for citations |
| E-E-A-T Signals | Google trusts expert-attributed content |
| Inverted Pyramid | Answer first, details after |
| FAQ + HowTo Schema | Highest AI citation rate |

### Ad Compliance (Better Ads Standards)
| Rule | Standard |
|------|----------|
| No popups/popunders | Better Ads Standards |
| Mobile ad density < 30% | Coalition for Better Ads |
| Desktop ad density < 50% | Coalition for Better Ads |
| No auto-play video with sound | Chrome blocks these |
| Max 3-4 ads per page | Google recommendation |

---

## Frameworks Supported

- Next.js 13/14/15 (App Router)
- React / Vue / Svelte
- Any web framework (HTML/CSS patterns are universal)

---

## License

MIT License

---

## Author

**Devesh Babbar** — Creator of [KanoonHub](https://kanoonhub.in)

Built from real-world SEO optimization of a 850+ page legal education website.

---

If this skill helped you, give it a star!
