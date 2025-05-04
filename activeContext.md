# Active Context

## Project Summary
This project is a custom AI chatbot API built using Express.js, TypeScript, LangChain, and MongoDB. It implements a RAG (Retrieval-Augmented Generation) pattern to provide context-aware responses about agricultural commodities, logistics, and supply chain services.

## Current State
- Basic RAG implementation is complete and functional
- Single API endpoint for chat interactions
- Document processing pipeline for DOCX files
- MongoDB vector store integration

## System Architecture
```
┌─────────────┐     ┌─────────────┐     ┌───────────────┐     ┌─────────────┐
│  Express    │────▶│  Controller │────▶│  LangChain    │────▶│  OpenAI     │
│  API Server │     │  Layer      │     │  StateGraph   │     │  LLM        │
└─────────────┘     └─────────────┘     └───────────────┘     └─────────────┘
                                               │
                                               ▼
                                        ┌─────────────┐
                                        │  MongoDB    │
                                        │  Vector DB  │
                                        └─────────────┘
```

## Key Components
1. **Express Server** (`src/app.ts`): Entry point handling API requests
2. **Chat Controller** (`src/controller/chat.ts`): Processes chat requests
3. **LangChain Graph** (`src/api/index.ts`): Manages the RAG workflow
4. **Vector Store** (`src/db/config.ts`): MongoDB integration for document storage
5. **Seed Script** (`src/db/seed.ts`): Processes documents for vector storage

## Technical Focus Areas
- RAG implementation using LangChain
- MongoDB Atlas Vector Search integration
- Document processing and chunking
- API design and error handling

## Business Domain Focus
- Agricultural commodities (grains, oilseeds, pulses)
- Derivative products (oils, meals)
- Logistics and transportation services
- Supply chain solutions

## Current Requirements
- Environment variables for OpenAI API and MongoDB configuration
- Node.js and pnpm for package management
- Source documents in DOCX format 