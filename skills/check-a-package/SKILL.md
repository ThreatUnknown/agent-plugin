---
name: check-a-package
description: Use when asked if an npm package is safe, whether to add or upgrade it, or to check a named dependency or version before installing it.
---

# Check a package

Follow `threat-unknown-safety`.

1. Call `supply_chain_check_package` with the exact package name, including its scope. Include the version when the person names one. Otherwise the check uses the latest version.
2. Report the verdict, the reasons that affect the person's decision, and any fixed version the tool names. Leave the package uninstalled if the verdict is `block`. Explain a `warn` before making a change.
3. Report `not-checked` when the tool could not check the package. Treat `ok` as the result of the checks that ran.
