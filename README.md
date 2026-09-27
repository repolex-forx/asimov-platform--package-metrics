# Repolex Knowledge Graph of asimov-platform/package-metrics

RDF knowledge graph data for [asimov-platform/package-metrics](https://github.com/asimov-platform/package-metrics), parsed by [repolex](https://repolex.ai).

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
rlex download asimov-platform/package-metrics
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fbbb5b10f928ec42f77664bc74eaf139a5c08ec3
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── fbbb5b10f928ec42f77664bc74eaf139a5c08ec3.nq.gz
│   └── repolex
│       └── fbbb5b10f928ec42f77664bc74eaf139a5c08ec3
│           └── chunk-001.nq.gz
├── blob
│   ├── 7ceacdd57cf2bc01059ed9e159c0961b3fead361.nq.gz
│   ├── 80d98c7fabf6b4ea6d32f1a61fd25f37a27478f2.nq.gz
│   ├── 83605f79ea14b94f97900abade872c4193db9757.nq.gz
│   ├── 859bf60858ff11bba9bd696844720540cc8a8580.nq.gz
│   ├── b266d64dbe239a50062ca89c4eacfaec23d7bf01.nq.gz
│   └── fdddb29aa445bf3d6a5d843d6dd77e10a9f99657.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── fbbb5b10f928ec42f77664bc74eaf139a5c08ec3.nq.gz
├── filetree
│   └── fbbb5b10f928ec42f77664bc74eaf139a5c08ec3.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 15 files
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

[asimov-platform/package-metrics](https://github.com/asimov-platform/package-metrics)

---
*Parsed on 2026-09-27 by [repolex](https://repolex.ai)*
