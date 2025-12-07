# RAG-Chatbot-using-LangChain-FAISS-HuggingFace-model

This project demonstrates a simple and efficient Retrieval-Augmented Generation (RAG) pipeline built using:

LangChain (Community + Core)

FAISS Vector Store

HuggingFace Text Embeddings

HuggingFace LLM Endpoint

PDF document ingestion

LCEL (LangChain Expression Language) for chain composition

The system loads PDF documents, splits them into chunks, embeds them, builds a FAISS vector database, retrieves the most relevant chunks, and passes them to a HuggingFace LLM to generate accurate, context-aware answers.

# Features

✔ Load and parse multiple PDF documents

✔ Split PDFs into semantically meaningful chunks

✔ Generate embeddings using HuggingFace embeddings

✔ Store vectors in FAISS (high-performance vector DB)

✔ Retrieve top-k relevant chunks

✔ Custom prompt for context-restricted answering

✔ LLM response using HuggingFace inference endpoint

✔ End-to-end RAG pipeline using LCEL (RunnableMap, RunnablePassthrough)

# How the Pipeline Works

# 1️⃣ Setup HuggingFace Token

Your HF token is required to access both embeddings and the LLM hosted on HuggingFace.
# 2️⃣ Load PDF Documents

Using MiniLM (a lightweight & efficient embedding model):

# 4️⃣ Initialize LLM
Uses the Zephyr-7B-Beta model for generation.
# 5️⃣ Split Documents into Chunks
Chunking helps improve vector retrieval accuracy.

# 6️⃣ Create FAISS Vector Database
Retrieves top 4 context chunks.

# 7️⃣ Define Prompt Template
Prevents hallucination by restricting the model to given context.
# 8️⃣ Build RAG Chain using LCEL
This chain:

Fetches top-k context

Injects context + question into prompt

Sends final prompt to the LLM
# 9️⃣ Run Query
The model replies strictly using PDF knowledge.


# 📦 Installation (requirements):
pip install langchain langchain-community langchain-core langchain-huggingface pypdf faiss-cpu

# 💡 Notes

Ensure your PDF files are placed inside the pdf/ folder.

HuggingFace Inference API requires a valid token.

For larger datasets or higher accuracy, use higher-capacity embedding models.

# Conclusion

This project provides a clean and modular RAG implementation that you can extend with:

Streamlit UI

FastAPI backend

Better LLMs

Improved relevance filters
