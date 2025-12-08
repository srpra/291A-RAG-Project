# Domain-Specific Biomedical RAG (CSE 291 A00: Systems for LLMs and AI Agents)

End-to-end, domain-specific Retrieval-Augmented Generation (RAG) pipeline for biomedical question answering, built for **CSE 291 A00: Systems for LLMs and AI Agents (UCSD)**.

The system implements:
- Document ingestion (PDF / text)
- Multiple chunking strategies (sliding / sentence / paragraph)
- Dense embeddings + FAISS vector search
- Optional TF–IDF hybrid scoring
- Cross-encoder reranking
- LLM-based answer generation
- Retrieval-level + LLM-judge evaluation

## Running the Pipeline

Open the main notebook:

```bash
jupyter notebook CSE291_FINAL_CODE.ipynb
```

The notebook is structured in the following stages (run top-to-bottom):

### 1. Config

Set high-level flags:

```python
USE_TFIDF = False
USE_RERANK = True
TOP_K_INIT = 25   # candidates from FAISS
TOP_K = 6   # final context chunks for LLM
```

### 2. Ingestion

Load PDFs / text from `data/raw/`.

### 3. Chunking

Create chunks according to `CHUNKING_STRATEGY`, save to `data/processed/`.

### 4. Embeddings

Encode chunks (SentenceTransformers), save to `data/embeddings/`.

### 5. FAISS Index

Build / load index from `data/faiss/`.

### 6. Retrieval + Reranking

For each query:
- FAISS dense retrieval
- Optional TF–IDF scoring
- Optional cross-encoder reranking

### 7. Evaluation

Compute retrieval metrics and LLM-based answer scores. Here you would need to configure your API key to be called via the parameter `api_key`.
