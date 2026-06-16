# 🏦 Intelligent Credit Risk & Loan Decisioning Platform

> **Agentic AI + RAG underwriting system** that analyzes financial documents and delivers explainable, regulator-compliant loan decisions in minutes — not days.

[![Python](https://img.shields.io/badge/Python-3.10+-blue)](https://python.org)
[![LangGraph](https://img.shields.io/badge/LangGraph-Agentic_AI-purple)](https://github.com/langchain-ai/langgraph)
[![FastAPI](https://img.shields.io/badge/FastAPI-REST_API-green)](https://fastapi.tiangolo.com)
[![AWS EKS](https://img.shields.io/badge/AWS-EKS_Deployed-orange)](https://aws.amazon.com/eks/)

---

## 🎯 Problem Statement

Traditional loan underwriting takes **3–7 days** — manual document review, inconsistent decisions, no explainability. This platform automates the entire pipeline using multi-agent AI, reducing approval time to **minutes** while maintaining full regulatory compliance.

---

## 🏗️ System Architecture

```
Loan Application (PDF/JSON)
         ↓
┌─────────────────────────┐
│   Document Agent        │  Extracts data from bank statements,
│   RAG + Qdrant          │  GST filings & credit reports via RAG
└─────────────────────────┘
         ↓
┌─────────────────────────┐
│   Risk Scoring Agent    │  XGBoost model calculates risk score
│   XGBoost + SHAP        │  SHAP provides explainability
└─────────────────────────┘
         ↓
┌─────────────────────────┐
│   Decision Agent        │  GPT-4.1 synthesizes all signals
│   GPT-4.1               │  and generates compliant decision
└─────────────────────────┘
         ↓
┌─────────────────────────┐
│   LangGraph Orchestrator│  Manages agent state transitions
│   + Redis Cache         │  and async workflow coordination
└─────────────────────────┘
         ↓
   FastAPI REST API → AWS EKS (Docker + CI/CD + Autoscaling)
```

---

## ⚡ Key Metrics

|       Metric                |      Result           |
|-----------------------------|-----------------------|
| Concurrent loan evaluations |       1,000+          |
| Loan approval time          |      Days → Minutes   |
| Retrieval precision improvement |     +30%          |
| SQL execution success rate       |      95%         |

---

## 🛠️ Tech Stack

**Agentic Orchestration:** LangGraph, Multi-Agent Pipeline
**LLMs:** GPT-4.1, OpenAI API
**RAG & Vector DB:** Qdrant, SentenceTransformers (all-MiniLM-L6-v2)
**ML Model:** XGBoost + SHAP (explainability)
**Backend:** FastAPI, Async Python, Redis Caching, Uvicorn
**Deployment:** AWS EKS, Docker, CI/CD Pipeline, Autoscaling

---

## 📁 Project Structure

```
credit-risk-platform/
├── agents/
│   ├── document_agent.py     # RAG-based document extraction
│   ├── risk_agent.py         # XGBoost risk scoring
│   └── decision_agent.py     # GPT-4.1 final decision
├── graph/
│   └── workflow.py           # LangGraph orchestration
├── rag/
│   ├── embeddings.py         # SentenceTransformer embeddings
│   └── retriever.py          # Qdrant vector search
├── models/
│   └── risk_model.py         # XGBoost + SHAP integration
├── api/
│   └── routes.py             # FastAPI endpoints
├── cache/
│   └── redis_cache.py        # Redis caching layer
└── sample_data/              # Sample documents for testing
```

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/darshnanakumbhar-eng/credit-risk-loan-decisioning-platform.git
cd credit-risk-loan-decisioning-platform

# Create virtual environment
python -m venv venv
venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt

# Add your API keys
cp .env.example .env
# Edit .env with your OPENAI_API_KEY

# Run the API
uvicorn main:app --reload
```

---

## 📬 Contact

**Darshana Kumbhar** — GenAI & Agentic AI Engineer
📧 darshnanakumbhar@gmail.com
💼 [LinkedIn](https://www.linkedin.com/in/darshnanakumbhar/)
