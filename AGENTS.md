<!-- agents-md-manager:start — managed section, do not edit by hand -->
# groupbees/.github — agent guide

Public repo of reusable GitHub Actions workflows called by other GroupBees
repos (see README.md for the list and how to call them).

## Rules

- Public: no secrets, project ids or internal names in any file.
- Every action is pinned to a commit SHA with its tag in a comment
  (`uses: owner/action@<sha>  # vX.Y.Z`); Dependabot bumps them.
- Tool versions live in a workflow's `env:`, in one place.
- A breaking change to a workflow's inputs or job names is a major release:
  callers' required status checks are named after the jobs.
- Check with `actionlint` before pushing (CI runs it).
- Releases: annotated `vX.Y.Z` tags with the `tag-opensource` skill; commits
  and PRs follow `commit-groupbees` / `pr-groupbees`.
<!-- agents-md-manager:end -->
