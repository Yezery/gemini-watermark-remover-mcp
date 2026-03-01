# Gemini Watermark Remove MCP Server

MCP server for removing Gemini AI watermarks from generated images.

## Local Stdio Mode

### Claude Desktop

```json
{
  "mcpServers": {
    "gemini-watermark-remove": {
      "command": "npx",
      "args": ["-y", "gemini-watermark-remover-mcp"]
    }
  }
}
```

### OpenCode

```json
{
  "mcp": {
    "gemini-watermark-remove": {
      "command": ["npx", "-y", "gemini-watermark-remover-mcp"],
      "type": "local",
      "enabled": true
    }
  }
}
```

## Development

### Prerequisites

- Node.js >= 22
- npm

### Installation

```bash
# Clone or download the project
cd gemini-watermark-remover-mcp

# Install dependencies
npm install

# Build the project
npm run build
```

### Running

**Development mode (hot reload):**
```bash
npm run dev
```

**Production mode:**
```bash
npm start
# or
node dist/index.js
```

### Local Development Debug Config

For debugging after modifying source code, you can use the locally built version:

**Claude Desktop:**

```json
{
  "mcpServers": {
    "gemini-watermark-remove": {
      "command": "node",
      "args": ["/path/to/gemini-watermark-remover-mcp/dist/index.js"]
    }
  }
}
```

## MCP Tool Usage

### gemini_remove_watermark

Removes the Gemini AI watermark from generated images.

**Parameters:**

| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| input_path | string | Yes | - | Input image path (PNG, JPG, WEBP) |
| output_path | string | Yes | - | Output image path |
| response_format | string | No | markdown | Output format: markdown or json |
| jpeg_quality | number | No | 95 | JPEG quality (1-100) |
| webp_quality | number | No | 80 | WEBP quality (1-100) |
| png_compression_level | number | No | 6 | PNG compression level (0-9) |

## License

This project is licensed under the MIT License

## Acknowledgments

This project is based on [journey-ad/gemini-watermark-remover](https://github.com/journey-ad/gemini-watermark-remover).

Thanks for the original implementation!
