# actions

Shared GitHub Actions for VeyronSakai repositories.

This repository hosts reusable composite actions that are shared across multiple repositories.

## Actions

| Path | Description | Outputs |
| --- | --- | --- |
| `git/config` | Reads `.lfsconfig` from the calling repository with `gh api` and extracts the Git LFS endpoint URL. | `lfs-url` |
| `git/checkout` | Runs `actions/checkout@v6` and can optionally read `.lfsconfig` to inject a custom Git LFS endpoint first. | `lfs-url` |

## Usage

```yaml
- uses: VeyronSakai/actions/git/checkout@<ref>
  with:
    lfs: "false"
```

Enable `lfs: "true"` when the calling repository needs `actions/checkout` to respect a custom Git LFS endpoint from `.lfsconfig`. In that case, also pass `github-token`.

```yaml
- uses: VeyronSakai/actions/git/checkout@<ref>
  with:
    github-token: ${{ github.token }}
    lfs: "true"
```
