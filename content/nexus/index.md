+++
title = "Project Nexus"
date = 2026-03-31T08:45:00+05:30
+++

Nexus is a production-grade Multi-Agent Research Intelligence Platform built to solve the "Black Box" problem of Retrieval Augmented Generation (RAG). By combining hybrid search, cross-encoder reranking, and real-time agentic observability, Nexus provides a transparent and verifiable AI research environment.

[🚀 Launch Live Demo](https://project-nexus.duckdns.org/)

## Features

1. **Hybrid Search + Cross-Encoder Reranking**  
   The retrieval pipeline runs two passes in parallel — a dense semantic search using OpenAI embeddings, and a sparse BM25/SPLADE index for keyword-exact matching. This catches both conceptual similarity and precise term matches that dense-only retrieval misses.

2. **Stateful Multi-Agent Loop**  
   The agents are managed by LangGraph as a directed cyclic graph — not a linear chain. Three nodes (Retriever, Analyst, and Validator) manage the research flow. If the Validator determines that a response isn't sufficiently grounded, it triggers a new retrieval cycle with a refined query.

3. **Real-Time Observability**  
   Every agent transition, token consumed, and evaluation score streams to the client over a single SSE connection. The UI shows the live process graph updating node-by-node, alongside per-turn latency, token costs, faithfulness scores, and guardrail status.

## Architecture

1. **Next.js 15 & React 19**  
   User-facing interface built with a streaming-first rendering model that perfectly aligns with the Server-Sent Events (SSE) architecture for real-time updates.

2. **FastAPI + LangGraph**  
   Backend orchestration layer providing an async-native, type-safe environment for managing complex agentic workflows and multi-node state transitions.

3. **Qdrant Cloud**  
   Used as the primary vector intelligence layer, supporting native hybrid search (dense + sparse) in a single unified query for maximum retrieval precision.

4. **Supabase & Redis**  
   PostgreSQL manages document metadata and ingestion history, while Upstash Redis provides high-speed semantic caching to reduce latency on repeated queries.

5. **Langfuse**  
   Full-stack tracing and observability. Surfacing per-turn latency, token costs, and automated evaluation metrics (Faithfulness and Relevance) directly in the research dashboard.

## Screenshots

### Multi-Agent Lab
![Lab Dashboard](/mypage/images/nexus/dashboard.png)
*Real-time agentic reasoning, trace metrics, and citation grounding — visible as it happens.*

### Knowledge Ingestion
![Knowledge Hub](/mypage/images/nexus/knowledge-base.png)
*The Automated Knowledge Hub for document ingestion and semantic chunking.*

### Observability Interface
![Chat Interface](/mypage/images/nexus/chat-interface.png)
*Explainable AI responses with deep trace visibility and evaluation scores.*

### Engine Configuration
![Engine Settings](/mypage/images/nexus/settings.png)
*Runtime controls for adjusting retrieval sensitivity and agent behavior.*

## Conclusion

Nexus demonstrates the transition from "Simple RAG" to "Agentic RAG." It moves beyond basic document retrieval into a stateful, observable, and self-correcting intelligence layer capable of handling complex research tasks with verified citations and professional-grade transparency.

For more details, please visit the [GitHub repository](https://github.com/bellerophon95/nexus).
