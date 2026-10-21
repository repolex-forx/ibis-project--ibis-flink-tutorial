# Repolex Knowledge Graph of ibis-project/ibis-flink-tutorial

RDF knowledge graph data for [ibis-project/ibis-flink-tutorial](https://github.com/ibis-project/ibis-flink-tutorial), parsed by [repolex](https://repolex.ai).

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
rlex download ibis-project/ibis-flink-tutorial
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 08cfeef6daf18922b9b3a876db1cdbb1d339978b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 08cfeef6daf18922b9b3a876db1cdbb1d339978b
│           └── chunk-001.nq.gz
├── blob
│   ├── 2c75c428a7e2f93f54dc7bbe167147dabd38cd75.nq.gz
│   ├── 903209b9dfb1ead2d16af2c39605afe3af03ca72.nq.gz
│   ├── 9e2ff02105f3c741b00bafe2e27adb5983b2f2eb.nq.gz
│   ├── b14d4b2760fe2ef5ad167d3cac3af217ab95e2f6.nq.gz
│   ├── ccf09a7c4651293940434b0735058f083ef1c2d1.nq.gz
│   ├── d969c3def12e72fe799bf80d9a46fb3898c99217.nq.gz
│   └── f5477dedc29ecb99ffb12f804aba1f0d29d3f5f7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 08cfeef6daf18922b9b3a876db1cdbb1d339978b.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 14 files
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

[ibis-project/ibis-flink-tutorial](https://github.com/ibis-project/ibis-flink-tutorial)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
