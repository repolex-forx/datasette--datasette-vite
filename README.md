# Repolex Knowledge Graph of datasette/datasette-vite

RDF knowledge graph data for [datasette/datasette-vite](https://github.com/datasette/datasette-vite), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-vite
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e30144caefbac2e64f6170a70e3180e46d12f04d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e30144caefbac2e64f6170a70e3180e46d12f04d
│           └── chunk-001.nq.gz
├── blob
│   ├── 0875766fd199e1b49955d2ac934858f99df3dd20.nq.gz
│   ├── 0957906d3cf81f14c2096fd3ef22c3602be57677.nq.gz
│   ├── 0f8af6c179943214d76484bf8f58726d164b5b9c.nq.gz
│   ├── 10dc5e568e12f06b6469493f0838608618513a60.nq.gz
│   ├── 1499b88cc7ab947fe505f64aadb82626224c8a55.nq.gz
│   ├── 149c53034666985c29eac3598444733c2ad01b02.nq.gz
│   ├── 153121e41c8ae4101b327cc7ed54c0094bb44ab0.nq.gz
│   ├── 1598b68bf6896062df4e4f24ab1a5f1e802d2c7d.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 4c0303bc25234c055ec20c7cebc79aa50bba3a86.nq.gz
│   ├── 4ce16a34f22ec58f1d8ab9e6da2bf9e12461abb1.nq.gz
│   ├── 5038e620b92f137f1e5c9fa5f515026574302513.nq.gz
│   ├── 62355f3d63cf49cbad1c47906ad1882831fde6bd.nq.gz
│   ├── 71fe395ada80b5f725837ee0bfb31c94524d1a18.nq.gz
│   ├── 741f27708a67712891645752c54ca948d49f8ae0.nq.gz
│   ├── 7c2abda4fe246483f67da104dcb4223b8fa4fdc7.nq.gz
│   ├── 7c44c11f3fce7dea4b6dbcbfb3c700547087f024.nq.gz
│   ├── 85ec0b778cd11f981d4fabbf49ea7edd1116241a.nq.gz
│   ├── 91e960de9a6f039f3b237d87b4e1d2cbc8615a3e.nq.gz
│   ├── 928b6c527461721f6af5e42d60a5256b32f18d8b.nq.gz
│   ├── a2587aa9c3b696c762429b812893c9d36c726533.nq.gz
│   ├── aad3408a3a11c3f40d299b1d225e65d17a47a66b.nq.gz
│   ├── ac874f0f798528029f997897daba911deaa131a1.nq.gz
│   ├── b11b8307ca48ff151aaea28dec941112c1aa7f62.nq.gz
│   ├── c23a670442e1c387eca4f229d47af2237338b643.nq.gz
│   ├── c363d29d90c7feb400144b7262ee3061673936c8.nq.gz
│   ├── d53f8fb2b477937d43f0bd77fae43c09cc569cfe.nq.gz
│   ├── d7295686869017ddb04ab7d5f99476fbdc6c7f90.nq.gz
│   ├── e34ea538612c08d8612fc542fe35398ca7ff650a.nq.gz
│   ├── e5a5dcbe9900061cf8f14fa03c6054d8c0e5897e.nq.gz
│   ├── e95edb77b9471094febb6f67e2a077507a7b2c5d.nq.gz
│   ├── ebede25f251978a66b2021b03a63134b814b69c8.nq.gz
│   ├── f2c14c283034fa04a624254200ba9e345534c04f.nq.gz
│   ├── f3658a6e09b0828efd417b1acb9b2073f5c4d759.nq.gz
│   ├── f3aae87b20f47af0e92a862daa649fee596f7b4a.nq.gz
│   ├── f543fd79a3aa34b3eac3e5e7295b0e9f28274ccb.nq.gz
│   └── f8abaed8c27ab769d42c3d87b31fcab944ec04d4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e30144caefbac2e64f6170a70e3180e46d12f04d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[datasette/datasette-vite](https://github.com/datasette/datasette-vite)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
