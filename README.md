# 🏥 AI-Powered Medical Assistant Project

This project is an **AI-powered healthcare assistant** composed of three main components:

1. **Medical Chatbot** → Image + Text-based Q&A using LLaMA/Groq API  
2. **Medical Report Analyzer** → Multi-agent system for medical diagnosis  
3. **Mental Health Chatbot** → RAG-based conversational agent with Gradio UI  

---

## 📂 Project Structure

```
Medical-Assistant-Project/
├── Medical Chatbot/
│ ├── app.py # FastAPI backend for chatbot with image & query input
│ ├── main.py # CLI script for testing chatbot locally
│ ├── templates/ # HTML templates for web UI
│
├── Medical Report Analyzer/
│ ├── utils/
│ │ ├── Agent.py # Specialized agents (Cardiologist, Psychologist, Pulmonologist, Team)
│ ├── app.py # Flask app for uploading medical reports
│ ├── main.py # CLI script to run analyzer
│ ├── templates/index.html # Frontend for uploading reports
│ ├── results/ # Stores final diagnosis reports
│
├── Mental Chatbot/
│ ├── Mental_Chatbot.ipynb # Terminal-based chatbot and Gradio UI for mental health chatbot 
│ ├── chroma_db/ # Persistent vector database
│ ├── data/ # PDF knowledge base for RAG
│
├── .env # Environment variables (API Keys, etc.)
├── requirements.txt # Python dependencies
└── README.md # Project documentation
```

---

## ⚙️ Technologies & Tools Used

### 🔹 Frameworks & Libraries
- **FastAPI** → Backend API for Medical Chatbot  
- **Flask** → Web app for Medical Report Analyzer  
- **LangChain** → Used in Mental Chatbot for RAG & LLM orchestration  
- **Gradio** → Web-based UI for Mental Health Chatbot  
- **ChromaDB** → Vector database for document retrieval  
- **HuggingFace Transformers / Embeddings** → Text embeddings for RAG  
- **PIL (Pillow)** → Image handling and validation  
- **Requests** → API requests to Groq endpoints  
- **ThreadPoolExecutor** → Parallel execution of agents in report analyzer  

### 🔹 APIs & Models
- **Groq API** → For running LLaMA family of models  
  - `llama-4-scout-17b-16e-instruct`  
  - `llama-3.3-70b-versatile`  

### 🔹 Storage & Utilities
- **ChromaDB** → For vector storage in RAG  
- **dotenv** → Secure environment variable management  

---

## 🚀 Components Overview

### 🧠 1. Medical Chatbot
- Built with **FastAPI**  
- Takes **image + query text** as input  
- Sends request to **Groq API (LLaMA models)** for medical insights  
- Returns **structured JSON response**  

**Run:**
```bash
cd "Medical Chatbot"
uvicorn app:app --reload --port 8000
```
Visit → http://127.0.0.1:8000

---

### 📝 2. Medical Report Analyzer

Built with Flask

Accepts text medical reports (.txt files)

Uses three AI agents:

Cardiologist

Psychologist

Pulmonologist

Results combined by a Multidisciplinary Team agent

Outputs Final Diagnosis Report

Run (Web App):
```bash
cd "Medical Report Analyzer"
python app.py
```
➡️ Visit → http://127.0.0.1:5000

Run (CLI):
```bash
python main.py
```

---

### 💬 3. Mental Health Chatbot

Uses LangChain + Groq LLaMA models

Employs RAG (Retrieval-Augmented Generation) with ChromaDB

Can load custom PDFs (knowledge base)

Provides supportive & compassionate responses

Available in two versions:

Terminal-based chatbot

Gradio web UI

Run (Gradio UI):
```bash
cd "Mental Chatbot"
python chatbot_gradio.py
```

Run (Terminal):
```bash
python chatbot_terminal.py
```

---

## 📦 Installation

Clone the repo:
```bash
git clone https://github.com/yourusername/medical-assistant.git
cd medical-assistant
```

Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
```

Install dependencies:
```bash
pip install -r requirements.txt
```

Create a .env file in the project root:
```bash
GROQ_API_KEY=your_groq_api_key_here
```

---

## 🛡️ Disclaimer

⚠️ This project is for educational and research purposes only.
It is not a replacement for professional medical advice.
Always consult certified healthcare professionals for medical concerns.

---

## 👨‍💻 Developed by

Ahmed Elnashar