# Repolex Knowledge Graph of simonw/ollama-models-atom-feed

RDF knowledge graph data for [simonw/ollama-models-atom-feed](https://github.com/simonw/ollama-models-atom-feed), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/ollama-models-atom-feed
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8b77d32addb923f65829aee54f325f48ded6c1eb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8b77d32addb923f65829aee54f325f48ded6c1eb
│           └── chunk-001.nq.gz
├── blob
│   ├── 685923752feb45df584920680eaea8ee185a527b.nq.gz
│   ├── 83928a34f2b96c08484eb1611e3d554548237d51.nq.gz
│   ├── d23ff1c363ee52c04adc317556df9699d7d24b1d.nq.gz
│   ├── dd005392c35cd12a4cc932101077049b3a821517.nq.gz
│   └── fb465646f488a6c4fcf720072f31f486783f2d32.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8b77d32addb923f65829aee54f325f48ded6c1eb.nq.gz
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

[simonw/ollama-models-atom-feed](https://github.com/simonw/ollama-models-atom-feed)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
