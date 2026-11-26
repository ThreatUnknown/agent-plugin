---
name: fix-a-finding
description: Use when asked to fix, patch, remediate, or resolve a security finding or vulnerability, to "fix this", "fix the critical ones", "can you fix it or should I", or after triage when the person wants something changed. Also when you are about to change code because of a Threat Unknown finding.
---

# Fix a finding

Follow `threat-unknown-safety`.

1. Find the finding with `list_findings` if you do not already have its area and fingerprint. Skip any finding that already has a fix pull request or session in progress, and share that link instead.
2. Call `get_suggested_fix` for the finding. Its result says who makes fixes for this organization (`fixPreference`) and what we know about the fix.
3. **"never" (the team makes its own fixes):** make the change in the person's repository yourself, keeping it as small as the suggested fix. Check your edit with `check_my_changes` when it is available, then run the project's own tests. Open or update the person's own pull request only if they asked you to.
4. **"on_request" or "automatic":** ask the person whether they want Threat Unknown to open the fix, or want you to make it. Threat Unknown's fix uses credits, so call `get_credit_balance` and say what it will use before you call `request_fix`. Then call `request_fix` and share the pull request it opens. A person reviews and merges it; merging is the approval.
5. If the person would rather you fix it, follow step 3 at any level.
6. Never say a finding is fixed until a pull request merges and a later scan or `list_findings` shows it closed. A pull request that is open is pending review.
