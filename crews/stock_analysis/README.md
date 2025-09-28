# AI Crew for Stock Analysis (Working Version)

  This is a **working version** of the CrewAI stock analysis example with compatibility fixes applied.

  ## 🛠️ Fixes Applied

  This version addresses several compatibility issues found in the original example:

  1. **Python 3.13 → 3.12**: Fixes C++ compilation errors with chroma-hnswlib
  2. **Calculator Tool Import**: Fixed `crewai_tools` → `crewai.tools` import
  3. **Pydantic v2 Compatibility**: Updated from `pydantic.v1` to `pydantic`
  4. **OpenAI instead of Ollama**: Configured for cloud LLM usage
  5. **SEC Tool Schema**: Fixed parameter mismatch errors

  ## 🚀 Quick Start

  ### Prerequisites
  - Python 3.12 (required for compatibility)
  - uv package manager
  - API keys for OpenAI, Serper, Browserless, and SEC-API

  ### Setup
  ```bash
  # Install Python 3.12 and set up environment
  uv python install 3.12
  uv python pin 3.12
  uv sync

  # Configure API keys
  cp .env.example .env
  nano .env  # Add your API keys

  # Run the analysis
  uv run python src/stock_analysis/main.py

  Required API Keys

  - OpenAI: https://platform.openai.com/api-keys
  - Serper: https://serper.dev/
  - Browserless: https://www.browserless.io/
  - SEC-API: https://sec-api.io/

  📊 What It Does

  This CrewAI system analyzes Amazon (AMZN) stock using three specialized AI agents:

  1. Financial Analyst - Analyzes SEC filings and financial metrics
  2. Research Analyst - Gathers market news and sentiment
  3. Investment Advisor - Synthesizes data into investment recommendations

  🔧 Technical Details

  - Framework: CrewAI for multi-agent orchestration
  - LLM: OpenAI GPT-4
  - Data Sources: SEC filings (10-K, 10-Q), web scraping
  - Vector Database: ChromaDB with HNSW for document search
  - Tools: Custom RAG tools, calculator, web scrapers

  📝 Sample Output

  The crew generates comprehensive investment reports including:
  - Financial health analysis
  - Growth metrics and ratios
  - Risk assessment
  - Buy/sell/hold recommendations

  🐛 Known Issues

  - Web scraping may fail due to anti-bot protection (crew adapts gracefully)
  - SSL certificate errors on some financial sites (non-critical)

  📚 Original Documentation

  See README_ORIGINAL.md for the original CrewAI example documentation.

  🤝 Contributing

  This is a working fork of the https://github.com/crewAIInc/crewAI-examples repository with fixes applied for real-world usage.
