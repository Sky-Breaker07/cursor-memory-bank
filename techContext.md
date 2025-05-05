# Technical Context

## Development Environment
- Node.js with TypeScript
- pnpm as package manager
- Express.js for API framework
- MongoDB Atlas for vector database
- Nodemon for development server

## Key Dependencies
- **@langchain/core**: Core LangChain functionality
- **@langchain/openai**: OpenAI integration for LangChain
- **@langchain/langgraph**: Graph-based workflow for LangChain
- **@langchain/mongodb**: MongoDB vector store integration
- **express**: Web server framework
- **mongodb**: MongoDB client library
- **dotenv**: Environment variable management
- **typescript**: TypeScript compiler

## File Structure
- **src/app.ts**: Main application entry point
- **src/routes/**: API route definitions
- **src/controller/**: Request handling logic
- **src/api/**: LangChain graph implementation
- **src/ai/**: AI model configurations
- **src/db/**: Database configuration and access
- **src/utils/**: Utility functions and helpers

## Environment Configuration
Required environment variables:
- `PORT`: Server port (default: 3000)
- `OPENAI_API_KEY`: OpenAI API key
- `MONGO_URI`: MongoDB connection string
- `MONGO_DB`: MongoDB database name
- `MONGO_COLLECTION`: MongoDB collection for vectors

## Build and Run Process
- Development: `pnpm dev` (uses nodemon)
- Build: `pnpm build` (compiles TypeScript)
- Start: `pnpm start` (runs built code)
- Seeding: `pnpm seed` (populates database with initial data)

## Testing Strategy
- Currently no automated tests
- Manual API testing via Postman or curl
- Console logging for development debugging

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