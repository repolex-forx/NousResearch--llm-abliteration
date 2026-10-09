# Repolex Knowledge Graph of NousResearch/llm-abliteration

RDF knowledge graph data for [NousResearch/llm-abliteration](https://github.com/NousResearch/llm-abliteration), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/llm-abliteration
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f1148c90753cb5ea4cb6763a73f15c5635957f6a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f1148c90753cb5ea4cb6763a73f15c5635957f6a
│           └── chunk-001.nq.gz
├── blob
│   ├── 006e99a3d69e2ee1e656c9c5eddfeddd52f78dce.nq.gz
│   ├── 021d629575695ec2eeb7591e54207ccfae977223.nq.gz
│   ├── 048dea9d64d4318285ae88557ee92f2175236ec5.nq.gz
│   ├── 180593ce5c0ce745ff6dc051d479f3bcf8e318c6.nq.gz
│   ├── 1e5f67f7d89224a2821ee31e69086690085b1e3c.nq.gz
│   ├── 2b4fbcee73d2186b5938bce12777b9614f108645.nq.gz
│   ├── 32680ae318395bbc466d10b60e2f0f18da5a1070.nq.gz
│   ├── 459b654b21c0aeb3adcfe12e051f81d53a8fdbb8.nq.gz
│   ├── 473da49aab3ded38f42d55e1219d3824be0e5962.nq.gz
│   ├── 75165fb998ada7a7e842a201b2acc491e220c303.nq.gz
│   ├── 7ff392785771127ae1ab301a455511e02bb94b54.nq.gz
│   ├── 82f927558a3dff0ea8c20858856e70779fd02c93.nq.gz
│   ├── 8eb85fbbd981eb387a078dd6fa931d59f5e45c2e.nq.gz
│   ├── bd7ae347bb8d153fc5d93f56aeb352123cde2b8c.nq.gz
│   ├── c32908ccc46e7ce1199a0dd94fd6c44e1ad5b24a.nq.gz
│   ├── c3cb671c0dddef5c1cd0046e898f837024f4cc67.nq.gz
│   ├── e8070c281c3981a1855e17ecbdd8b993cdeea55a.nq.gz
│   ├── f288702d2fa16d3cdf0035b15a9fcbc552cd88e7.nq.gz
│   ├── f83ce76de4966190781d396a5da2b4dbf890479c.nq.gz
│   └── f96948f6e2fb11f42e8fbb064f69a7d72d652a48.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f1148c90753cb5ea4cb6763a73f15c5635957f6a.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 26 files
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

[NousResearch/llm-abliteration](https://github.com/NousResearch/llm-abliteration)

---
*Parsed on 2026-10-09 by [repolex](https://repolex.ai)*
