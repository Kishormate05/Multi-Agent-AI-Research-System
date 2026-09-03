# 🤖 Multi-Agent AI Research System

```{=html}
<p align="center">
```
`<strong>`{=html}Research • RAG • Analysis • Report
Generation`</strong>`{=html}
```{=html}
</p>
```
```{=html}
<p align="center">
```
`<a href="https://multi-agentic-ai-research-system.streamlit.app/">`{=html}
🚀 Live Demo `</a>`{=html}   •  
`<a href="https://github.com/Kishormate05/Multi-Agent-AI-Research-System">`{=html}
💻 GitHub Repository `</a>`{=html}
```{=html}
</p>
```

------------------------------------------------------------------------

## 📌 Overview

**Multi-Agent AI Research System** is an Agentic AI-powered research
assistant that automates the end-to-end research workflow using multiple
specialized AI agents.

The system combines **web research, PDF-based Retrieval-Augmented
Generation (RAG), AI analysis, and automated report generation** into a
single workflow.

Instead of depending on one LLM call, the application uses specialized
agents coordinated through **LangGraph**. Each agent performs a
dedicated task and passes its results to the next stage, producing a
structured research report.

### 🎯 Core Workflow

``` text
User Query
    ↓
Research Agent
    ↓
RAG Agent
    ↓
Analysis Agent
    ↓
Report Agent
    ↓
Final Research Report
```

------------------------------------------------------------------------

## 🚀 Live Demo

### 👉 [Launch the Live Application](https://multi-agentic-ai-research-system.streamlit.app/)

The application is deployed on **Streamlit Community Cloud** and can be
accessed directly from a browser.

------------------------------------------------------------------------

## ✨ Key Features

### 🔍 1. Web Research Agent

The Research Agent uses **Tavily Search** to gather relevant information
from the web.

**Responsibilities:** - Search the web for the requested topic - Collect
relevant sources - Extract useful research content - Prepare research
information for downstream analysis

------------------------------------------------------------------------

### 📚 2. PDF-Based RAG Agent

The RAG Agent allows the system to use knowledge stored in research
PDFs.

**Pipeline:**

``` text
PDF Documents
     ↓
PyPDF Loader
     ↓
Text Splitting
     ↓
HuggingFace Embeddings
     ↓
FAISS Vector Database
     ↓
Semantic Similarity Search
     ↓
Relevant Context
     ↓
Gemini LLM
```

The system retrieves relevant document chunks before generating an
answer, helping the model ground its response in the available PDF
knowledge.

------------------------------------------------------------------------

### 🧠 3. Analysis Agent

The Analysis Agent combines:

-   Web research results
-   Retrieved PDF/RAG context

It analyzes the information and identifies:

-   Key findings
-   Important insights
-   Trends
-   Challenges
-   Future scope

------------------------------------------------------------------------

### 📝 4. Report Generation Agent

The Report Agent converts the analysis into a structured research
report.

The generated report can contain:

-   Executive Summary
-   Key Findings
-   Important Trends
-   Challenges
-   Future Scope

------------------------------------------------------------------------

### 🔗 5. Multi-Agent Workflow with LangGraph

The complete agent workflow is orchestrated using **LangGraph**.

``` text
                 ┌─────────────────────┐
                 │     User Query      │
                 └──────────┬──────────┘
                            ↓
                 ┌─────────────────────┐
                 │   Research Agent   │
                 │   Tavily Search    │
                 └──────────┬──────────┘
                            ↓
                 ┌─────────────────────┐
                 │      RAG Agent      │
                 │ PDF + FAISS Search  │
                 └──────────┬──────────┘
                            ↓
                 ┌─────────────────────┐
                 │   Analysis Agent   │
                 │   Compare & Reason │
                 └──────────┬──────────┘
                            ↓
                 ┌─────────────────────┐
                 │    Report Agent    │
                 │ Structured Report  │
                 └──────────┬──────────┘
                            ↓
                 ┌─────────────────────┐
                 │   Final AI Report  │
                 └─────────────────────┘
```

------------------------------------------------------------------------

## 🏗️ System Architecture

The system consists of four major AI agents:

  -----------------------------------------------------------------------
  Agent                   Main Responsibility     Technology
  ----------------------- ----------------------- -----------------------
  🔍 Research Agent       Web research and source Tavily
                          collection              

  📚 RAG Agent            PDF retrieval and       FAISS + HuggingFace
                          contextual answering    

  🧠 Analysis Agent       Analyze and synthesize  Gemini
                          information             

  📝 Report Agent         Generate structured     Gemini
                          research report         
  -----------------------------------------------------------------------

### Agent State Flow

``` text
query
  │
  ├── web_result
  │
  ├── pdf_result
  │
  ├── analysis
  │
  └── report
```

The workflow state is passed between agents using LangGraph.

------------------------------------------------------------------------

# 🛠️ Tech Stack

  Technology         Purpose
  ------------------ ------------------------------------
  🐍 Python          Core programming language
  🔗 LangGraph       Multi-agent workflow orchestration
  🦜 LangChain       LLM application framework
  💎 Google Gemini   Large Language Model
  🌐 Tavily          Web search and research
  🗄️ FAISS           Vector similarity search
  🤗 HuggingFace     Text embeddings
  📄 PyPDF           PDF document processing
  🎈 Streamlit       Web application interface
  🔐 python-dotenv   Environment variable management

------------------------------------------------------------------------

# 📂 Project Structure

``` text
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

------------------------------------------------------------------------

# ⚙️ How It Works

## Step 1 --- Enter a Research Query

The user enters a topic such as:

``` text
What is Agentic AI and how does it work?
```

------------------------------------------------------------------------

## Step 2 --- Research Agent

The Research Agent sends the query to Tavily and collects relevant web
information.

``` text
User Query
    ↓
Tavily Search
    ↓
Relevant Web Sources
    ↓
Research Summary
```

------------------------------------------------------------------------

## Step 3 --- RAG Agent

The RAG Agent searches the FAISS vector database for relevant PDF
content.

``` text
User Query
    ↓
Embedding
    ↓
FAISS Similarity Search
    ↓
Top Relevant Chunks
    ↓
Context
```

------------------------------------------------------------------------

## Step 4 --- Analysis Agent

The Analysis Agent receives both sources of information:

``` text
Web Research
     +
PDF/RAG Context
     ↓
Analysis Agent
     ↓
Combined Insights
```

------------------------------------------------------------------------

## Step 5 --- Report Agent

The Report Agent converts the analysis into a structured final report.

``` text
Analysis
   ↓
Report Generation
   ↓
Executive Summary
Key Findings
Trends
Challenges
Future Scope
```

------------------------------------------------------------------------

# 📚 RAG Implementation

The project uses a local FAISS vector database for semantic document
retrieval.

### Document Processing

``` text
PDF
 ↓
PyPDFLoader
 ↓
Document Pages
 ↓
RecursiveCharacterTextSplitter
 ↓
Text Chunks
 ↓
all-MiniLM-L6-v2 Embeddings
 ↓
FAISS Index
```

### Retrieval

``` text
Question
   ↓
Question Embedding
   ↓
FAISS Similarity Search
   ↓
Top-k Relevant Documents
   ↓
LLM Context
   ↓
Answer
```

The current vector database is generated from the PDFs stored under:

``` text
documents/pdfs/
```

------------------------------------------------------------------------

# 🖥️ Application Features

The Streamlit interface provides:

-   📂 PDF file upload
-   🗄️ FAISS vector database creation
-   🔍 Research query input
-   🤖 Multi-agent execution status
-   📚 PDF-based RAG
-   🧠 AI-powered analysis
-   📝 Automated report generation
-   📥 Report download
-   🕒 Chat history

------------------------------------------------------------------------

# 🧪 Example

### Input

``` text
What is Agentic AI and how does it work?
```

### Agent Execution

``` text
🔍 Research Agent      → Complete
📚 RAG Agent           → Complete
🧠 Analysis Agent      → Complete
📝 Report Agent        → Complete
```

### Output

A structured research report containing sections such as:

``` text
Executive Summary
Key Findings
Important Trends
Challenges
Future Scope
```

------------------------------------------------------------------------

# 📊 Why Multi-Agent Architecture?

A multi-agent architecture separates complex research into specialized
tasks.

### Benefits

-   🎯 Task specialization
-   🔄 Structured workflow
-   🧩 Modular architecture
-   📈 Easier scalability
-   🧠 Better separation of responsibilities
-   🔍 Combination of web and document knowledge
-   📝 Automated end-to-end report generation

------------------------------------------------------------------------

# 🔐 Environment Variables

The application requires API credentials for external services.

Create a `.env` file locally:

``` env
GOOGLE_API_KEY=your_google_api_key
TAVILY_API_KEY=your_tavily_api_key
```

### ⚠️ Security

Never commit API keys or `.env` files to GitHub.

For Streamlit Cloud deployment, use the platform's **Secrets**
configuration instead of committing credentials.

------------------------------------------------------------------------

# 💻 Installation & Local Setup

## 1. Clone the Repository

``` bash
git clone https://github.com/Kishormate05/Multi-Agent-AI-Research-System.git
```

``` bash
cd Multi-Agent-AI-Research-System
```

------------------------------------------------------------------------

## 2. Create a Virtual Environment

### Windows

``` bash
py -m venv .venv
```

Activate it:

``` bash
.venv\Scripts\activate
```

------------------------------------------------------------------------

## 3. Install Dependencies

``` bash
pip install -r requirements.txt
```

------------------------------------------------------------------------

## 4. Configure API Keys

Create `.env`:

``` env
GOOGLE_API_KEY=your_google_api_key
TAVILY_API_KEY=your_tavily_api_key
```

------------------------------------------------------------------------

## 5. Create the FAISS Vector Database

``` bash
python -c "from vectorstore.create_db import create_vector_db; create_vector_db()"
```

This processes the PDFs and creates:

``` text
vectorstore/faiss_index/
├── index.faiss
└── index.pkl
```

------------------------------------------------------------------------

## 6. Run the Application

``` bash
streamlit run streamlit_app.py
```

------------------------------------------------------------------------

# ☁️ Deployment

The project is deployed using **Streamlit Community Cloud**.

### Production Workflow

``` text
GitHub Repository
       ↓
Streamlit Community Cloud
       ↓
Dependency Installation
       ↓
Secrets Configuration
       ↓
Application Deployment
       ↓
Public Live Demo
```

### 🌐 Live Application

👉 **https://multi-agentic-ai-research-system.streamlit.app/**

------------------------------------------------------------------------

# 📈 Current Implementation

The current version successfully demonstrates:

-   ✅ Multi-agent orchestration
-   ✅ Web research
-   ✅ PDF-based RAG
-   ✅ FAISS vector retrieval
-   ✅ HuggingFace embeddings
-   ✅ Gemini-powered reasoning
-   ✅ Automated report generation
-   ✅ Streamlit web interface
-   ✅ Public cloud deployment

------------------------------------------------------------------------

# 🔮 Future Improvements

Potential improvements include:

-   ⚡ Parallel agent execution for faster responses
-   🧠 Persistent long-term memory
-   📊 Research analytics and visualizations
-   📑 Multiple independent document collections
-   🔎 Improved source citation and verification
-   💬 Persistent conversational memory
-   📥 Advanced PDF report generation
-   👤 User authentication
-   🗂️ Research project/workspace management
-   🚀 Production-grade caching and model optimization

------------------------------------------------------------------------

# 🎯 Use Cases

The system can support:

-   📖 Academic research
-   🔬 Technical research
-   🤖 AI/ML research
-   📊 Market research
-   📰 Information analysis
-   📚 Research paper analysis
-   🧑‍💻 Developer research
-   📑 Automated report generation

------------------------------------------------------------------------

# 📸 Demo

### Application Interface

The application provides a simple research workflow where users can:

1.  Upload PDF documents
2.  Create/update the vector database
3.  Enter a research query
4.  Run the multi-agent workflow
5.  Review the generated report
6.  Download the result

------------------------------------------------------------------------

# 🧩 Design Principles

### Modular

Each agent is implemented as an independent module.

### Extensible

New agents and tools can be added to the LangGraph workflow.

### Retrieval-Augmented

The RAG pipeline grounds responses using relevant PDF content.

### Agent-Oriented

Different stages of research are handled by specialized agents rather
than a single monolithic prompt.

### Deployment Ready

The application is configured for browser-based use through Streamlit
Community Cloud.

------------------------------------------------------------------------

# 👨‍💻 Author

## Kishor Mate

**AI / ML • Generative AI • Agentic AI • Data Science**

------------------------------------------------------------------------

## ⭐ Project

If you find this project useful or interesting, consider giving the
repository a ⭐ on GitHub.

### 🚀 [Try the Live Demo](https://multi-agentic-ai-research-system.streamlit.app/)

### 💻 [View Source Code](https://github.com/Kishormate05/Multi-Agent-AI-Research-System)

------------------------------------------------------------------------

```{=html}
<p align="center">
```
Built with Python, LangGraph, LangChain, Gemini, Tavily, FAISS,
HuggingFace & Streamlit.
```{=html}
</p>
```
