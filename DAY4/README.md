
# Agentic AI – Day 4
Learning text embeddings, semantic search, and vector databases.  
This module focuses on embedding text using both Gemini and HuggingFace models and performing semantic search with ChromaDB.

---

## 🚀 Day 4 Overview

### ✔ What You Learned Today
Day 4 introduces **embeddings**, **vector databases**, and **semantic search**.  
You generated embeddings using two models (Gemini + HuggingFace) and performed similarity search using **ChromaDB**.

---

## 📦 Installing Required Libraries
```python
!pip install langchain chromadb sentence-transformers langchain-google-genai google-generativeai
````

Installed tools for:

* Text embeddings
* Vector databases
* Google Gemini
* Open-source HuggingFace models

---

## 📝 Preparing the Data

### ✔ Sample Documents

A small set of text documents was created for testing semantic search.

### ✔ User Query

Defined a query that will be embedded and compared with the documents.

This helps measure how similar each document is to the user query.

---

## 🤖 Text Embeddings

### 🔹 1. Gemini Embeddings

Using **GoogleGenerativeAIEmbeddings** with model:

```
text-embedding-004
```

Generated embeddings for:

* All documents
* User query

### 🔹 2. HuggingFace Embeddings

Using open-source `all-MiniLM-L6-v2` from SentenceTransformers.

This allowed comparing:

* Proprietary vs open-source embeddings
* Speed, size, and quality differences

---

## 🗂 Vector Database – ChromaDB

### ✔ Initialization

A ChromaDB collection was created to store:

* Document text
* Metadata
* Vector embeddings

A wrapper was used so ChromaDB could call Gemini for embedding generation.

### ✔ Adding Documents

Each document (with ID + metadata) was inserted into the vector store.

This enables fast semantic search instead of manually comparing vectors.

---

## 🔍 Semantic Search & Similarity

### ✔ Cosine Similarity (Manual)

You calculated cosine similarity manually between:

* Query embedding
* Each document embedding

This shows how semantic similarity works mathematically.

### ✔ ChromaDB Semantic Query

You performed:

```python
collection.query(query_texts=[query], n_results=2)
```

ChromaDB returned:

* The most relevant documents
* Their similarity scores
* Metadata

Demonstrating efficient **vector-based document retrieval**.

---

## 🧠 Concepts Learned Today

* What embeddings are and why they are used
* Difference between Gemini embeddings vs HuggingFace embeddings
* How semantic similarity works
* How cosine similarity is computed
* Importance of vector databases (ChromaDB)
* How to perform semantic search efficiently

---

## 🧰 Tools Used Today

* Google Gemini (text-embedding-004)
* HuggingFace SentenceTransformer
* ChromaDB
* LangChain

```

