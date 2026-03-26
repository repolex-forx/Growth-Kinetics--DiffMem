# Repolex Knowledge Graph of Growth-Kinetics/DiffMem

RDF knowledge graph data for [Growth-Kinetics/DiffMem](https://github.com/Growth-Kinetics/DiffMem), parsed by [repolex](https://repolex.ai).

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
lexq download Growth-Kinetics/DiffMem
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── blob
│   ├── 077e67eb7af1e6956d0dbeac997cc22a9a1599b5.nq.gz
│   ├── 09e30e3baa733dca632d90d7c5d6bd7ec38f6a27.nq.gz
│   ├── 107759eeea5b2f88e6ce81f9263ba275cacf52ba.nq.gz
│   ├── 13bdb893e594ceb6ac077934b5bcea9011ff20e3.nq.gz
│   ├── 18212cc418dd4935782a14e6c22eff847bec05c4.nq.gz
│   ├── 1a215c2da0ae2eacb9189d18f26e0c1d526008ca.nq.gz
│   ├── 24b0f5e4598d6135127beeea5921970d3643ea95.nq.gz
│   ├── 2555c59a608848a0f68a14068ebe29c122feb1a7.nq.gz
│   ├── 259113c402b1459b334b2650dc6e1689293a1378.nq.gz
│   ├── 25d567f656879316f2b3e3b579ad3c1a8f665525.nq.gz
│   ├── 25f64d35d9d457fcee221fb11015cf582bc236e1.nq.gz
│   ├── 35196752af96b11c7f6b3fa77a94ccbc8b1b13cc.nq.gz
│   ├── 38d9da6fa17124e0927c5b9699192c6073815321.nq.gz
│   ├── 41d2d1d78e1bc530c33b7b931b8ae18e8e60d9bd.nq.gz
│   ├── 43c519f5663e9c918c20427f5219ae7af31fdf43.nq.gz
│   ├── 5223885d315419b0094af3c91ada154aa81eebe1.nq.gz
│   ├── 52e2a4155f6a3089a2a0b866c332be54822c39fe.nq.gz
│   ├── 5f26c48b2b97a40f141b04b5cbdcb9bfa06d2685.nq.gz
│   ├── 6159640eebf81743a850fd9e56d287f2046f2675.nq.gz
│   ├── 65f4cc78d9885160c2df1157bc7a808bb2b1a58f.nq.gz
│   ├── 7472d3dec5e0d7d25be68619f5edb0648ca810bc.nq.gz
│   ├── 75ec364656330985ce0b261e2fbfedba44f5b133.nq.gz
│   ├── 7aeef8d7e21042240ebbc5a6407c68906bce2a0e.nq.gz
│   ├── 8747be35e9eda329897f61ecf625b5d5d0d0b113.nq.gz
│   ├── 9262798fe7c2e003a45210b9ee01a58c37dde117.nq.gz
│   ├── 9eeb2d66befa8c52674741297739e7664bc8c710.nq.gz
│   ├── 9f276ca7dbb8db5fd5b43c1b4b8978dfafdf9c3f.nq.gz
│   ├── a49ced1dc612b9b91736c46d82d13dace96be159.nq.gz
│   ├── a6c8cee9de06cf47f39cc49f85d418de3a5c9d1c.nq.gz
│   ├── b3a0105c69cbe84fe8551b7aaae5dacccb183829.nq.gz
│   ├── bb72dce6858ba329be436a58dcf4a3a52d37be7b.nq.gz
│   ├── c4073a75b4fa85c0b30776bffbf4b433c0be2c7c.nq.gz
│   ├── e1de2e66159f772b1ca0538b6ed5321d88a31063.nq.gz
│   ├── e337983ea982c923a69b94599a0a54cd1b442cde.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ecebb52cc02c770b2428a0b94876a4a7150905d3.nq.gz
│   ├── edc784ce86218bc0a1772f85720f48cdfc8bea3e.nq.gz
│   ├── f02a3aa64bd278c3dfa1478c869ecb6e38925bb6.nq.gz
│   ├── f5acd57f95a94aa5147d5a95bad2d828a9a800c0.nq.gz
│   └── fe07880fa5f9c11d4e02cc5d1ff426fa97284a83.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8c1ef82af6fee8bf0e2d850095876efbdd7dfecf.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

8 directories, 46 files
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

[Growth-Kinetics/DiffMem](https://github.com/Growth-Kinetics/DiffMem)

---
*Parsed on 2026-03-26 by [repolex](https://repolex.ai)*
