# Intelligent RAG - HR Policy Assistant

An AI-powered HR Policy Assistant built using **Retrieval-Augmented Generation (RAG)**.

The system retrieves relevant information from HR policy documents and uses a Large Language Model (LLM) to generate clear, grounded answers to employee questions.

---

## Overview

This project demonstrates a complete RAG pipeline:

- PDF document loading
- Text chunking
- Semantic embeddings
- FAISS vector database
- Similarity-based retrieval
- Context-aware prompting
- LLM-based answer generation

The project was developed as part of the **NxtWave GenAI Intelligent RAG competition**.

---

## Architecture

```text
HR Policy Documents
        |
        v
Document Loading
        |
        v
Text Chunking
        |
        v
HuggingFace Embeddings
        |
        v
FAISS Vector Database
        |
        v
Similarity Retriever
        |
        v
Relevant Context
        |
        v
Groq LLM
        |
        v
Grounded HR Answer
```

---

## Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| LangChain | RAG pipeline orchestration |
| PyPDF | PDF document loading |
| HuggingFace | Text embeddings |
| FAISS | Vector database and similarity search |
| Groq | LLM inference |
| Jupyter Notebook | Development environment |

---

## Models

### Embedding Model

```text
sentence-transformers/all-MiniLM-L6-v2
```

### LLM

```text
openai/gpt-oss-20b
```

The LLM is accessed through the Groq API.

---

## RAG Pipeline

### 1. Document Loading

HR policy PDF documents are loaded using `PyPDFDirectoryLoader`.

### 2. Text Chunking

The documents are divided into smaller chunks using `RecursiveCharacterTextSplitter`.

Configuration:

```text
Chunk size: 800
Chunk overlap: 100
```

### 3. Embedding Generation

Each text chunk is converted into a numerical vector using:

```text
sentence-transformers/all-MiniLM-L6-v2
```

### 4. Vector Database

The generated embeddings are stored in a FAISS vector database.

### 5. Retrieval

For each employee question, the system retrieves the top 3 most relevant chunks.

```text
Top K = 3
```

### 6. Context Construction

The retrieved document chunks are combined to create the context supplied to the LLM.

### 7. Answer Generation

The retrieved context and employee question are passed to the Groq LLM.

The prompt instructs the model to:

- Use only the provided context
- Answer directly using company policy
- Avoid guessing or making assumptions
- State when the required information cannot be found

---

## Project Structure

```text
Intelligent-RAG-HR-Chatbot/
|
├── code.ipynb
├── requirements.txt
├── README.md
├── .gitignore
└── .env.example
```

The competition dataset, HR policy PDFs, test data, submission files, and API credentials are intentionally excluded from the repository.

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/md-abidhussain/Intelligent-RAG-HR-Chatbot.git
```

### 2. Move into the project directory

```bash
cd Intelligent-RAG-HR-Chatbot
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure the API key

Create a `.env` file in the project directory:

```env
GROQ_API_KEY=your_groq_api_key_here
```

The `.env` file is intentionally excluded from Git using `.gitignore`.

### 5. Run the notebook

Open:

```text
code.ipynb
```

and run the notebook cells in order.

---

## Environment Variable

The project requires:

```text
GROQ_API_KEY
```

A template is provided in:

```text
.env.example
```

**Never commit your actual API key to GitHub.**

---

## Competition Result

The project achieved a:

**Kaggle Public Score: 81.81000**

**Leaderboard Rank: 33**

The score was obtained using the RAG pipeline implemented in this project.

---

## Dataset

The HR policy documents and test data were provided as part of the NxtWave GenAI Intelligent RAG competition.

The competition dataset is **not included in this repository**.

This repository contains only the implementation and configuration required to reproduce the RAG pipeline with the appropriate data and API credentials.

---

## Key Concepts Demonstrated

This project demonstrates practical implementation of:

- Retrieval-Augmented Generation
- Semantic Search
- Text Embeddings
- Vector Databases
- Similarity Retrieval
- Prompt Engineering
- LLM Integration
- LangChain
- FAISS
- HuggingFace Sentence Transformers
- Groq API

---

## Future Improvements

Potential improvements include:

- Build a web-based chat interface
- Add conversation memory
- Implement hybrid search
- Add metadata-based filtering
- Evaluate retrieval quality
- Add answer evaluation metrics
- Add source citations to responses
- Deploy the application as a web service

---

## Author

**Mohd Abid Hussain**

B.Tech Computer Science & Engineering

GitHub:  
https://github.com/md-abidhussain

---

## Disclaimer

This project was created for educational and competition purposes.

The HR policy documents and competition-specific data are not included in this repository.