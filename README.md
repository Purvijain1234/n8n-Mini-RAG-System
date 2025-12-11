# 📄 n8n Simple RAG Model (Retrieval-Augmented Generation)

A lightweight RAG system built completely inside **n8n**.  
This workflow allows you to upload files from Google Drive, split and embed the content using HuggingFace embeddings, store vectors in **Pinecone**, and answer questions using **Google Gemini** with retrieved context.

---

## 🚀 Features
- Fetch documents from Google Drive
- Chunk text using a recursive text splitter
- Generate embeddings with HuggingFace
- Store & retrieve vectors using Pinecone
- Use Gemini AI to answer questions with context
- Clean and modular n8n workflow divided into:
  - **RAG Pipeline (Ingestion)**
  - **Answer Pipeline (Querying)**

---

## 🧩 Workflow Overview

### **1. RAG (Document Ingestion Pipeline)**
This workflow runs when you click *Execute Workflow*.

Steps:
1. Search files/folders in Google Drive  
2. Download selected file  
3. Load document content  
4. Split text into chunks  
5. Generate embeddings using HuggingFace  
6. Store vectors in Pinecone Vector Store  

This prepares your knowledge base.

---

### **2. Answer (Query Pipeline)**
This workflow runs when a chat message is received.

Steps:
1. User sends a question  
2. AI Agent receives the query  
3. Pinecone searches for the most relevant chunks  
4. Retrieved context is passed into Gemini Chat Model  
5. AI generates an accurate, context-aware answer  

---

## 🛠️ Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/your-username/n8n-simple-rag.git
```
2. Set up n8n
Install n8n locally or use n8n Cloud.

Installation guide: https://docs.n8n.io/hosting/installation/

3. Import Workflow(s)
Import the RAG and Answer workflows from the /workflows/ folder.

Includes:

Google Drive search & download

Document loader

Text splitter

HuggingFace embeddings

Pinecone vector store

Gemini chat model answering pipeline

4. Configure Credentials
Inside n8n, add:

Google Drive Credential

Pinecone API Key

HuggingFace Embedding Model

Google Gemini API Key

Make sure to connect them to each node.

5. Customize the Workflow
You can modify:

Chunk size in text splitter

Embedding model

Pinecone index name

Gemini prompt instructions

All changes can be made directly inside n8n.

6. Run the Workflow
Run RAG workflow manually to ingest documents

Use chat trigger to ask questions

OR connect it to WhatsApp/Telegram API

🖼️ Workflow Diagram
(Based on your screenshot)

📥 RAG Pipeline
pgsql
Copy code
Execute → Search Files → Download File → Data Loader → Text Splitter → Embeddings → Pinecone Vector Store
💬 Answer Pipeline
mathematica
Copy code
Chat Trigger → AI Agent → (Memory + Pinecone Vector Query) → Gemini Model → Answer
📚 Tech Stack
n8n (Workflow Automation)

HuggingFace Embeddings

Recursive Text Splitter

Pinecone Vector DB

Google Gemini Chat Model

📌 Use Cases
Personal knowledge base

FAQ bot

Document question-answering

Automated note search

Project-specific AI assistant

📝 License
MIT License

👩‍💻 Author
Purvi Jain
LinkedIn: https://www.linkedin.com/in/purvi-jain-315683326
