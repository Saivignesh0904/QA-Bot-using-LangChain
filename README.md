

# QA Bot with LangChain, LLM & Gradio

A question-answering (QA) bot that loads your documents (PDF, DOCX, TXT, etc.), indexes them with embeddings, and answers natural-language questions based **only** on the content of those documents. Built with **LangChain**, an **LLM backend** (IBM watsonx AI), a **vector database**, and a **Gradio** web UI.

---

## ✨ Features

- 🔍 **Document-aware QA** – Answers questions using only your loaded files
- 📚 **Multi-format document loader** – PDFs, Word documents, plain text, etc.
- 🧩 **Smart text chunking** – Splits long documents into meaningful chunks
- 🧠 **Embeddings & vector store** – Semantic search over your docs
- 🔎 **Retriever pipeline** – Retrieves only relevant chunks per query
- 💬 **LLM-powered answers** – Uses a large language model for natural, contextual responses
- 🌐 **Gradio front-end** – Clean web UI for uploading docs and chatting with the bot
- 📈 **Scalable design** – Easily extend with more docs or a different vector database / LLM

---

## 🧱 Architecture Overview

End-to-end flow:

1. **Document Loader**  
   Load source documents (PDF, DOCX, TXT, etc.) into memory.

2. **Text Splitter**  
   Split long documents into smaller, overlapping text chunks to make embedding and retrieval efficient.

3. **Embeddings**  
   Convert each chunk into a numerical vector using an embedding model (OpenAI, watsonx, or other).

4. **Vector Database**  
   Store vectors in a vector store (e.g., FAISS, Chroma, etc.) for efficient similarity search.

5. **Retriever**  
   Given a user question, retrieve top-k most relevant chunks from the vector database.

6. **LLM Question Answering**  
   Feed the retrieved chunks + question into an LLM via LangChain to generate a final answer.

7. **Gradio Front-end**  
   Provide a simple web interface where users:
   - Upload documents
   - Ask questions
   - See answers and (optionally) source snippets

---

## 🧰 Tech Stack

- **Language:** Python
- **Framework:** [LangChain](https://python.langchain.com/)
- **LLM Backend (examples):**
  - OpenAI GPT models
  - IBM watsonx AI LLM and embedding APIs :contentReference[oaicite:1]{index=1}
- **Vector Store:** (example) FAISS / Chroma / other LangChain-compatible store
- **UI:** [Gradio](https://www.gradio.app/)
- **Environment:** `pip` / `virtualenv` / `conda`

> 💡 You can swap the LLM and vector DB as long as they are supported by LangChain.

---


