# Team 401 Renovate configuration

Shared Renovate policy for Team 401 applications.

Team 401 repositories inherit this policy automatically through
`org-inherited-config.json`. Repositories outside the organization opt in with:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>team401/renovate-config"]
}
```

Repositories that promote changes through a `staging` branch also set:

```json
{
  "baseBranchPatterns": ["staging"]
}
```

## Policy

- Runs are scheduled weekly before 9 AM Monday in `America/New_York`.
- Minor, patch, pin, and digest updates are grouped by package ecosystem and
  automerged after their status checks pass.
- Major updates remain separate and require manual review.
- Security updates can run outside the weekly schedule and are not held by the
  normal three-day release delay.
- Lockfiles receive monthly maintenance updates and automerge after checks pass.
- Renovate performs PR-based automerge itself instead of enabling GitHub's
  platform automerge, so repositories without branch protection still wait for
  CI.
- A pull request with no passing status check remains open for manual review.

Update `default.json` through a pull request to change the policy for every repository that extends this preset.
