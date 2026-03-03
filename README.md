---
title: Conversational AI Agent
emoji: 🚀
colorFrom: gray
colorTo: red
sdk: streamlit
sdk_version: 6.8.0
app_file: app.py
pinned: false
license: apache-2.0
short_description: Conversation chatbot with AI Agent
---


# 🔎 LangChain - Chat with Search

> An AI-powered chatbot that can search the web, query Wikipedia, and find research papers on Arxiv — all in real time using **Groq LLM** and **LangChain Agents**. Free to use!

---

## 📌 What Does This App Do?

This app is a smart conversational agent that can:

- 🌐 **Search the web** using DuckDuckGo for current information
- 📚 **Search Wikipedia** for factual and encyclopedic knowledge
- 🔬 **Search Arxiv** for academic research papers
- 💬 **Maintains chat history** across the entire conversation
- 🧠 **Shows its thinking process** — watch the agent reason step by step in real time

---

## 🛠️ How It Works

```
User asks a question
        │
        ▼
Groq LLM (llama-3.1-8b-instant) decides which tool to use
        │
        ├──► DuckDuckGo Search  → for general web queries
        ├──► Wikipedia          → for factual knowledge
        └──► Arxiv              → for research papers
        │
        ▼
Agent reasons through results (ReAct framework)
        │
        ▼
Final answer streamed back to user via Streamlit
```

The agent uses the **ZERO_SHOT_REACT_DESCRIPTION** strategy — it reads the tool descriptions and decides on its own which tool best answers each question.

---

## ⚙️ Tech Stack

| Technology | Purpose | Cost |
|------------|---------|------|
| [Groq](https://console.groq.com) | LLM inference (llama-3.1-8b-instant) | Free |
| [LangChain](https://python.langchain.com) | Agent and tool orchestration | Free |
| [DuckDuckGo Search](https://pypi.org/project/duckduckgo-search/) | Real-time web search | Free, no API key |
| [Wikipedia API](https://pypi.org/project/wikipedia/) | Encyclopedic knowledge | Free, no API key |
| [Arxiv API](https://pypi.org/project/arxiv/) | Research paper search | Free, no API key |
| [Streamlit](https://streamlit.io) | Web UI with streaming | Free |

> ✅ **Only requires a free Groq API key — no other API keys needed!**

---

## 🚀 How to Use

### On HuggingFace Spaces:
1. Open the app
2. Enter your **free Groq API key** in the sidebar ([get one here](https://console.groq.com))
3. Type any question in the chat input
4. Watch the agent search and reason in real time!

### Run Locally:

**1. Clone the repo:**
```bash
git clone https://huggingface.co/spaces/dev-2106/langchain-chat-search
cd langchain-chat-search
```

**2. Install dependencies:**
```bash
pip install streamlit langchain langchain-groq langchain-community duckduckgo-search wikipedia arxiv python-dotenv
```

**3. Create `.env` file:**
```env
GROQ_API_KEY=your-groq-api-key
```

**4. Run the app:**
```bash
streamlit run app.py
```

---

## 🔑 API Keys Required

| Key | Where to Get | Cost |
|-----|-------------|------|
| `GROQ_API_KEY` | [console.groq.com](https://console.groq.com) | Free |

> DuckDuckGo, Wikipedia, and Arxiv require **no API keys** at all.

---

## 💡 Features

- ✅ **Real-time streaming** — see the response being generated token by token
- ✅ **Agent thought process visible** — watch the agent decide which tool to use
- ✅ **3 search tools** — web, Wikipedia, and Arxiv all in one chatbot
- ✅ **Chat history** — full conversation context maintained across messages
- ✅ **No OpenAI needed** — powered entirely by free Groq inference

---

## 📋 Requirements

```txt
streamlit
langchain
langchain-groq
langchain-community
duckduckgo-search
wikipedia
arxiv
python-dotenv
```

---

## 🐛 Common Issues & Fixes

| Error | Cause | Fix |
|-------|-------|-----|
| `No module named 'langchain_classic'` | Deprecated package | Use `from langchain.agents import initialize_agent` |
| `DuckDuckGo RateLimit` | Too many requests | Wait 30 seconds and retry |
| `GROQ 429 rate limit` | Free tier exceeded | Wait 60 seconds and retry |
| `Parsing error` | LLM response format issue | Already handled with `handle_parsing_errors=True` |

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<p align="center">Built with ❤️ using LangChain, Groq and Streamlit</p>
