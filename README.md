# rag-python-doc-bot

# Python Documentation Q/A Bot using Retrieval Augmented Generation (RAG)

## Project Purpose
This beginner-friendly project implements a **RAG-based Question Answering bot** that retrieves knowledge from the official Python documentation website and generates accurate, context-grounded answers using a Transformer LLM.

The goal is to understand the full working of:
- **Semantic search**
- **Embeddings**
- **Vector databases**
- **Retrieval + generation grounding**
- **LLM prompt augmentation**

## How RAG Works (Simple Explanation)
RAG (Retrieval Augmented Generation) makes an AI behave like an **open-book exam solver**:
1. It first **reads a knowledge source** (your website — here Python docs)
2. It **splits the text into small chunks**
3. It **converts chunks into meaning-vectors** using embeddings
4. It stores them in a **vector database** (ChromaDB)
5. When you ask a question, it:
   - **Searches the DB for relevant info by meaning**
   - **Injects that info into the prompt**
   - **LLM answers using only that retrieved context**

So yes — instead of guessing from memory, the bot answers based on your website knowledge.

## Tech Stack Used
- `LangChain Community` → Loads website text & manages retrieval interface
- `sentence-transformers/all-MiniLM-L6-v2` → Creates semantic embeddings
- `ChromaDB` → Vector database for storing & searching knowledge chunks
- `Flan-T5-Base` LLM → Generates grounded Q/A answers
- `Google Colab` → Development and learning environment
- `GitHub` → Project hosting and portfolio visibility

## What This Project Demonstrates
- Website scraping as knowledge source
- Document chunking with overlap
- Embedding creation (text → vectors)
- Vector DB storage & semantic retrieval
- LLM prompt augmentation for grounded answers
- End-to-end RAG pipeline flow

## Example
**Q:** What are Python lists?  
**A:** A list is a compound, versatile data structure written inside square brackets `[ ]`, holding comma-separated items that can be of same or mixed data types.

## Setup Instructions (Run in Colab)
```python
!pip install langchain langchain-community chromadb sentence-transformers transformers accelerate
