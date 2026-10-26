# Workflow security baseline

External GitHub Actions are pinned to exact commits to prevent moving tags from changing the code executed by CI. Version comments preserve the update intent for Renovate. Existing action major versions are retained. Local actions remain local.

Workflows default to read-only repository contents. Existing explicit job permissions are preserved; release jobs retain the write permissions required to publish their existing outputs.

Only enable repository or organization SHA-pinning enforcement after these changes are merged into every branch that runs workflows and all references are verified. This change does not alter branch protection, approval counts, deployment credentials, or repository access.

Validation in this rollout uses a partial workflow snapshot: YAML parsing and semantic review. Application builds, cloud deployments, and release publishing are not executed locally. Review the PR checks before merging.

