# Repolex Knowledge Graph of acornjs/acorn-jsx

RDF knowledge graph data for [acornjs/acorn-jsx](https://github.com/acornjs/acorn-jsx), parsed by [repolex](https://repolex.ai).

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
rlex download acornjs/acorn-jsx
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 52a64313bb95aba5fbfddd1b0256aa0fce229bb2
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 52a64313bb95aba5fbfddd1b0256aa0fce229bb2.nq.gz
│   └── repolex
│       └── 52a64313bb95aba5fbfddd1b0256aa0fce229bb2
│           └── chunk-001.nq.gz
├── blob
│   ├── 004e0809024006335916314d605090629b73575f.nq.gz
│   ├── 2c630f15ac2d921b1eb1ad54bcea43a93a8b6238.nq.gz
│   ├── 317c3ac4a5534ecda2c0087e7de1fa883b9ccc8f.nq.gz
│   ├── 3e152c1697bb12089fe6dfd4bed3c7cdd930eb30.nq.gz
│   ├── 695d4b93082bee2494e7a1519c3b6b88b33a1568.nq.gz
│   ├── 9ff0fa3990cbcdffc922eda5abfaba8ed63d9588.nq.gz
│   ├── a876081a8286b3b9e70eff92fab826cf6ede76ac.nq.gz
│   ├── b53549d6fd5633c4ab5936cf551b215b14428255.nq.gz
│   ├── b9d98bfe0430efba270766e3e8d1e8897a782755.nq.gz
│   ├── c14d5c67b407d8d183bb2aec0f99de5e0b6e8994.nq.gz
│   ├── c1520092f8e31ed589d21605ede2ebd27386b218.nq.gz
│   ├── d50251241e7bac3d4dd3b9ad2aec7e9349179edd.nq.gz
│   ├── f42a7ea1437c8c2cda5af55dd1cf07186935c515.nq.gz
│   └── fcadb2cf97913f58a2523f535336e725c6b59d1f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 52a64313bb95aba5fbfddd1b0256aa0fce229bb2.nq.gz
├── filetree
│   └── 52a64313bb95aba5fbfddd1b0256aa0fce229bb2.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 24 files
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

[acornjs/acorn-jsx](https://github.com/acornjs/acorn-jsx)

---
*Parsed on 2026-09-28 by [repolex](https://repolex.ai)*
