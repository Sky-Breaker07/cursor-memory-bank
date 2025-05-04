# Technical Context

## Application Structure
- `src/app.ts`: Main Express application entry point
- `src/routes/chat.ts`: API route definitions for chat endpoint
- `src/controller/chat.ts`: Controller logic for handling chat requests
- `src/api/index.ts`: LangChain graph implementation
- `src/ai/index.ts`: AI model configurations
- `src/db/config.ts`: Database connection and vector store configuration
- `src/db/seed.ts`: Data seeding script for processing documents
- `src/db/data/`: Source documents (DOCX files)

## Implementation Details

### RAG (Retrieval-Augmented Generation) Pattern
The application implements the RAG pattern using LangChain's StateGraph:
1. User sends a question to the API
2. System retrieves relevant documents from MongoDB vector store
3. Retrieved document content is used as context for OpenAI to generate a response
4. Response is sent back to the user

### Vector Store Implementation
- Uses MongoDB Atlas Vector Search
- Documents are embedded using OpenAI's text-embedding-3-large model
- Contains configuration for collection, index name, and embedding fields

### Document Processing
- DOCX files are loaded from the data directory
- Text is extracted and split into chunks (1000 characters with 200 character overlap)
- Chunks are embedded and stored in MongoDB

### API Structure
- Simple RESTful endpoint at `/api/v1/chat`
- Accepts POST requests with a JSON body containing a `prompt` field
- Returns JSON response with AI-generated answer

## Dependencies
- `@langchain/core`, `@langchain/langgraph`, `@langchain/mongodb`, `@langchain/openai`: LangChain ecosystem
- `express`: Web framework
- `mongodb`: Database driver
- `mammoth`, `pdf-parse`: Document parsing
- `dotenv`: Environment variable management
- `typescript`, `ts-node`, `nodemon`: Development tools

## Environment Considerations
The application is configured to run with Node.js and TypeScript, with a development setup using nodemon for auto-reloading during development. 