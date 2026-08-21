---
name: geo-optimize-site
description: Audit and implement Generative Engine Optimization (GEO) for websites so accurate public content is easier for AI search and answer engines to discover, understand, quote, and cite. Use when a user asks for GEO, AI-search visibility, answer-engine optimization, stale AI citations, post-deployment propagation checks, llms.txt, or crawler access; do not trigger for ordinary SEO-only or marketing-copy tasks.
---

# GEO Optimize Site

Improve AI-answer visibility without inventing facts, degrading the visitor experience, or replacing conventional crawlability and SEO.

## Audit before editing

- Read repository instructions and determine the framework, deployment target, canonical host, routes, rendering model, and existing SEO/GEO configuration.
- Inspect the latest intended base branch and preserve unrelated or user-owned changes.
- Map the site's real entities, offers, expertise, claims, prices, dates, source links, and public contact/profile information. Treat the repository and supplied sources as authoritative; flag contradictions instead of resolving them by guesswork.
- Identify missing or weak H1s, answer-first summaries, question-oriented sections, crawlable text, canonicals, structured data, sitemaps, crawler rules, image descriptions, and internal linking.
- Look for client-only content, experiment placeholders, hidden fallback text, or metadata that crawlers could extract incorrectly.

## Implement proportionately

- Give each indexable page one descriptive H1 and an early self-contained summary that directly answers what the page or offering is.
- Prefer compact, independently understandable paragraphs, descriptive question headings, lists, tables, and FAQs where they help users and reflect visible page content.
- Never invent qualifications, statistics, testimonials, outcomes, prices, dates, availability, locations, or third-party endorsements. Do not add keyword stuffing or mass-generated pages.
- Preserve the site's design, conversion flow, analytics, experiments, accessibility, and application behavior unless a change is required for accurate crawlable output.
- Add page-specific titles, descriptions, canonical URLs, index directives, and social metadata when missing or weak.
- Add only Schema.org types and properties supported by visible, verified content. Keep JSON-LD consistent with the page. Do not create aggregate ratings or review markup from unsupported evidence.
- Keep important content available in initial HTML or server-rendered output. Remove crawler-visible placeholder tokens without breaking runtime population.
- Add or repair a sitemap containing canonical public pages. Add `llms.txt` only as a supplemental, prompt-friendly site map when the deployment can serve it from the site root.
- Make crawler policy deliberate. For current bot names or behaviors, verify official provider documentation at implementation time. Distinguish search/indexing and user-request retrieval crawlers from model-training crawlers; preserve the owner's stated preference and do not imply that training access is required for citations.
- Add meaningful alt text and useful internal links, avoiding redundant or speculative descriptions.

## Validate observable behavior

- Run the project's existing formatter, type checks, tests, and production build in proportion to the change.
- Parse every added JSON-LD block and XML sitemap.
- Verify one intended H1 and canonical per indexable page, valid local assets and internal routes, and successful HTTP responses for public GEO files.
- Render changed pages locally at relevant viewport sizes. Inspect headings, layout, browser console output, dynamic content, and key interactions.
- Review the final diff for unsupported claims, stale dates, accidental design changes, secrets, unrelated files, and whitespace errors.

## Re-check downstream propagation only when requested

- Treat site-side correctness and downstream engine freshness as separate results. A valid deployment does not prove that an external engine has refreshed an index, cache, or generated answer.
- Run live engine queries, authenticated webmaster actions, reindex requests, or recurring checks only when the user explicitly requests and authorizes them.
- For a propagation check, read [references/propagation-checks.md](references/propagation-checks.md) and report comparable evidence without implying control over engine refresh timing.

## Publish only within authorization

- Create a feature branch from the latest default branch when requested.
- Stage only reviewed task files. Treat staging, committing, pushing, and PR creation as separate external actions requiring the user's authorization.
- Create at most one PR against the resolved default branch, defaulting to draft unless the user requests otherwise. Summarize GEO decisions and list concrete validation performed.
