﻿# PersonaForge 🤖✨

**AI-Powered Personality Chatbot Platform with Advanced Memory & Authentication**

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![React](https://img.shields.io/badge/react-18.3+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.115+-green.svg)

PersonaForge is a full-stack web application that enables users to create, customize, and interact with AI chatbots featuring distinct personalities. Built with modern technologies, it offers persistent memory, real-time conversations, and a seamless user experience.

## 🚀 Features

### Core Functionality
- **🎭 Custom Personality Creation**: Create unique AI chatbots with tailored personalities, custom avatars, and specific behavioral traits
- **🧠 Advanced Memory System**: Persistent conversation memory using FAISS vector stores with chat summarization after each session
- **👥 Multi-User Support**: Secure user authentication with individual chatbot collections and privacy controls
- **🌐 Public Bot Sharing**: Share your created bots publicly for others to discover and chat with
- **💬 Human-like Conversations**: Multi-message parsing and natural conversation flow with typing indicators

### Technical Features
- **🔐 JWT Authentication**: Secure token-based authentication system
- **📊 ScyllaDB Integration**: High-performance NoSQL database for scalable data storage
- **🔍 Vector Search**: FAISS-powered semantic search for intelligent conversation context
- **⚡ Real-time Communication**: Fast API responses with optimized message handling
- **📱 Responsive Design**: Modern UI built with Tailwind CSS

## 🛠️ Tech Stack

### Backend
- **Framework**: FastAPI (Python 3.8+)
- **Database**: ScyllaDB (Cassandra-compatible)
- **Vector Store**: FAISS (Facebook AI Similarity Search)
- **AI/ML**: LangChain + Google Generative AI (Gemini)
- **Authentication**: JWT with bcrypt password hashing
- **Additional**: Uvicorn (ASGI server), Pydantic (data validation)

### Frontend
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite
- **Styling**: Tailwind CSS
- **Routing**: React Router DOM
- **Icons**: Lucide React
- **State Management**: React Context API

## 📁 Project Structure

```
PersonaForge/
├── Chatbot-backend/          # FastAPI backend application
│   └── backend/
│       ├── app/
│       │   ├── api/          # API routes and endpoints
│       │   ├── core/         # Business logic and services
│       │   └── db/           # Database models and operations
│       ├── requirements.txt   # Python dependencies
│       └── uvicorn_runner.py # Server startup script
├── chatbot-frontend-main/    # React frontend application
│   └── frontend/
│       ├── src/
│       │   ├── components/   # Reusable UI components
│       │   ├── pages/        # Application pages
│       │   ├── services/     # API communication
│       │   └── contexts/     # React contexts
│       ├── package.json      # Node.js dependencies
│       └── vite.config.ts    # Vite configuration
└── user_vector_stores/       # Individual user vector databases
```

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- Node.js 16+
- ScyllaDB instance
- Google AI API key

### Backend Setup

1. **Navigate to backend directory**
   ```bash
   cd Chatbot-backend/backend
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Environment configuration**
   ```bash
   # Create .env file with:
   GOOGLE_API_KEY=your_google_ai_api_key
   SCYLLA_HOSTS=localhost
   JWT_SECRET_KEY=your_jwt_secret_key
   ```

5. **Run the server**
   ```bash
   python uvicorn_runner.py
   ```

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd chatbot-frontend-main/frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm run dev
   ```

4. **Access the application**
   ```
   Frontend: http://localhost:5173
   Backend API: http://localhost:8000
   API Documentation: http://localhost:8000/docs
   ```

## 🔧 Configuration

### Environment Variables

#### Backend (.env)
```env
GOOGLE_API_KEY=your_google_generative_ai_key
SCYLLA_HOSTS=localhost,127.0.0.1
SCYLLA_PORT=9042
SCYLLA_KEYSPACE=chatbot_db
JWT_SECRET_KEY=your_super_secret_jwt_key
JWT_ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
```

#### Database Setup
```sql
-- ScyllaDB keyspace creation
CREATE KEYSPACE IF NOT EXISTS chatbot_db 
WITH REPLICATION = {'class': 'SimpleStrategy', 'replication_factor': 1};
```

## 📊 API Endpoints

### Authentication
- `POST /api/v1/auth/register` - User registration
- `POST /api/v1/auth/login` - User login
- `GET /api/v1/auth/me` - Get current user

### Bot Management
- `GET /api/v1/bots` - List user's bots
- `POST /api/v1/bots` - Create new bot
- `PUT /api/v1/bots/{bot_id}` - Update bot
- `DELETE /api/v1/bots/{bot_id}` - Delete bot
- `GET /api/v1/bots/public` - List public bots

### Chat
- `POST /api/v1/chat/{bot_id}` - Send message to bot
- `GET /api/v1/chat/{bot_id}/history` - Get chat history
- `POST /api/v1/chat/{bot_id}/save-memory` - Save conversation memory

## 🎯 Key Features Implementation

### Memory Management
- **Session-based Memory**: Each user-bot pair maintains isolated conversation context
- **Vector Storage**: FAISS indexes store conversation embeddings for semantic retrieval
- **Automatic Summarization**: Chat sessions are summarized and stored for long-term memory

### Security
- **Password Hashing**: bcrypt for secure password storage
- **JWT Tokens**: Stateless authentication with configurable expiration
- **CORS Protection**: Configured for secure cross-origin requests
- **Input Validation**: Pydantic models for request/response validation

### Performance Optimizations
- **Async Operations**: FastAPI's async support for concurrent request handling
- **Vector Indexing**: FAISS for efficient similarity search
- **Database Connection Pooling**: Optimized ScyllaDB connections
- **Frontend Code Splitting**: Vite's automatic code splitting for faster loads

## 🧪 Example Bots

The platform includes several pre-configured personality bots:
- **Custom Characters**: Users can create bots with unique personalities, backgrounds, and speaking styles

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Developer

**Tridibesh** - *Full Stack Developer* - [tridibeshsarkar07@gmail.com](mailto:tridibeshsarkar07@gmail.com)
- Designed and implemented the complete architecture
- Built responsive frontend with modern React patterns
- Implemented secure authentication and database design
- Also Helped in the Gen AI part

**Anik** - *ML Engineer* - [anikpanja362@gmail.com](mailto:anikpanja362@gmail.com)
- Integrated AI/ML capabilities with LangChain and Google AI
- Also Helped in the frontend 


## 🙏 Acknowledgments

- Google AI for Generative AI capabilities
- ScyllaDB for high-performance database solutions
- Facebook Research for FAISS vector similarity search
- The React and FastAPI communities for excellent frameworks

---

*PersonaForge - Where AI personalities come to life* 🌟
