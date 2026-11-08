# Repolex Knowledge Graph of canonical/accountsservice-snap

RDF knowledge graph data for [canonical/accountsservice-snap](https://github.com/canonical/accountsservice-snap), parsed by [repolex](https://repolex.ai).

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
rlex download canonical/accountsservice-snap
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 333550cf5186158a2a921bda9e6a0ed410cd41ff
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 333550cf5186158a2a921bda9e6a0ed410cd41ff
│           └── chunk-001.nq.gz
├── blob
│   ├── 04927f1ab6d34da4516e40d9fc55593c41ca8a92.nq.gz
│   ├── 2c499bfdca780f4da5fd8d810e9de09342e6c438.nq.gz
│   ├── 48a54a902798669a1caec6c650d2c23d421e28ae.nq.gz
│   ├── 573ed8b878d49b2efae686811fb8febb5c5de240.nq.gz
│   ├── 74459836dfd01fcf9f441c6b3c55ea963105d9fc.nq.gz
│   └── dbb9ba3abb07bf44ff6add545c4c8a9724791088.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 333550cf5186158a2a921bda9e6a0ed410cd41ff.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 13 files
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

[canonical/accountsservice-snap](https://github.com/canonical/accountsservice-snap)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
