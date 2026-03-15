🤖 n8n RAG System – Document-Powered AI Agent
A Retrieval-Augmented Generation system built in n8n that answers questions strictly based on uploaded documents — no hallucinations, no outside knowledge.

1️⃣ Document Ingestion Pipeline
Purpose: Process documents and store them in vector database for future searches.

How It Works:
User uploads a document (PDF/text) through a form

Document is automatically downloaded and processed

Text is extracted from the file

Long documents are split into smaller chunks (500 characters each with 50 overlap)

Each chunk is converted into vector embeddings using AI models (Cohere or Gemini)

These vectors are stored in Pinecone vector database with metadata

Why This Matters:
Documents are processed only once

Embeddings are generated only when new files are added

Saves API costs and compute time

Creates a searchable knowledge base for the AI



2️⃣ Chat Query Pipeline
Purpose: Answer user questions by searching the document database.

How It Works:
User sends a message through chat interface

AI Agent receives the question

Agent automatically calls the vector store tool

User's question is converted to embeddings

Pinecone searches for similar document chunks

Relevant chunks are sent to AI model

AI generates answer strictly from those chunks

Response is sent back to user



Memory Feature:
Bot remembers last messages

Can handle follow-up questions like "Can you summarize that?"

Maintains conversation context naturally
