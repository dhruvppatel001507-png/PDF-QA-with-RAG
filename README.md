PDF QA with RAG
Overview

This project is a Retrieval-Augmented Generation (RAG) application that allows users to upload a PDF document and ask natural-language questions about its content, receiving accurate, context-grounded answers rather than generic LLM responses.

How it works
When a PDF is uploaded, the app breaks the document into smaller text chunks, which are then converted into vector embeddings that capture their semantic meaning.
These embeddings are stored and searched to retrieve the most relevant chunks of the document whenever a user asks a question — this is the "retrieval" step of RAG.
The retrieved context is then passed along with the user's question to a language model, which generates an answer grounded specifically in the content of the uploaded PDF — this is the "generation" step.
rag_utility.py contains the core logic for this pipeline: document chunking, embedding generation, similarity search/retrieval, and answer generation.
app.py provides the Streamlit interface where users upload their PDF and interact with the Q&A chat.
env_template.txt and packages.txt indicate the app relies on external API keys (likely for an LLM/embedding provider) and system-level packages (possibly needed for PDF parsing).
Key components
app.py — Streamlit UI for uploading PDFs and asking questions.
rag_utility.py — the RAG pipeline: chunking, embedding, retrieval, and answer generation logic.
env_template.txt — template for required API keys/environment variables.
packages.txt — system-level dependencies needed for the app to function (e.g., PDF processing libraries).
requirements.txt — Python package dependencies.
Purpose / Use case

A practical implementation of the RAG pattern — one of the most widely used techniques for building LLM applications that answer questions accurately over private/custom documents, rather than relying purely on a model's pre-trained knowledge.
