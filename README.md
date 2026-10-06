# Intelligent RAG - HR Policy Assistant

An AI-powered HR assistant built using Retrieval-Augmented Generation (RAG).

The system retrieves relevant information from HR policy documents and uses an LLM to generate grounded answers to employee questions.

## Project Overview

This project implements a complete Retrieval-Augmented Generation pipeline:

1. Document Loading
2. Text Chunking
3. Embedding Generation
4. Vector Database Creation
5. Similarity Retrieval
6. LLM Generation
7. RAG Chain
8. Answer Generation

The project was developed as part of the NxtWave GenAI Intelligent RAG competition.

## Architecture

HR Policy Documents
        ↓
Document Loading
        ↓
Text Chunking
        ↓
HuggingFace Embeddings
        ↓
FAISS Vector Database
        ↓
Retriever
        ↓
Relevant Context
        ↓
Groq LLM
        ↓
Grounded HR Answer

## Tech Stack

- Python
- LangChain
- HuggingFace Sentence Transformers
- FAISS
- Groq
- PyPDF
- Jupyter Notebook

## Models

### Embedding Model

`sentence-transformers/all-MiniLM-L6-v2`

### LLM

`openai/gpt-oss-20b` through Groq

## RAG Pipeline

### 1. Document Loading

HR policy documents are loaded using `PyPDFDirectoryLoader`.

### 2. Chunking

Documents are divided into smaller chunks using:

- Chunk size: 800
- Chunk overlap: 100

### 3. Embeddings

Each chunk is converted into a vector using the HuggingFace embedding model.

### 4. Vector Database

FAISS stores the document embeddings and enables similarity search.

### 5. Retrieval

The system retrieves the top 3 relevant document chunks for each question.

### 6. Generation

The retrieved context is passed to the Groq LLM.

The prompt instructs the model to answer only using the retrieved HR policy information.

## Environment Setup

Create a `.env` file in the project directory:

```env
GROQ_API_KEY=your_groq_api_key

Never commit your `.env` file or API key.

## Installation

Clone the repository:
```
git clone https://github.com/YOUR-USERNAME/intelligent-rag-hr-chatbot.git
```

Move into the project:
```
cd intelligent-rag-hr-chatbot
```

Install dependencies:
```
pip install -r requirements.txt
```

Create your `.env` file and add your Groq API key.

Then open:
```
code.ipynb
```

and run the notebook.

## Competition Result

Kaggle Public Score:

**81.81000**

The project achieved a public leaderboard rank of **33** at the time of submission.

## Dataset

The competition dataset and test files are not included in this repository.

They were provided separately as part of the NxtWave competition.

## Future Improvements

- Add a web-based chat interface
- Add conversation memory
- Improve retrieval with hybrid search
- Add metadata filtering
- Add retrieval evaluation
- Add response evaluation metrics
- Deploy the application