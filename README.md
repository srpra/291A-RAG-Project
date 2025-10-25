# 291A-RAG-Project

This repository contains the resources and evaluation setup for a domain-specific Retrieval-Augmented Generation (RAG) system. The project is structured to support dataset creation, query testing, and evaluation of retrieval quality for a specialized domain.

## Repository Structure

- **Dataset/** – Collection of ≥100 domain-specific data sources (PDFs, code, documents, etc.) used for retrieval experiments.
- **Golden Dataset/** – Manually curated retrieval results for each query, used as a reference for evaluation.
- **Queries/** – Set of ≥10 realistic and domain-specific retrieval requests designed to capture key use cases.

## Getting Started

1. Clone the repository:
    ```bash
    git clone https://github.com/<your-username>/<repo-name>.git
    ```
2. Explore the datasets in `Dataset/` and `Golden Dataset/`.
3. Run the evaluator scripts on `Queries/` to compare retrieval results.
4. Use Phase 2 code to test your own domain-specific RAG improvements.
