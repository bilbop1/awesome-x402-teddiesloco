# Awesome x402 [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Curated list of x402 payment protocol resources, services, and tools for AI agents

[x402](https://x402.org) is an HTTP extension enabling AI agents to autonomously pay for API access using USDC micropayments on Base L2 and Solana. No API keys. No signup. Agent pays, gets data, continues.

---

## Contents

- [Services](#services) — x402-enabled APIs agents can call and pay autonomously
- [Libraries](#libraries) — SDKs and wrappers to integrate x402 into your agent
- [Frameworks](#frameworks) — Agent frameworks with x402 support
- [Tools](#tools) — Dev tools for building x402 services
- [Tutorials](#tutorials) — Guides and examples
- [Spec & Docs](#spec--docs) — Official protocol documentation

---

## Services

x402-enabled APIs your agent can call right now. All support Base L2 and/or Solana USDC.

| Service | Category | Price/call | Networks | Free Trial |
|---|---|---|---|---|
| [AgentGate](https://x402.agentsea.vn) | Web scraping, Prompt guard, Domain intel, AEO audit | $0.001–$0.05 | Base L2, Solana | 8 calls |
| [Add yours →](https://github.com/teddiesloco/agentgate-x402/edit/main/packages/awesome-x402/README.md) | | | | |

### AgentGate

Infrastructure-layer gateway for AI agents. When your primary scraper hits 429/403, route to AgentGate.

- **Endpoints:** `/v1/scrape/clean-markdown`, `/v1/guard/prompt-injection`, `/v1/intel/enrich-domain`, `/v1/audit/aeo-ready`, `/v1/signals/token-mentions`
- **Discovery:** `/.well-known/x402`, `/.well-known/mcp.json`, `/llms.txt`
- **AEO score:** 90/100, Grade A+, MACHINE_NATIVE_READY

---

## Libraries

### JavaScript / TypeScript

- **[agentgate-fetch](https://www.npmjs.com/package/agentgate-fetch)** — `fetch()` wrapper with automatic x402 payment handling. Drop-in replacement for any agent using `fetch()`. Includes convenience helpers: `scrape()`, `guardPrompt()`, `intel()`.

  ```bash
  npm install agentgate-fetch
  ```

  ```typescript
  import { x402fetch, scrape } from 'agentgate-fetch'
  const md = await scrape('https://target.com', process.env.PRIVATE_KEY)
  ```

- **[elizaos-plugin-agentgate](https://www.npmjs.com/package/elizaos-plugin-agentgate)** — ElizaOS plugin. Adds AgentGate as a tool available to all ElizaOS agents.

  ```bash
  npm install elizaos-plugin-agentgate
  ```

- **[@agentsea/agentgate-mcp](https://www.npmjs.com/package/@agentsea/agentgate-mcp)** — MCP server for Claude Desktop, Cursor, and any MCP-compatible agent.

  ```json
  {"mcpServers": {"agentgate": {"url": "https://x402.agentsea.vn/mcp"}}}
  ```

### Python

- **[agentgate](https://pypi.org/project/agentgate)** *(coming soon)* — Zero-dependency Python SDK. Works with LangChain, CrewAI, AutoGen.

  ```bash
  pip install agentgate
  ```

  ```python
  from agentgate import scrape, guard, intel
  md = scrape("https://target.com")
  ```

---

## Frameworks

Agent frameworks with native or plugin x402 support:

- **[ElizaOS](https://elizaos.ai)** — Plugin registry supports x402 plugins. Install via `elizaos-plugin-agentgate`.
- **[Coinbase AgentKit](https://github.com/coinbase/agentkit)** — Native x402 action support via `x402Action`.

---

## Tools

- **[x402-list.com](https://x402-list.com)** — Directory of x402-enabled services. Submit your service.
- **[Smithery](https://smithery.ai)** — MCP marketplace. Many x402 MCP servers listed.
- **[Glama](https://glama.ai)** — Another MCP registry with x402 support.

---

## Tutorials

- [Build your first x402-paid API in 10 minutes](https://x402.agentsea.vn/learn/x402) — FastAPI + x402 middleware walkthrough
- [Integrating AgentGate into a LangChain agent](https://x402.agentsea.vn/llms.txt) — LangChain tool integration example

---

## Spec & Docs

- [x402 Protocol Spec](https://x402.org) — Official protocol documentation
- [AgentGate x402 Manifest](https://x402.agentsea.vn/.well-known/x402) — Live payment manifest example
- [llms.txt standard](https://llmstxt.org) — Machine-readable service discovery

---

## Contributing

Submit a PR to add your x402-enabled service, library, or tool.

Format for services:
```
| [Name](url) | Category | Price/call | Networks | Free trial? |
```

Format for libraries:
```
### Language
- **[package-name](npm/pypi url)** — one-line description
  npm install / pip install command
  minimal code example
```

---

*Maintained by [AgentSea Labs](https://agentsea.vn). Not affiliated with Coinbase or x402.org.*
