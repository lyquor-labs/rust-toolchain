# Agent instructions

## Repo purpose

This repo is a minimal wrapper around a GitHub Actions workflow on `main` that builds atomics and unwind variants of `rust-std` for `wasm32-unknown-unknown`. The shared Rust tag is set by `RUST_VERSION` in `.github/workflows/build.yml`; variant configs live in `atomics/bootstrap.toml` and `unwind/bootstrap.toml`. Each build uploads artifacts from `rust/build/dist` and publishes its variant's release when run on `main`.

## Local testing

Use this command for local workflow testing with `act`:

```bash
act -P ubuntu-22.04-arm64-large=catthehacker/ubuntu:full-22.04 --artifact-server-path /tmp/act-artifacts
```

## Change guidelines

- Keep workflow changes scoped to `.github/workflows/build.yml` unless requested otherwise.
- Preserve the arm64 large runner label `ubuntu-22.04-arm64-large` unless explicitly changed.
