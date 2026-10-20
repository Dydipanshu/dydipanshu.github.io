# SEO + AEO + GEO Audit skill for Claude Code

The SEO + AEO + GEO Audit skill makes your AI coding agent audit a website for Google rankings, answer-engine snippets and citations in ChatGPT, Claude, Perplexity and Gemini. It scores the site, lists the top fixes by impact, then implements them in your codebase: meta tags, structured data, sitemap, robots.txt and llms.txt.

Tier: free

## When to use it

- Your site isn't showing up on Google
- You want ChatGPT or Perplexity to cite your product
- You need valid JSON-LD structured data
- You're adding llms.txt and AI crawler rules

## SKILL.md

---
name: seo-geo-audit
description: Audit a website or web codebase for SEO (Google), AEO (answer engines, featured snippets) and GEO (getting cited by ChatGPT, Claude, Perplexity, Gemini), then fix what it finds. Use when the user asks to improve search ranking, SEO, AI visibility, rich results, structured data, llms.txt, or "why doesn't my site show up".
---

# SEO + AEO + GEO Audit

You audit a site against three audiences: search engine crawlers (SEO), answer boxes and voice
assistants (AEO), and LLM-based search and chat products (GEO). Then you fix the issues directly
in the codebase, highest impact first.

## Step 1: Find what you're auditing

- If the user gave a URL, fetch the homepage plus 2-3 key pages, `/robots.txt`, `/sitemap.xml`
  and `/llms.txt`.
- If you're in a codebase, find the framework (Next.js, Astro, Hugo, plain HTML, etc.) and where
  `<head>` tags, routes and static files live. Run the dev build if needed and inspect rendered HTML,
  not just source templates.
- Ask the user one question if unclear: "What are the 3-5 searches you most want to show up for?"
  If they don't know, infer them from the product and state your assumption.

## Step 2: Run the checklist

Score each item PASS / WARN / FAIL with a one-line reason and the file or URL it applies to.

### Crawlability and indexing (SEO)
- Pages return 200, render meaningful HTML without JavaScript (view-source has the main content)
- `robots.txt` exists, does not block important paths, links to the sitemap
- `sitemap.xml` exists, lists every indexable page with `<lastmod>`, no 404s or redirects in it
- Each page has a self-referencing `<link rel="canonical">`; no duplicate URLs (trailing slash, www, http)
- No accidental `noindex` on pages that should rank
- Internal links: every important page reachable within 3 clicks, descriptive anchor text

### On-page (SEO)
- Unique `<title>` per page, under 60 characters, primary keyword first
- Unique meta description per page, 120-160 characters, says what the reader gets
- Exactly one `<h1>`, logical h2/h3 hierarchy, keyword in the h1
- Images have descriptive `alt`, explicit width/height, modern formats, lazy-loading below the fold
- `lang` attribute on `<html>`, viewport meta present
- Open Graph and Twitter card tags (title, description, image 1200x630)

### Performance (SEO ranking factor)
- Largest Contentful Paint under 2.5s, CLS under 0.1, INP under 200ms (use Lighthouse or PageSpeed if available)
- No render-blocking scripts in `<head>`; fonts use `font-display: swap`
- Total page weight reasonable; no multi-MB hero images

### Answer readiness (AEO)
- Key pages lead with a direct, 40-60 word answer to the page's main question before elaborating
- Question-shaped headings ("How much does X cost?") followed by a concise answer paragraph
- FAQ section for real customer questions, marked up with `FAQPage` JSON-LD
- Lists and tables for steps, comparisons and specs (these get pulled into snippets)
- Structured data valid for the page type: `Organization`, `WebSite`, `Product`/`SoftwareApplication`
  (with `offers`), `Article` (with `author`, `datePublished`), `HowTo`, `BreadcrumbList`

### AI citation readiness (GEO)
- `robots.txt` explicitly allows AI crawlers the user wants to be cited by: `GPTBot`, `OAI-SearchBot`,
  `ChatGPT-User`, `ClaudeBot`, `Claude-SearchBot`, `PerplexityBot`, `Google-Extended`, `Applebot-Extended`
- `/llms.txt` exists: product name, one-paragraph summary, and links to the most important pages
  (ideally with Markdown versions)
- Content is quotable: specific numbers, named entities, clear definitions, original data or
  examples an LLM can attribute ("X costs $9.99/month and includes Y")
- Consistent entity naming: the product name, category and one-line description are identical
  across the site, structured data, and external profiles
- Author and organization credibility signals: about page, real author names, `sameAs` links to
  GitHub/X/LinkedIn in `Organization` JSON-LD
- Comparison and "best X for Y" pages exist for the product's category, written fairly (LLMs
  heavily cite these)
- Freshness: visible "last updated" dates on content that changes

## Step 3: Report

Output a short report:

1. **Score**: SEO x/10, AEO x/10, GEO x/10, one sentence each on why
2. **Top 5 fixes by impact**, each with the exact file and what to change
3. **Full checklist table** (item, status, note)
4. **Content gaps**: 3-5 pages that should exist to win the target searches, with suggested
   title, h1 and the question each one answers

## Step 4: Fix

Unless the user only asked for a report, implement the top fixes:

- Add or correct meta tags, canonicals, OG tags in the framework's head mechanism (don't hand-edit
  build output)
- Generate `robots.txt`, `sitemap.xml` and `llms.txt` from the route list so they stay in sync
- Add JSON-LD as `<script type="application/ld+json">`, generated from the same data the page
  renders, so markup never drifts from visible content
- Never invent facts for structured data or FAQ answers (prices, ratings, reviews, dates). Use
  what's on the page, or ask the user. Fake `aggregateRating` can earn a Google manual penalty.

After fixing, re-check the changed items and show the before/after for each.

## Rules

- Prioritize by impact on the user's target searches, not checklist completeness
- Don't recommend keyword stuffing, hidden text, doorway pages, or buying links
- Don't block AI crawlers unless the user asks; explain the trade-off (training vs. citation) if they do
- Validate JSON-LD syntax before finishing (parse it as JSON at minimum)

