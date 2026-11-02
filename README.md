# Repolex Knowledge Graph of zopefoundation/MultiMapping

RDF knowledge graph data for [zopefoundation/MultiMapping](https://github.com/zopefoundation/MultiMapping), parsed by [repolex](https://repolex.ai).

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
rlex download zopefoundation/MultiMapping
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9f92fade6658c5fecb3b80a6ef1b02d6ec446b23
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9f92fade6658c5fecb3b80a6ef1b02d6ec446b23
│           └── chunk-001.nq.gz
├── blob
│   ├── 188120b692cc972bed5f7063baaa7ebd9dd5fcea.nq.gz
│   ├── 207fbd16c0e1663349846c7528f1e72694554392.nq.gz
│   ├── 354ba03b9d562fe2185f50ce4954d38b5ab5b105.nq.gz
│   ├── 5578473625108fe8463e6ef678fafa484eabc02d.nq.gz
│   ├── 59a266a4a6721a02dba7591e59cc0e0a068ea1b1.nq.gz
│   ├── 75eb89ff13f9341c62cf248063755a1ea7f1f26c.nq.gz
│   ├── 79859e06010bf4967c5b4b044afea6ef39742938.nq.gz
│   ├── 7c88981e70016fa6fd2b97ea76f5378feef28d96.nq.gz
│   ├── 841db889d566fdf6c126334c1a02d84782d975b0.nq.gz
│   ├── 8a1cde635fcfe005cc4438d504940505395236a7.nq.gz
│   ├── a3df1ed2dc539d0590216374fb1488de65c3ecc6.nq.gz
│   ├── b3e09256097acee1f344272bb8b6151789d4e070.nq.gz
│   ├── ca517f4eb0cec1c691c0c2b54cd5eb85e906f11b.nq.gz
│   ├── d9eb3230aa0cdf123bde69e6cc8e7d791574890a.nq.gz
│   ├── e1f9ad7b3b48377bfbfaa1b380c384ddea24060f.nq.gz
│   ├── e4b867329e05886a4818f86b117fca2102bc84bf.nq.gz
│   ├── e5a05b0b3a40889c4f797b786ebc8de931f2fff8.nq.gz
│   ├── f7d8f8387cc5cf9ad226e72d4661b47dbddd160c.nq.gz
│   └── fd46227c9191e99fff40e24d02b90ba866d11262.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9f92fade6658c5fecb3b80a6ef1b02d6ec446b23.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 26 files
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

[zopefoundation/MultiMapping](https://github.com/zopefoundation/MultiMapping)

---
*Parsed on 2026-11-02 by [repolex](https://repolex.ai)*
