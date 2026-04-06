---
title: "Nexus: Multi-Agent RAG Intelligence"
date: 2025-01-01
draft: false
slug: "nexus"
description: "A production-grade Multi-Agent Research Intelligence Platform that makes RAG transparent, observable, and self-correcting."
tags: ["AI", "RAG", "LangGraph", "FastAPI", "Next.js", "Qdrant", "Langfuse"]
---

> **[🚀 Launch Live Demo](https://project-nexus.duckdns.org/)**  &nbsp;|&nbsp;  **[📁 View Source](https://github.com/bellerophon95/nexus)**

---

## The Problem

Most RAG systems are black boxes. You ask a question, get an answer, and have no idea whether the system actually found relevant documents, hallucinated connections, or silently dropped critical context along the way. When the stakes are high—research, compliance, decision support—"trust me" isn't good enough.

**Nexus was built to fix that.**

It's a production-grade Multi-Agent Research Intelligence Platform where every retrieval decision, every reranking score, and every synthesis step is surfaced in real-time. No hidden reasoning. No unexplainable answers.

{{< figure src="/mypage/images/nexus/dashboard.png" title="The Nexus Multi-Agent Lab Dashboard — real-time agentic reasoning, trace metrics, and citation logic at a glance." >}}

---

## How It Works

Nexus doesn't follow the traditional retrieve-then-generate pipeline. Instead, it deploys a team of specialized agents that collaborate, challenge each other, and self-correct.

### The Agent Trio

**Retriever** — Executes hybrid search across Qdrant's sparse (keyword) and dense (semantic) indices. Top-K candidates are re-scored through a Cross-Encoder Reranker (`BGE-Reranker-v2-m3`) to eliminate noise and maximize precision.

**Analyst** — Synthesizes retrieved documents into a coherent, cited response. Every claim is grounded in specific source passages.

**Validator** — The internal skeptic. Reviews the Analyst's output against source documents. If grounding falls below threshold, it triggers a new retrieval cycle with a refined query. This self-correcting loop is what separates Nexus from simple RAG.

All three agents are orchestrated by **LangGraph**, with autonomous state transitions and observable decision points at every step.

{{< figure src="/mypage/images/nexus/knowledge-base.png" title="The Automated Knowledge Hub — document ingestion and semantic chunking." >}}

---

## What You Can See (That Other RAG Systems Hide)

Nexus integrates **Langfuse** for full-stack observability, surfacing metrics that are typically buried:

| What's Tracked | Why It Matters |
|---|---|
| **Faithfulness Score** (target > 0.95) | LLM-as-a-Judge validation — did the answer actually come from the documents? |
| **Per-Turn Latency** (target < 1.5s) | Semantic caching + SSE streaming keep things fast |
| **Token Cost per Query** | Dynamic context window trimming prevents runaway costs |
| **Guardrail Status** | Real-time flag if a response triggers safety or grounding concerns |

The **Engine Tuning Interface** puts these levers directly in the user's hands — adjust `match_threshold`, `rerank` sensitivity, and `max_iterations` at runtime to balance speed against depth.

{{< figure src="/mypage/images/nexus/engine-tuning.png" title="Engine Settings — adjust retrieval sensitivity and agent behavior on the fly." >}}

---

## Under the Hood

### The Stack

| Layer | Technology |
|---|---|
| **Frontend** | Next.js 15 (App Router) + React 19 (Server Components) |
| **Backend** | FastAPI + LangGraph + Pydantic AI |
| **Vector Store** | Qdrant Cloud (Hybrid: Dense + Sparse) |
| **Database** | Supabase (Postgres) |
| **Caching** | Upstash Redis (semantic vector cache) |
| **Observability** | Langfuse (tracing, evals, cost tracking) |

### The Details That Matter

**SSE Multiplexing** — A single persistent Server-Sent Events connection carries text tokens, activity logs, and final metrics simultaneously. No polling, no WebSocket overhead.

**Cross-Encoder Reranking** — Initial retrieval casts a wide net. The `BGE-Reranker-v2-m3` cross-encoder then evaluates each candidate against the original query as a full pair, dramatically improving signal-to-noise over embedding similarity alone.

**Self-RAG Validation** — The Validator agent isn't a simple filter. It performs structured comparison between generated claims and source passages, identifying unsupported statements and triggering targeted re-retrieval when needed.

{{< figure src="/mypage/images/nexus/chat-interface.png" title="The Chat Interface — deep trace visibility and explainable AI responses." >}}

---

## Why This Matters

The AI industry is moving from "can it generate text?" to "can we trust the text it generates?" Nexus is a working answer to that question — a system where transparency isn't an afterthought but the core design principle.

It demonstrates the leap from **Simple RAG** (retrieve → generate → hope for the best) to **Agentic RAG** (retrieve → synthesize → validate → self-correct → prove it).

---

{{< rawhtml >}}
<p style="text-align: center; font-size: 1.1em; margin-top: 2rem;">
  <a href="https://project-nexus.duckdns.org/" style="font-weight: bold;">Try the Live Demo →</a>
  &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://github.com/bellerophon95/nexus" style="font-weight: bold;">Read the Source →</a>
</p>
{{< /rawhtml >}}
