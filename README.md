# Agent-Based Call Drop Analysis in Telecommunications

CAPSTONE PROJECT 13

Title: Agent-Based Call Drop Analysis in Telecommunications

Problem Statement:
Telecom operators continuously monitor network performance to ensure seamless connectivity for customers. However, call drops remain a persistent issue in urban and semi-urban areas due to factors such as weak signal strength, tower congestion, and handoff failures.

Traditionally, engineers spend significant time manually analyzing telecom logs to find root causes. This is time-consuming, error-prone, and reactive instead of proactive.

The challenge is to design an AI Agent system that can:
1. Retrieve relevant network logs from a database.
2. Analyze and identify the most likely causes of call drops in a given region.
3. Summarize findings in human-readable language.
4. Recommend possible solutions automatically.

The system should be built using open-source tools only, with no fine-tuning or new model training. Instead, it should rely on retrieval-augmented generation (RAG) and agent orchestration to perform reasoning and reporting.
Key Objectives
- Automate call drop root cause analysis.
- Provide explainable outputs for telecom engineers.
- Reduce time from log collection to actionable insight.
- Demonstrate the use of LLM agents in telecommunications.
Benefits
- Faster troubleshooting and reduced manual effort.
- Scalable to larger telecom datasets.
- Improves customer experience with quicker issue resolution.
- Provides a practical demonstration of AI agent applications.
Technical Stack (Open Source)
- Programming: Python
- Framework: LangChain or LlamaIndex (for agent + RAG)
- LLM: Open-source models via Hugging Face (e.g., LLaMA-2-7B-chat, Mistral-7B-Instruct)
- Embeddings: SentenceTransformers (all-MiniLM-L6-v2)
- Vector Database: ChromaDB / FAISS
- Data Storage: CSV / JSON (telecom logs)
- Interface: Jupyter Notebook or Streamlit
Detailed Steps 
Step 1 (2h): Setup
- Install Python, LangChain/LlamaIndex, ChromaDB, HuggingFace Transformers.
- Load sample telecom log dataset (CSV).

Step 2 (3h): Data Preparation
- Clean and chunk logs.
- Convert into embeddings (e.g., SentenceTransformers all-MiniLM-L6-v2).
- Store in ChromaDB.

Step 3 (4h): Build AI Agent
- Use LangChain Agent with:
   • Tool 1: Query vector DB (fetch relevant log snippets).
   • Tool 2: Summarize issue (via LLM).
   • Tool 3: Recommend resolution (rules-based + LLM).

Step 4 (3h): Test Use Cases
- Input queries like:
   • 'Why are call drops happening in Hyderabad region?'
   • 'Suggest fixes for tower congestion in Delhi.'

Step 5 (3h): Final Output & Report
- Generate text report with:
   • Root cause
   • Evidence from logs
   • Resolution steps
Sample Input Dataset
telecom_logs.csv

| Region   | Tower_ID | Date       | Call_Drops | Signal_Strength | Congestion_Level | Handoff_Failure | Notes |
|----------|----------|------------|------------|-----------------|------------------|-----------------|---------------------|
| Hyderabad| T123     | 2025-09-01 | 56         | -95 dBm         | High             | 12%             | Heavy user load     |
| Delhi    | T456     | 2025-09-01 | 34         | -88 dBm         | Medium           | 8%              | Poor weather        |
| Mumbai   | T789     | 2025-09-01 | 22         | -75 dBm         | Low              | 2%              | Normal operation    |
| Hyderabad| T123     | 2025-09-02 | 72         | -97 dBm         | High             | 15%             | Peak hour traffic   


Sample Output
User Query: 'Why are call drops high in Hyderabad?'

Agent Response:
- Region: Hyderabad, Tower T123
- Observation: Call drops increased from 56 → 72 in last 2 days.
- Root Cause: Weak signal (-95 to -97 dBm) + High congestion + 15% handoff failure.
- Suggested Resolution:. Increase backhaul capacity
   1. Optimize handoff algorithms.
   2. Deploy additional microcell during peak hours.  
