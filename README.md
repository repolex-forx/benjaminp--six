# Repolex Knowledge Graph of benjaminp/six

RDF knowledge graph data for [benjaminp/six](https://github.com/benjaminp/six), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download benjaminp/six
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ebd9b3af90247b8858d415a05e96e9ee61e48d07
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── ebd9b3af90247b8858d415a05e96e9ee61e48d07.nq.gz
│   └── repolex
│       └── ebd9b3af90247b8858d415a05e96e9ee61e48d07
│           └── chunk-001.nq.gz
├── blob
│   ├── 10ab03fd1d3c47f01339ebc191c426b2808423c3.nq.gz
│   ├── 1cc22a5aa7679ebaa10934212f356823931bdc3e.nq.gz
│   ├── 299040f348aba0f03dc29736daa9eff33220bfb7.nq.gz
│   ├── 3674bc956e44d8c40dfe557ab9f250240c7c216b.nq.gz
│   ├── 3d5990afb6ef08cd5f6c9fc946aaadb1d1ce7c07.nq.gz
│   ├── 3de5969b1ad3b973342e5e88ee1770fa7c798152.nq.gz
│   ├── 48e0a852a3744c34b58542f0977d9a3f12e20be1.nq.gz
│   ├── 643ced9f439fb59858f3167d38acc59132650cd4.nq.gz
│   ├── 660cf397936c4d04668786efd1a1ad5db9db2d34.nq.gz
│   ├── 8890c0e3e2654e78c7401817b05f691cb12e820f.nq.gz
│   ├── a1e34676267a1377bb5ad4b43a3f36a73d685962.nq.gz
│   ├── b6e3b12327c46e086779855acd17e55c4b5e6943.nq.gz
│   ├── b924e068eeeec0f2816bb0b2adb5340a6f7a36b7.nq.gz
│   ├── be72290ded35f1ad931782d7ff827125dcc483a5.nq.gz
│   ├── d4b534be53efbd69504f2f2e158917f5c7e45f05.nq.gz
│   └── eebafcd6d60f129cb5c626fb2e04d40f78e375da.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── ebd9b3af90247b8858d415a05e96e9ee61e48d07.nq.gz
├── filetree
│   └── ebd9b3af90247b8858d415a05e96e9ee61e48d07.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 26 files
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

## Source repository

[benjaminp/six](https://github.com/benjaminp/six)

---
*Parsed on 2026-09-17 by [repolex](https://repolex.ai)*
