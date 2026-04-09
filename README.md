# Repolex Knowledge Graph of requests/httpbin

RDF knowledge graph data for [requests/httpbin](https://github.com/requests/httpbin), parsed by [repolex](https://repolex.ai).

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
lexq download requests/httpbin
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2607b7e6c78bab21f9791331bdde15c583521c90
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 2607b7e6c78bab21f9791331bdde15c583521c90.nq.gz
│   └── repolex
│       └── 2607b7e6c78bab21f9791331bdde15c583521c90
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e8e71598580d71709e95b0ca6b1bef16fc0ad9d.nq.gz
│   ├── 18fe967ec7fde547efb5c8570d6a94dbf59b14c5.nq.gz
│   ├── 1983c068f331b930d0977645307a82dd65775623.nq.gz
│   ├── 1a6ec6f27f34bcb38840c0d16a3c49e4d323709e.nq.gz
│   ├── 2a9acf13daa95e85642ea255d3e3bd1ef8252804.nq.gz
│   ├── 34049e5eecedce8fce2f80d19fe4494c77fedb31.nq.gz
│   ├── 35abff6fb597ee4762f6200b4370914ba63cc105.nq.gz
│   ├── 37f5392d54cea2bda1c4bb97a5cd31f5ad93ad10.nq.gz
│   ├── 38fdef3f85f158484928e4306182387da868b5a9.nq.gz
│   ├── 44da70f04a2b82ffa7471411e4315248a913d06d.nq.gz
│   ├── 4595401b50252633c24558f799cfe50bfeac19e4.nq.gz
│   ├── 5ff09579e3842100aad840366b3a3031b05bef62.nq.gz
│   ├── 63308a83d95b1ea56b5514cdb77186c6fc03ad2e.nq.gz
│   ├── 63e0d2b9567890ab9b8131407bc62eda50282fa3.nq.gz
│   ├── 66a2ed64a6f39dfaa41c28034df63a7f841e8d8d.nq.gz
│   ├── 6e2e0591b33b8ebdb87c7a8eabb0d50ee35ad177.nq.gz
│   ├── 726dd626b0ba6e1d947b702a91f075b0bfa52fa4.nq.gz
│   ├── 7f9956bd392bbe5b71c6d35d3a32d414d60f480d.nq.gz
│   ├── 885f52d8de8220b4aa0430061054cd2230611656.nq.gz
│   ├── 9ec972405676f9d77d05b0abe4386107987823e3.nq.gz
│   ├── a4e824c247f97b4f524b885a358c0d0008e4e161.nq.gz
│   ├── c6268b6adea2a6192d4ea330b3af8a5b5043ced5.nq.gz
│   ├── cc0c128257cace9da1d84bb92bbcc4f3a7ed9257.nq.gz
│   ├── d46082e89db3007befae4518964644e40e013018.nq.gz
│   ├── e4b7e589a0e2e96626a14cdbdc990731fe75ec40.nq.gz
│   ├── ec156a9568f5b3b99ebc860ea55077fe639f91ba.nq.gz
│   └── f890b2471ec3f2d20b802abe7fc1d49bddb8cba1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 2607b7e6c78bab21f9791331bdde15c583521c90.nq.gz
├── filetree
│   └── 2607b7e6c78bab21f9791331bdde15c583521c90.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 37 files
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

[requests/httpbin](https://github.com/requests/httpbin)

---
*Parsed on 2026-04-09 by [repolex](https://repolex.ai)*
