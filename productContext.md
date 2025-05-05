# Product Context

## Chatbot Purpose
The AI chatbot API provides a backend system for powering intelligent conversational interfaces. It's designed to:
- Answer user questions based on document context stored in a vector database
- Maintain conversation history for contextual responses
- Handle a variety of question categories with specialized processing
- Provide fallback mechanisms for questions that require human assistance

## User Experience Goals
- Fast, relevant responses to user queries
- Context-aware conversation that remembers previous interactions
- Appropriate handling of edge cases and limitations
- Seamless handoff to human support when necessary

## Performance Metrics
- Response time (tracked in analytics)
- Context relevance scores
- Token usage efficiency
- Question categorization accuracy

## Integration Points
- MongoDB Atlas for vector search and document storage
- OpenAI API for LLM and embedding models
- Express.js REST API endpoints for client applications

## Limitations and Boundaries
- The system handles only text-based queries and responses
- No streaming responses implemented (batch responses only)
- Limited to the information contained in the vector database
- Model context window limitations apply to conversation history

## Business Domain
This chatbot API appears to be designed for a company operating in the following domains:

### 1. Agricultural Commodities
- **Grains**: Wheat, Barley, Oats, Millet
- **Oilseeds**: Flaxseed, Rapeseed, Sunflower Seeds
- **Pulses**: Lentils (Red & Green), Chickpeas, Peas

### 2. Derivative Products
- **Meals**: Flaxseed Meal, Rapeseed Meal, Sunflower Meal, Soybean Meal
- **Oils**: Flaxseed Oil, Rapeseed Oil, Sunflower Oil
- **Processed Products**: Flour

### 3. Logistics & Transportation
- **Air Freight**: Air Cargo services and rates
- **Ocean Freight**: Shipping services
- **Land Transport**: Rail Cargo, Truck Transport
- **Specialized Transport**: OOG (Out of Gauge) Cargo, Project Cargo, Temperature Controlled

### 4. Industrial Chemicals
- **Petrochemicals**: Ethylene, Polyethylene, Propylene

## User Needs
The chatbot likely serves the following user needs:

1. **Information Retrieval**:
   - Quick access to commodity specifications
   - Transportation options and rates
   - Supply chain information

2. **Customer Support**:
   - Answering FAQs about products and services
   - Providing information on logistics capabilities
   - Supporting potential clients with service offerings

3. **Sales Support**:
   - Providing information about services to potential clients
   - Answering preliminary questions before human handoff
   - Explaining value propositions ("Elevate Your Operations with Us")

## Potential Use Cases

### 1. Customer Portal Integration
The API could be integrated into a customer portal where clients can:
- Ask questions about commodity specifications
- Get quick quotes on transport options
- Learn about available services

### 2. Internal Knowledge Base
The chatbot could serve as an internal tool for:
- New employee onboarding
- Sales team reference
- Customer service representatives

### 3. Website Integration
Integration with the company website to:
- Engage visitors with instant information
- Qualify leads through conversation
- Provide 24/7 basic information access

## Target Audience
Based on the document collection, the target audience likely includes:

1. **Commodity Traders & Buyers**
2. **Logistics Managers**
3. **Supply Chain Professionals**
4. **Procurement Specialists**
5. **Agricultural Business Operators** 