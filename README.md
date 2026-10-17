# Repolex Knowledge Graph of colcon/colcon-test-result

RDF knowledge graph data for [colcon/colcon-test-result](https://github.com/colcon/colcon-test-result), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-test-result
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ccccca0ea6f1d1117116e3402591eb05c58b3235
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ccccca0ea6f1d1117116e3402591eb05c58b3235
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f17157ed42b486a0c57cbffddd97987a4844e6b.nq.gz
│   ├── 2331215dccebf14c56a48580384c9d54ea659ef5.nq.gz
│   ├── 740fbc8f55cf532baafbab91cabd3cf82d0e58a7.nq.gz
│   ├── 79043d402078515931a2b39c9f507da37a4836b7.nq.gz
│   ├── 7c4537c0ebb05023d42fa1d528c8c2faab7b409b.nq.gz
│   ├── 9765445ceddda04f3ee1fc0b6cc286e059c72348.nq.gz
│   ├── b49f5e0872ed3e29806c21346ae1d3f1a8b9a032.nq.gz
│   ├── b99e0016a12a1c3687d52ee4e9dd671219833dde.nq.gz
│   ├── bd7c8693b373f16474a10254e75b502ef8389f27.nq.gz
│   ├── c1606e732743be12b1938fb73f4048117b3829a0.nq.gz
│   ├── ce5858ba930264d30613d30f006b080fc9314d5c.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── df9235b1372b4e607b019df420de04219f83f6da.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e82fd0b0abbf1472480d19d468efe7819276e80d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ccccca0ea6f1d1117116e3402591eb05c58b3235.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[colcon/colcon-test-result](https://github.com/colcon/colcon-test-result)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
