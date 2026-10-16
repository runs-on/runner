# RunsOn runner

Builds of the [GitHub Actions runner](https://github.com/actions/runner) that
[RunsOn](https://runs-on.com) installs on its runners.

Each release is built from an upstream `actions/runner` release, with any
RunsOn changes applied, for Linux x64, Linux arm64 and Windows x64. The
packages keep upstream's file names and layout, and the runner reports the
upstream version to GitHub, so GitHub's runner version rules apply unchanged.

## Versions

`v2.338.0-runs-on.1` is RunsOn build 1 of upstream `v2.338.0`. Its release
notes name the upstream commit it was built from.

## Verifying a download

Releases are immutable: once published, their tag and files can't change.
GitHub signs an attestation for each release, which the GitHub CLI (2.81 or
later) checks:

```bash
gh release verify-asset v2.338.0-runs-on.1 actions-runner-linux-x64-2.338.0.tar.gz --repo runs-on/runner
```

Each release also lists its SHA-256 checksums in `SHA256SUMS`:

```bash
sha256sum --check --ignore-missing SHA256SUMS
```

## Issues

Report problems in [runs-on/runs-on](https://github.com/runs-on/runs-on/issues).

## License

The upstream runner is MIT-licensed by GitHub; its notice is in
[LICENSE](LICENSE) and ships in every package.
