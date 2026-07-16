# Rust std (wasm32) build workflow

This repository contains a GitHub Actions workflow that checks out `rust-lang/rust` at tag `1.97.1`, copies in `bootstrap.toml`, builds `rust-std` for `wasm32-unknown-unknown`, and uploads artifacts from `rust/build/dist`.

## Local testing

Use `act` with a larger arm64 runner image:

```bash
act -P ubuntu-22.04-arm64-large=catthehacker/ubuntu:full-22.04 --artifact-server-path /tmp/act-artifacts
```
