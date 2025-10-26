# 🧠 Document Q&A using LangChain, FAISS & AWS Bedrock

Chat with your **PDF documents** using **Retrieval-Augmented Generation (RAG)** powered by **LangChain**, **FAISS**, and **AWS Bedrock**.  
This app uses **Titan embeddings** to index your documents and lets you query them using **Claude 3 Haiku** or **Llama 3** models — all through a simple **Streamlit** interface.

---

## 🚀 Features

- 📄 Upload and query **PDF documents**
- 🔍 Retrieve context with **FAISS vector store**
- 🧩 Generate embeddings using **Amazon Titan**
- 💬 Chat with **Claude 3 Haiku (Anthropic)** or **Llama 3 Instruct (Meta)**
- ⚡ Built with **Streamlit** for an interactive web UI
- 🪣 Fully runs on **AWS Bedrock** — no OpenAI API keys required

---

## 🧰 Tech Stack

| Component | Technology |
|------------|-------------|
| Framework | [Streamlit](https://streamlit.io/) |
| LLMs | Claude 3 Haiku / Llama 3 70B via [AWS Bedrock](https://aws.amazon.com/bedrock/) |
| Embeddings | Amazon Titan Text-Embed-V2 |
| Vector Store | FAISS |
| LangChain Modules | Text splitter, document loader, retrieval chain |

---

## 🏗️ Architecture Overview

            ┌────────────────────────────┐
            │        PDF Loader           │
            └────────────┬───────────────┘
                         │
             Split into chunks (LangChain)
                         │
            ┌────────────▼───────────────┐
            │ Titan Embeddings (AWS)     │
            └────────────┬───────────────┘
                         │
                Store vectors in FAISS
                         │
            ┌────────────▼───────────────┐
            │ Retriever + LLM (RAG)      │
            │ Claude 3 / Llama 3 on AWS  │
            └────────────┬───────────────┘
                         │
                 Streamlit Web UI

Create a Virtual Environment
python -m venv venv
# On macOS/Linux
source venv/bin/activate
# On Windows
venv\Scripts\activate

Install Dependencies
pip install -r requirements.txt

You need AWS access keys with Bedrock permissions:
aws configure


