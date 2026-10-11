# Repolex Knowledge Graph of samuelcolvin/pull_pull_request

RDF knowledge graph data for [samuelcolvin/pull_pull_request](https://github.com/samuelcolvin/pull_pull_request), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/pull_pull_request
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 74df6a76a35a6a0c4853682164ec31818eb988d1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 74df6a76a35a6a0c4853682164ec31818eb988d1
│           └── chunk-001.nq.gz
├── blob
│   ├── 0640d980e43d12671ba77655a874b3e202a39a82.nq.gz
│   ├── 0a9708acb42940d431af21267cd7c8b2e4e02fd4.nq.gz
│   ├── 0c75cfdf99c065455104b1029282c42335130771.nq.gz
│   ├── 24ee5b1be9961e38a503c8e764b7385dbb6ba124.nq.gz
│   ├── 509fca7168a73e83192d027e185e829a2bca5af3.nq.gz
│   ├── 5b710ae148ceec5633ae092cab2c81e25d3c261a.nq.gz
│   ├── 5c511c75cc485d6f3d9e6ad031561f25fe731db9.nq.gz
│   ├── 8126b3c7edae59f27eeee735c7fdcca5cc3ad997.nq.gz
│   ├── bf110f1102e35a9647413c032adedace0ff31f58.nq.gz
│   └── c6fc301e8adcf33c7d9c5ad574a57befb5a93807.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 74df6a76a35a6a0c4853682164ec31818eb988d1.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
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

[samuelcolvin/pull_pull_request](https://github.com/samuelcolvin/pull_pull_request)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
