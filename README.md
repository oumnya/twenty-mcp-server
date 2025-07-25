# Twenty MCP Server

A standalone MCP (Model Context Protocol) server that integrates with Twenty CRM to provide AI-powered customer relationship management capabilities.

## Overview

This server enables seamless AI interaction with Twenty CRM through the Model Context Protocol, allowing AI assistants to perform CRM operations, analyze data, and provide intelligent insights.

## Features

- **Complete CRM Integration**: Full CRUD operations for all Twenty CRM entities
- **Real-time Synchronization**: WebSocket-based real-time updates
- **Schema Awareness**: Dynamic adaptation to custom fields and objects
- **Intelligent API Selection**: Optimized GraphQL and REST API usage
- **Production Ready**: Docker containerization and monitoring

## Quick Start

### Prerequisites

- Node.js 18+
- Docker and Docker Compose
- Git

### Installation & Setup

1. **Clone and install:**
```bash
git clone <repository-url>
cd twenty-mcp-server
npm install
```

2. **Start Twenty CRM:**
```bash
# Smart start (only starts what's needed)
npm run twenty:quick
```

3. **Create workspace:**
   - Open http://localhost:3000
   - Create workspace and user account
   - Generate API key in Settings > API

4. **Configure MCP server:**
```bash
# Setup environment file
npm run twenty:setup
# Edit .env file with your API key
```

5. **Test integration:**
```bash
# Test API discovery
npm run discover

# Start MCP server
npm run dev
```

### Configuration

The setup script creates an `.env` file with:

- `TWENTY_API_URL`: Local Twenty instance (http://localhost:3000)
- `TWENTY_API_KEY`: Your Twenty API key

See `.env.example` for all configuration options.

## Development

### Development Scripts

#### MCP Server
- `npm run dev` - Start MCP server in development mode
- `npm run build` - Build the TypeScript project
- `npm run test` - Run tests
- `npm run lint` - Run linting
- `npm run discover` - Run API discovery tool (requires Twenty CRM)

#### Twenty CRM (for testing)
- `npm run twenty:quick` - Smart start Twenty CRM (recommended)
- `npm run twenty:status` - Check Twenty status
- `npm run twenty:setup` - Configure MCP environment
- `npm run twenty:logs` - View Twenty logs
- `npm run twenty:stop` - Stop Twenty services

### Project Structure

```
src/
   server.ts          # Main MCP server entry point
   twenty-client/     # Twenty CRM API client
   tools/             # MCP tools implementation
   types/             # TypeScript type definitions
   utils/             # Utilities and configuration
```

## Deployment

### Docker

Build and run with Docker:

```bash
docker build -t twenty-mcp-server .
docker run -d --env-file .env -p 3001:3001 twenty-mcp-server
```

### Docker Compose

```bash
docker-compose up -d
```

## License

MIT License - see LICENSE file for details.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## Documentation

- [Quick Start Guide](./QUICK_START.md) - Get running in 5 minutes
- [Twenty Scripts Guide](./scripts/README.md) - Complete script documentation
- [API Discovery Reports](./reports/) - Generated after running `npm run discover`

## Troubleshooting

- **Twenty won't start**: `npm run twenty:logs`
- **Connection issues**: `npm run twenty:status`
- **Fresh restart**: `npm run twenty:start` (resets everything)
- **View help**: `npm run twenty:help`

## Support

For support and documentation, see the documentation links above or open an issue on GitHub.