🇮🇳 Indian Sign Language Knowledge Assistant (Advanced RAG)

📌 Project Overview

Large Language Models (LLMs) often struggle with localized linguistic nuances, frequently misrepresenting Indian Sign Language (ISL) as a hand-based version of spoken languages such as Hindi or English. In reality, ISL is an independent, natural language with its own grammar, structure, and cultural context.

This project addresses these limitations by implementing an Advanced Retrieval-Augmented Generation (RAG) system.
The system is grounded in a curated knowledge base of 35 factual anchors covering ISL grammar, history, and linguistic identity. By retrieving authoritative content before generating responses, the model eliminates hallucinations and delivers factually grounded, context-aware answers related to Indian Sign Language and the Deaf community.

⸻

🛠️ Tools & Technologies Used

The project is designed for local execution in a Jupyter Notebook or Google Colab environment using the following AI stack:
	•	LangChain / LangChain-Community
Orchestration framework for document loading, vector storage, and retrieval pipelines.
	•	HuggingFace Transformers & HuggingFacePipeline
Used to run embedding and generation models locally on CPU/GPU.
	•	Sentence-Transformers (all-MiniLM-L6-v2)
Lightweight embedding model mapping text into a 384-dimensional dense vector space for semantic similarity.
	•	FAISS (Facebook AI Similarity Search)
High-performance vector database for efficient similarity search and retrieval.
	•	PyPDF
Used to extract and parse text from PDF-based knowledge sources.
	•	Google FLAN-T5-Large
Sequence-to-sequence language model used for answer generation based on retrieved context.

⸻

🚀 How to Run the Notebook

Follow the steps below to execute the project:

1️⃣ Environment Setup
	•	Use Google Colab or a local Jupyter Notebook
	•	Enable GPU runtime (optional but recommended)

2️⃣ Install Dependencies

Run the following command in the notebook:

pip install langchain langchain-community langchain-huggingface faiss-cpu sentence-transformers pypdf

3️⃣ Load Knowledge Base
	•	Upload your PDF knowledge source (e.g., SignLang_RAG.pdf)
	•	The PyPDFLoader automatically extracts text and metadata from the document

4️⃣ Text Chunking
	•	Uses RecursiveCharacterTextSplitter
	•	Chunk size: 400 characters
	•	Chunk overlap: 50 characters
This ensures contextual continuity across document splits.

5️⃣ Vectorization
	•	Generate embeddings using all-MiniLM-L6-v2
	•	Store vectors in a local FAISS index

6️⃣ Query the System

Use the following method to ask questions:

qa_chain.invoke(query)

	•	Retrieves the top 3 most relevant chunks
	•	Generates fact-grounded answers using FLAN-T5

⸻

🎯 Key Features
	•	✅ Fact-grounded responses (no hallucinations)
	•	✅ Accurate representation of ISL as an independent language
	•	✅ Efficient semantic search using FAISS
	•	✅ Fully local execution (privacy-friendly)
	•	✅ Scalable RAG architecture

⸻

🔮 Future Improvements

The current system provides a strong baseline. Planned enhancements include:
	•	Semantic Chunking
Replace fixed-size chunking with embedding-distance-based splitting for better contextual integrity.
	•	Neural Reranking
Two-stage retrieval:
	•	FAISS retrieves top-10 candidates
	•	Cross-Encoder reranker selects the most relevant context
	•	Metadata Filtering
Enable filtering by page number, chapter, or topic for targeted searches.
	•	Interactive UI
Integrate Gradio to provide a chat-based web interface for non-technical users.
	•	Hybrid Search
Combine semantic vector search with BM25 keyword search to improve accuracy for ISL-specific terminology and proper nouns.

⸻

📚 Academic Relevance

This project demonstrates:
	•	Practical application of Retrieval-Augmented Generation
	•	Responsible AI by reducing hallucinations
	•	Language preservation through technology
	•	Accessibility-focused AI system design
