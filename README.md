# groupbees/.github

Shared GitHub Actions workflows for the GroupBees organization.

| Workflow | For | What it checks |
|----------|-----|----------------|
| [`skills-module.yml`](.github/workflows/skills-module.yml) | every skills module (`skills-core`, `skills-opensource`, …) | `skill-validator check --strict` on each skill, `pollen validate`, the generated README table and unique skill names, `shellcheck` |

Call it from a module, pinned to a commit with the release in a comment:

```yaml
jobs:
  ci:
    uses: groupbees/.github/.github/workflows/skills-module.yml@<sha>  # vX.Y.Z
```

The module's `.github/dependabot.yml` (`package-ecosystem: github-actions`)
keeps that pin up to date. Tool versions (skill-validator, pollen) are pinned
here only, so a bump is one PR in this repo.

Releases are `vX.Y.Z` tags; the GitHub Releases page is the changelog.
