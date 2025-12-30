# ⚖️ LexiBot — Legal Document Question Answering Chatbot (RAG)

**LexiBot** is a Retrieval-Augmented Generation (RAG) based legal chatbot built in Python.

It allows users to upload legal documents (PDFs) and ask natural-language questions, returning accurate, grounded answers strictly derived from the uploaded content. The system is designed to be fast, hallucination-resistant, demo-ready, and production-oriented.

---

## ✨ Key Features

* **📄 PDF Parsing:** Upload and parse complex legal documents.
* **🔍 Semantic Search:** High-precision retrieval using vector embeddings.
* **🧠 LLM Synthesis:** Context-aware answer generation via RAG.
* **🛑 Hallucination Control:** Strict "context-only" answers to ensure legal reliability.
* **💬 Clean UI:** Built with Gradio for a notebook-native, user-friendly interface.
* **⚡ Optimization:** Tailored for Google Colab GPU or 8GB RAM CPU systems.
* **📊 Formatted Responses:** Presentation-ready outputs.

---

## 🏗️ Architecture Overview



1.  **User Query**
2.  **Embedding Model** (Converts query to vector)
3.  **Vector Similarity Search** (LlamaIndex identifies relevant text)
4.  **Relevant Document Chunks** (Context extraction)
5.  **LLM Answer Synthesis** (Generates response based *only* on context)
6.  **Grounded Legal Answer**

> **Note:** LexiBot is a true RAG system — the LLM never answers without retrieved document context.

---

## 🛠️ Tech Stack

### Core
* **Language:** Python (≥ 3.10)
* **RAG Framework:** LlamaIndex
* **PDF Parsing:** PyPDF
* **Transformers:** Hugging Face

### Models
| Environment | LLM | Embeddings |
| :--- | :--- | :--- |
| **Google Colab (GPU)** | `Qwen/Qwen2-7B-Instruct` (4-bit) | `BAAI/bge-base-en-v1.5` |
| **Local Machine (CPU)** | `TinyLlama/TinyLlama-1.1B-Chat-v1.0` | `sentence-transformers/all-MiniLM-L6-v2` |

### UI
* **Gradio:** Notebook-native web interface.

---

## 📦 Installation

### Google Colab (Recommended)
1. Set **Runtime** → **Change runtime type** → **GPU**.
2. Install dependencies:
```bash
pip install llama-index llama-index-embeddings-huggingface llama-index-llms-huggingface transformers accelerate sentence-transformers pypdf bitsandbytes gradio
