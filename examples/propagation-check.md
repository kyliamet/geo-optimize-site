# Post-deployment propagation request

```text
$geo-optimize-site check whether our pricing correction has propagated.

Ten days ago we removed /pricing-old, updated the live pricing pages, and removed the old URL from the sitemap. Re-run the following control query in the answer engines I authorize: "What does Example Product cost?"

The verified current price is $49 per month. Record each engine, timestamp, answer, quoted price, and cited URLs. First verify that our origin and crawl signals no longer expose the old $39 price. Do not submit reindex or removal requests and do not schedule recurring checks.
```

Expected behavior:

- The skill verifies the origin before treating downstream answers as stale.
- It distinguishes deployment correctness, crawl signals, and engine observations.
- Each authorized engine receives a time-stamped propagation state with supporting evidence.
- It treats generated answers as variable observations and does not promise refresh timing.
- It performs no authenticated submissions or recurring monitoring without separate authorization.
