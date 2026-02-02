# Agent instructions

## Repo purpose

This repo is a minimal wrapper around a GitHub Actions workflow that builds `rust-std` for `wasm32-unknown-unknown` from `rust-lang/rust` tag `1.93.0` and uploads artifacts from `rust/build/dist`.

## Local testing

Use this command for local workflow testing with `act`:

```bash
act -P ubuntu-22.04-arm64-large=catthehacker/ubuntu:full-22.04 --artifact-server-path /tmp/act-artifacts
```

## Change guidelines

- Keep workflow changes scoped to `.github/workflows/build.yml` unless requested otherwise.
- Preserve the arm64 large runner label `ubuntu-22.04-arm64-large` unless explicitly changed.
