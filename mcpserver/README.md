# Alternative MCP Server

Alternative MCP server implementation with multiple client patterns and Docker support.

## What it does

- **Alternative MCP Server**: Different server implementation approach
- **Multiple Clients**: stdio and Server-Sent Events (SSE) clients
- **Docker Support**: Containerized deployment option

## Setup

**Local setup:**
```bash
pip install -r requirements.txt
```

**Docker setup:**
```bash
docker build -t mcp-server .
```

## Run

**Start the server:**
```bash
python server.py
```

**Test with stdio client:**
```bash
python client-stdio.py
```

**Test with SSE client:**
```bash
python client-sse.py
```

**Docker deployment:**
```bash
docker run -p 8000:8000 mcp-server
```