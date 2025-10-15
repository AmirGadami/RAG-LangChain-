# Retrieval-Augmented Generation (RAG) Variants

This repository presents a set of experiments and implementations around **Retrieval-Augmented Generation (RAG)** and its modern extensions. It demonstrates the progression from a simple RAG pipeline to advanced frameworks such as **Corrective RAG (CRAG)** and **Adaptive RAG**, enabling more reliable retrieval, document grading, and query routing.

---

## Overview
- **RAG**: Baseline retrieval-augmented generation using vectorstores and large language models (LLMs).
- **CRAG**: Introduces document grading and corrective mechanisms to filter irrelevant or noisy information.
- **Adaptive RAG**: Dynamically routes queries to the most appropriate strategy (LLM-only, Web Search, or RAG) based on query analysis.

Each approach is implemented in a dedicated notebook and visualized with graph flows to illustrate the decision-making process.

---

## Notebooks

### 1. RAG.ipynb
Implements the baseline RAG pipeline:
- Embed and index documents
- Retrieve relevant passages
- Generate concise answers grounded in retrieved evidence

### 2. CRAG.ipynb — Corrective RAG
Enhances the baseline pipeline with document relevance grading:
- Filters retrieved documents by semantic relevance
- Removes irrelevant evidence
- Iteratively re-queries if results are insufficient

**Graph Flow**  
![CRAG Graph](./images/crag_graph.png)

### 3. AdaptiveRAG.ipynb
Introduces query routing and adaptability:
- Supports multiple strategies:
  - LLM-only (no retrieval)
  - Web Search (for real-time knowledge)
  - Vectorstore Retrieval (RAG)
- Uses LangGraph conditional edges for decision-making

**Graph Flow**  
![Adaptive RAG Graph](./images/adaptive_rag_graph.png)

---

## Key Features
- **Retriever Integration**: Chroma vectorstore with Cohere/OpenAI embeddings
- **Grading Pipelines**:
  - Document relevance assessment
  - Hallucination detection
  - Answer validation
- **Adaptive Routing**: Intelligent query analysis to select the optimal answering strategy
- **Evaluation Ready**: Extensible with metrics for faithfulness, coverage, and accuracy

---

## Visualizations
The CRAG and Adaptive RAG graphs illustrate the control flow and decision logic behind each framework.

---

## Resources
- [YouTube: Retrieval-Augmented Generation (RAG) Explained](https://youtu.be/NEc6V7mLBiY?si=VbJZc5cOIhGASeeL)

---

## Setup

### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Configure environment variables
Create a `.env` file with:
```
OPENAI_API_KEY=...
COHERE_API_KEY=...
TAVILY_API_KEY=...
```

---

## Roadmap
- Extend Adaptive RAG with multi-hop retrieval
- Add quantitative evaluation metrics for systematic benchmarking
- Analyze tradeoffs across latency, accuracy, and cost

---


## Contributing
Contributions are welcome. Please open issues or submit pull requests to improve notebooks, add new retrieval strategies, or extend evaluation pipelines.

---

## Maintainer
This project is maintained as part of ongoing research into advanced RAG architectures and their applications.
