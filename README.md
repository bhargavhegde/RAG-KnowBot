<img width="2263" height="1220" alt="image" src="https://github.com/user-attachments/assets/68cb01ac-5666-4fed-a767-17c77216aecb" />

# KnowBot (v1.0) - Personal RAG Chatbot (100% Local & Private)

A beautiful, fully offline personal knowledge chatbot that lets you chat with your own documents using **Retrieval-Augmented Generation (RAG)**.  
No API keys, no cloud services, no data ever leaves your machine.

> **Note**: This is the original Streamlit version. For the production-ready cloud deployment, see [KnowBot 3.0](https://github.com/bhargavhegde/KnowBot3.0).

## Demo

Click to watch:[knowbotDemo.webm](https://github.com/user-attachments/assets/d7484a5b-3f2e-430e-842e-167a9e14f497)

## ✨ Features

- 100% local execution using Ollama + Llama 3.1 8B  
- Supports PDF, TXT, and Markdown documents  
- Upload, delete, and re-index files directly from the browser  
- Customizable system prompt (change tone, format, rules)  
- Automatic source citations (shows which document parts were used)  
- Modern dark-themed chat interface built with Streamlit  
- Persistent Chroma vector database (fast reloads)  
- Strong hallucination guardrails (refuses to make up facts)

## 🛠️ Tech Stack

- **LLM**: Llama 3.1 8B (via Ollama)  
- **Embeddings**: nomic-embed-text (via Ollama)  
- **Vector Store**: Chroma  
- **Framework**: LangChain + LangChain-Ollama  
- **UI**: Streamlit  
- **Python**: 3.10+

## 🚀 Quick Start (Local Setup)

### 1. Install Ollama

Download and install from: https://ollama.com/download

### 2. Pull the required models

```bash
ollama pull llama3.1:8b
ollama pull nomic-embed-text
```

### 3. Clone this repository

```bash
git clone https://github.com/bhargavhegde/RAG-KnowBot.git
cd RAG-KnowBot
```

### 4. Create and activate virtual environment

```bash
# Create
python3 -m venv rag_env

# Activate (Linux/macOS)
source rag_env/bin/activate

# Activate (Windows)
rag_env\Scripts\activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

### 6. Start the application

```bash
streamlit run app.py
```

Open your browser at: http://localhost:8501

## 📂 Project Structure

```
RAG-KnowBot/
├── app.py               # Streamlit UI + all user interaction logic
├── rag_chain.py         # Document loading, chunking, embedding, RAG chain
├── data/                # Put your documents here (gitignored)
├── chroma_db/           # Persistent vector database (gitignored)
├── requirements.txt     # Exact dependencies
├── README.md
└── .gitignore
```

## ⚙️ Customization Options

- **Chunk size & overlap** → edit in `rag_chain.py`  
- **Default system prompt** → change in `build_rag_chain()` function  
- **More file types** → add loaders in `load_and_chunk_documents()`  
- **Model** → change `LLM_MODEL` or `EMBEDDING_MODEL` variables

## 🔄 Evolution

This project evolved through three major versions:
- **v1.0** (this repo): Local Streamlit app - perfect for personal use
- **v2.0**: Docker migration with Next.js frontend (experimental)
- **[v3.0](https://github.com/bhargavhegde/KnowBot3.0)**: Production deployment on Vercel/Railway with JWT auth, hybrid search, and multi-user support

## 📄 License

MIT License
