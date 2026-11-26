---
name: pen-test-status
description: Use when asked about a penetration test or pen test, "is the pen test done", "what did the test find", "how is the security test going", to see test runs or a run report, or to stop, cancel, or halt a test that is running.
---

# Pen test status

Follow `threat-unknown-safety`.

1. Call `list_pentest_runs` to see the organization's runs, newest first, with each run's status and target.
2. For one run's report and its findings, call `get_pentest_run`. Pen test findings also appear in `list_findings` with area `pentest`; use `fix-a-finding` to fix one.
3. When the person asks to stop a running test, call `stop_pentest_run` for that run and report the status the tool returns. Stopping is always allowed; it only ends traffic to their target.
4. Starting a test, giving or revoking consent for a target, and saving test logins are done in the Threat Unknown portal by a person. Tell the person that when they ask, and do not try another way.
