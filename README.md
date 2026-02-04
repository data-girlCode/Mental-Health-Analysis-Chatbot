# Mental-Health-Chatbot (using Sentiment-Analysis)

An AI-powered conversational agent for mental health support using NLP techniques like emotion detection and empathetic response generation. Built with Hugging Face Transformers, FastAPI.
 

## ✨ Features
- Real-time emotion classification (joy, sadness, anger, etc.) using fine-tuned DistilBERT.

- Context-aware, empathetic responses via T5 seq2seq model + RAG retrieval.

- Multilingual support: English and basic Pidgin English.

- Session memory for natural conversation flow.

Disclaimer: This is not a substitute for professional therapy. It is just a side project i decided to work on.

 

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

**Project Workflow**
- Data Prep: Load GoEmotions via datasets, preprocess with spaCy.

- Model Training: Fine-tune BERT (trainer.train()) + T5 for responses.

- RAG Pipeline: Embed WHO mental health PDFs into FAISS.

- API: FastAPI endpoints with LangChain orchestration.

- Deploy: Docker → Vercel (backend) + Netlify (frontend).

**Datasets & Models**
GoEmotions: 58k samples, 27 emotions [Hugging Face].

Language: English, 

Fine-tuned Models:  


## 🚀 Quick Start

Type "I'm feeling down today" → Detects sadness, responds empathetically.

Say "I want to end it all" → Triggers crisis mode with resources.
```


## 🛠️ Tech Stack

| Component | Technology | Purpose |
|-----------|------------|---------|
| **Backend** |Python 3.11 | FastAPI 0.115 | LangChain | Redis |
| **NLP Models** | Hugging Face Transformers (DistilBERT, T5)|  FAISS |
| **Database** | PostgreSQL 16 |  |
| **Deployment** | Docker | Vercel/Render |
| **Data** | GoEmotions | EmpatheticDialogues datasets |


### Render
1. Connect GitHub repo
2. Build = `Dockerfile`
3. Service = Web Service
4. PORT = 8000

 

## 👨‍💼 Author

**Sharon** - ML Engineer  
***

<div align="center">

**⭐ Star this repo if it helps your ML journey!**



</div>

 
