---
name: check-your-changes
description: Use when you have changed code (even one line), a dependency, a Dockerfile, Terraform or a CI workflow in a repository, before you say the work is done, even if nobody mentioned security; or when asked to check your changes, or whether a change is safe or secure.
---

# Check your changes

Follow `threat-unknown-safety`.

This is part of finishing any code change, like running the tests. Do it before you report the
work done, and before you commit, push, open a pull request or deploy.

1. List what changed: `git status` and `git diff`. Take every changed or new file, including
   changes that were there before you started. Skip files that are only documentation. If you
   are pushing commits that are already made, take the files they change since the remote
   branch, and use the commit they start from as `baseSha`.
2. Call `check_my_changes` with:
   - `repository`: `owner/name`, from `git remote -v`.
   - `baseSha`: `git rev-parse HEAD`, before you commit.
   - `edits`: each changed file's path and its full new content, not a diff.
   Leave `effort` at low: it uses no credits and saves nothing.
3. If it answers `{"status":"running","checkId":...}`, call it again with only that `checkId`.
4. Fix every new finding in a failing section, then check again. A finding marked warn, accepted
   or dismissed does not fail the check. A section that did not finish does not pass: check again.
5. If it answers `baseFallback`, your commit is not pushed yet, so the edits were checked against
   the default branch. Say so when you report.
6. On `CHECK_RATE_LIMITED`, tell the person what the refusal says and wait until `resetsAt`.
7. Once it passes, go on with the commit, push or deploy. After you push a branch, follow
   `scan-a-repository` to scan it.

Tell the person what the check found, in a sentence. Never say the changes are safe unless the
check passed.
