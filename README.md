# Multilingual-Sentiment-Analysis-Chatbot

# Multilingual Sentiment Analysis API

[
[
[
[

A production-ready **Multilingual Sentiment Analysis API** that analyzes text sentiment across 100+ languages (English, Yoruba, Igbo, Hausa, etc.) using Hugging Face transformers. Built with FastAPI, PostgreSQL, and Docker Compose for easy deployment.

 

## ✨ Features

- 🌍 **100+ Languages** - Pre-trained multilingual BERT model
- ⚡ **FastAPI** - Automatic API docs + validation
- 🗄️ **PostgreSQL** - Persistent prediction storage
- 🐳 **Docker Compose** - One-command deployment
- 📊 **Prediction History** - View all analyses
- 🧪 **Full Test Suite** - Production quality

## 🏗️ Architecture & Workflow

```mermaid
graph TD
    A[User Request<br/>POST /predict] --> B[FastAPI Router]
    B --> C[Multilingual BERT<br/>sentiment-analysis pipeline]
    B --> D[SQLAlchemy ORM]
    C --> E[{'POSITIVE'<br/>'NEGATIVE'}<br/>confidence score]
    D --> F[PostgreSQL<br/>predictions table]
    E --> G[Store Prediction<br/>id, text, sentiment,<br/>confidence, created_at]
    G --> H[Response<br/>JSON with full record]
    
    I[GET /predictions] --> J[Query DB<br/>limit=100, skip=0]
    J --> H
    
    K[Docker Compose] --> L[Postgres Container]
    K --> M[FastAPI Container]
```

**Data Flow**:
1. User sends text → FastAPI validates
2. Transformers pipeline predicts sentiment (0.3s)
3. Result saved to PostgreSQL with timestamp
4. Full prediction record returned
5. History endpoint shows recent analyses

## 🚀 Quick Start

### Prerequisites
- Docker & Docker Compose
- Git

```bash
git clone https://github.com/yourusername/multilingual-sentiment.git
cd multilingual-sentiment
cp .env.example .env  # Edit DATABASE_URL if needed
docker compose up --build
```


## 🛠️ Tech Stack

| Component | Technology | Purpose |
|-----------|------------|---------|
| **Backend** | FastAPI 0.115 | REST API + Auto-docs |
| **ML Model** | bert-base-multilingual | 100+ language sentiment |
| **Database** | PostgreSQL 16 | Prediction persistence |
| **ORM** | SQLAlchemy 2.0 | Async database operations |
| **Deployment** | Docker Compose | Local + Production ready |
| **Testing** | Pytest | Model + API validation |



## 🌐 API Documentation

- **Swagger UI**: `/docs`
- **ReDoc**: `/redoc`

**Endpoints**:
```
POST  /predict           # Analyze single text
POST  /predict_batch     # Analyze multiple texts
GET   /predictions       # View prediction history
GET   /health            # System status
```
 

### Render
1. Connect GitHub repo
2. Build = `Dockerfile`
3. Service = Web Service
4. PORT = 8000

 

## 📄 License

MIT License

## 👨‍💼 Author

**Sharon** - ML Engineer & Tech Entrepreneur  
***

<div align="center">

**⭐ Star this repo if it helps your ML journey!**



</div>

 
