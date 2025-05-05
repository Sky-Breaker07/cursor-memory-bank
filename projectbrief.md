# Custom AI Bot API Project Brief

## Project Overview
This is an API for a custom AI chatbot built with Express.js, MongoDB, and LangChain. The system is designed to provide intelligent responses to user queries by leveraging a conversational RAG (Retrieval-Augmented Generation) architecture.

## Key Components
- **Express.js Backend**: Handles HTTP requests and manages the API endpoints
- **MongoDB with Vector Search**: Stores documents and provides vector search capabilities
- **LangChain Integration**: Facilitates the creation of the conversational graph and RAG workflow
- **OpenAI Models**: GPT-4o for conversation and text-embedding-3-large for embeddings

## System Architecture
The system follows a graph-based processing pipeline:
1. Categorize the user question
2. Retrieve relevant documents from MongoDB
3. Generate an answer using the LLM with context
4. Validate the answer quality
5. Refine the answer if needed
6. Handle potential human assistance needs

## Technical Stack
- TypeScript/Node.js
- Express.js for API framework
- MongoDB for document and vector storage
- LangChain for RAG pipeline
- OpenAI GPT-4o and embeddings

## Project Goals
- Provide accurate, contextual responses to user queries
- Maintain conversation history across sessions
- Support dynamic document retrieval based on question context
- Handle edge cases with appropriate human handoff

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