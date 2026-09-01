# Branch ruleset

Matches the opsdevcode/repave-family `main branch` ruleset (PRs required,
non-fast-forward, admin bypass). Status checks are docs-repo equivalents
of `commitlint` and `semantic-pull-request` only; this repository has no
engine, CLI, or operator test jobs.

```bash
gh api --method POST repos/opsdevcode/convergence/rulesets \
  --input .github/rulesets/main-branch.json
```

To update after create:

```bash
RULESET_ID="$(gh api repos/opsdevcode/convergence/rulesets \
  --jq '.[] | select(.name=="main branch") | .id')"
gh api --method PUT "repos/opsdevcode/convergence/rulesets/${RULESET_ID}" \
  --input .github/rulesets/main-branch.json
```
