# synapcores-releases

This repository exists for one reason: **to host the public release
artifacts of [SynapCores Community Edition](https://synapcores.com)**.

The SynapCores source code is **not** in this repository. Source lives
in a private repository owned by SynapCores and is not publicly
distributed.

## Where to find the binaries

The [Releases page](https://github.com/SynapCores/synapcores-releases/releases)
holds the signed CE binary tarballs (linux-x86\_64, linux-aarch64,
darwin-x86\_64, darwin-aarch64) and matching SHA-256 checksums for every
tagged release.

You should not need to download artifacts from this repo by hand. The
official one-line installer at
[`get.synapcores.com`](https://get.synapcores.com) handles platform
detection, version resolution, checksum verification, and installation
for you:

```bash
curl -fsSL https://get.synapcores.com/install.sh | sh
```

## Why a separate repo?

SynapCores is **proprietary software**. Source-code distribution is not
part of the Community Edition license. To make CE binaries publicly
downloadable without exposing source, the release pipeline in the
private source repository pushes signed artifacts to **this** public
repo's Releases section. That is the only thing this repository is
used for.

## License

The binaries published here are licensed under the SynapCores Community
Edition end-user license. See `LICENSE` inside any release tarball, or
the SynapCores website for the canonical terms.

## Reporting bugs

File issues at the public issue tracker that ships with each release
(announced on the [SynapCores docs site](https://docs.synapcores.com))
or email `support@synapcores.com`. Please include:

- Output of `synapcores --version`
- Your OS / distro / kernel
- Steps to reproduce

Source-level bug reports (file paths, line numbers) are not actionable
because the source is not published; please describe the user-visible
behavior instead.
