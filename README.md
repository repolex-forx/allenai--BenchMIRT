# Repolex Knowledge Graph of allenai/BenchMIRT

RDF knowledge graph data for [allenai/BenchMIRT](https://github.com/allenai/BenchMIRT), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/BenchMIRT
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── faceefdbde352d7aeba7fb563c0b48b11879b570
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── faceefdbde352d7aeba7fb563c0b48b11879b570
│           └── chunk-001.nq.gz
├── blob
│   ├── 04cb984162bd11e00fb6bbff8427a92a75cd4aea.nq.gz
│   ├── 051dadf54b80f5fd260912829910e4754f3348a8.nq.gz
│   ├── 207dcc7d1a1200b0415a0fe8c7ce17bf60f841d8.nq.gz
│   ├── 227aa61d4b99172fec26221431bde004bc6c2977.nq.gz
│   ├── 22f9c44dc5b30b100568525e6f93f3b4dbda00a9.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2aff232521d5a34a5e8c6a9cacde1d34b329c2c4.nq.gz
│   ├── 2bbdb9d00a83a1ac12605aa995a038b9be436e28.nq.gz
│   ├── 2e81daa71a09a47f63adf291d369a8107bdc6d4a.nq.gz
│   ├── 3ae66bc2b764f281dc855fc0b9025489393c09bc.nq.gz
│   ├── ab6607ca8cf66c1c0382bc8c01cc4038de8a86a1.nq.gz
│   ├── bcda0ced761e4a33a07fbe902427dbd510cb39ec.nq.gz
│   ├── bd43a3f765cc77c529f070dbffa57074ba185dcb.nq.gz
│   ├── bf34e6fcc4cc1ba274e47631893cffefc44c699d.nq.gz
│   ├── c6abc15206dccd8c41d1e09487ac36250c8cc670.nq.gz
│   ├── e4e7e87e60cee8c50aeb62067f6a321524d17bde.nq.gz
│   └── fa393a8b9cd0b1608d202a180afb3192e46f511a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── faceefdbde352d7aeba7fb563c0b48b11879b570.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 23 files
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

[allenai/BenchMIRT](https://github.com/allenai/BenchMIRT)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
