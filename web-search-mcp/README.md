# Web Search MCP

A Model Context Protocol server that provides web search capabilities using SerpAPI.

## What it does

- **General Search**: Regular web search results
- **News Search**: Recent news articles  
- **Product Search**: Shopping/product results
- **Q&A Search**: Direct answers to questions

## Setup

1. Get a free API key from [SerpAPI](https://serpapi.com/)
2. Create `.env` file:
   ```
   SERPAPI_KEY=your_api_key_here
   ```
3. Install dependencies:
   ```bash
   uv sync
   ```

## Run

**Start the server:**
```bash
python server.py
```

**Test with client (new terminal):**
```bash
python client.py
```

**Interactive mode:**
```bash
python client.py --interactive
```