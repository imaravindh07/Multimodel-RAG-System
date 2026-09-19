# Multimodal RAG System

A **Multimodal Retrieval-Augmented Generation (RAG)** system that enables question answering over PDF documents containing **text, tables, headings, and images**.

The system extracts different types of content from a PDF, processes and chunks the extracted information, creates embeddings, stores them in **ChromaDB**, retrieves relevant context for a user query, and uses **Google Gemini** to generate an answer.

## Features

- 📄 PDF document processing
- 📝 Text and heading extraction
- 📊 Table extraction
- 🖼️ Image extraction and processing
- 🔍 Semantic similarity search
- 🧠 Multimodal RAG pipeline
- 🤖 Google Gemini for response generation
- 🗄️ ChromaDB for vector storage
- 🔢 Sentence Transformer embeddings
- 📦 Exported document chunks for inspection

## Tech Stack

- **Python**
- **LangChain**
- **Google Gemini API**
- **Unstructured**
- **ChromaDB**
- **Sentence Transformers**
- **Tesseract OCR**
- **Poppler**

## How It Works

The system follows a multimodal RAG pipeline:

```text
PDF Document
     ↓
Content Extraction
     ↓
Text / Tables / Images
     ↓
Chunking & Processing
     ↓
Embeddings
     ↓
ChromaDB
     ↓
User Query
     ↓
Relevant Context Retrieval
     ↓
Google Gemini
     ↓
Generated Answer
```

### 1. Document Processing

The PDF is processed using **Unstructured** to extract and identify different document elements, including text, titles, tables, and images.

### 2. Chunking

The extracted content is divided into meaningful chunks to preserve context and improve the effectiveness of retrieval.

### 3. Embeddings

Text chunks are converted into vector embeddings using the **all-MiniLM-L6-v2** Sentence Transformer model.

### 4. Vector Storage

The generated embeddings are stored in **ChromaDB**, enabling semantic similarity-based retrieval.

### 5. Retrieval

When a user submits a query, the system searches the vector database and retrieves the most relevant chunks from the document.

### 6. Generation

The retrieved context is passed to **Google Gemini**, which generates a context-aware response based on the retrieved information.

## Project Structure

```text
Multimodel-RAG-System/
│
├── app.ipynb
├── chunks_export.json
├── data/
│   └── uploads/
│       └── attention-is-all-you-need.pdf
│
├── .gitignore
└── README.md
```

> The generated ChromaDB files and Python virtual environment are excluded from the repository using `.gitignore`.

## Example Use Case

The project uses the research paper **"Attention Is All You Need"** as the source document.

The system can retrieve relevant information from the paper and use the retrieved context to answer questions related to its content.

## Author

**Aravind Kumar Devasani**

B.Tech — Information Technology

GitHub: [imaravindh07](https://github.com/imaravindh07)
