# LangGraph_with_API
AI Chatbot with Gemini + LangGraph  This project is a Python chatbot that uses LangGraph with Google Gemini and external tools to answer questions and call APIs when needed (weather, distance, search, stock price, CEO lookup). It demonstrates how to build an LLM agent that combines model reasoning with real-time data via tool execution.

# 🤖 AI Chatbot using LangGraph + Google Gemini + External APIs

This project implements an intelligent chatbot in Python that combines **LLM reasoning (Google Gemini)** with **external tool execution** using **LangGraph**.  
Unlike a normal LLM chatbot that only responds from its trained data, this agent can call real APIs at runtime to fetch **live information** (weather, maps distance, search results, etc.) when needed.

---

## 🧠 What This Bot Can Do

| Capability | Powered By |
|-----------|------------|
| Answer general questions | Google Gemini LLM |
| Get current weather by city | OpenWeather API |
| Calculate driving distance & time between locations | Google Maps Distance Matrix API |
| Perform Google search | SerpAPI |
| Lookup stock prices (demo) | Local Python function |
| Lookup company CEO names (demo) | Local Python function |

---

## 🧩 Architecture Overview

This project uses **LangGraph** to manage the decision flow between the LLM and tools.

- `chatbot` node → calls the LLM with tool-binding
- `tools` node → executes Python functions when the LLM requests a tool call
- `tools_condition` → automatically routes execution to tools only when necessary

The graph maintains conversation state using `add_messages` so the conversation is preserved between turns.

---

## 📁 Project Structure (conceptual)

├── chatbot_logic.py # LLM + tools binding + graph routing

├── tools/ # Weather, maps, search helpers

├── .env # API keys (not committed)

└── README.md

yaml
Copy code

---

## 🔑 Environment Variables

Create a `.env` file in project root:

OPENWEATHER_API_KEY=YOUR_KEY

SERPAPI_API_KEY=YOUR_KEY

MAPS_API_KEY=YOUR_KEY

GOOGLE_API_KEY=YOUR_KEY

yaml
Copy code

---

## 🛠 Installation & Setup

```bash
git clone <repo-url>
cd <repo-folder>
pip install -r requirements.txt
Run the script:

bash
Copy code
python your_script.py
✅ Example Queries You Can Try
pgsql
Copy code
What is the weather in Dallas city?
What is the distance and duration between 12024 Arabian Rd and 3520 Ashley Gardens?
Who is the CEO of Google?
Who invented gravity?
The chatbot will automatically decide when to answer via Gemini and when to make API calls.

🎯 Why This Project Matters
Modern AI systems should not rely only on static training.
This project demonstrates how to build real-world LLM agents that merge:

Reasoning (large language models)

Real-time data (APIs)

Decision flow control (LangGraph)

This provides a reusable blueprint for building AI copilots, business assistants, and production-ready intelligent agents.

📌 Next Steps (Ideas to Extend)
Add database queries as tools

Add ERP / CRM integrations (SAP / Oracle / Salesforce)

Add RAG (vector DB) for internal knowledge answers

Add error handling + retries for API calls

Convert to API (FastAPI endpoint for chatbot)

Feel free to fork, extend, or integrate this into your own AI agent pipelines.

Happy Building! 🚀
