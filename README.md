# embd-pre-commit

A [`pre-commit`](https://pre-commit.com/) hook for [`embd`](https://github.com/ptsouchlos/embd) that uses pre-built `embd-cli` Python wheels from PyPI, so no Rust toolchain is required.

## Usage

Add the following to your `.pre-commit-config.yaml`:

```yaml
repos:
  - repo: https://github.com/ptsouchlos/embd-pre-commit
    rev: v0.4.0 # pin to a released tag
    hooks:
      - id: embd-status
```

By default, `embd-status` runs `embd status` across your repository. You can pass extra arguments via `args`, for example:

```yaml
repos:
  - repo: https://github.com/ptsouchlos/embd-pre-commit
    rev: v0.4.0
    hooks:
      - id: embd-status
        args: ["--quiet", "infra"]
```
