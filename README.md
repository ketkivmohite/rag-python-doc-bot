# Python Documentation Q/A Bot using Retrieval Augmented Generation (RAG)

## Overview
This project implements a simple and fully working **Retrieval Augmented Generation (RAG) Question Answering pipeline** that retrieves knowledge from the official **Python 3 Tutorial documentation website** and generates **grounded, context-based answers** using a lightweight open Transformer LLM.

The bot behaves like an **open-book assistant** — it first retrieves the most relevant documentation sections by meaning (semantic search) and then answers only from that context instead of relying on model memory or guessing.

## What This RAG Pipeline Does
- Loads text content from Python documentation webpages  
- Splits the content into small overlapping chunks  
- Converts chunks into **semantic embeddings (meaning vectors)**  
- Stores vectors in **ChromaDB (local vector database)**  
- Retrieves the most relevant chunks for a user question using **semantic similarity search**  
- Injects retrieved context into the LLM prompt  
- Generates a grounded answer using **google/flan-t5-base** (open, instruction-tuned model)

## RAG Build Steps (In Words Only)
Load docs → Chunk text → Create embeddings → Store vectors → Retrieve relevant chunks → Answer from context only

## Tech Stack
- **LangChain Community** → Document loading & retriever interface  
- **Sentence Transformers** → `all-MiniLM-L6-v2` embedding model  
- **ChromaDB** → Vector storage & semantic search  
- **Hugging Face Transformers** → `flan-t5-base` LLM for grounded Q/A  
- **PyTorch** → Model acceleration (CPU/GPU auto-handled)  
- **Google Colab** → Development & pipeline prototyping  
- **GitHub** → Project hosting & portfolio visibility  

## Example Query
**Question:** What are Python lists?  
**Answer:** A list is a versatile compound data structure written inside square brackets `[ ]` that holds comma-separated items and can contain the same or mixed data types.

## Installation (For Google Colab)
```python
!pip install langchain-community chromadb sentence-transformers transformers accelerate torch
