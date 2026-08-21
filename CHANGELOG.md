# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- Opt-in post-deployment propagation checks that distinguish a corrected origin from stale downstream engine answers.
- Evidence-based propagation states for comparable control queries and citations, reserving propagation for measured stale-to-correct transitions.
- Mutually exclusive source-readiness states for conclusive source failures, inconclusive origin verification, and stale or unverified crawl signals.
- A deleted pricing-page example covering source verification, engine observations, authorization boundaries, and monitoring limits.

## [1.0.0] - 2026-08-20

### Added

- Initial public release of the `geo-optimize-site` Codex skill.
- Audit guidance for page structure, crawlability, metadata, structured data, sitemaps, crawler policy, `llms.txt`, images, and internal links.
- Implementation safeguards against invented claims, unsupported schema, and accidental product changes.
- Validation guidance covering project checks, rendered pages, JSON-LD, sitemaps, routes, assets, and final-diff review.
- Codex interface metadata, usage examples, contribution guidance, and security policy.

[Unreleased]: https://github.com/kyliamet/geo-optimize-site/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/kyliamet/geo-optimize-site/releases/tag/v1.0.0
