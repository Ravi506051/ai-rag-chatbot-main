# AI RAG Chatbot

A modular document-question-answering project demonstrating how document ingestion, text processing, semantic retrieval, and response generation work together in a Retrieval-Augmented Generation (RAG) pipeline.

## Supported Inputs
The project documentation lists PDF, DOCX, PPTX, CSV, and TXT files. Availability depends on the parsers configured in the current source code.

## Architecture
```text
Documents → Parsing → Text Cleaning → Chunking
          → Embeddings → Vector Retrieval
          → Context Assembly → Answer Generation
```

## Core Features
- Document ingestion and text extraction.
- Text chunking for retrieval.
- Embedding generation with Sentence Transformers.
- Semantic retrieval of relevant passages.
- Context-grounded response generation.
- Mock LLM option for local workflow testing, as described by the project.

## Technology
Python · Hugging Face Sentence Transformers · Embeddings · RAG · NLP

## Setup
```bash
git clone https://github.com/Ravi506051/ai-rag-chatbot-main.git
cd ai-rag-chatbot-main
python -m venv .venv
# Windows: .venv\Scripts\activate
pip install -r requirements.txt
```
Run the entry point documented in the repository after installing its dependencies.

## Evaluation
Evaluate retrieval quality separately from answer quality. Useful checks include retrieval relevance, answer faithfulness, response latency, and behaviour when the documents do not contain the answer.

## Future Improvements
- Add persistent vector storage and source-level citations.
- Add automated tests for supported file formats.
- Compare embedding models and chunking strategies.
- Add document access controls and privacy-aware logging.

## Maintainer
**Ravi Kumar Rao** · [GitHub](https://github.com/Ravi506051)
