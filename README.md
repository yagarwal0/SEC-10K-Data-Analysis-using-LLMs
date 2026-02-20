# BLS Case Study – RAG, Multi‑Query Reasoning & API Integration

## Overview

This case study demonstrates an end‑to‑end **LLM application pipeline** combining **Retrieval‑Augmented Generation (RAG)**, **query decomposition**, and **external API integration**. The notebook is organized into three problems that progressively showcase document understanding, reasoning over complex queries, and real‑time data retrieval.

---

## Repository Structure

* `BLS_Assignment.ipynb` – Main notebook containing all experiments and results
* `data/` – PDF documents used for RAG (company annual reports)
* `README.md` – Project documentation

---

## Tech Stack

* Python
* LangChain
* OpenAI (LLM + Embeddings)
* ChromaDB (Vector Store)
* RapidAPI (Stock Market Data)
* Requests

---

## Problem 1: Document Question Answering using RAG

### Objective

Enable question answering over company annual reports using a retrieval‑augmented pipeline.

### Approach

1. Load multi‑page PDF documents.
2. Split documents into overlapping text chunks.
3. Generate embeddings for each chunk.
4. Store embeddings in a vector database.
5. Retrieve the top‑k most relevant chunks for a query.
6. Use an LLM to generate grounded answers.

### Key Features

* Chunk size: **1000 characters**
* Overlap: **200 characters**
* Top‑5 relevant chunks retrieved
* Dynamic extraction of **company name** and **year** from user queries

---

## Problem 2: Multi‑Part Query Handling

### Objective

Handle complex queries that involve **comparison or multiple sub‑tasks**.

### Approach

* Decompose a complex query into multiple atomic sub‑queries.
* Execute each sub‑query independently using the RAG pipeline.
* Aggregate and present structured results.

### Example

**Query:**

> Compare Amazon and Google revenue in 2022

**Steps:**

* Extract entities (Amazon, Google)
* Generate individual queries per entity
* Run retrieval and response generation
* Combine outputs into a comparative answer

---

## Problem 3: Real‑Time Stock Information using API

### Objective

Fetch and present **live and historical stock market data** based on user intent.

### Approach

* Detect user intent (current price vs timeline data).
* Query stock data via RapidAPI.
* Parse and format raw API responses.
* Present structured financial metrics.

### Extracted Information

* Current price
* Day high & low
* Percentage change
* Historical timeline (when requested)

---

## Setup Instructions

### 1. Install Dependencies

```bash
pip install langchain langchain-community langchain-openai chromadb requests
```

### 2. API Keys

Set the following environment variables:

```bash
export OPENAI_API_KEY="your_openai_key"
export RAPID_API_KEY="your_rapidapi_key"
```

### 3. Run the Notebook

```bash
jupyter notebook BLS_Assignment.ipynb
```

---

## Highlights

* Modular and extensible architecture
* Clear separation of retrieval, reasoning, and action
* Demonstrates practical LLM application design
* Combines static knowledge (PDFs) with dynamic data (APIs)

---

## Future Improvements

* Add evaluation metrics for RAG accuracy
* Cache API responses for efficiency
* Extend support to more document formats
* Add UI using Streamlit or Gradio

---

## Author

**Yash**
M.Tech Computer Science | LLMs | RAG | Applied AI

---

## License

This project is for educational and case‑study purposes.
