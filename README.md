# Repolex Knowledge Graph of pre-commit/pre-commit-mirror-maker

RDF knowledge graph data for [pre-commit/pre-commit-mirror-maker](https://github.com/pre-commit/pre-commit-mirror-maker), parsed by [repolex](https://repolex.ai).

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
rlex download pre-commit/pre-commit-mirror-maker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b7a43f1c73e30f14f295e6d04fefb7ca581cd2d9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b7a43f1c73e30f14f295e6d04fefb7ca581cd2d9
│           └── chunk-001.nq.gz
├── blob
│   ├── 12eab86c1f9ac02ee5049ec560f7979975514bd0.nq.gz
│   ├── 1741053f5397693138ade469f1ee8b471a0a5816.nq.gz
│   ├── 1dcdfec974686f4d4b6ef356e4b53d7ad9006fe4.nq.gz
│   ├── 20f05b42997292bd8b4bf6db07840c7c9c8cc154.nq.gz
│   ├── 22ef1def97c44fe96a24cc98654033fa42da700a.nq.gz
│   ├── 367b0cef9c8ccdf3fdd0a983f2e4485fabd69b91.nq.gz
│   ├── 36c90edf2a58461f83d89b7963517562d2894493.nq.gz
│   ├── 3d93aefb2da505dba9c0114404cfaaeee5ad0d3f.nq.gz
│   ├── 3dfeffafb0ffd713c56bbf4f07ffc6fc9b33eeb4.nq.gz
│   ├── 568da609f6d2fabfbd93b87a18fe6f17a338b470.nq.gz
│   ├── 56f9786db291a966055a468682dafd11a84ec686.nq.gz
│   ├── 5a27f23209683d516aeb94019a9a73d7b75fded6.nq.gz
│   ├── 5fd6892cf9dba9d920595d4c65cd7efc86160552.nq.gz
│   ├── 65f0c6af5ee83199e4daa904c2fc0bb43a3d76a0.nq.gz
│   ├── 6a581d61107450a11a858edb40a654fcf8a19afb.nq.gz
│   ├── 72e8ffc0db8aad71a934dd11e5968bd5109e54b4.nq.gz
│   ├── 804b4cbd84bc868bb3e4c5eafd9749ce18466ec0.nq.gz
│   ├── 96035aadb46d9c558a3ac81f9d5faa661af309df.nq.gz
│   ├── 96cf1f799715f613185772c83b18fa9b3a6bd47b.nq.gz
│   ├── c270039cecde179d74949f9e0d4e2b169a5ad342.nq.gz
│   ├── d282b6c1ecc7facc07561ee4762aa5445489c8e0.nq.gz
│   ├── d319a107133d57b6168db4cf9c9d67a460309f3e.nq.gz
│   ├── d86d9ea06347dbd79c04079484155ea94fa2c3ed.nq.gz
│   ├── da11a08d29878d49e39117a30bb5d6bb6c1fbd49.nq.gz
│   ├── e311fbb2ef75607cc5c2b5ca9822155e193c0a48.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b7a43f1c73e30f14f295e6d04fefb7ca581cd2d9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[pre-commit/pre-commit-mirror-maker](https://github.com/pre-commit/pre-commit-mirror-maker)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
