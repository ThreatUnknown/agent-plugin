---
name: check-a-package
description: Use before you add, install, upgrade, or start using an npm package in code, including one already in package.json that this code did not use before, and when asked if a package or version is safe.
---

# Check a package

Follow `threat-unknown-safety`.

1. Call `supply_chain_check_package` with the exact package name, including its scope. Include the version when the person names one. Otherwise the check uses the latest version.
2. Report the verdict, the reasons that affect the person's decision, and any fixed version the tool names. Leave the package uninstalled if the verdict is `block`. Explain a `warn` before making a change.
3. Report `not-checked` when the tool could not check the package. Treat `ok` as the result of the checks that ran.
