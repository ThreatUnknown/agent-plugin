---
name: scan-a-repository
description: Use when you have pushed a branch or are about to open a pull request in a connected repository, or when asked to scan a repo or branch, check code for security issues, or answer "is this safe to merge?". Also for scan results and merged fixes.
---

# Scan a repository

Follow `threat-unknown-safety`.

## Before you push

Check your edits with `check_my_changes` first, as `check-your-changes` says. Push only once that
check passes.

## After you push

1. Before the pull request opens, call `code_scan_repository` once with the repository and the
   `branch` you pushed, at medium effort, which adds our review. Do not stop to ask first. Tell the
   person in one line that it used credits; with no credits left, the scan runs at low on its own.
   Read the result with `get_code_scan`; while it runs, wait a minute between checks.
2. Report the new findings, and the findings no longer present, compared with the default branch.
3. Open the pull request only when the person agrees.

## Other scans

- If the person gives you a scan ID, read it with `get_code_scan`.
- To scan the default branch, call `code_scan_repository` with no branch or commit. For a merge question, scan the branch or commit under review.
- For a finished default-branch scan, read the recorded findings with `list_findings`.
- If a scan fails or was not checked, report the tool's reason.
