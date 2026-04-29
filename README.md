# actions

Shared GitHub Actions for VeyronSakai repositories.

This repository hosts reusable composite actions that are shared across multiple repositories.

## Actions

| Path | Description | Outputs |
| --- | --- | --- |
| `git/config` | Reads `.lfsconfig` from the calling repository with `gh api` and extracts the Git LFS endpoint URL. | `lfs-url` |
| `git/checkout` | Reads `.lfsconfig`, injects the resolved LFS endpoint into `GIT_CONFIG_*`, and runs `actions/checkout@v6`. | `lfs-url` |

## Usage

```yaml
- uses: VeyronSakai/actions/git/checkout@<ref>
  with:
    github-token: ${{ github.token }}
```

Use `git/checkout` when the calling repository needs `actions/checkout` to respect a custom Git LFS endpoint from `.lfsconfig`.
