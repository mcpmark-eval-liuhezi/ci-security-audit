# Audit Dry-Run Notes

## What this dry run covers

- **Manual trigger (`workflow_dispatch`)**: the `dep-audit.yml` workflow can be started by hand from the Actions tab, confirming the workflow file is present on the default branch (`main`) — a requirement for `workflow_dispatch` to register.
- **Pull-request trigger**: the workflow also fires automatically when a pull request is opened, verifying that PR-opened events are wired up correctly.
- **Single-job execution**: the workflow contains one job (`audit`) that runs on `ubuntu-latest` and prints `Audit dry run completed`, exercising the Actions runner end-to-end without touching any real dependencies.
- **Branch + PR flow**: a dedicated `audit-dry-run` branch carries these notes and is opened as a pull request back into `main`, rehearsing the review path.
- **Security surfaces checked**: Dependabot alerts are listed for this repository (expected: none on a brand-new sandbox) and repository notifications are switched to **watching**, so the audit trail is visible during rehearsal.

This sandbox exists to rehearse the full CI security-audit flow before running it anywhere real. Nothing here is production-affecting.
