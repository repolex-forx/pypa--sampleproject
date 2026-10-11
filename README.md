# Repolex Knowledge Graph of pypa/sampleproject

RDF knowledge graph data for [pypa/sampleproject](https://github.com/pypa/sampleproject), parsed by [repolex](https://repolex.ai).

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
rlex download pypa/sampleproject
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 621e4974ca25ce531773def586ba3ed8e736b3fc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 621e4974ca25ce531773def586ba3ed8e736b3fc
│           └── chunk-001.nq.gz
├── blob
│   ├── 4eef093a5f541b72cba0f895f6872d9f52be98e8.nq.gz
│   ├── 5bde2fcd3182b2dc804f1c15bf7c8abf2ea9836c.nq.gz
│   ├── 64d0c4ffa5627c4c8ce4fbdda7bf971790760fed.nq.gz
│   ├── 7c0646bfd53c1f0ed45ffd81563f30017717ca58.nq.gz
│   ├── b7a0ee3a65de8d46c15df764b83505d2f9b6ff4e.nq.gz
│   ├── c74aceda037b84c08858a7d653a956e65355fa6a.nq.gz
│   ├── c8f10649946fda329ad70975b0c82629bfcb5859.nq.gz
│   ├── c929f885b60a11bfc703f7b358bb2b1dc7d10253.nq.gz
│   ├── d2ec8f7070d4f6d70b6551683e101422faf086ca.nq.gz
│   ├── d6c10ebb3006b55da0222d37658dba0788a34b76.nq.gz
│   ├── d97bdabb1f6e04b59bf75e1c513ee26eaa00b7f2.nq.gz
│   └── ddc2bd1192b160b38fb18b68805512014ef738f3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 621e4974ca25ce531773def586ba3ed8e736b3fc.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[pypa/sampleproject](https://github.com/pypa/sampleproject)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
