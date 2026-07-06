# Agentic Technical Support Assistant

##  Project Overview

This project implements an **Agentic Retrieval-Augmented Generation (RAG)** system using **LangGraph**, **LangChain**, **OpenAI GPT**, **ChromaDB**, and **Streamlit**.

The application acts as an intelligent technical support assistant for the **Orion SmartHub X1 Pro**. It retrieves relevant information from a product manual, evaluates document relevance, generates grounded responses, performs web search when necessary, and checks for hallucinations before presenting the final answer.

---

##  Features

- Multi-Agent workflow using LangGraph
- Query Rewriting Agent
- Semantic Search with Chroma Vector Database
- Document Relevance Grading
- Web Search Fallback using DuckDuckGo
- Grounded Response Generation using GPT
- Hallucination Detection
- Interactive Streamlit User Interface

---

## Project Architecture

```text
                 User Question
                       │
                       ▼
             Query Rewriter Agent
                       │
                       ▼
          Chroma Vector Database Search
                       │
                       ▼
            QA Document Grader Agent
                 │             │
         Relevant? Yes       No
                 │             │
                 ▼             ▼
         Response Generator   Web Search
                 │             │
                 └──────┬──────┘
                        ▼
           Hallucination Checker
                        │
                        ▼
                 Final Response
```

---

##  Project Structure

```text
Agentic_AI_Assignment/
│
├── Agentic_AI_Assignment.ipynb     # Development notebook
├── graph.py                        # LangGraph workflow
├── app.py                          # Streamlit application
├── requirements.txt                # Project dependencies
├── README.md                       # Project documentation
├── orion_hub_manual.pdf            # Knowledge base
└── .env                            # OpenAI API Key (not included)
```

---

## Technologies Used

- Python
- LangChain
- LangGraph
- OpenAI GPT-4.1 Mini
- ChromaDB
- OpenAI Embeddings
- Streamlit
- PyPDF
- DuckDuckGo Search
- Pydantic
- Python Dotenv

---

## Installation

### 1. Clone the repository

```bash
git clone <repository-url>
cd Agentic_AI_Assignment
```

### 2. Create a virtual environment

```bash
python3 -m venv venv
```

### 3. Activate the environment

**macOS / Linux**

```bash
source venv/bin/activate
```

**Windows**

```bash
venv\Scripts\activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Create a `.env` file

Create a file named `.env` in the project root and add your OpenAI API key:

```text
OPENAI_API_KEY=your_openai_api_key
```

---

## ▶️ Run the Application

Start the Streamlit application:

```bash
streamlit run app.py
```

The application will open in your browser at:

```
http://localhost:8501
```

---

## 💬 Example Questions

Try asking questions such as:

- My hub keeps showing a flashing red light.
- How do I factory reset the SmartHub?
- What does the blinking amber LED indicate?
- How do I configure the SmartHub for the first time?
- What is ERR-302?

---

##  Agent Workflow

The application uses multiple AI agents coordinated through LangGraph:

1. **Query Rewriter** – Converts user questions into optimized technical search queries.
2. **Retriever** – Searches the Chroma vector database for relevant document chunks.
3. **QA Grader** – Determines whether retrieved documents are relevant.
4. **Web Search Agent** – Performs external search if retrieved documents are insufficient.
5. **Response Generator** – Produces a grounded technical answer using retrieved context.
6. **Hallucination Checker** – Verifies that the generated response is supported by the available evidence.

---

## Future Improvements

- Conversation memory
- Multi-document support
- Citation of retrieved document sections
- Persistent Chroma database
- Docker deployment
- Cloud deployment (Streamlit Community Cloud)

---

##  Author

**Iram Ishtiaq**

Agentic AI Assignment

---

## 📄 License

This project was developed for educational purposes as part of an Agentic AI assignment.
