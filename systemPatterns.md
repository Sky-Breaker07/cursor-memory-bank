# System Patterns

## Core Architectural Patterns

### 1. RAG (Retrieval-Augmented Generation)
The primary pattern used in this application is RAG, which:
- Enhances LLM responses with retrieved information from a knowledge base
- Reduces hallucinations by grounding responses in factual data
- Provides domain-specific knowledge without fine-tuning the base model

### 2. Layered Architecture
The application follows a standard layered architecture:
- **Route Layer**: Handles HTTP routing (`src/routes`)
- **Controller Layer**: Manages request/response lifecycle (`src/controller`)
- **Service Layer**: Contains business logic (`src/api`)
- **Data Layer**: Manages data access and persistence (`src/db`)

### 3. State Graph Pattern
Using LangChain's StateGraph to manage the flow of:
- Input state (user question)
- Processing state (retrieval and context formation)
- Output state (generated answer)

## Data Flow Patterns

### 1. Document Processing Pipeline
```
DOCX Files → Text Extraction → Chunking → Embedding → Vector Storage
```

### 2. Query Processing Pipeline
```
User Query → API → Embedding → Vector Search → Context Assembly → LLM Generation → Response
```

## Design Patterns

### 1. Dependency Injection
- Configuration variables injected via environment variables
- Services composed at initialization time

### 2. Factory Pattern
- Database connections created via factory methods
- Vector store instances created with appropriate configurations

### 3. Middleware Pattern
- Express middleware for request processing
- Error handling middleware for consistent error responses

## Integration Patterns

### 1. API Gateway
- Express server acting as an API gateway
- Single endpoint exposing the chatbot functionality

### 2. External Service Integration
- MongoDB Atlas for vector storage
- OpenAI for embeddings and language model

## Operational Patterns

### 1. Environment-based Configuration
- Application configured via environment variables
- Different settings for development vs. production

### 2. Seeding Pattern
- Initial data loaded via a seeding script
- Document processing happens outside the main application flow 