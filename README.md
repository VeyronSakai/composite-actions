# composite-actions

Shared GitHub Actions for VeyronSakai repositories.

This repository hosts reusable composite actions that are shared across multiple repositories.

## Actions

| Path | Description | Outputs |
| --- | --- | --- |
| `.github/actions/git/config` | Reads `.lfsconfig` from the calling repository with `gh api` and extracts the Git LFS endpoint URL. | `lfs-url` |

## Usage

```yaml
- name: Read LFS config
  id: read-lfs-config
  uses: VeyronSakai/composite-actions/.github/actions/git/config@<ref>
  with:
    github-token: ${{ github.token }}
```

Use the returned `lfs-url` output to populate `GIT_CONFIG_*` environment variables for a later `actions/checkout` step when the repository uses a custom Git LFS endpoint.
