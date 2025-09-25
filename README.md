# MCP Weather Server

This repository contains a comprehensive Model Context Protocol (MCP) server implementation that fetches real-time weather alerts from the National Weather Service API. The project showcases multiple MCP server patterns, client implementations including interactive chat with LLM integration, and various deployment options from Claude Desktop integration to Docker containerization, making it an excellent learning resource for MCP development and weather data integration.

## Features

### Weather Tools
- **Weather Alerts**: Get active weather alerts for any US state using the National Weather Service API
- **Real-time Data**: Fetch current weather warnings, watches, and advisories
- **Formatted Output**: Clean, readable alert descriptions with severity levels and instructions

### MCP Implementation
- **FastMCP Framework**: Built with FastMCP for streamlined server development
- **Multiple Server Patterns**: Includes both basic and advanced MCP server examples
- **Resource Support**: Echo resources for testing and development

### Client Options
- **Interactive Chat**: Conversational interface powered by LangChain and Groq LLM
- **Multiple Protocols**: Support for both stdio and Server-Sent Events (SSE)
- **Memory Management**: Built-in conversation history and context management
- **Docker Support**: Containerized deployment option

## Project Structure

```
├── server/                 # Main weather MCP server
│   ├── weather.py         # FastMCP-based weather server implementation
│   ├── client.py          # Interactive chat client with Groq LLM
│   └── weather.json       # MCP server configuration file
├── mcpserver/             # Alternative server implementations
│   ├── server.py          # Alternative MCP server approach
│   ├── client-sse.py      # Server-Sent Events client
│   ├── client-stdio.py    # Standard I/O client
│   ├── Dockerfile         # Docker containerization
│   └── requirements.txt   # Docker dependencies
└── pyproject.toml         # Project configuration and dependencies
```

## Setup & Installation

1. **Clone and setup the project**:
```bash
git clone <repository-url>
cd mcp-sample
```

2. **Install dependencies**:
```bash
uv sync
```

3. **Set up environment variables** (create a `.env` file):
```env
GROQ_API_KEY=your_groq_api_key_here
```

## Usage Options

### Option 1: Install in Claude Desktop
```bash
uv run mcp install server/weather.py
```
Then use Claude Desktop to interact with your weather server.

### Option 2: Interactive Chat Client
```bash
uv run server/client.py
```
Start a conversational session with memory support.

### Option 3: Development Mode
```bash
uv run mcp dev server/weather.py
```
Run with MCP Inspector for development and debugging.

### Option 4: Docker Deployment
```bash
cd mcpserver
docker build -t mcp-server .
docker run -p 8000:8000 mcp-server
```

## Example Usage

Ask for weather information:
- "Get weather alerts for California"
- "What are the current weather warnings in Texas?"
- "Show me any active alerts in New York"
- "Are there any severe weather alerts in Florida?"

The server accepts 2-letter US state codes (CA, TX, NY, FL, etc.) and returns formatted weather alerts with:
- Event type and severity
- Affected areas
- Detailed descriptions
- Safety instructions

## Development

### Running Alternative Implementations
```bash
cd mcpserver
uv run server.py
```

### Client Testing
```bash
# Test stdio client
uv run mcpserver/client-stdio.py

# Test SSE client  
uv run mcpserver/client-sse.py
```

## Technical Stack

- **MCP (Model Context Protocol)**: Core protocol implementation
- **FastMCP**: Simplified MCP server framework  
- **LangChain**: LLM integration framework
- **Groq**: Fast inference LLM provider
- **National Weather Service API**: Real-time weather data source
- **Docker**: Containerization support
- **uv**: Modern Python package and project management
- **httpx**: Async HTTP client for API requests

## Configuration

### MCP Server Configuration (`server/weather.json`)
```json
{
    "mcpServers": {
        "weather": {
            "command": "uv",
            "args": ["run", "--with", "mcp[cli]", "mcp", "run", "server/weather.py"]
        }
    }
}
```

### Environment Variables
- `GROQ_API_KEY`: Required for conversational AI features
- Configure in `.env` file or system environment


This project is licensed under the MIT License - see the LICENSE file for details.
