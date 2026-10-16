# AI Agent Backend Service

A powerful and scalable **AI-powered backend service** built using Node.js and Express.js. This project provides an intelligent AI assistant capable of understanding user queries, maintaining contextual conversations, executing real-world tasks, and communicating with users in real time.

It integrates **Google Gemini, LangChain, Pinecone, and Socket.io** to deliver a personalized AI experience with long-term memory and intelligent tool execution.

## 🚀 Key Features

- **Secure User Authentication:** Implements user registration, login, and logout using `bcrypt` for password hashing and `jsonwebtoken` (JWT) for secure authentication.

- **Real-Time AI Communication:** Uses `Socket.io` to establish bidirectional communication between users and the AI assistant, enabling instant responses and interactive conversations.

- **Intelligent AI Agent:** Integrates `@google/genai` and `@langchain/core` to understand natural language queries, maintain conversational context, and dynamically select appropriate tools based on user intent.

- **Long-Term AI Memory:** Utilizes `Pinecone` as a vector database to store and retrieve relevant user information through semantic search, allowing the assistant to provide personalized and context-aware responses.

- **Real-Time Web Search:** Integrates the `Tavily API` to retrieve up-to-date information from the internet whenever external knowledge is required.

- **External Tool Integration:** Enables the AI assistant to perform real-world actions, including:
  - Fetching current weather information.
  - Retrieving the latest news for a specific city.
  - Searching the web for relevant information.
  - Composing and sending professional emails using Resend.

- **Database Management:** Uses MongoDB and Mongoose to manage structured application data, including user profiles and authentication-related information.

- **Centralized Error Handling:** Implements structured error handling using `try/catch` blocks to manage unexpected failures and provide meaningful HTTP responses.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Node.js | Backend runtime environment |
| Express.js | REST API development |
| MongoDB | NoSQL database |
| Mongoose | Database schema and modeling |
| Socket.io | Real-time bidirectional communication |
| Google GenAI | Gemini AI model integration |
| LangChain | AI agent orchestration and tool execution |
| Pinecone | Vector database and long-term memory |
| Tavily API | Real-time AI-powered web search |
| Resend | Professional email delivery |
| JWT & bcrypt | Authentication and password security |

## ⚙️ Environment Configuration

Create a `.env` file in the root directory and configure the following environment variables:

```env
# Server Configuration
PORT=8000

# Authentication
KEY=your_jwt_secret

# Database
MONGODB_URI=your_mongodb_connection_string

# Google Gemini
GOOGLE_API_KEY=your_google_genai_api_key

# Pinecone Vector Database
PINECONE_API_KEY=your_pinecone_api_key

# Tavily Web Search
TAVILY_API_KEY=your_tavily_api_key

# Resend Email Service
RESEND_API_KEY=your_resend_api_key
```

*Note: Ensure the environment variable names match those referenced in your implementation. Never expose API keys or commit your `.env` file to version control.*

## 🔄 How It Works

The AI agent follows an intelligent workflow to process user requests:

1. **User Request:** The user sends a message through the client application.
2. **Real-Time Communication:** Socket.io transfers the message to the backend.
3. **Context Retrieval:** The agent retrieves relevant stored information from Pinecone.
4. **AI Processing:** Google Gemini processes the query using the available conversational context.
5. **Tool Selection:** LangChain helps orchestrate the execution of appropriate external tools when required.
6. **Action Execution:** The agent performs the requested operation, such as web search, weather retrieval, news fetching, or email delivery.
7. **Response Generation:** The AI generates a contextual response and communicates it back to the user.

## 🆕 Recent Updates & Improvements

### 1. Improved Authentication Error Handling
- Added `try/catch` blocks across the registration, login, and logout controllers.
- Improved handling of asynchronous errors and unexpected failures.
- Implemented meaningful HTTP error responses, including `500 Internal Server Error`, to improve backend reliability.

### 2. Production Email Delivery Fix
- Replaced Nodemailer-based SMTP delivery with the **Resend API**.
- Resolved email timeout issues caused by outbound SMTP restrictions on Render's Free tier (ports 25, 465, and 587).
- Implemented HTTPS-based email delivery through Resend for better compatibility with the production hosting environment.

## 🎯 Project Objective

The primary objective of this project is to build an intelligent AI assistant that goes beyond traditional question-answering systems.

By combining **real-time communication, contextual memory, autonomous tool selection, and external API integrations**, the system enables users to interact with an AI agent capable of understanding requests and performing meaningful real-world actions through a unified conversational interface.
