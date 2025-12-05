
# Agentic AI – Day 5  
Building a complete **End-to-End RAG (Retrieval Augmented Generation) system** using **Gemini Flash**, **Gemini Embeddings**, **ChromaDB**, and a fully custom ingestion + querying pipeline.  
This module teaches how to load documents, split them into chunks, embed them, store them in a vector database, and answer questions using retrieved context.

---

## 🚀 Day 5 Overview

### ✔ What You Learned Today  
Day 5 covers the **full workflow of a real RAG system**, including:

- Loading `.txt` documents  
- Splitting documents into overlapping chunks  
- Generating text embeddings  
- Storing vectors in **ChromaDB**  
- Retrieving top-K similar chunks  
- Feeding context to Gemini Flash for final answers  
- Running an interactive RAG chatbot  

You built everything from scratch — no LangChain abstractions.

---

## 📦 Installing Required Libraries
```python
!pip install -q google-generativeai chromadb
````

Installed tools:

* **google-generativeai** → Gemini Flash + Embeddings
* **ChromaDB** → Vector database
* File handling, text cleaning, chunking utilities

---

## 🧱 RAG Components Built Today

### 1️⃣ Configuration Class (`RAGConfig`)

Defines all key system settings:

* Model: `gemini-2.5-flash-lite`
* Embedding model: `text-embedding-004`
* Chunk size: 500
* Overlap: 50
* Vector store collection name

This makes your RAG reusable and easy to tune.

---

## 📂 2️⃣ Custom Text Loader

You created a loader that:

* Reads **single .txt files**
* Reads **multiple files from a directory**
* Stores content + metadata (filename, path)

This allows RAG to ingest real documents from disk.

---

## ✂️ 3️⃣ Custom Text Splitter

A powerful text-splitting module that:

* Cleans text (whitespace, symbols)
* Splits content into sentences
* Builds **overlapping chunks** for better context continuity
* Handles semantic sentence boundaries

Each chunk includes:

* Chunk text
* Chunk ID
* Total chunks available

---

## 🧠 4️⃣ Embedding Manager

Handles all embedding operations using Gemini:

* `embed_text()` – document embeddings
* `embed_query()` – question embeddings
* `embed_batch()` – multiple documents

Uses:

```
models/text-embedding-004
```

This converts text → numerical vectors for semantic search.

---

## 🗃️ 5️⃣ Vector Store (ChromaDB)

A complete vector database pipeline:

* Creates / resets a ChromaDB collection
* Adds document chunks with metadata
* Generates vector IDs
* Stores embeddings, text, and metadata
* Performs semantic search using embedding similarity

Query returns:

* Matching chunks
* Similarity scores
* Metadata (source file, chunk number)

---

## 🤖 6️⃣ Full RAG System Class

The core of your end-to-end pipeline:

### ✔ `ingest_documents()`

* Loads file(s)
* Splits into chunks
* Embeds chunks
* Stores them in ChromaDB

### ✔ `query(question)`

* Embeds user query
* Retrieves top-K documents
* Builds a combined context block
* Creates a prompt
* Sends it to Gemini Flash for final answer

If answer is not found →
**"I cannot answer this based on the provided context."**

---

## 💬 7️⃣ Interactive RAG Mode

You built an interactive console assistant:

* User uploads or chooses a sample document
* RAG system ingests it
* User asks any question
* Model retrieves exact chunks
* Gemini Flash generates answer + source citations

Features:

* `quit`, `exit`, `q` to stop
* Shows chunk previews
* Displays source filenames

---

## 🧪 8️⃣ Example Usage (main function)

The provided example demonstrates:

* Creating a sample AI-theory document
* Ingesting it into RAG
* Asking multiple questions like:

  * "What is machine learning?"
  * "What are the applications of NLP?"
  * "What is the future of AI?"

Each answer includes:

* Model-generated response
* Source chunk references
* Small preview text

---

## 🔍 Concepts Learned Today

### ✔ End-to-End RAG Architecture

From loading documents → splitting → embedding → storing → retrieval → answering.

### ✔ Chunking Strategies

Why overlap improves retrieval quality.

### ✔ Embedding Generation

Using Gemini for both document & query embeddings.

### ✔ Vector Search with ChromaDB

Efficient top-K retrieval with metadata.

### ✔ Context Injection

Providing retrieved text back to the model for grounded answers.

### ✔ Building Interactive RAG Applications

User input → retrieval → reasoning → response.

---

## 🧰 Tools Used Today

* Gemini 2.5 Flash Lite (LLM)
* Gemini text-embedding-004 (Embedding model)
* ChromaDB (Vector store)
* Custom loaders & splitters
* Python (I/O, regex, metadata handling)

```


