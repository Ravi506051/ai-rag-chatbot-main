# AI RAG Chatbot

A modular document-question-answering project that demonstrates how ingestion, retrieval, query handling and response generation can be separated into distinct components.

## Supported document types
The original project documentation lists PDF, DOCX, PPTX, CSV and TXT inputs. Confirm parser availability for each format in the current source code.

## Core workflow
1. Ingest and parse a document.
2. Normalize extracted content into text chunks.
3. Generate vector embeddings.
4. Retrieve relevant content for a user query.
5. Pass the retrieved context to the response-generation component.
6. Return an answer through the command-line interface.

## Technology
Python · Hugging Face Sentence Transformers · Embeddings · Retrieval-Augmented Generation

The repository documentation describes a mock LLM option for local workflow testing without a provider API key.

## Setup
```bash
git clone https://github.com/Ravi506051/ai-rag-chatbot-main.git
cd ai-rag-chatbot-main
python -m venv .venv
# Windows: .venv\\Scripts\\activate
pip install -r requirements.txt
```
Run the entry point documented in the repository after installing dependencies.

## Engineering notes
Keep ingestion and retrieval independently testable. Evaluate retrieval relevance separately from answer quality, handle unsupported questions gracefully, and avoid exposing private document text in logs.

## Future improvements
Add persistent vector storage, source references, configurable embedding models and automated tests for different file types.

## Maintainer
**Ravi Kumar Rao** · [GitHub](https://github.com/Ravi506051)
