# Custom AI Bot API Project Brief

## Overview
This project is a custom AI chatbot API built with Express.js and TypeScript. It uses LangChain, MongoDB vector database, and OpenAI to create a RAG (Retrieval-Augmented Generation) system that can answer questions based on document retrieval.

## Technology Stack
- **Backend**: Node.js with Express.js (TypeScript)
- **AI Framework**: LangChain (with langgraph)
- **Vector Database**: MongoDB Atlas with vector search capabilities
- **AI Models**: OpenAI for both the chat model and embeddings
- **Document Processing**: Tools for processing DOCX files

## Current Architecture
1. **Express Server**: Handles API endpoints
2. **LangChain Graph**: Implements a state graph for RAG operations:
   - Retrieves relevant documents from vector DB
   - Generates responses using OpenAI with context from retrieved documents
3. **MongoDB Vector Store**: Stores document embeddings for similarity search
4. **Document Seeding**: System for converting and chunking DOCX files into vector embeddings

## Domain Focus
Based on the document collection, this appears to be a specialized chatbot for:
- Agricultural commodities (grains, oilseeds, pulses)
- Logistics and transportation (air cargo, ocean freight, rail logistics)
- Supply chain management

## Current Features
- RESTful API endpoint for chat interactions
- Document ingestion system (from DOCX files)
- RAG pattern implementation for context-aware responses
- Error handling and appropriate status codes

## Environment Requirements
The application requires environment variables:
- OPENAI_API_KEY
- MONGO_URI
- MONGO_DB
- MONGO_COLLECTION
- PORT (optional, defaults to 3000) 