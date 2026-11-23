---
name: threat-model-a-feature
description: Use when the person asks to read, write, or update a feature's threat model, or to review what can go wrong in a change to sign-in, a route, a webhook, a data store, or an external call.
---

# Threat-model a feature

Follow `threat-unknown-safety`.

1. Call `get_feature_context` with `repo` and `featureId` to read the accepted model, any draft, and open review questions. Leave out `featureId` to list the repository's models. Read the relevant code before proposing changes.
2. Map how the feature receives requests, stores data, and talks to other systems. Describe what could go wrong and what prevents it. Cite file paths and lines for safeguards already in place. Name an owner for planned work.
3. When the person asks to save the model, call `submit_threat_model`. Use `new` for a first model or `revise` with the current `expectedRevision`. Use `answer` with the feature, revision, and question IDs to respond to a review. Cite real code. Read the new revision again if the tool reports a conflict.
4. Tell the person which questions remain and whether Threat Unknown accepted the revision. When the person chooses to accept a threat, call `accept_risk` with the feature, threat, current revision, and their reason. Share the pull request for a person to review and merge.
5. Keep `.threatunknown/features.yaml` current with the feature ID and its file patterns in the repository. Keep the model in Threat Unknown.
