---
name: mcp-server-starter
description: Plan, build and test a small Model Context Protocol (MCP) server that gives an AI agent safe access to one internal tool or data source, using the current official SDKs. Use when someone wants to build an MCP server, connect an internal API or database to Claude or another agent, or fix an MCP server built from an outdated tutorial.
---

# MCP server starter

Build the smallest server that does one job well, test it in the MCP Inspector, then connect it to the agent.

## Before writing code: check the SDK version

Both official SDKs changed in v2 (mid-2026), and most online tutorials still show v1. Read the current README before writing imports.

- TypeScript v2 packages: `@modelcontextprotocol/server` and `@modelcontextprotocol/client` (docs: https://ts.sdk.modelcontextprotocol.io/v2/). v1 used `@modelcontextprotocol/sdk`.
- Python: package `mcp` (Python 3.11+), install with `uv add "mcp[cli]"`. In v2 the server class is `MCPServer` from `mcp.server`; the v1 path `mcp.server.fastmcp` was removed. Docs: https://py.sdk.modelcontextprotocol.io/
- "FastMCP" can also mean the separate `fastmcp` package (PrefectHQ). Say which one you use.
- Spec: https://modelcontextprotocol.io/specification/latest

## Steps

1. **Scope one job.** Write one sentence: "This server lets the agent <verb> <thing> in <system>." Prefer read-only first.
2. **Design tools, not endpoints.** 2 to 5 tools, each with a plain-English description the model will read, typed inputs, and short outputs. Return the fields the agent needs, not whole records.
3. **Add guardrails.** Credentials come from environment variables, never from tool inputs. Validate inputs. Cap result sizes. Log every call. Any write or delete tool needs an explicit confirmation field.
4. **Build** with the current SDK, using its stdio transport for a local server.
5. **Test in the Inspector** before connecting an agent:
   - Python: `uv run mcp dev server.py`
   - Any stdio server: `npx @modelcontextprotocol/inspector <command>` (for example `node build/index.js`). The Inspector v2 needs Node 22.19 or later.
   Call each tool with a good input, a bad input and an empty result.
6. **Connect to Claude Code:** `claude mcp add --transport stdio <name> -- <command> [args...]`, then run `/mcp` in a session to check it's connected.
7. **Write a README:** what it does, setup, environment variables, each tool, and what it can't do.

## Don't

- Don't expose a generic "run SQL" or "call any URL" tool. Narrow tools are safer and easier for the model to use well.
- Don't put secrets in tool descriptions, logs or results.
- Don't ship the reference servers from modelcontextprotocol/servers to production; their README says they are reference implementations. Check https://registry.modelcontextprotocol.io/ for maintained servers first.
