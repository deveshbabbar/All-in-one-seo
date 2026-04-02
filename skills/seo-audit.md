---
name: SEO/GEO/AEO Full Audit & Optimization
description: Complete SEO, GEO (Generative Engine Optimization), and AEO (AI Engine Optimization) audit and implementation for Next.js websites following 2025-2026 Google guidelines
triggers:
  - seo
  - seo audit
  - geo optimization
  - aeo optimization
  - google ranking
  - search optimization
---

# SEO/GEO/AEO Full Audit & Optimization Skill

## When to Use
- When optimizing a website for Google Search, AI search engines (Perplexity, ChatGPT, Google AI Overviews)
- When launching new pages and need SEO setup
- When auditing existing SEO and fixing issues
- When adding structured data for rich results

---

## PHASE 1: SEO AUDIT CHECKLIST

### 1.1 Meta Tags (check every page)
- [ ] `title` — unique, < 60 chars, primary keyword first
- [ ] `description` — unique, < 160 chars, includes CTA
- [ ] `keywords` — 5-10 relevant terms
- [ ] OpenGraph: `og:title`, `og:description`, `og:image`, `og:type`, `og:url`
- [ ] Twitter: `card`, `title`, `description`
- [ ] `canonical` URL via alternates
- [ ] **Client components ("use client") CANNOT export metadata** — create a separate `layout.tsx` in the same directory

### 1.2 Schema.org / JSON-LD
- [ ] Organization + WebSite + SearchAction (root layout)
- [ ] BreadcrumbList (on all inner pages)
- [ ] Article / Legislation (content pages)
- [ ] FAQPage (pages with FAQ sections)
- [ ] HowTo (tutorial/guide pages)
- [ ] CollectionPage + ItemList (listing pages)
- [ ] Person (author attribution — E-E-A-T)

### 1.3 Sitemap
- [ ] All static pages included
- [ ] All dynamic pages included
- [ ] Priority and changefreq set correctly
- [ ] New pages added when created

### 1.4 robots.txt
- [ ] Allow all important crawlers
- [ ] Allow AI bots: GPTBot, PerplexityBot, ClaudeBot, Google-Extended
- [ ] Sitemap URL declared
- [ ] No accidental disallow of important paths

### 1.5 Technical SEO
- [ ] Custom 404 page (`not-found.tsx`)
- [ ] Error boundary (`error.tsx`)
- [ ] Image optimization (next/image, AVIF/WebP)
- [ ] Security headers (X-Content-Type-Options, X-Frame-Options)
- [ ] No placeholder verification codes
- [ ] Fonts with `display=swap`
- [ ] `poweredByHeader: false` in next.config

### 1.6 Content SEO
- [ ] H1 on every page (unique)
- [ ] Heading hierarchy (H1 > H2 > H3)
- [ ] Alt text on all images (descriptive, not empty)
- [ ] Internal linking between related pages
- [ ] External source citations

---

## PHASE 2: GEO OPTIMIZATION (Generative Engine Optimization)

### Goal: Get cited by AI search engines (Google AI Overviews, Perplexity, ChatGPT)

### 2.1 Structured Answer Blocks
Add clear, concise answer blocks that AI can extract:
```jsx
<section>
  <h2>What is [Topic]?</h2>
  <p>[Direct answer in 2-3 sentences. Factual, cited.]</p>
  <h3>Key Features</h3>
  <ul>
    <li>• [Feature 1]</li>
    <li>• [Feature 2]</li>
  </ul>
  <p className="text-xs text-muted">Source: [Official source] | Reviewed by [Expert]</p>
</section>
```

### 2.2 E-E-A-T Signals (Experience, Expertise, Authoritativeness, Trustworthiness)
- Author attribution with credentials on every content page
- "Reviewed by [Expert Name], [Title]" with schema Person markup
- Source citations: "Source: The Gazette of India"
- Last updated dates
- Disclaimer where appropriate

### 2.3 AI-Friendly Content Patterns
- Start paragraphs with the answer (inverted pyramid)
- Use definition format: "[Term] is [definition]"
- Include numbered lists and bullet points
- Add "Key Takeaways" or "Summary" sections
- Use comparison tables where relevant

### 2.4 Schema.org for GEO
```json
{
  "@type": "Article",
  "author": { "@type": "Person", "name": "Expert Name", "jobTitle": "Title" },
  "publisher": { "@type": "Organization", "name": "Site Name" },
  "dateModified": "2026-01-01",
  "citation": { "@type": "CreativeWork", "name": "Source Name" }
}
```

---

## PHASE 3: AEO OPTIMIZATION (AI Engine Optimization)

### 3.1 Allow AI Crawlers (robots.txt)
```
User-agent: GPTBot
Allow: /

User-agent: Google-Extended
Allow: /

User-agent: PerplexityBot
Allow: /

User-agent: ClaudeBot
Allow: /

User-agent: ChatGPT-User
Allow: /
```

### 3.2 Structured Data Priority
AI engines prefer:
1. FAQ schema — highest citation rate
2. HowTo schema — for procedural queries
3. Article schema — for informational queries
4. ItemList schema — for "best of" / "list of" queries

### 3.3 Content Optimization for AI
- Answer questions directly in H2 + first paragraph
- Use "What is X?", "How to X?", "Why X?" format
- Include bilingual content (Hindi + English) for Indian audience
- Cite official sources with links
- Keep paragraphs < 3 sentences for easier extraction

---

## PHASE 4: ADS PLACEMENT (Google-Compliant)

### Better Ads Standards (Chrome blocks violators)
**BANNED on Desktop:**
- Pop-up ads, auto-play video with sound, prestitial with countdown
- Large sticky ads, ad density > 50%

**BANNED on Mobile:**
- Pop-up ads, prestitial ads, ad density > 30%
- Flashing ads, auto-play video with sound
- Full-screen scrollover, large sticky ads

**SAFE Ad Formats:**
- 728x90 Leaderboard (desktop, between content)
- 320x50 Mobile Banner (mobile, between content)
- 300x250 Rectangle (both, in-content)
- 160x600 Skyscraper (desktop sidebar)

**Rules:**
- Max 3-4 ads per page
- No ads above the fold on mobile
- Content loads before ads (`lazyOnload`)
- No click-hijacking scripts (avoid native banner scripts that intercept clicks)
- Ads clearly distinguishable from content
- Print CSS hides ads (`.no-print`)

### Adsterra Specific
- Use iframe format, NOT popunder or social bar
- Set `atOptions` BEFORE loading `invoke.js`
- Contain ads in `overflow: hidden` divs
- Never use native banner scripts globally (they hijack clicks)

---

## PHASE 5: NEXT.JS SPECIFIC PATTERNS

### Metadata for Client Components
```tsx
// src/app/my-page/layout.tsx (SERVER component)
import type { Metadata } from "next";
export const metadata: Metadata = {
  title: "Page Title — Site Name",
  description: "Description here",
  keywords: ["keyword1", "keyword2"],
  openGraph: { title: "...", description: "...", type: "website", url: "/path" },
  twitter: { card: "summary_large_image", title: "...", description: "..." },
  alternates: { canonical: "/path" },
};
export default function Layout({ children }) { return <>{children}</>; }
```

### Sitemap Template
```tsx
import { getCategories, getSectionsByLaw } from "@/lib/data";
import { MetadataRoute } from "next";

export default async function sitemap(): Promise<MetadataRoute.Sitemap> {
  const base = "https://yoursite.com";
  const static_pages = [
    { url: base, changeFrequency: "daily", priority: 1.0 },
    { url: `${base}/page2`, changeFrequency: "weekly", priority: 0.8 },
  ];
  // Add dynamic pages...
  return [...static_pages, ...dynamic_pages];
}
```

### next.config.mjs Template
```js
const nextConfig = {
  images: { formats: ['image/avif', 'image/webp'] },
  poweredByHeader: false,
  headers: async () => [
    {
      source: '/(.*)',
      headers: [
        { key: 'X-Content-Type-Options', value: 'nosniff' },
        { key: 'X-Frame-Options', value: 'DENY' },
        { key: 'X-XSS-Protection', value: '1; mode=block' },
      ],
    },
  ],
};
```

---

## QUICK REFERENCE: Priority Order of Fixes

1. **Missing metadata on pages** — biggest SEO impact
2. **Sitemap incomplete** — Google can't find pages
3. **No structured data** — no rich results
4. **Missing 404/error pages** — poor UX signal
5. **GEO content blocks** — AI citation opportunity
6. **Image optimization** — Core Web Vitals
7. **Security headers** — trust signal
8. **Ad compliance** — avoid penalties
