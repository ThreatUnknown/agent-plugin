---
name: scan-a-repository
description: Use when the person asks Threat Unknown to run a fresh code scan on a connected repository, scan a branch before a pull request, track a code scan, or check a merged fix.
---

# Scan a repository

Follow `threat-unknown-safety`.

1. Confirm the connected repository and any branch, commit, or feature the person wants scanned. With no branch or commit, the scan uses the default branch. Explain any credit use before selecting an effort that uses credits.
2. Call `code_scan_repository` with the repository as `owner/name`. Pass either `branch` or `commit` for a specific revision. Use the returned scan ID with `get_code_scan`.
3. While the scan is running, wait a minute before checking again. If a scan fails or was not checked, report the tool's reason.
4. For a finished default-branch scan, read the recorded findings with `list_findings`. For a branch or commit scan, report the new findings and findings no longer present compared with the default branch.
