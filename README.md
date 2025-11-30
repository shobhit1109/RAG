# RAG — Setup & Usage

A concise README to run and troubleshoot the Retrieval-Augmented Generation (RAG) notebook in this workspace.

**Quick Start**
- **Create venv:** `python -m venv .venv`
- **Activate (PowerShell):** `.\.venv\Scripts\Activate.ps1`
# What is RAG (Retrieval-Augmented Generation)

Retrieval-Augmented Generation (RAG) combines a retrieval system (a vector search over document embeddings) with a generative language model. The retriever finds relevant document passages for a user query and the LLM uses those retrieved passages as context to produce a more accurate, grounded answer.

Key steps: ingest documents -> split into chunks -> compute embeddings -> index into a vector store -> retrieve top-k passages -> generate answer with LLM using retrieved context.

## Architecture diagram

```mermaid
flowchart LR
  A[PDF / Documents] -->|load| B[Document Loader]
  B --> C[Text Splitter]
  C --> D[Embeddings]
  D --> E[Vector DB (FAISS / other)]
  E --> F[Retriever]
  F --> G[RetrievalQA / LLM]
  G --> H[Answer (with citations)]
```

Version: README updated on 2025-11-30
  )
  answer = qa_chain.run(query)
  print(answer)
  ```

## Suggestions & next steps

- I can patch `RAG Implementation.ipynb` to replace `.run(query)` usage with the safe `qa_chain({"query": query})` pattern that prints the answer and top source snippets.
- I can also add a standalone `rag.py` script that runs the pipeline outside the notebook for reproducible runs.

If you'd like either, reply with which change you want me to apply.

---

Version: README updated on 2025-11-30

