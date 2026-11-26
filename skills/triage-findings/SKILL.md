---
name: triage-findings
description: Use when asked about security findings, vulnerabilities, security issues, anything critical, what to fix first, or to check my dependencies. Also for finding or policy decisions.
---

# Triage findings

Follow `threat-unknown-safety`.

1. Call `list_findings` to read findings Threat Unknown has already recorded. Filter by area when the person asks about one, such as supply chain for "check my dependencies." For a specific repository, use only entries you can tie to it. Ask the person to open that repository's findings in the portal if the result does not identify the repository.
2. Group by status. Start with open findings and put the most severe first. Explain where each issue is, why it matters, and what to change. Link to any fix pull request the result includes.
3. When the person wants a finding fixed, follow `fix-a-finding`. A later scan can show whether the finding is fixed.
4. When the person decides to accept a risk or mark a finding as a false positive, call `accept_risk` with `repo`, the `findings` object, and their reason. Copy the area and fingerprints from the result. Share the pull request for a person to review and merge before counting the finding as settled.

## Repository policies

Use `list_policy_packs` to see which policies a repository runs and `recommend_policy_packs` when the person asks what fits their code. After the person chooses a change, use `set_policy_packs` to open a pull request and share it for review.
