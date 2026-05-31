# Multi-Agent Research System

A multi-agent AI pipeline built with LangGraph, LangChain, and Groq that autonomously researches any topic — searching the web, scraping content, writing a structured report, and critically reviewing it.

---

## Features

- **Search Agent:** Finds recent and reliable information about any topic using web search.
- **Reader Agent:** Scrapes the most relevant URL from search results for deeper content.
- **Writer Chain:** Generates a detailed, structured research report with key findings and sources.
- **Critic Chain:** Reviews and scores the report with strengths, areas to improve, and a final verdict.
- **Streamlit UI:** Clean interactive interface to run the full pipeline from the browser.
- **Terminal Mode:** Run the full pipeline directly from the command line.

---

## Tech Stack

- [LangChain](https://langchain.com/) — Agent framework
- [LangGraph](https://langchain-ai.github.io/langgraph/) — Multi-agent orchestration
- [Groq](https://groq.com/) — LLM inference (Llama 3.3 70B)
- [Streamlit](https://streamlit.io/) — Web interface

---

## Project Structure

```
multi-agent-system/
├── app.py           # Streamlit UI
├── pipeline.py      # Main research pipeline orchestration
├── agents.py        # Agent and chain definitions
├── tools.py         # Web search and scraping tools
├── requirements.txt
└── README.md
```

---

## Requirements

- Python 3.10+
- Groq API Key — [Get one free here](https://console.groq.com)

---

## Installation

1. **Clone the repository:**

```bash
git clone https://github.com/Vatshitha392/multi-agent-system.git
cd multi-agent-system
```

2. **Install dependencies:**

```bash
pip install -r requirements.txt
```

3. **Set up environment variables:**

Create a `.env` file in the project root:

```
GROQ_API_KEY=your_groq_api_key_here
```

---

## Usage

**Run the Streamlit app:**

```bash
streamlit run app.py
```

**Or run in terminal mode:**

```bash
python pipeline.py
```

The pipeline runs 4 stages sequentially:

| Step | Agent | What it does |
|------|-------|-------------|
| 1 | 🔍 Search Agent | Finds recent, reliable information on the topic |
| 2 | 📄 Reader Agent | Scrapes the most relevant URL for deeper content |
| 3 | ✍️ Writer Chain | Drafts a structured report with key findings and sources |
| 4 | 🎯 Critic Chain | Reviews, scores, and provides feedback on the report |

---

## Deployment

Live Demo: https://multi-agent-system.streamlit.app

This app is deployed on **Streamlit Community Cloud**. To deploy your own instance:

1. Push your code to GitHub
2. Go to [share.streamlit.io](https://share.streamlit.io) and connect your repo
3. Under **Advanced settings → Secrets**, add:

```toml
GROQ_API_KEY = "your_groq_api_key_here"
```

4. Set main file path to `app.py` and deploy

---

## Notes

- Never commit your `.env` file or expose your API key publicly.
- Groq's free tier has rate limits — avoid rapid repeated requests.
- On Streamlit Cloud, API keys must be set via **Manage App → Settings → Secrets**, not via `.env`.
