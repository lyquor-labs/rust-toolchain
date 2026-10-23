# Rust std (wasm32) build workflow

This repository builds two variants of `rust-std` for `wasm32-unknown-unknown` in one GitHub Actions workflow on `main`:

- `atomics/bootstrap.toml` enables atomics.
- `unwind/bootstrap.toml` enables atomics and exception handling with panic unwinding.

Both matrix jobs check out the same `rust-lang/rust` tag, set by `RUST_VERSION` in `.github/workflows/build.yml`. Update that value once to update both builds. Each job copies its variant's config to `rust/bootstrap.toml` and uploads `rust/build/dist` as `rust-std-dist-wasm32-atomics` or `rust-std-dist-wasm32-unwind`.

Pushes to `main` build both variants; the workflow can also be run manually. Runs on `main` publish separate `atomics-YYYYMMDD` and `unwind-YYYYMMDD` releases, preserving the existing release tags and archive filenames. Manual runs on other branches only build and upload workflow artifacts.

## Local testing

Use `act` with a larger arm64 runner image:

```bash
act -P ubuntu-22.04-arm64-large=catthehacker/ubuntu:full-22.04 --artifact-server-path /tmp/act-artifacts
```
