# Post-deployment propagation checks

Use this workflow only when the user asks whether a verified site correction has propagated to one or more AI search or answer engines.

## Define a comparable check

- Record the target engine, control query, locale or region when relevant, timestamp, expected verified fact, observed answer or quoted claim, and cited URLs.
- Reuse the same query and materially relevant settings for later checks when practical. Note any differences that weaken comparison.
- Treat each engine response as a time-stamped observation. Generated answers can vary without an underlying index change, so do not infer propagation from wording alone.

## Verify the source first

- Confirm the corrected fact is visible on the intended canonical pages and absent from crawlable metadata, structured data, feeds, and other public sources that should no longer contain it.
- For deleted pages, verify the intended HTTP status or redirect behavior, removal from sitemaps and internal links, and the absence of misleading canonicals or stale structured data. Do not redirect a removed URL to an irrelevant destination merely to avoid a `404` or `410`.
- Distinguish a deployed fix from submitted crawl signals. A sitemap update or reindex request is evidence of submission, not evidence that an engine processed it.
- If an intended source still exposes the superseded fact, report `source-not-fixed` with the affected URLs and evidence. Stop propagation classification until the source is corrected; run a downstream query only if the user separately requests a current observation rather than a propagation conclusion.
- If access, authentication, rendering, or conflicting evidence prevents a defensible source conclusion, report `source-unverified` with the constraint. Do not classify propagation; run a downstream query only if the user separately requests a current observation.

## Check downstream observations

- Query only the engines the user named or authorized. Do not silently broaden the check to additional providers.
- Capture the answer, relevant quoted fact, cited URLs, and timestamp. Preserve a short excerpt only when needed to identify the stale claim.
- Compare facts and citations with the baseline. Without a demonstrated stale-to-correct transition, do not claim propagation: use `current-observation` for a correct current result, `engine-stale` for a disproven or superseded current result, and `unable-to-verify` when the evidence is inconclusive.
- Report one source-readiness state for the overall check:
  - `source-not-fixed`: the origin or an intended crawl source still exposes the superseded fact, so downstream propagation cannot yet be assessed.
  - `source-unverified`: available evidence cannot establish whether the origin and intended crawl sources are corrected.
  - `site-fixed`: the origin is corrected, but one or more intended crawl signals are stale or were not verified as updated.
  - `crawl-signals-updated`: the origin and intended discovery signals are verified as corrected.
- When downstream queries run, report one observation state for each engine and query:
  - `current-observation`: the current engine response reflects the corrected fact without relying on the stale source, but no comparable stale baseline establishes a change; this includes a missing baseline or a baseline that was already correct.
  - `engine-stale`: the engine still presents the disproven or superseded fact, or cites a removed source as supporting it.
  - `propagated`: a comparable baseline presented the superseded fact or relied on the stale source, and the current observation now reflects the corrected fact without relying on that source.
  - `unable-to-verify`: access, authentication, regional variation, missing citations, or another constraint prevents a defensible conclusion.

## Keep actions bounded

- Never claim that the skill can force recrawling, purge an engine cache, or guarantee when a correction will propagate.
- Before provider-specific submissions or removal requests, verify current official provider documentation and obtain authorization for authenticated or externally mutating actions.
- Recurring monitoring requires an explicit cadence, stopping condition, target engines, and control-query set. Do not create an automation from a one-time check request.
- Report unresolved stale observations with evidence and the next provider-supported action, if one is verified and available.
