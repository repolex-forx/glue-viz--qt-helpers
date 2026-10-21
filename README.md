# Repolex Knowledge Graph of glue-viz/qt-helpers

RDF knowledge graph data for [glue-viz/qt-helpers](https://github.com/glue-viz/qt-helpers), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/qt-helpers
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b437b2e79a2914042cebad6d6be1028d90648f82
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b437b2e79a2914042cebad6d6be1028d90648f82
│           └── chunk-001.nq.gz
├── blob
│   ├── 46ec9c12e025df8a68ce4adba70ea5504358b121.nq.gz
│   ├── 57b02751e8e691f275c58fc85c28bd7a156b2114.nq.gz
│   ├── 58fae332a687fc93c77ffffad1b4d85357beffba.nq.gz
│   ├── 59a279204b6af3951a79b656d3edb4ae71b935b8.nq.gz
│   ├── 96398ccc840a9c6040bf1df1f57e46dffb638f01.nq.gz
│   ├── 9ed85f15bc4d0c0f014fb1b984c6e1122e820a9a.nq.gz
│   ├── ba74660506d90c514ee1d32bf4eb5ecb0af14075.nq.gz
│   ├── bfc2d53adf8411fcedbcf4beb09c41e5cd5d200c.nq.gz
│   ├── c3c8186d4d73f990645a1a23a9914f117b7b43a3.nq.gz
│   ├── c61018014bf81f3bd1b96e4fe3eaa94e2736b082.nq.gz
│   └── d3541bed21f093456de4a770b0fbaa2ed0101c4a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b437b2e79a2914042cebad6d6be1028d90648f82.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[glue-viz/qt-helpers](https://github.com/glue-viz/qt-helpers)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
