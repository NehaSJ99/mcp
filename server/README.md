# Weather MCP Server

A FastMCP-based server that provides weather alerts from the National Weather Service API.

## What it does

- **Weather Alerts**: Get active weather alerts for any US state
- **Echo Resource**: Simple resource for testing
- **Interactive Chat**: Conversational interface with LLM integration

## Setup

1. Create `.env` file:
   ```
   GROQ_API_KEY=your_groq_api_key_here
   ```

2. Install dependencies (from project root):
   ```bash
   uv sync
   ```

## Run

**Install in Claude Desktop:**
```bash
uv run mcp install server/weather.py
```

**Development mode:**
```bash
uv run mcp dev server/weather.py
```

**Interactive chat client:**
```bash
uv run server/client.py
```

## Usage

Ask for weather alerts by state code:
- "Get weather alerts for California" (CA)
- "Show me alerts for Texas" (TX)
- "Any weather warnings in New York?" (NY)