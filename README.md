# Repolex Knowledge Graph of tox-dev/azure-pipelines-template

RDF knowledge graph data for [tox-dev/azure-pipelines-template](https://github.com/tox-dev/azure-pipelines-template), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/azure-pipelines-template
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c231fdfb68d4f3d7ca09be0d72db1a56a1c46767
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c231fdfb68d4f3d7ca09be0d72db1a56a1c46767
│           └── chunk-001.nq.gz
├── blob
│   ├── 04c3665ae72412830a1678f4db85261738ac83f7.nq.gz
│   ├── 3ac92972bc3c89cc03558cec13ca9dafcb9789b2.nq.gz
│   ├── 51a4e25fbaa564ca095ea817ac71058659d4c615.nq.gz
│   ├── 5a70286778a43d231f9675e88c0992c1ba4d61ad.nq.gz
│   ├── 7cb8162d4b086d32b9335b6d9848355c8cd278bd.nq.gz
│   ├── 870bc36bea2120508bc29fe57e1cf0a050cc5c8a.nq.gz
│   ├── 9a0fe9dba5ca4fe2184fb436243ba7961f0a6174.nq.gz
│   └── db9d9a49ff55f59f3c20c9f8d1e881490d3a94ce.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c231fdfb68d4f3d7ca09be0d72db1a56a1c46767.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 16 files
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

[tox-dev/azure-pipelines-template](https://github.com/tox-dev/azure-pipelines-template)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
