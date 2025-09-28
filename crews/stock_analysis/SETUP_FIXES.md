 # Working CrewAI Stock Analysis Setup

  This version includes fixes for compatibility issues found in the original example.

  ## Fixes Applied

  ### 1. Python Version Compatibility
  - **Issue**: Python 3.13 compilation errors with chroma-hnswlib
  - **Fix**: Use Python 3.12 (`uv python pin 3.12`)

  ### 2. Calculator Tool Import Fix
  - **File**: `src/stock_analysis/tools/calculator_tool.py`
  - **Issue**: `from crewai_tools import BaseTool` (wrong import)
  - **Fix**: `from crewai.tools import BaseTool`

  ### 3. SEC Tools Pydantic Version Fix
  - **File**: `src/stock_analysis/tools/sec_tools.py`
  - **Issue**: `from pydantic.v1 import BaseModel, Field` (old version)
  - **Fix**: `from pydantic import BaseModel, Field`

  ### 4. LLM Configuration Fix
  - **File**: `src/stock_analysis/crew.py`
  - **Issue**: Ollama configuration without local installation
  - **Fix**: Switch to OpenAI (`from langchain_openai import ChatOpenAI`)

  ### 5. SEC Tool Schema Fix
  - **Issue**: Schema mismatch causing `stock_name` parameter errors
  - **Fix**: Use `FixedSEC10KToolSchema` and `FixedSEC10QToolSchema` as default schemas

  ## Quick Setup

  ```bash
  # Use Python 3.12
  uv python install 3.12
  uv python pin 3.12

  # Install dependencies
  uv sync

  # Configure API keys
  cp .env.example .env
  # Edit .env with your API keys

  # Run the analysis
  uv run python src/stock_analysis/main.py

  API Keys Required

  - OpenAI API Key
  - Serper API Key (free tier)
  - Browserless API Key (free tier)
  - SEC API Key (free tier)
