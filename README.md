# lspmux-build

Prebuilt Linux binaries of [lspmux](https://codeberg.org/p2502/lspmux), the language-server
multiplexer that lets several LSP clients share one server (for example one `rust-analyzer`)
per workspace. Upstream publishes no prebuilt Linux aarch64 binary; this repository builds one.

Each [release](../../releases) is upstream's source at the tagged commit named in its notes,
built unmodified with `cargo build --release --locked` on GitHub-hosted runners, for
`aarch64-unknown-linux-gnu` and `x86_64-unknown-linux-gnu`. Every archive carries a `.sha256`
file, upstream's `LICENSE` and upstream's `README.md`.

The build is [`.github/workflows/release.yml`](.github/workflows/release.yml): it fetches the
tag from Codeberg, refuses to build if the tag no longer points at the pinned commit, and
skips a version whose release already exists.

## Licence

lspmux is © its authors and licensed under the
[EUPL-1.2](https://codeberg.org/p2502/lspmux/src/branch/main/LICENSE); the binaries are
distributed under that licence, and their source is the upstream commit named in each
release. Problems with lspmux itself belong upstream; this repository only builds it.
