# AI Stock Analyst Crew

> Multi-agent AI system that analyzes stocks using SEC filings, news, and market data

**Built for:** Audience request for automated stock research using AI agents  
**Build time:** ⏱️ 11 hours (including compatibility fixes)  
**Part of:** [thexperiment.dev](https://thexperiment.dev)

---

## 🎯 What It Does

Enter a stock ticker (e.g., AMZN) and watch three AI agents collaborate to produce a comprehensive investment report. The Financial Analyst reviews SEC filings, the Research Analyst gathers market sentiment, and the Investment Advisor synthesizes everything into actionable recommendations.

**Note:** This runs entirely in the terminal - you'll see the agents "thinking" and collaborating in real-time as they research the stock.

---

## ⚡ Tech Stack

- **Framework:** CrewAI (multi-agent orchestration)
- **LLM:** OpenAI GPT-4
- **Data Sources:** SEC-API (10-K, 10-Q filings), Serper (web search), Browserless (web scraping)
- **Vector DB:** ChromaDB with HNSW

---

## 🚀 Quick Start

**Step 1: Get Your API Keys** (15 minutes)
1. **OpenAI:** Go to [platform.openai.com](https://platform.openai.com/api-keys) → Create account → Generate API key
2. **Serper:** Visit [serper.dev](https://serper.dev/) → Sign up → Get free 2,500 searches
3. **Browserless:** Visit [browserless.io](https://www.browserless.io/) → Sign up for free trial
4. **SEC-API:** Go to [sec-api.io](https://sec-api.io/) → Create account → Get API key


**Step 2: Download and Setup** (5 minutes)
```bash
# Download the project
git clone https://github.com/irivelez/crewAI-examples.git
cd crews
cd stock_analysis

# Copy the configuration template
cp .env.example .env

# Edit .env file and paste your 4 API keys
# (Use any text editor like Notepad, TextEdit, or nano)
```

**Step 3: Install and Run** (5 minutes)
```bash
# Install Python environment manager (one-time setup)
# Mac/Linux:
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows:
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# Install dependencies
uv sync

# Run the analysis
uv run python src/stock_analysis/main.py
```

**What happens next:**
- The terminal will show the agents working
- You'll see them searching, analyzing, and discussing
- After 2-5 minutes, you'll get a full investment report
- Default stock: Amazon (AMZN).

The crew will analyze AMZN (Amazon) by default. Edit `main.py` to change the stock ticker.

---

## 💡 Why This Exists

Someone asked: "quiero construir un CFA - AI que pueda hacer todas las funciones de un analista financiero, inversiones, revison de portafolios, asesor de inversion y financiero etc.. " This proves a CFA can be built. Three specialized agents collaborating to produce institutional-quality stock analysis.

---

## 🤖 The Agent Crew

- **Financial Analyst** - Deep dives into SEC filings and financial metrics
- **Research Analyst** - Gathers market news, sentiment, and trends
- **Investment Advisor** - Synthesizes findings into buy/sell/hold recommendations

---

## 📊 Output Example

Generates a comprehensive report with:
- Financial health analysis
- Growth metrics and valuation ratios
- Risk assessment
- Investment recommendation with reasoning

---

## ⚠️ Note

This is a **working fork** of the official CrewAI example with Python 3.13 compatibility fixes applied. Original example had dependency conflicts. This version works out of the box.

Here's what I fixed:
- **Python 3.13 compatibility issues** - Downgraded to 3.12 to fix C++ compilation errors
- **Import path bugs** - Fixed `crewai_tools` → `crewai.tools`
- **Pydantic v2 migration** - Updated deprecated `pydantic.v1` imports
- **SEC Tool schema errors** - Fixed parameter mismatches
- **Dependency conflicts** - Resolved ChromaDB HNSW issues

Real-world debugging > following tutorials. This version works first try.

---

## ⚠️ Troubleshooting

**"Command not found: uv"**  
→ Run the install script again from Step 3, then restart your terminal

**"API key error"**  
→ Check your .env file has all 4 keys (no quotes needed, one per line)

**Agents seem stuck**  
→ It's normal! GPT-4 can take 30-60 seconds per agent. Watch the terminal output.

---

**⚡ Built in 11 hours • Part of [thexperiment.dev](https://thexperiment.dev)**

