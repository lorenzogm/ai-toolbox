# AI Toolbox

A comprehensive collection of AI development tools, GitHub Copilot configurations, and Model Context Protocol (MCP) server integrations for enhanced development workflows.

## Overview

This repository contains a curated set of AI-powered development tools including:

- GitHub Copilot chat modes for different team roles
- Reusable prompt templates for common development tasks
- MCP server configurations for external integrations
- VS Code extensions and settings for AI-enhanced development

## Repository Structure

```
.github/
├── chatmodes/           # GitHub Copilot chat modes
│   ├── Team - BA.chatmode.md
│   ├── Team - Dev BE.chatmode.md
│   ├── Team - Dev FE.chatmode.md
│   ├── Team - QA.chatmode.md
│   ├── Tool - Lovable.chatmode.md
│   ├── Tool - bolt.chatmode.md
│   └── Tool - v0.chatmode.md
├── prompts/             # Reusable prompt templates
│   ├── ticket-create.prompt.md
│   ├── ticket-get.prompt.md
│   ├── ticket-start.prompt.md
│   └── ui.prompt.md
└── copilot-instructions.md

.vscode/
├── extensions.json      # Recommended VS Code extensions
├── mcp.json            # Model Context Protocol server configurations
└── settings.json       # VS Code workspace settings
```

## GitHub Copilot Chat Modes

The `.github/chatmodes/` directory contains specialized chat modes for different team roles and AI tools:

### Team Roles

- **Team - BA**: Business Analyst focused interactions
- **Team - Dev BE**: Backend development assistance
- **Team - Dev FE**: Frontend development with React/TypeScript conventions
- **Team - QA**: Quality assurance and testing guidance

### AI Tools Integration

- **Tool - Lovable**: Integration with Lovable.dev
- **Tool - bolt**: Integration with Bolt.new
- **Tool - v0**: Integration with v0.dev

## Prompt Templates

Reusable prompt templates in `.github/prompts/`:

- **ticket-create.prompt.md**: Template for creating new tickets
- **ticket-get.prompt.md**: Template for retrieving ticket information
- **ticket-start.prompt.md**: Template for starting work on tickets
- **ui.prompt.md**: Frontend UI development guidelines and conventions

## Model Context Protocol (MCP) Servers

The `.vscode/mcp.json` file configures various MCP servers for enhanced AI capabilities:

### Available Servers

- **fetch**: Web content retrieval
- **filesystem**: File system operations
- **memory**: Persistent memory across sessions
- **sequentialthinking**: Enhanced reasoning capabilities
- **contentful**: Contentful CMS integration
- **figma**: Figma design file access
- **playwright**: Browser automation and testing
- **lighthouse**: Web performance auditing
- **terraform**: Infrastructure as Code support
- **atlassian**: Jira and Confluence integration

### Setup

Each MCP server requires specific environment variables. Configure these in your VS Code settings:

- `CONTENTFUL_API_KEY`: Contentful Management API Token
- `FIGMA_API_KEY`: Figma Personal Access Token
- `ATLASSIAN_API_KEY`: Atlassian API Token
- `ATLASSIAN_URL`: Base URL for your Atlassian workspace
- `EMAIL`: Email for Atlassian authentication

## VS Code Extensions

The repository includes curated VS Code extension recommendations in `.vscode/extensions.json`:

### Core Extensions

- **ESLint**: Code linting and formatting
- **Prettier**: Code formatting
- **GitLens**: Enhanced Git capabilities
- **EditorConfig**: Consistent coding styles

### Development Tools

- **Auto Rename Tag**: HTML/XML tag synchronization
- **Import Cost**: Bundle size analysis
- **Vitest Explorer**: Test runner integration
- **TypeScript**: Enhanced TypeScript support

### Design & Content

- **Figma**: Design file integration
- **Grammarly**: Writing assistance
- **CSS Modules**: CSS module support
- **SCSS IntelliSense**: Enhanced SCSS support

## Usage

1. **Clone the repository** to your local development environment
2. **Install recommended VS Code extensions** when prompted
3. **Configure MCP servers** by setting required environment variables
4. **Use chat modes** by referencing them in GitHub Copilot conversations
5. **Apply prompt templates** for consistent development workflows

## Frontend Development Guidelines

For frontend development, this toolbox includes comprehensive guidelines in the `ui.prompt.md` file covering:

- TypeScript conventions and interfaces
- React component patterns and structure
- Tailwind CSS styling guidelines
- Component testing and mocking
- ESLint configuration and code quality

### Key Conventions

- Use **kebab-case** for file names
- Use **PascalCase** for React components
- Use **camelCase** for variables and functions
- Avoid props destructuring, use `props.propName` pattern
- Single `useState` per component
- Presentational components only (no data fetching or global state)

## Contributing

When adding new chat modes, prompts, or MCP server configurations:

1. Follow existing naming conventions
2. Include clear documentation and usage examples
3. Test configurations before committing
4. Update this README with new additions

---

This AI Toolbox is designed to enhance development workflows through intelligent automation and consistent patterns across different AI tools and platforms.
