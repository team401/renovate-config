# Team 401 Renovate configuration

Shared Renovate policy for Team 401 applications.

Repositories opt in with:

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
- Minor, patch, pin, and digest updates are grouped by package ecosystem.
- Major updates remain separate and require manual review.
- Security updates can run outside the weekly schedule.
- Lockfiles receive monthly maintenance updates.
- Renovate never automerges pull requests.
- Each repository's normal CI and branch protection remain the merge gate.

Update `default.json` through a pull request to change the policy for every repository that extends this preset.
