# Repolex Knowledge Graph of sphinx-contrib/emojicodes

RDF knowledge graph data for [sphinx-contrib/emojicodes](https://github.com/sphinx-contrib/emojicodes), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/emojicodes
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   ├── 63444cf58ca118b846720d376cdb559491a98c09
│   │   │   └── chunk-001.nq.gz
│   │   └── cb2f29e1a8a5245621ba081043416b2862ff2a5e
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── cb2f29e1a8a5245621ba081043416b2862ff2a5e.nq.gz
│   └── repolex
│       ├── 63444cf58ca118b846720d376cdb559491a98c09
│       │   └── chunk-001.nq.gz
│       └── cb2f29e1a8a5245621ba081043416b2862ff2a5e
│           └── chunk-001.nq.gz
├── blob
│   ├── 03a916e340347dae6e16ba62bd8ed618544db82b.nq.gz
│   ├── 113dec982a6d8c809c10709e382d06716719d8cc.nq.gz
│   ├── 1955b3d779285803d9ea23e4fc7a9cd2fc985711.nq.gz
│   ├── 2eb996c05afd07d1b9d49e0a5ac521bf56612b48.nq.gz
│   ├── 567609b1234a9b8806c5a05da6c866e480aa148d.nq.gz
│   ├── 6d6be19defb3a650a87d768bc627d3472caf3095.nq.gz
│   ├── 73e3bb4f38bada34ca9359469effd05bb6767ac7.nq.gz
│   ├── 79c9c54c5cf5df2faaa34f8387b78ef1b7ace2bf.nq.gz
│   ├── 878d070d16d9fbb1fc64c3129f9300f2ed19204c.nq.gz
│   ├── 91bc868f4f48969607602c684d08c9a6477c5bc6.nq.gz
│   ├── a3ba1412646fa297b8c963ae53fa4d4e7d612bff.nq.gz
│   ├── ae68db326a3a1e8fc19379dd0c3ae4ccd4178a9a.nq.gz
│   ├── b15dd940b569c92deb795053bb7f893e077c3933.nq.gz
│   ├── b3d9eb54b29fde15b7ea973c3f116863cecdcaec.nq.gz
│   ├── cfd2edc768b0b88fb1fd91ecab0268f92364a507.nq.gz
│   ├── d0c3cbf1020d5c292abdedf27627c6abe25e2293.nq.gz
│   └── e013ccc195b8439e7ca316e75a892c0127b446ab.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── cb2f29e1a8a5245621ba081043416b2862ff2a5e.nq.gz
├── filetree
│   ├── 63444cf58ca118b846720d376cdb559491a98c09.nq.gz
│   └── cb2f29e1a8a5245621ba081043416b2862ff2a5e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

17 directories, 30 files
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

[sphinx-contrib/emojicodes](https://github.com/sphinx-contrib/emojicodes)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
