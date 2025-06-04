# 🧠 Retrieval-Augmented Medical QA Chatbot

A **domain-specific, context-aware medical chatbot** that leverages **Retrieval-Augmented Generation (RAG)** by combining **FAISS-based document retrieval** and **Mistral-7B-Instruct** via HuggingFace. Built using **LangChain**, it serves medical answers grounded in a curated knowledge base — ideal for healthcare assistants, research Q&A systems, or intelligent triage bots.

---

## 📌 Table of Contents

- [Demo](#demo)
- [Features](#features)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Example Output](#example-output)
- [Project Structure](#project-structure)
- [Future Work](#future-work)
- [License](#license)
- [Author](#author)

---

## 🚀 Demo

> 💬 Example Query:
> ```
> Write Query Here: What are the symptoms of dengue?
> ```

> ✅ Output:
> ```
> Common symptoms of dengue include high fever, severe headaches, pain behind the eyes, joint and muscle pain, fatigue, nausea, skin rashes, and mild bleeding such as nose or gum bleed.
> ```

---

## ✅ Features

- 🔍 **Semantic Retrieval**: FAISS-based search using medical domain embeddings.
- 🧠 **LLM-Powered Answering**: Uses Mistral-7B-Instruct via HuggingFace Inference API.
- 💬 **Context-Aware QA**: Answers generated only from retrieved context to ensure factuality.
- 🛡️ **Safe Prompting**: Refuses to hallucinate or provide unverifiable information.
- ⚙️ **Custom Prompt Templates**: Controls response behavior with precision.
- 📁 **Local Vector Store**: Easily replaceable with your own medical documents.

---

## 🧱 Architecture

User Query
│
▼
Retriever (FAISS Vector Store)
│ (Semantic Similarity Search)
▼
Relevant Chunks from Knowledge Base
│
▼
LLM (Mistral-7B-Instruct via HuggingFace Endpoint)
│ (Prompt + Context → Answer)
▼
Final Response

---

## 🧰 Tech Stack

| Component        | Technology                                 |
|------------------|---------------------------------------------|
| LLM              | HuggingFace `mistralai/Mistral-7B-Instruct-v0.3` |
| Framework        | LangChain                                  |
| Retrieval Engine | FAISS                                       |
| Embeddings       | `sentence-transformers/all-MiniLM-L6-v2`    |
| Language         | Python                                      |
| Environment      | `python-dotenv`, `venv`, `.env`             |

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

git clone https://github.com/your-username/retrieval-augmented-medical-qa-chatbot.git
cd retrieval-augmented-medical-qa-chatbot

2. Create & Activate a Virtual Environment

python -m venv .venv
.venv\Scripts\activate         # On Windows
# or
source .venv/bin/activate     # On Linux/macOS

3. Set Your HuggingFace API Token

Create a .env file in the root directory:
HF_TOKEN=your_huggingface_api_token_here

Example Output:
Write Query Here: What is hypertension?

RESULT:
Hypertension, or high blood pressure, is a chronic medical condition where the force of blood against the artery walls is too high. It can lead to heart disease, stroke, and other complications if untreated.

Project Structure

├── connect_memory_with_llm.py        # Main script to run the chatbot
├── vectorstore/
│   └── db_faiss/                     # FAISS vector index and metadata
├── .env                              # HuggingFace token
├── requirements.txt
├── README.md

Future Work

Add curated public medical datasets (e.g., PubMed, Medline)

Support multilingual medical queries

 Add user feedback and query logging

 Author:
 Pranjal Srivastava
 M.Tech, IIIT Allahabad
