# AI RAG Chatbot

A smart chatbot that can read and understand different types of documents (**PDF, DOCX, PPTX, CSV, TXT**) and answer questions using **RAG (Retrieval-Augmented Generation)** principles.

This project uses:
- Python Agents (Ingestion, Retrieval, Query, LLM)
- HuggingFace Embeddings (via `sentence-transformers`)
- Mock LLM to simulate response generation
- Supports multiple file formats

---

## Features

- Multi-document support: PDF, DOCX, PPTX, CSV, TXT
- Agent-based architecture using message passing
- Vector embeddings using HuggingFace
- MockLLM included (no API key needed)
- Simple CLI-based interaction
- Modular design for easy extension

---

## Project Folder Structure

ai-rag-chatbot/
│
├── agents/
│ ├── ingestion_agent.py
│ ├── retrieval_agent.py
│ ├── query_agent.py
│ └── llm_response_agent.py
│
├── utils/
│ └── file_parser.py
│
├── data/
│ ├── sample.pdf
│ ├── sample.docx
│ ├── sample.pptx
│ ├── sample.csv
│ └── sample.txt
│
├── main.py
├── requirements.txt
└── README.md


---

## How to Run This Project

### 1. Clone the Repository

git clone https://github.com/your-username/ai-rag-chatbot.git
cd ai-rag-chatbot

### 2. Create Virtual Environment

python -m venv venv


### 3. Activate Virtual Environment

On Windows:
venv\Scripts\activate

On Mac/Linux:
source venv/bin/activate


### 4. Install Requirements

pip install -r requirements.txt

### 5. Run the App

python main.py

---

## Sample Output

===============================
Processing file: data/sample.pdf
[IngestionAgent] Reading file: data/sample.pdf
[RetrievalAgent] Received message from IngestionAgent
[QueryAgent] Received user query

Final LLM Answer:
Based on the document: "Quarter 1 KPIs Report Revenue increased by 20% from last quarter. Customer retention rate was 87%..."
Answer to your question "What is the customer retention rate?" is summarized above.

---

## Notes

This project uses **MockLLM** to avoid OpenAI or API integration since it’s for demo/evaluation purposes.  
You can easily switch to OpenAI or other providers by updating the `llm_response_agent.py` agent.

---

## Tech Stack

- Python 3.10+
- sentence-transformers
- PyMuPDF
- python-docx
- python-pptx
- pandas
- torch

---

## Author

**Sree Gnyana Dhathri Paladi**

- GitHub: [dhathri-paladi](https://github.com/dhathri-paladi)  
- LinkedIn: [paladisreegnyanadhathri09](https://www.linkedin.com/in/paladisreegnyanadhathri09/)

## 🎥 Demo Video  
[Click here to watch the demo video](https://drive.google.com/file/d/16upra9j1sT13jJVnLWaAgYHPvI0H1AI3/view?usp=sharing)

---

## Challenges Faced

- Parsing multiple document formats consistently
- Handling smooth message passing between agents
- Aligning the Streamlit UI with backend logic
- Managing Git version control and push issues

## Future Improvements

- Integrate real LLM (e.g., OpenAI GPT or Claude) instead of mock responses
- Add upload history & query logging
- Improve document retrieval using hybrid or semantic search methods
- Add voice input/output and chat history persistence
- 

## 📈 Future Improvements

- Integrate a real Large Language Model (LLM) for improved answer generation
- Add a user-friendly web interface for document uploads and chat
- Improve document retrieval using hybrid search and reranking
- Add source citations so users can verify answers against original documents
- Evaluate retrieval quality and answer correctness using suitable metrics

## 🧪 Testing and Evaluation

Test the chatbot with different supported document types and questions. Verify that retrieved passages are relevant and that generated answers are consistent with the source documents.

## ⚠️ Limitations

- Answer quality depends on document parsing and retrieval accuracy.
- Generated responses should be verified against the original documents.
- MockLLM mode is intended for demonstration and does not provide the capabilities of a production LLM.

## 👨‍💻 Maintainer

Ravi Kumar Rao

GitHub: https://github.com/Ravi506051

## Retrieval and Answer Quality Checks

Test ingestion separately for each supported file type and include documents with tables, long passages, and unusual formatting. For each test question, inspect the retrieved passages and verify that the generated answer is supported by them. Include questions with no answer in the source and ensure the system can state that the information was not found.

## Extension Ideas

Useful next steps include adding source references to answers, testing retrieval precision on a small question set, and replacing the mock response component only after documenting the chosen model and its configuration. Do not describe mock responses as production LLM output.

## Project Development Notes

Test each file parser independently and inspect retrieved chunks before trusting an answer. Clearly distinguish mock response generation from a real LLM integration.

For reproducible updates, record the dataset or upstream version, environment and dependency versions, configuration, and actual outputs from each run. Keep illustrative examples clearly labelled and never commit credentials or private data.

### Technical Deep Dive

Keep ingestion, retrieval, query handling, and response generation as separate stages with explicit input/output contracts. Parse each supported format independently, normalize extracted text, attach document and page metadata to chunks, and verify retrieval before passing context to the response component. Since this repository documents a MockLLM, distinguish deterministic demo output from responses generated by a real language model.

Suggested engineering checks: include malformed and empty files in parser tests, test questions whose answers are missing, cap file size and token volume, and prevent one user's uploaded documents from appearing in another user's retrieval results.

## RAG Quality and Extension Notes

- The current README describes a MockLLM demonstration; clearly distinguish simulated responses from a production LLM integration.
- Evaluate document parsing and retrieval separately from response generation.
- Test supported file types with empty files, malformed documents, long documents, and documents containing tables.
- Measure retrieval relevance and answer faithfulness on a fixed document-question set; verify answers against source passages.
- Before adding a live LLM, document provider configuration, protect API keys, and handle rate limits and provider errors safely.

## RAG Pipeline Engineering

- Separate document ingestion, text normalization, chunking, embedding, vector retrieval, and answer generation.
- Store metadata with each chunk to support source attribution, filtering, and traceable responses.
- Tune chunk size, overlap, retrieval count, and similarity thresholds using a repeatable evaluation set.
- Measure retrieval relevance and answer faithfulness independently rather than relying only on fluent responses.
- Protect API keys and avoid logging private document contents unnecessarily.

## RAG Pipeline Verification

- Test ingestion, parsing, chunking, embedding, retrieval, and response generation as separate stages.
- Include malformed files, empty documents, unsupported formats, and very large documents in the test set.
- Evaluate retrieval relevance independently from answer quality and avoid answering when retrieved context does not support a claim.
- Document the actual parser and embedding model used; keep sample documents free of personal or confidential information.
