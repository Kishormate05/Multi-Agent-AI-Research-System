# 🤖 Multi-Agent AI Research System

> **An Agentic AI research assistant that combines Web Research, PDF RAG, Multi-Agent Reasoning, and Automated Report Generation.**

[![Live Demo](https://img.shields.io/badge/🚀%20Live%20Demo-Streamlit-red?style=for-the-badge)](https://multi-agentic-ai-research-system.streamlit.app/)
[![GitHub](https://img.shields.io/badge/💻%20GitHub-Repository-black?style=for-the-badge&logo=github)](https://github.com/Kishormate05/Multi-Agent-AI-Research-System)
[![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python)](https://www.python.org/)
[![LangGraph](https://img.shields.io/badge/LangGraph-Multi--Agent-orange?style=for-the-badge)](https://www.langchain.com/langgraph)
[![Streamlit](https://img.shields.io/badge/Streamlit-Deployed-FF4B4B?style=for-the-badge&logo=streamlit)](https://streamlit.io/)

---

## 🚀 Live Demo

### 👉 [Open the Live Application](https://multi-agentic-ai-research-system.streamlit.app/)

Enter a research question and let the multi-agent pipeline collect information, retrieve relevant PDF knowledge, analyze the results, and generate a structured report.

---

## 🎯 What This Project Does

This project automates the research workflow using **specialized AI agents** instead of a single LLM prompt.

For every research query, the system:

**🔍 Researches the Web → 📚 Retrieves PDF Knowledge → 🧠 Analyzes Information → 📝 Generates a Report**

The application combines external web knowledge with information retrieved from a local **FAISS vector database**.

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 🔍 **Web Research** | Uses Tavily to collect relevant web information |
| 📚 **PDF RAG** | Retrieves relevant content from uploaded research PDFs |
| 🗄️ **FAISS Vector Search** | Performs semantic similarity search over document chunks |
| 🤖 **Multi-Agent Workflow** | Uses LangGraph to orchestrate specialized agents |
| 🧠 **AI Analysis** | Combines web and document knowledge |
| 📝 **Report Generation** | Produces a structured research report |
| 📂 **PDF Upload** | Upload research documents through the Streamlit UI |
| 🕒 **Chat History** | Keeps generated research queries in the current session |
| 📥 **Report Download** | Download the generated report as a text file |
| ☁️ **Cloud Deployment** | Available as a public Streamlit application |

---

# 🧠 Multi-Agent Architecture

```text
                         USER QUERY
                              │
                              ▼
                  ┌──────────────────────┐
                  │   🔍 RESEARCH AGENT  │
                  │      Tavily Search   │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │      📚 RAG AGENT    │
                  │   PDF + FAISS Search │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │    🧠 ANALYSIS AGENT │
                  │  Reason & Synthesize │
                  └──────────┬───────────┘
                             │
                             ▼
                  ┌──────────────────────┐
                  │    📝 REPORT AGENT   │
                  │ Structured Reporting │
                  └──────────┬───────────┘
                             │
                             ▼
                    FINAL RESEARCH REPORT
```

---

# 🔄 End-to-End Workflow

### 1️⃣ User Query
The user enters a research question.

Example:

```text
What is Agentic AI and how does it work?
```

### 2️⃣ Research Agent
Tavily searches the web and collects relevant sources.

### 3️⃣ RAG Agent
The query is matched against PDF embeddings stored in FAISS.

### 4️⃣ Analysis Agent
Web research and retrieved document context are combined and analyzed.

### 5️⃣ Report Agent
The analysis is converted into a structured research report.

### 6️⃣ Final Output
The user receives the generated report directly in the Streamlit interface.

---

# 📚 RAG Pipeline

```text
Research PDFs
     │
     ▼
PyPDFLoader
     │
     ▼
Text Extraction
     │
     ▼
Recursive Text Splitting
     │
     ▼
HuggingFace Embeddings
     │
     ▼
FAISS Vector Database
     │
     ▼
Similarity Search
     │
     ▼
Relevant Document Chunks
     │
     ▼
Gemini LLM
     │
     ▼
Context-Aware Answer
```

### Why RAG?

RAG allows the system to retrieve relevant information from the project's PDF knowledge base before generating an answer. This makes the document knowledge an explicit part of the research workflow.

---

# 🤖 Agent Responsibilities

### 🔍 Research Agent
**Tool:** Tavily

- Performs web search
- Collects relevant sources
- Extracts useful research content
- Produces web-based research information

### 📚 RAG Agent
**Tools:** FAISS + HuggingFace Embeddings

- Searches the PDF knowledge base
- Finds semantically relevant chunks
- Passes retrieved context to the LLM

### 🧠 Analysis Agent
**Model:** Google Gemini

- Combines web research and RAG results
- Identifies important findings
- Extracts trends and challenges
- Produces analytical insights

### 📝 Report Agent
**Model:** Google Gemini

- Converts analysis into a structured report
- Generates executive summaries
- Organizes findings, trends, challenges, and future scope

---

# 🛠️ Tech Stack

| Technology | Role |
|---|---|
| **Python** | Core development |
| **LangGraph** | Agent orchestration |
| **LangChain** | LLM application framework |
| **Google Gemini** | LLM / reasoning |
| **Tavily** | Web research |
| **FAISS** | Vector database |
| **HuggingFace** | Text embeddings |
| **PyPDF** | PDF processing |
| **Streamlit** | Web interface |
| **python-dotenv** | Environment configuration |

---

# 📂 Project Structure

```text
Multi-Agent-AI-Research-System/
│
├── agents/
│   ├── research_agent.py
│   ├── rag_agent.py
│   ├── analysis_agent.py
│   └── report_agent.py
│
├── documents/
│   └── pdfs/
│       └── research_documents.pdf
│
├── vectorstore/
│   └── faiss_index/
│       ├── index.faiss
│       └── index.pkl
│
├── utils/
│   ├── llm.py
│   ├── prompts.py
│   └── pdf_generator.py
│
├── app.py
├── streamlit_app.py
├── requirements.txt
├── .gitignore
└── README.md
```

---

# 🖥️ Application

The Streamlit application provides a simple research workspace:

```text
┌─────────────────────────────────────────────────┐
│        🤖 Multi-Agent AI Research System        │
├─────────────────────────────────────────────────┤
│                                                 │
│  📂 PDF Management                              │
│  ├── Upload PDF Files                           │
│  └── Create Vector Database                     │
│                                                 │
│  🔍 Enter Research Query                        │
│                                                 │
│  [ Generate Report ]                            │
│                                                 │
│  🔍 Research Agent      ✓ Complete              │
│  📚 RAG Agent           ✓ Complete              │
│  🧠 Analysis Agent     ✓ Complete              │
│  📝 Report Agent       ✓ Complete              │
│                                                 │
│  📄 Generated Research Report                   │
│                                                 │
└─────────────────────────────────────────────────┘
```

---

# 📊 Example

### Input

```text
What is Agentic AI and how does it work?
```

### Processing

```text
Web Sources
     +
PDF Knowledge
     ↓
Research + RAG
     ↓
Analysis
     ↓
Report Generation
```

### Output

The application generates a structured report containing sections such as:

- Executive Summary
- Key Findings
- Important Trends
- Challenges
- Future Scope

---

# 💻 Run Locally

## 1. Clone the Repository

```bash
git clone https://github.com/Kishormate05/Multi-Agent-AI-Research-System.git
cd Multi-Agent-AI-Research-System
```

## 2. Create Virtual Environment

### Windows

```bash
py -m venv .venv
.venv\Scripts\activate
```

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

## 4. Configure API Keys

Create a `.env` file:

```env
GOOGLE_API_KEY=your_google_api_key
TAVILY_API_KEY=your_tavily_api_key
```

> ⚠️ Never commit API keys or `.env` files to GitHub.

## 5. Build the FAISS Database

```bash
python -c "from vectorstore.create_db import create_vector_db; create_vector_db()"
```

## 6. Start the Application

```bash
streamlit run streamlit_app.py
```

---

# ☁️ Deployment

The application is deployed on **Streamlit Community Cloud**.

### 🌐 Production Demo

**[Launch Multi-Agent AI Research System →](https://multi-agentic-ai-research-system.streamlit.app/)**

The deployment uses:

- Python 3.12
- GitHub repository
- Streamlit Community Cloud
- Secure environment secrets
- Pre-built FAISS vector database

---

# 🔐 Environment Variables

| Variable | Purpose |
|---|---|
| `GOOGLE_API_KEY` | Access Google Gemini |
| `TAVILY_API_KEY` | Access Tavily web search |

For cloud deployment, store these values in the hosting platform's secret manager.

---

# 🎯 Use Cases

This system can be useful for:

- 📖 Academic research
- 🔬 Technical research
- 🤖 AI / ML research
- 📊 Market research
- 📚 Research paper analysis
- 🧑‍💻 Developer research
- 📰 Information analysis
- 📑 Automated report generation

---

# 📈 What This Project Demonstrates

This project demonstrates practical implementation of:

- ✅ Agentic AI
- ✅ Multi-Agent Systems
- ✅ LangGraph orchestration
- ✅ LangChain
- ✅ Retrieval-Augmented Generation
- ✅ Vector databases
- ✅ Semantic search
- ✅ LLM-based reasoning
- ✅ Web research automation
- ✅ Document intelligence
- ✅ Automated report generation
- ✅ Streamlit deployment

---

# 🔮 Future Enhancements

- ⚡ Parallel agent execution
- 💾 Persistent long-term memory
- 📊 Research analytics and visualizations
- 🔎 Better source citation and verification
- 📑 Multiple document collections
- 💬 Persistent conversational memory
- 📥 Advanced PDF report generation
- 👤 User authentication
- 🗂️ Research workspace management
- 🚀 Advanced caching and performance optimization

---

# 🧩 Design Principles

### Modular
Each agent has a dedicated responsibility and can be modified independently.

### Scalable
New agents, tools, and workflow stages can be added to the LangGraph pipeline.

### Retrieval-Augmented
Relevant document context is retrieved before generating RAG-based answers.

### Agent-Oriented
The research workflow is divided into specialized stages instead of relying on a single prompt.

### Deployment Ready
The application is available as a public Streamlit web application.

---

# 👨‍💻 Author

## Kishor Mate

**AI / ML • Generative AI • Agentic AI • Data Science**

---

## ⭐ Support the Project

If you find this project useful, consider giving the repository a ⭐.

### 🚀 [Live Demo](https://multi-agentic-ai-research-system.streamlit.app/)

### 💻 [GitHub Repository](https://github.com/Kishormate05/Multi-Agent-AI-Research-System)

---

<p align="center">
  <strong>Built with Python • LangGraph • LangChain • Gemini • Tavily • FAISS • HuggingFace • Streamlit</strong>
</p>
