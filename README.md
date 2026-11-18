# SynapCores Community Edition: releases

**SynapCores is a self-hosted AI database.** SQL tables, vector search, Cypher graph queries, in-database machine learning, agent memory and a built-in MCP server run in one engine on your own machine. The Community Edition is free, with no signup.

This repository hosts the public CE binaries and their SHA-256 checksums. → **[Latest release](https://github.com/SynapCores/synapcores-releases/releases/latest)**

## Install in one line

Linux (x86_64, aarch64) and macOS on Apple Silicon. On Windows, run it inside a WSL2 (Ubuntu) terminal.

```bash
curl -fsSL https://get.synapcores.com | SYNAPCORES_REF=github-releases sh
```

The installer detects your OS and architecture, verifies the checksum, installs the binary and a service (systemd on Linux, launchd on macOS), and downloads the local models. When it finishes it prints your local URL and first-boot login.

### Or with Docker (Linux and macOS)

```bash
docker run -d --name synapcores \
  -p 8080:8080 \
  -e AIDB_ACCEPT_LICENSE=1 \
  -v synapcores-data:/var/lib/synapcores \
  synapcores/community:latest

docker logs synapcores   # look for the FIRST-BOOT CREDENTIALS block
```

The same multi-arch image is mirrored at `ghcr.io/synapcores/community:latest`.

### Want to look before you install?

The **[Playground](https://synapcores.com/playground?utm_source=github&utm_medium=readme&utm_campaign=releases)** runs real SQL, Cypher and vector queries against a live SynapCores engine in your browser.

## What to try first

- **[Recipes](https://synapcores.com/recipes?utm_source=github&utm_medium=readme&utm_campaign=releases)**: copy-paste SQL for semantic search, fraud rings, anomaly detection, RAG with citations, agent memory and more.
- **[Build a RAG app in one database](https://synapcores.com/blog/build-a-rag-app-in-one-database?utm_source=github&utm_medium=readme&utm_campaign=releases)**: an end-to-end tutorial.
- **[Docs](https://docs.synapcores.com)**: SQL reference, REST API and setup guides.
- **MCP**: connect Claude, Cursor or any MCP client with [SynapCores/synapcores-mcp](https://github.com/SynapCores/synapcores-mcp).
- **LangChain**: [SynapCores/langchain-synapcores](https://github.com/SynapCores/langchain-synapcores).

## Downloading artifacts by hand

For air-gapped or locked-down hosts, every release lists the CE tarballs for each supported platform, each with a matching `.sha256` file. Check the checksum before you unpack:

```bash
shasum -a 256 -c synapcores-ce-<version>-<platform>.tar.gz.sha256
```

## License and source

The binaries are free to use under the SynapCores Community Edition end-user license (see `LICENSE` inside any release tarball, or [synapcores.com](https://synapcores.com)). SynapCores is proprietary software: the source code lives in a private repository and is not published here.

## Help and bug reports

Open an issue in this repository or email `support@synapcores.com`. Please include:

- the output of `synapcores --version`
- your OS, distro and kernel (or Docker version)
- steps to reproduce

Because the source isn't public, please describe what you saw rather than file paths or line numbers.
