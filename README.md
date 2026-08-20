# GEO Optimize Site

`geo-optimize-site` is a Codex skill for auditing and improving a website's visibility in AI-generated answers. It helps Codex make public content easier for answer engines to discover, understand, quote, and cite while preserving factual accuracy, accessibility, design, and conventional SEO.

The skill covers answer-first page structure, crawlable content, metadata, canonicals, structured data, sitemaps, `llms.txt`, crawler policy, internal links, and implementation validation. It does not manufacture claims or treat model-training access as a requirement for citation visibility.

## When to use it

Use the skill for requests such as:

- "Audit this site for generative engine optimization."
- "Improve our visibility in AI search and answer engines."
- "Review our `llms.txt`, sitemap, structured data, and crawler rules."
- "Implement the highest-value GEO fixes and validate the site afterward."

It is intentionally not triggered for ordinary SEO-only work or generic marketing copy.

## Install

### Ask Codex to install it

After this repository is published, give Codex the repository URL:

```text
Use $skill-installer to install the skill from
https://github.com/kyliamet/geo-optimize-site
```

Restart Codex if the newly installed skill is not discovered in the current session.

### Install manually

Place this repository at:

```text
~/.codex/skills/geo-optimize-site/
```

The final path must contain `SKILL.md` directly, with `agents/openai.yaml` beneath it.

## Use

Invoke the skill explicitly:

```text
$geo-optimize-site audit this website for AI-answer visibility and return a prioritized report.
```

Or ask naturally for GEO or AI-search optimization; Codex can select the skill automatically when the request matches its description.

See [examples](examples/) for audit-only and implementation prompts plus a representative report structure.

## What the skill changes

Depending on the site and the user's request, the skill may:

- Improve page headings and answer-first summaries.
- Repair titles, descriptions, canonical URLs, robots directives, and social metadata.
- Add or correct evidence-backed Schema.org JSON-LD.
- Improve server-rendered or otherwise crawlable page content.
- Add or repair a sitemap and a supplemental `llms.txt` file.
- Review crawler rules using current official provider documentation.
- Improve descriptive alt text and internal linking.
- Run project checks and inspect rendered pages before reporting completion.

The skill audits before editing and preserves unrelated changes. It requires separate authorization before staging, committing, pushing, or opening a pull request.

## Design principles

- Verified facts over speculative claims.
- Useful content for people first.
- GEO as a complement to crawlability and SEO, not a replacement.
- Structured data that matches visible page content.
- Observable validation instead of checklist-only completion.
- Deliberate separation of search, user-request retrieval, and model-training crawler policies.

## Compatibility

The skill is designed for Codex's skill format: a directory with a `SKILL.md` entrypoint and optional supporting resources. It does not require an API key or third-party service by itself. Site-specific builds, browser testing, and documentation checks may use tools already available in the user's Codex environment.

## Contributing

Bug reports and focused improvements are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request. Security-sensitive reports should follow [SECURITY.md](SECURITY.md).

## License

Released under the [MIT License](LICENSE).

This is a community project and is not an official OpenAI product.
