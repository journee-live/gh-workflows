# gh-workflows

Reusable GitHub Actions workflows for the Journee organization.

## Available Workflows

### Secret Scan (`secret-scan.yml`)

Scans PR diffs for leaked tokens, secrets, and credentials using [TruffleHog](https://github.com/trufflesecurity/trufflehog).

**Usage** — add this to `.github/workflows/secret-scan.yml` in your repo:

```yaml
name: Secret Scan
on:
  pull_request:
    branches: [main]

jobs:
  trufflehog:
    uses: journee-live/gh-workflows/.github/workflows/secret-scan.yml@main
```

Then enforce it as a required status check via branch protection or an org-level ruleset.
