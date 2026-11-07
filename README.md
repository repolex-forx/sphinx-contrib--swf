# Repolex Knowledge Graph of sphinx-contrib/swf

RDF knowledge graph data for [sphinx-contrib/swf](https://github.com/sphinx-contrib/swf), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/swf
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f4a83901a6dab5ca2d5828038d7886ac4e153615
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f4a83901a6dab5ca2d5828038d7886ac4e153615
│           └── chunk-001.nq.gz
├── blob
│   ├── 058514c310f6a8ff0d7d887bd28633cd0a35646b.nq.gz
│   ├── 17ef86bd5703ecc9d1ffd1e3393b7a2bf8943738.nq.gz
│   ├── 2c449488fdfd52637d17b214106d9425e90b1d9a.nq.gz
│   ├── 467e797128f546254f152760d8deff0fc4434ae3.nq.gz
│   ├── 58de9b32b6c9f9c6fc948b769a70576affca09a4.nq.gz
│   ├── 67ed51b72b733d87147c4d000fe89ba19ce8c86e.nq.gz
│   ├── 7fbe34736290ea72f797e70818ca88b9dac421d7.nq.gz
│   ├── 82f3f8078d33378e85c18eb23e3b41a94d54cded.nq.gz
│   ├── 860f5bf6422848c6ea88c44a26ec0b52a4d99c99.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── bfb9f4b5e992f8af7ca8153e93dab5c67e47976f.nq.gz
│   ├── cf165b2789d88b483a0c1a1420bcd80d6cfd1e43.nq.gz
│   └── ecc1f438fcb8eaf3032c794677902764d3be994b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f4a83901a6dab5ca2d5828038d7886ac4e153615.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 20 files
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

[sphinx-contrib/swf](https://github.com/sphinx-contrib/swf)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
