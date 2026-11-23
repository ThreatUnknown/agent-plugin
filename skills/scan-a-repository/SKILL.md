---
name: scan-a-repository
description: Use when asked to scan my repo or branch, scan before I push, check my code for security issues, or answer "is this safe to merge?" Also for scan results and merged fixes.
---

# Scan a repository

Follow `threat-unknown-safety`.

1. Confirm the connected repository and any branch, commit, or feature the person wants scanned. With no branch or commit, the scan uses the default branch. Explain any credit use before selecting an effort that uses credits.
2. If the person gives you a scan ID, read it with `get_code_scan`. To start a fresh scan, call `code_scan_repository` with the repository as `owner/name` and pass either `branch` or `commit` for a specific revision. Use the returned scan ID with `get_code_scan`. For a merge question, use a scan of the branch or commit under review.
3. While the scan is running, wait a minute before checking again. If a scan fails or was not checked, report the tool's reason.
4. For a finished default-branch scan, read the recorded findings with `list_findings`. For a branch or commit scan, report the new findings and findings no longer present compared with the default branch.
