# 📧 Cold Mail Generator using LangChain, Groq, and ChromaDB

An end-to-end GenAI application that generates high-quality cold emails based on any company or website URL. It uses a **Retrieval-Augmented Generation (RAG)** pipeline powered by **LangChain**, **Groq’s LLaMA3-70B model**, and **ChromaDB** for fast and accurate information retrieval.

> 🚀 Powered by Python • LangChain • ChromaDB • Groq Cloud • Streamlit

---

## 💡 Features

- 🔗 Accepts a company or personal website URL
- 🌐 Scrapes and embeds real-time website content
- 🧠 Uses a RAG pipeline to feed context to the LLM
- ✍️ Generates tailored cold emails using LLaMA3-70B (Groq)
- 💬 Interactive web UI built with Streamlit
- ⚡ Extremely fast responses via Groq inference engine

---

## 🛠️ Tech Stack

| Component       | Tool/Service                   |
|-----------------|--------------------------------|
| Frontend        | Streamlit                      |
| LLM             | Groq Cloud – `llama3-70b-8192` |
| Orchestration   | LangChain                      |
| Vector DB       | ChromaDB (with persistent storage) |
| Language        | Python 3.10+                   |
| Deployment      | Local / Streamlit Cloud        |

---

## 📁 Project Structure



cold-email-project/ │ ├── app/ │ ├── main.py # Streamlit app entry point │ ├── chains.py #LangChain logic & Groq LLM configuration │└── utils.py # Web scraping, cleaning & parsing │ ├── .env # Environment variables (Groq API Key) ├── requirements.txt # Python dependencies └── README.md # This file!


---

## 🚀 Getting Started

### 1. Clone the Repo

```bash
git clone https://github.com/Nithishkaranam2002/cold-email-generator.git
cd cold-email-generator

python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
GROQ_API_KEY=your_groq_api_key_here



streamlit run "/Users/nithishkaranam/Downloads/projects /cold email project/app/main.py


┌────────────────────┐
│    User Input UI   │ ← Streamlit
└─────────┬──────────┘
          │
          ▼
┌─────────────────────────────┐
│  Web Scraper (utils.py)     │ ← Extracts data from URL
└─────────┬───────────────────┘
          ▼
┌─────────────────────────────┐
│  Text Chunking & Embedding  │ ← LangChain Embeddings
└─────────┬───────────────────┘
          ▼
┌─────────────────────────────┐
│     ChromaDB Vector Store   │ ← Stores embedded chunks
└─────────┬───────────────────┘
          ▼
┌─────────────────────────────┐
│    LangChain Retriever      │ ← Finds most relevant docs
└─────────┬───────────────────┘
          ▼
┌─────────────────────────────┐
│   Prompt Injection + RAG    │ ← Context-aware prompt builder
└─────────┬───────────────────┘
          ▼
┌─────────────────────────────┐
│  Groq LLM (LLaMA3-70B)      │ ← Fast generation via Groq API
└─────────┬───────────────────┘
          ▼
┌────────────────────┐
│ Streamlit Output   │ ← Final email displayed
└────────────────────┘

