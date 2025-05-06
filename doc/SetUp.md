# Setting Up MCP Debugging Tools

This document provides instructions for setting up and using the Model Context Protocol (MCP) debugging tools.

## Prerequisites

- Node.js: ^22.7.5
- A working MCP server implementation to debug

## Installation

The primary debugging tool for MCP is the MCP Inspector, which can be run without installation using `npx`:

```bash
npx @modelcontextprotocol/inspector <command>
```

## Configuration

### Basic Configuration

The MCP Inspector can be configured through the UI or using configuration files:

```json
{
  "mcpServers": {
    "my-server": {
      "command": "node",
      "args": ["build/index.js", "arg1", "arg2"],
      "env": {
        "key": "value",
        "key2": "value2"
      }
    }
  }
}
```

Save this configuration as a JSON file and reference it with:

```bash
npx @modelcontextprotocol/inspector --config path/to/config.json --server my-server
```

### Advanced Configuration

The MCP Inspector supports the following configuration settings:

| Setting | Description | Default |
| ------- | ----------- | ------- |
| `MCP_SERVER_REQUEST_TIMEOUT` | Timeout for requests to the MCP server (ms) | 10000 |
| `MCP_REQUEST_TIMEOUT_RESET_ON_PROGRESS` | Reset timeout on progress notifications | true |
| `MCP_REQUEST_MAX_TOTAL_TIMEOUT` | Maximum total timeout for requests (ms) | 60000 |
| `MCP_PROXY_FULL_ADDRESS` | Custom MCP Inspector Proxy address | "" |

## Next Steps

After setting up the MCP Inspector, refer to the [DevReport.md](DevReport.md) for a detailed analysis of the debugging capabilities.
