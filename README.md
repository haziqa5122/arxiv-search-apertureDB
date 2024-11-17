# Semantic Search and Retrieval System for Arxiv Papers

This project enables ingestion and retrieval pipeline for Arxiv papers, facilitating semantic search and integration with a chatbot application. 

---

## Overview

The system is divided into two main processes:

1. **Ingestion Pipeline**  
   - Extracts content and metadata from Arxiv papers.
   - Embeds the extracted content for semantic representation.
   - Stores embeddings and metadata into a vector database for future retrieval.

2. **Retrieval Pipeline**  
   - Handles user queries via a chat app interface.
   - Performs semantic search using embeddings to retrieve relevant documents.
   - Integrates with an LLM to provide contextual and detailed answers.

---

## Architecture

### **Ingestion Pipeline**
1. **Source:**  
   The dataset is a 1.7M papers repository.

2. **Content Parsing:**  
   - The PDF files are processed using [Unstructured.io](https://unstructured.io/), a library for content extraction from PDFs.
   - Metadata is extracted in parallel.

3. **Embedding Generation:**  
   - The extracted text is passed through an embedding model (e.g., OpenAI's embeddings API) to generate vector representations.

4. **Storage:**  
   - Both embeddings and metadata are stored in a vector database (`Aperture DB`).

### **Retrieval Pipeline**
1. **User Interaction:**  
   A user submits a query through a chat app.

2. **Query Embedding:**  
   - The query is converted into an embedding vector using the same embedding model.

3. **Semantic Search:**  
   - The embedding vector is compared with stored document embeddings in the database.
   - Relevant documents are retrieved using similarity metrics.

4. **Response Generation:**  
   - The retrieved documents are passed to a Large Language Model (LLM) for response synthesis.
   - The chatbot returns a contextually rich and user-friendly response.

---

## Components and Tools

- **Data Processing:**  
  - `Unstructured.io` for PDF content extraction.
  - Metadata extraction tools for managing document metadata.

- **Embedding Model:**  
  - OpenAI's embedding model for generating vector representations.

- **Database:**  
  - `Aperture DB`, a vector database for storing embeddings and associated metadata.

- **Chat App Integration:**  
  - An LLM-based chatbot interface for user interaction.

---
