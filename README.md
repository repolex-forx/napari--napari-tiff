# Repolex Knowledge Graph of napari/napari-tiff

RDF knowledge graph data for [napari/napari-tiff](https://github.com/napari/napari-tiff), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download napari/napari-tiff
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3223b3ba2a8ea0927700b8d1f9f32bc32656f56b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3223b3ba2a8ea0927700b8d1f9f32bc32656f56b
│           └── chunk-001.nq.gz
├── blob
│   ├── 04393845e8d1e82a27ee78576655c13ad99a9c1b.nq.gz
│   ├── 08593628b97c6aeb567660c32f87cb6b258b7138.nq.gz
│   ├── 1df263587a05c4dc4e7811df4e1682e537245ea9.nq.gz
│   ├── 1e9e8de913cc575a085ae3832e9c6a7a433aa20d.nq.gz
│   ├── 210cc7c3c5257569d470f2374fffd40e94c9000e.nq.gz
│   ├── 23a8a85617d862ab4d58b9fdeb44a54aadc07389.nq.gz
│   ├── 2cff8cf0546260993a87fd693f50b429447f2ce3.nq.gz
│   ├── 37c8a4300c3fe50ac37b66b7c3d91e74e835faa6.nq.gz
│   ├── 3e2d1f2159eb7a2e953fa7ce1736df7372be11d6.nq.gz
│   ├── 522b05bd4e68858881fcafa28d40502318d59170.nq.gz
│   ├── 5538d0499e777488dd877d11015db6a78136a824.nq.gz
│   ├── 5ea995230d42b58502f3896ffb1514246fc8388f.nq.gz
│   ├── 60de246d68c4fb2c416967abc5a2880ac166fb8b.nq.gz
│   ├── 6dd4e72d2ac16e2cc0ecd1b2a92a25118ea53b8d.nq.gz
│   ├── 7a0baf7327fb58f882b77b4c736910747f1f40ba.nq.gz
│   ├── 83997fb450465a87de49d7240f51ff5ddf74e343.nq.gz
│   ├── 8e71290080bc6847d6f6b1e3b7302caae233ee06.nq.gz
│   ├── 90af58aea68b2681be5e2b7e4a6b1b2af6bcf2cd.nq.gz
│   ├── 9a39d7c58d9a9ae532551d26e230aa1d15afe8e2.nq.gz
│   ├── aa1f0b9eb32c5c1b9022f7eb64513abc86b58bf4.nq.gz
│   ├── b7510cec76cda5810dac4e26830edeeac2eb730b.nq.gz
│   ├── c0ecf4d6587991ba6ad7f2145eb5aaba7c0ef272.nq.gz
│   ├── c6e2070edbbec10ef4661366763f349ea733c622.nq.gz
│   └── ca44497dfc342e94e559eee2c2eeb5922a7328c5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3223b3ba2a8ea0927700b8d1f9f32bc32656f56b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[napari/napari-tiff](https://github.com/napari/napari-tiff)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
