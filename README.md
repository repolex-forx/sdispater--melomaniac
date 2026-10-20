# Repolex Knowledge Graph of sdispater/melomaniac

RDF knowledge graph data for [sdispater/melomaniac](https://github.com/sdispater/melomaniac), parsed by [repolex](https://repolex.ai).

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
rlex download sdispater/melomaniac
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 26edeba844d4822bb1df287d996356786d6d7a38
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 26edeba844d4822bb1df287d996356786d6d7a38
│           └── chunk-001.nq.gz
├── blob
│   ├── 0520e9e53b9e80ab560bee4b95c166f6f00551a5.nq.gz
│   ├── 0b5ee95a461579f2e0f1bd6660618590e6899ace.nq.gz
│   ├── 123216561ac776907a92673ff607efe113055d0e.nq.gz
│   ├── 183371ff864ab9638b32e7ca806b627c31ade7e6.nq.gz
│   ├── 1bd1af92bd67747168009f831d2661647e7062fa.nq.gz
│   ├── 22c200ffa0857567d67e5ae2bf40da6744b6dad2.nq.gz
│   ├── 23ea927eb644dabbe777ce140a865e17defc39ba.nq.gz
│   ├── 25494efd320fa833543ec08b96ecf9cf21b8df6a.nq.gz
│   ├── 2a9acf13daa95e85642ea255d3e3bd1ef8252804.nq.gz
│   ├── 3c9878491dca3ba252fe23ae46161fb7dcdd7028.nq.gz
│   ├── 3cea5f2972c9ce4fa343161c05077002c5e6e964.nq.gz
│   ├── 49b22a626d9568f9d772425c57fcb1d24955d270.nq.gz
│   ├── 53a11acad3feb30caea7b84b3afbffb98b8d1db1.nq.gz
│   ├── 57a7e71095a8e8c1cc4a43f004a6221ece83d42a.nq.gz
│   ├── 59bd4307f8e57267de07838ea2e4878e4c42eab5.nq.gz
│   ├── 633f866158ac742cf754a2c43edcb07e3a094f3c.nq.gz
│   ├── 701df228d97e9bf3f2b10c5634107daff2f7bd3d.nq.gz
│   ├── 755e9c95d7f4c722d66d361cc296d479dc9f9d9d.nq.gz
│   ├── 77ed2e953809e0567f33002927b2de9b05993eb1.nq.gz
│   ├── 7997b86c5065bf5ab60ec1ae85ea91465b55d8ac.nq.gz
│   ├── 79cc32277f30900cb1f3372353f07011d9cc1506.nq.gz
│   ├── 89fa4033b8312b089cbc9eaaf07c43a383701155.nq.gz
│   ├── 91e4b8e20e8359d142de9250eea63f5875bf9519.nq.gz
│   ├── a006784a252f757660cf6797c243b993f0381fab.nq.gz
│   ├── a64dcb8913a049849dcdd74541f2289e467c2202.nq.gz
│   ├── a7b16a14459ba8b868d2225702e045edec416e53.nq.gz
│   ├── b287d955655aac7376d55fa7f913ea0a949b23e2.nq.gz
│   ├── bc14a9c17cc52c2f0a8f3e0cfb0efc586b01243b.nq.gz
│   ├── bf67586cec86e7cdd49406d53bdf8bbf01a9df26.nq.gz
│   ├── c045d54c666d81effc8e949f9f519640af996dcc.nq.gz
│   ├── c16d885dde13f323ad4adacdabcdc815d5c99840.nq.gz
│   ├── ca7a78d623a9274c51beb0ec5050ae0dad6f62b4.nq.gz
│   ├── d6acc0996e9c5a8bb1b6d13e57aa06647a7b79f6.nq.gz
│   ├── dd25ebf8c6e19b5e0ccb330fc256aa4aedbcc663.nq.gz
│   ├── e501d2a2d342b8c57ce97cc9b6f287f3f8c75ba5.nq.gz
│   ├── e57ee8a2dba810412225e34a43424363150f4529.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e9452837b2c0083a7299b33540e9a31cb2450681.nq.gz
│   └── f7ea1b8f1582fcb3d8603567741716e446d8ade3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 26edeba844d4822bb1df287d996356786d6d7a38.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 47 files
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

[sdispater/melomaniac](https://github.com/sdispater/melomaniac)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
