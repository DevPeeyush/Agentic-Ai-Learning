# AgenticAI

A hands-on learning project for building LLM applications and agentic workflows with
LangChain, LangGraph, Streamlit, vector search, and external tools.

The repository progresses from simple graph workflows to chat applications with
streaming, conversation persistence, tools, MCP integration, and retrieval-augmented
generation (RAG).

## What this project covers

- Basic LangGraph state and message handling
- Linear/sequential workflows
- Parallel workflows
- Conditional routing
- Iterative workflows
- LangGraph persistence and checkpoints
- Streamlit chat interfaces
- Streaming model responses
- Conversation threads and database-backed chat history
- Tool-calling agents
- MCP-based tool integration
- RAG pipelines and document loading
- Human-in-the-loop (HITL) workflows
- Subgraphs and shared state
- LangSmith tracing and observability
- Embeddings and FAISS-based vector search

## Repository structure

```text
00_Dependency_check.ipynb       Dependency and environment checks
01_Simple_Liner_WorkFlow/       Sequential workflows, with and without an LLM
02_Parallel_WorkFlow/            Parallel graph execution
03_Conditional_Workflow/         Conditional routing
04_Iterative_Workflow/           Iterative graph execution
05_ChatBot/                     Streamlit chat applications and backends
06_Persitence/                  LangGraph persistence examples
07_Langsmith/                   LangSmith, RAG, agents, and LangGraph examples
08_HITL/                        Human-in-the-loop examples
09_SubGraph/                    Subgraph and shared-state examples
requirements.txt                 Project dependencies
technology_know.md               Broader technology learning roadmap
```

## Chatbot examples

The [`05_ChatBot`](./05_ChatBot) directory contains progressively more capable
applications:

1. Threaded Streamlit chat
2. Streaming responses
3. Basic Streamlit frontend
4. Database-backed conversation history
5. Tool-calling chatbot
6. MCP-enabled chatbot
7. RAG chatbot

The chatbot backends are kept in separate Python files so that the frontend and
LangGraph logic can be studied independently.

## Requirements

- Python 3.10 or newer
- A configured LLM provider API key
- Git (optional, for version control)

The project currently uses Python packages including:

- `langchain`, `langchain-core`, and `langgraph`
- OpenAI, Anthropic, Google Gemini, Hugging Face, and Groq integrations
- `streamlit`
- `python-dotenv`
- `pypdf`
- `sentence-transformers`
- `faiss-cpu`
- `langgraph-checkpoint-sqlite`

## Setup

From the project root:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
```

On Windows PowerShell, activate the environment with:

```powershell
.venv\Scripts\Activate.ps1
```

Create a local `.env` file in the project root and add only the credentials
required by the example you want to run. For example:

```dotenv
OPENAI_API_KEY=your-key
GROQ_API_KEY=your-key
LANGCHAIN_API_KEY=your-key
LANGCHAIN_TRACING_V2=true
LANGCHAIN_PROJECT=AgenticAI
```

Never commit `.env` or API keys. They are excluded by
[`.gitignore`](./.gitignore).

## Running the examples

### Jupyter notebooks

Start Jupyter from the project root:

```bash
jupyter notebook
```

Then open the notebook for the topic you want to study. The numbered directories
are arranged in a recommended learning order.

### Streamlit chatbots

Run a selected frontend from the `05_ChatBot` directory:

```bash
cd 05_ChatBot
streamlit run 01_streamlit_frontend_threading.py
```

Other frontends can be started in the same way:

```bash
streamlit run 02_streamlit_frontend_streaming.py
streamlit run 04_streamlit_frontend_database.py
streamlit run 05_streamlit_frontend_tool.py
streamlit run 06_streamlit_frontend_mcp.py
streamlit run 07_streamlit_rag_frontend.py
```

The exact API keys and external services required depend on the selected backend.
Check the corresponding backend file before running an example.

### LangSmith examples

The examples in [`07_Langsmith`](./07_Langsmith) demonstrate:

- Simple LLM calls
- Sequential chains
- Multiple RAG versions
- Agents
- LangGraph execution

Run a script from that directory with:

```bash
cd 07_Langsmith
python 1_simple_llm_call.py
```

Set the LangSmith environment variables in `.env` when tracing is enabled.

## Local data and generated files

Local virtual environments, environment files, Jupyter checkpoints, indexes,
SQLite databases, logs, caches, and Python build artifacts are intentionally
ignored by Git. This keeps machine-specific and generated files out of GitHub.

## Learning path

For a structured walkthrough, follow the numbered folders in this order:

1. Dependency check
2. Simple and parallel workflows
3. Conditional and iterative workflows
4. Chatbot frontends and LangGraph backends
5. Persistence
6. LangSmith observability
7. Human-in-the-loop workflows
8. Subgraphs

## Status

This is an active educational project. Examples may use different model providers
and may require provider-specific configuration before they run.
