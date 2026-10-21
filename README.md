# Repolex Knowledge Graph of explosion/murmurhash

RDF knowledge graph data for [explosion/murmurhash](https://github.com/explosion/murmurhash), parsed by [repolex](https://repolex.ai).

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
rlex download explosion/murmurhash
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 58831632dab79389a5cee7715fb688ef2297ff78
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 58831632dab79389a5cee7715fb688ef2297ff78
│           └── chunk-001.nq.gz
├── blob
│   ├── 1cd3251c30a9fecb357773a381a69d0a7e630eb7.nq.gz
│   ├── 22641c13b166ad4784de8d283a5c052b9f6fc8e5.nq.gz
│   ├── 2f8b0272d5a40fb445b251ee455b9eca0f2ca3f0.nq.gz
│   ├── 341228b25dc1f1f8cea27d7ee5cbd63980dbd869.nq.gz
│   ├── 3e476a0f8223d4e13200b056cb223de9f3352e67.nq.gz
│   ├── 3e85038f3ec9329ec1b799a8615075f5a8c8944a.nq.gz
│   ├── 48abee3735b972cf4636d348035fd25c6b7b698b.nq.gz
│   ├── 4fe0ef9a9b21859dea9fd834ce3d2fcf23bad2e0.nq.gz
│   ├── 601da1cc9deceba3826946f1a5a53744a33eb806.nq.gz
│   ├── 6d7ccf4b2afef3c5dbe22058007d0fbb068b25fb.nq.gz
│   ├── 85042da5a018ca86840233fa838f4d9f740c57a7.nq.gz
│   ├── 865dc924a147c542fec9c577eebebfb4a00c4d20.nq.gz
│   ├── 9b4c3c90bf49c6b8c8342f8e0b1f6b03b70d8a35.nq.gz
│   ├── 9d089c2ca6c0089761c62fdd1c47de6e46fa1c9f.nq.gz
│   ├── bdc0bb8a30d39f38784941f4b72a371fef4b7ddf.nq.gz
│   ├── c55f4a4f0f5096443bc848d59e3486a023300235.nq.gz
│   ├── d9245f158cc2f2ef8a8070f863625c2ba3a6813c.nq.gz
│   ├── e19157d9a852332670b8c5f8d6ce6ba599ffdfcc.nq.gz
│   ├── e337c37cea98c49e9c70bc9e2e70ead9dd9267ac.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb9638f45354d96c723679b6aa11a109492d59e1.nq.gz
│   ├── f01c9452f3fed06595a71d8fa93458aa70b58072.nq.gz
│   └── f59d39179402904d46626806156735f2dbe930d7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 58831632dab79389a5cee7715fb688ef2297ff78.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[explosion/murmurhash](https://github.com/explosion/murmurhash)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
