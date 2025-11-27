<p align="center">
  <img src="frontend/public/herbal-remedies-guide-og-image.png" alt="Herbal Remedies Guide" width="400">
</p>

# Herbal Remedies Guide

> **Note**: This is a public documentation repository. The source code is maintained in a private repository.

**Live App**: [https://herbal-remedies-guide.vercel.app](https://herbal-remedies-guide.vercel.app)

A RAG (Retrieval-Augmented Generation) system for herbal remedies that provides AI-powered question answering about herbal medicine. The system processes herbal medicine documents, generates semantic embeddings, and delivers intelligent responses through both REST API and WebSocket interfaces.

## Features

- **Intelligent Document Processing**: Extracts and processes herbal remedy information from PDF and Markdown documents
- **Semantic Search**: Uses sentence transformers to find relevant information based on context, not just keywords
- **AI-Powered Answers**: Generates natural language responses using LLM technology with retrieved context
- **Real-time Chat Interface**: WebSocket support for responsive, interactive conversations
- **Payment Integration**: Stripe-powered paywall system for premium content access
- **Rate Limiting**: Built-in protection against API abuse
- **Question History**: Track and review previous queries

## Architecture

### Backend (Python FastAPI)

- **FastAPI** server with WebSocket support
- **Sentence Transformers** for semantic embeddings
- **LLM Integration** for intelligent response generation
- **Vector Search** with numpy-based similarity matching
- **Document Processing Pipeline** for PDF and Markdown files
- **Rate Limiting** and input validation

### Frontend (React + TypeScript)

- **React 19** with TypeScript for type safety
- **Vite** for fast development and optimized builds
- **WebSocket** integration for real-time responses
- **Stripe** integration for payment processing
- **Vercel KV** for data storage

## Key Components

### Document Processing Pipeline

1. **Document Ingestion**: Loads PDF and Markdown files with hash-based change detection
2. **Text Chunking**: Splits documents into meaningful chunks with configurable sizes
3. **Embedding Generation**: Creates semantic vectors using sentence transformers
4. **Vector Storage**: Saves embeddings as numpy arrays for efficient retrieval
5. **Query Processing**: Finds relevant chunks using cosine similarity
6. **Response Generation**: Uses LLM to synthesize answers from retrieved context

### API Endpoints

- `POST /query` - Submit questions via REST API
- `WebSocket /ws` - Real-time chat interface
- Rate limiting and input validation on all endpoints

## Performance Optimizations

- **Lazy Loading**: Heavy ML models loaded on-demand to reduce startup time
- **Vector Caching**: Hash-based cache prevents unnecessary reprocessing
- **Batch Processing**: Efficient embedding generation for multiple texts
- **Request Validation**: Input sanitization and rate limiting

## Notes

All rights reserved.
