# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## OpenCode Repository Overview

OpenCode is an open-source AI coding agent designed as an alternative to Claude Code. It's built with a focus on being 100% open source, provider-agnostic (works with Claude, OpenAI, Google, or local models), and features a client/server architecture with TUI as the primary interface.

## Architecture & Structure

The OpenCode project is organized as a monorepo with multiple packages:
- `packages/opencode`: Core application logic and CLI entry point
- `packages/app`: Application-specific components
- `packages/console`: Console UI components
- `packages/desktop`: Desktop application wrapper
- `packages/ui`: Shared UI components
- `packages/sdk`: JavaScript/TypeScript SDK
- `packages/web`: Web-based components
- `packages/containers`: Container configurations
- `packages/extensions`: Editor extensions
- `packages/plugin`: Plugin system
- `packages/identity`: Authentication/identity management
- `packages/function`: Serverless functions
- `packages/slack`: Slack integration

Built with Bun as the runtime and uses a variety of AI SDKs for different providers (Anthropic, OpenAI, Google, etc.).

## Development Commands

### Running OpenCode
```bash
# Install dependencies
bun install

# Run in development mode
bun run dev

# Build the project
bun run build

# Run tests
bun test
```

### Package Management
```bash
# Add dependency to workspace
bun add package-name --workspace

# Run commands in specific packages
bun --cwd packages/opencode run dev

# Run tests for specific package
bun --cwd packages/opencode test
```

### Global Commands
```bash
# Type checking
bun turbo typecheck

# Clean installation
bun run clean
```

## Key Configuration Files

- `package.json`: Root package configuration and workspaces
- `bun.lock`: Bun lockfile with dependency versions
- `bunfig.toml`: Bun configuration
- `turbo.json`: Turbo configuration for monorepo builds
- `tsconfig.json`: TypeScript configuration
- `sst.config.ts`: SST configuration for infrastructure
- `packages/opencode/AGENTS.md`: Agent-specific guidelines and style guide
- `.github/workflows/`: CI/CD workflows

## Important Features

- **Provider Agnostic**: Supports multiple AI providers via ai-sdk
- **Client/Server Architecture**: Terminal UI can connect to remote server
- **Multiple Agents**: Built-in 'build' (full access) and 'plan' (read-only) agents
- **Plugin System**: Extensible via plugins and hooks
- **Cross-platform**: Available as CLI tool, desktop app, and remote service

## Style Guide & Conventions

From `AGENTS.md`:
- Avoid `let` statements, prefer `const`
- Avoid `else` statements, use early returns
- Use single-word variable names when possible
- Use Bun APIs where available
- Avoid `try`/`catch` where possible
- Avoid `any` type
- Prefer parallel tools when applicable
- Minimize use of mocks in testing

## Common Development Tasks

- Adding support for new AI providers via ai-sdk
- Implementing new agents with specific capabilities
- Extending the plugin system
- Improving the terminal UI experience
- Adding new tools and commands
- Enhancing LSP support
- Improving security and permission systems