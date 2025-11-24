# iholovatsky-mcps
MCP Servers to enable my personal AI workflows

## Solution Structure

This repository contains a Visual Studio solution (`Mcps.sln`) with multiple Model Context Protocol (MCP) server projects built using .NET 10.

### Projects

| Project | Description |
|---------|-------------|
| `Saldeo.Mcp` | MCP server for Saldeo integration |
| `Ibkr.Mcp` | MCP server for Interactive Brokers (IBKR) integration |
| `BnpParibasPoland.Mcp` | MCP server for BNP Paribas Poland integration |
| `Lucit.Mcp` | MCP server for Lucit integration |

## Getting Started

### Prerequisites

- .NET 10 SDK

### Building

```bash
dotnet build Mcps.sln
```

### Running an MCP Server

Each MCP server runs as a console application communicating via STDIO:

```bash
dotnet run --project src/Saldeo.Mcp/Saldeo.Mcp.csproj
```

## Adding to AI Clients

To connect an MCP server to an AI client (e.g., GitHub Copilot in VS Code), add an entry to your `.vscode/mcp.json`:

```json
{
  "servers": {
    "Saldeo": {
      "type": "stdio",
      "command": "dotnet",
      "args": ["run", "--project", "path/to/src/Saldeo.Mcp/Saldeo.Mcp.csproj"]
    }
  }
}
```
