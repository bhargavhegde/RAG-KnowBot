

# KnowBot - Personal RAG Chatbot (100% Local & Private)

A beautiful, fully offline personal knowledge chatbot that lets you chat with your own documents using **Retrieval-Augmented Generation (RAG)**.  
No API keys, no cloud services, no data ever leaves your machine.

![Demo](demo/knowbot_demo.gif)  
*(Add a 30–60 second screen recording here – it dramatically improves first impressions!)*

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
git clone https://github.com/YOUR_USERNAME/knowbot.git
cd knowbot
```

### 4. Create and activate virtual environment

```bash
# Create
python -m venv venv

# Activate (Linux/macOS)
source venv/bin/activate

# Activate (Windows)
venv\Scripts\activate
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
knowbot/
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

## 📌 Future / Nice-to-have Ideas

- Multi-turn conversation memory  
- Hybrid search (dense + BM25 keyword)  
- Reranker (cross-encoder) for better retrieval quality  
- Export/import knowledge base  
- FastAPI backend + React/Vite frontend  
- Evaluation metrics (RAGAS or manual)

## 📄 License

MIT License

---

Made with ❤️ for privacy, learning, and local AI  
Feel free to ⭐ the repo if you find it useful!
```
