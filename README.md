# 🧠 LangGraph Blog Writing Agent

An **Agentic AI-powered blog generation system** built using **LangGraph, Azure OpenAI, and Streamlit** that can autonomously plan, research, write, and enhance technical blogs with optional image generation.

---

## 🚀 Overview

This project implements a **multi-agent workflow** where different agents collaborate to generate high-quality blogs:

* 🧭 **Router Agent** → decides if research is needed
* 🔎 **Research Agent** → gathers real-world evidence (via Tavily)
* 🧩 **Planner (Orchestrator)** → creates structured blog outline
* ✍️ **Worker Agents** → generate individual sections
* 🖼️ **Reducer + Image Agents** → merge content + generate diagrams
* 💻 **Streamlit UI** → interactive interface for users

---

## ✨ Features

* ✅ End-to-end **automated blog generation**
* ✅ Supports **3 modes**:

  * `closed_book` → no research
  * `hybrid` → partial research
  * `open_book` → real-time/news-based blogs
* ✅ Multi-agent architecture using **LangGraph**
* ✅ Parallel section generation using **fan-out workers**
* ✅ Automatic **image generation (Gemini API)**
* ✅ Markdown preview with **local image rendering**
* ✅ Download options:

  * Markdown file
  * Full bundle (MD + images)
* ✅ View and reload **past blogs**

---

## 🏗️ Architecture

```
User Input (Topic)
        ↓
     Router
        ↓
   (Optional)
    Research
        ↓
  Orchestrator (Plan)
        ↓
     Fan-out
   Worker Agents
        ↓
   Reducer Graph
 (Merge → Images → Final)
        ↓
   Streamlit UI Output
```

---

## 🛠️ Tech Stack

* **LLM**: Azure OpenAI (GPT-based models)
* **Framework**: LangGraph
* **Backend**: Python
* **Frontend**: Streamlit
* **Search API**: Tavily
* **Image Generation**: Gemini (google-genai)
* **Data Handling**: Pandas
* **State Management**: TypedDict + Pydantic

---

## 📂 Project Structure

```
.
├── app.py                  # Streamlit UI
├── bwa_backend.py          # LangGraph workflow
├── images/                 # Generated images
├── *.md                    # Generated blogs
├── .env                    # API keys
└── README.md
```

---

## ⚙️ Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/your-username/blog-writing-agent.git
cd blog-writing-agent
```

### 2. Set environment variables

Create a `.env` file:

```env
AZURE_ENDPOINT=your_endpoint
AZURE_OPENAI_API_KEY=your_key
AZURE_DEPLOYMENT=your_deployment
AZURE_API_VERSION=your_version

TAVILY_API_KEY=your_tavily_key
GOOGLE_API_KEY=your_gemini_key
```

---

## ▶️ Run the App

```bash
streamlit run app.py
```

---

## 🧪 How It Works

1. Enter a **blog topic**
2. System decides:

   * Does it need research?
3. If yes:

   * Fetches latest data using Tavily
4. Generates:

   * Blog outline (Plan)
   * Multiple sections (Workers)
5. Merges content
6. Optionally:

   * Adds diagrams using Gemini
7. Outputs:

   * Markdown blog
   * Images
   * Downloadable bundle

---

## 🖼️ Image Generation

* Automatically inserts placeholders like:

  ```
  [[IMAGE_1]]
  ```
* Replaces with:

  * Generated diagrams
  * Captions + alt text
* Falls back gracefully if generation fails

---

## 📊 Example Use Cases

* Technical blog writing
* AI/ML explainers
* Weekly AI news summaries
* System design articles
* Developer tutorials

---

## 📌 Future Improvements

* 🔄 Integration with publishing platforms (Medium, Hashnode)
* 🧠 Better memory for personalized writing style
* 🌐 Real-time web scraping improvements
* 🎨 UI enhancements
* 📊 SEO optimization agent

---

Give it a ⭐ on GitHub and share with others!
