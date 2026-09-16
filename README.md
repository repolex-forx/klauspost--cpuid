# Repolex Knowledge Graph of klauspost/cpuid

RDF knowledge graph data for [klauspost/cpuid](https://github.com/klauspost/cpuid), parsed by [repolex](https://repolex.ai).

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
lexq download klauspost/cpuid
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f871662950fd6434e19bb056fb1f6efb6eba6144
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── f871662950fd6434e19bb056fb1f6efb6eba6144.nq.gz
│   └── repolex
│       └── f871662950fd6434e19bb056fb1f6efb6eba6144
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f082da8afe4614942d144ad16e6d200ca850b4f.nq.gz
│   ├── 116456bd355c04bdd5c97f0161ed339df5c30ace.nq.gz
│   ├── 14a56b9301ca7b5078598fcbebd5a4111b9d107b.nq.gz
│   ├── 1b695b62c3510b9ceb09faf62634dd4848ced631.nq.gz
│   ├── 241f4caf9c7f97cbf8df14f551e4f2609439411b.nq.gz
│   ├── 2888bae8faa4477599945d20420be340a164620b.nq.gz
│   ├── 2cb1f263fa0ddf190bc3f206840854bdba00cfae.nq.gz
│   ├── 2ef4714f7165b56b6825b498f3d76103f018b44d.nq.gz
│   ├── 471d986d2488aeb2885237e9f2733cd59c84eabd.nq.gz
│   ├── 50ef65534987f60b470e63ee6b6de459eb98803a.nq.gz
│   ├── 574f9389c07e4a23591563735c2113f396502590.nq.gz
│   ├── 5cec7ee949b1041ec1c2fc416f60c998a9abb40c.nq.gz
│   ├── 7462816b4a9cd24d3b545d3a6eff19f9b3b84133.nq.gz
│   ├── 818301ee49fb5f61020d104ce4d167fac4d36fd5.nq.gz
│   ├── 84cac4d745d3b6cd85b923ddbcdb36eabc2c3c07.nq.gz
│   ├── 8587c3a1fc552f0eaadd8e713bc73339d41263aa.nq.gz
│   ├── 8733ba343638eb5560e5b3c51547b15ad982f605.nq.gz
│   ├── 88d68d5286ff2b60c39d87e7eeff223167386274.nq.gz
│   ├── 92af622eb8ca65b77f6949d9c8e68655ee0da842.nq.gz
│   ├── 9ae32d607dc1b3910b2562cad8d3fb9501ff9e47.nq.gz
│   ├── 9cf7738a9756845444fdce2efe173e4ba6606369.nq.gz
│   ├── b196f78eb447f974cc04b843b96ffe888bac790a.nq.gz
│   ├── b43360297ff9aebc74eb591186cd5ea709f860d0.nq.gz
│   ├── bc11f8942193fee838f3a5daef12797e1187f729.nq.gz
│   ├── d96d24438b3eea8350d30fe903b0bc8eb0f983c1.nq.gz
│   ├── da07522e7cba43b66cbc6916849e44158d4e443b.nq.gz
│   ├── daf913b1b347aae6de6f48d599bc89ef8c8693d6.nq.gz
│   ├── ddda87c02a5a50cd2323cd9feed83d7490000f48.nq.gz
│   ├── e3cc3853306a08b33b7fe025643d5ddef13868b6.nq.gz
│   ├── f11f9881d0479de9b55e5b41fc45cb002be0c8e8.nq.gz
│   └── f8f201b5f7bb6b9a37061dc4a480e0fabd53ab3d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f871662950fd6434e19bb056fb1f6efb6eba6144.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 40 files
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

[klauspost/cpuid](https://github.com/klauspost/cpuid)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*
