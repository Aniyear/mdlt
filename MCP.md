# Model Context Protocol (MCP)

MCP is an open protocol that connects AI applications to external tools, data and services in a standard way.

## Core idea

- **Server** exposes capabilities: *tools* (actions the model can call), *resources* (read-only data) and *prompts* (reusable templates).
- **Client** is the AI application (for example OpenClaw). It discovers the server's capabilities and lets the model call them.
- Messages are JSON-RPC 2.0, sent over stdio for local servers or HTTP for remote ones.

## Why it matters

- One integration per service instead of one per model or app.
- Tools are discovered at runtime, so the model sees their names, descriptions and input schemas.
- Access is scoped by the server: it can be read-only or limited to certain actions.

## In this course

- Task 9 (OpenClaw group) asks for an MCP GitHub integration, which lets the agent list issues and pull requests, read commits and create branches or files through GitHub's API.
- Safety points: keep tokens out of prompts, prefer read-only scopes, and require confirmation before writes such as creating or merging pull requests.

## Further reading

- Model Context Protocol specification and official SDKs (Python and TypeScript).
