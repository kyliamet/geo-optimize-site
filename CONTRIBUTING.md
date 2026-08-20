# Contributing

Thank you for helping improve `geo-optimize-site`.

## Good contributions

- Correct guidance that is outdated, ambiguous, or unsafe.
- Improve skill routing without attracting unrelated SEO or copywriting tasks.
- Add validation for a concrete failure observed on a real website stack.
- Make an instruction shorter or clearer without weakening an important constraint.
- Add a small, representative example that clarifies a recurring use case.

Avoid adding speculative ranking tactics, provider behavior that is not supported by current official documentation, universal framework instructions, or rules based on a single anecdote.

## Propose a change

1. Open an issue for substantial behavioral changes so the intended scope can be discussed.
2. Create a focused branch and update only the files needed for the change.
3. Validate the skill locally.
4. Explain the user request or observed failure that motivates the change.
5. Open a pull request and describe the behavior before and after the update.

## Validate locally

If Codex's `skill-creator` skill is installed, ask it to validate this directory. The underlying validator can also be run from that skill package:

```text
quick_validate.py /path/to/geo-optimize-site
```

Validation checks the skill's structure and frontmatter. Also review behavior manually with realistic audit-only and implementation requests; passing structural validation does not prove that the instructions make sound GEO decisions.

## Pull-request checklist

- The `name` and `description` still route only appropriate GEO requests.
- New instructions change a meaningful decision or prevent a demonstrated failure.
- Claims about crawlers or platforms are current and sourced from official provider documentation.
- The skill does not imply authorization for unrelated edits or publishing actions.
- Examples contain no secrets, private URLs, customer data, or unsupported performance claims.
- Documentation and changelog entries are updated when user-visible behavior changes.
