# RAG Assignment: Baseline vs. Re-Ranking

Compares two retrieval pipelines for question answering over the IIIT-H Computational Natural Sciences (dual degree) curriculum handbook.

- Pipeline 1 (baseline): bi-encoder retrieves the Top-10 chunks, the first 3 go to the LLM.
- Pipeline 2 (re-ranking): the same Top-10 are re-ordered by a cross-encoder, the new top 3 go to the LLM.

Everything else is identical (chunks, index, prompt, greedy decoding), so the only difference is the chunks sent to the LLM as reference.

## Models (all open)

| Role | Model |
|---|---|
| Bi-encoder | `sentence-transformers/all-MiniLM-L6-v2` |
| Cross-encoder | `cross-encoder/ms-marco-MiniLM-L-6-v2` |
| LLM | `Qwen/Qwen2.5-3B-Instruct` |

## Repo contents

```
.
├── 1.1-CND-Curriculum-Annexure5.pdf              # the source document (118 pages)
├── RAG_Baseline_vs_Reranking.ipynb # the full notebook
├── results/
│   ├── latency.csv                 # runtime of each pipeline stage
│   └── answers.csv                 # Answer 1 vs Answer 2 for the selected queries
└── README.md
```
