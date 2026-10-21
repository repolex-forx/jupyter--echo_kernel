# Repolex Knowledge Graph of jupyter/echo_kernel

RDF knowledge graph data for [jupyter/echo_kernel](https://github.com/jupyter/echo_kernel), parsed by [repolex](https://repolex.ai).

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
rlex download jupyter/echo_kernel
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ad2ff4f47e9c9ef6b63c440ed5f8739a19b8ad12
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ad2ff4f47e9c9ef6b63c440ed5f8739a19b8ad12
│           └── chunk-001.nq.gz
├── blob
│   ├── 0dc89813dc10ed07777226c26d348a19ce3afb93.nq.gz
│   ├── 1b965c740fa596e7f39edb75a0b61cd7a96e5891.nq.gz
│   ├── 4a69984aa598274ef5cc6c920cee859da2d16c4e.nq.gz
│   ├── 616f2fc5fbeeb5debed1973e7725d6a096d7a4d8.nq.gz
│   ├── 725feab5ce652dc39f3f2c77b9fd3c90bf049c65.nq.gz
│   ├── 8d39ac55ca8c40e3942010610079b9564f16ecf3.nq.gz
│   ├── a488ec66da4575ebdbbfd3bc2aeee7592e64385f.nq.gz
│   ├── a83018a0c77a7d3bb41f8bcf153262bb7824fe2e.nq.gz
│   ├── f0bcb612743bfcb508aafcb36853a89d0d103873.nq.gz
│   ├── f29841a02dd44e1b008c8e7f9af10eafc87b0f27.nq.gz
│   ├── f7c3a78262a67fd84d9a1f68a63bd07c5d5fcb64.nq.gz
│   └── fe50edf02a94883be4d2769bb395b1eb42caeecf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ad2ff4f47e9c9ef6b63c440ed5f8739a19b8ad12.nq.gz
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

[jupyter/echo_kernel](https://github.com/jupyter/echo_kernel)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
