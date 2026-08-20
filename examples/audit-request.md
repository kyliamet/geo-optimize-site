# Audit-only request

```text
$geo-optimize-site audit this website for generative engine optimization.

Inspect the repository and rendered public pages. Prioritize issues that affect whether AI search and answer engines can discover, understand, quote, and cite accurate information. Include crawlability, answer-first content, headings, metadata, canonicals, structured data, sitemaps, crawler rules, llms.txt, internal links, and image descriptions where relevant.

Do not edit files. Return findings in impact order, cite the affected files or routes, distinguish verified problems from recommendations, and identify any claims or business facts that require owner confirmation.
```

Expected behavior:

- The skill inspects the actual stack and site rather than applying a generic checklist.
- It reports evidence and prioritizes material issues.
- It does not change files because the request is audit-only.
- It flags uncertain facts rather than inventing them.
