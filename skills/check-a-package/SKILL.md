---
name: check-a-package
description: Use when the person asks whether to add or upgrade a package from the npm registry or wants Threat Unknown to check a package version.
---

# Check a package

Follow `threat-unknown-safety`.

1. Call `supply_chain_check_package` with the exact package name, including its scope. Include the version when the person names one. Otherwise the check uses the latest version.
2. Report the verdict, the reasons that affect the person's decision, and any fixed version the tool names. Leave the package uninstalled if the verdict is `block`. Explain a `warn` before making a change.
3. Report `not-checked` when the tool could not check the package. Treat `ok` as the result of the checks that ran.
