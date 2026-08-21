# Representative report structure

The skill should adapt its response to the repository and user request. A useful audit or implementation summary commonly contains:

## Outcome

A short explanation of what was audited or changed and the most important effect.

## High-impact findings

For each material finding:

- Affected route or file.
- Observable evidence.
- Why it matters for accurate discovery, extraction, or citation.
- Recommended or completed correction.
- Any factual input still required from the site owner.

## Changes made

Only for implementation requests: list the focused changes and connect them to the findings they address.

## Validation

Report checks actually performed, such as builds, tests, parsed JSON-LD and XML, route checks, rendered-page inspection, heading and canonical verification, or browser-console review. Do not claim checks that were not run.

## Remaining decisions

Call out crawler-policy choices, unsupported claims, deployment-dependent behavior, or owner-supplied facts that Codex should not decide by inference.

## Propagation observations

Include this section only when the user requested downstream re-checking. First report one source-readiness state: `source-not-fixed`, `source-unverified`, `site-fixed`, or `crawl-signals-updated`. For `source-not-fixed`, include the affected URLs and evidence; for `source-unverified`, record the constraint. In either case, omit downstream propagation states unless the user separately requested current observations. When downstream queries run, record the timestamp, expected fact, observed fact, cited URLs, comparison limitations, and one observation state per engine and query: `current-observation`, `engine-stale`, `propagated`, or `unable-to-verify`. Use `propagated` only for a measured stale-to-correct transition. Without that transition, use `current-observation` for a correct current answer and `engine-stale` for a disproven or superseded current answer.
