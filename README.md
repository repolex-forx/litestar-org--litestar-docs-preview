# Repolex Knowledge Graph of litestar-org/litestar-docs-preview

RDF knowledge graph data for [litestar-org/litestar-docs-preview](https://github.com/litestar-org/litestar-docs-preview), parsed by [repolex](https://repolex.ai).

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
rlex download litestar-org/litestar-docs-preview
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fe3e255ba405e7f4aad6021d2fcb2498a9f65e25
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fe3e255ba405e7f4aad6021d2fcb2498a9f65e25
│           └── chunk-001.nq.gz
├── blob
│   ├── 63dbb0ffb8198cd62b4250f6ea22e8544fe26d53.nq.gz
│   ├── 68bc17f9ff2104a9d7b6777058bb4c343ca72609.nq.gz
│   ├── bbbe1a2e09f6b55f2e814c14a7f496a5fe4944bf.nq.gz
│   ├── c5ba3b7ec0be0ed3f0ee09b5364ece3b20321bd3.nq.gz
│   └── fe8eadb8b73ebd79d4019f1f614215d68f1c8f81.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fe3e255ba405e7f4aad6021d2fcb2498a9f65e25.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 13 files
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

[litestar-org/litestar-docs-preview](https://github.com/litestar-org/litestar-docs-preview)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
