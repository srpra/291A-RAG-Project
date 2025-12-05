# Domain-Specific Biomedical RAG (CSE 291 – Phase 2)

End-to-end, domain-specific Retrieval-Augmented Generation (RAG) pipeline for biomedical question answering, built for **CSE 291 A00: Systems for LLMs and AI Agents (UCSD)**.

The system implements:
- Document ingestion (PDF / text)
- Multiple chunking strategies (sliding / sentence / paragraph)
- Dense embeddings + FAISS vector search
- Optional TF–IDF hybrid scoring
- Cross-encoder reranking
- LLM-based answer generation
- Retrieval-level + LLM-judge evaluation

Running the Pipeline

Open the main notebook:

jupyter notebook CSE291_FINAL_CODE.ipynb


The notebook is structured in the following stages (run top-to-bottom):

Config – set high-level flags:

CHUNKING_STRATEGY = "paragraph"  # "sliding" | "sentence" | "paragraph"
USE_TFIDF = False
USE_RERANK = True
TOP_K_INIT = 25   # candidates from FAISS
TOP_K_FINAL = 6   # final context chunks for LLM


Ingestion – load PDFs / text from data/raw/.

Chunking – create chunks according to CHUNKING_STRATEGY, save to data/processed/.

Embeddings – encode chunks (SentenceTransformers), save to data/embeddings/.

FAISS Index – build / load index from data/faiss/.

Retrieval + Reranking – for each query:

FAISS dense retrieval

optional TF–IDF scoring

optional cross-encoder reranking

Evaluation – compute retrieval metrics and LLM-based answer scores
