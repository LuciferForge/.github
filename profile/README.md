# LuciferForge

**Open source tools for AI agents, trading bots, and developer infrastructure. MIT licensed.**

We build things that work in production — where costs explode, inputs get poisoned, and decisions need audit trails at 3AM.

---

### AI Agent Safety

| Library | What it does | Install |
|---|---|---|
| [ai-injection-guard](https://github.com/LuciferForge/prompt-shield) | Prompt injection scanner — 69 patterns, 9 categories, multilingual, offline | `pip install ai-injection-guard` |
| [ai-cost-guard](https://github.com/LuciferForge/ai-cost-guard) | Hard budget cap — blocks LLM calls before they exceed your limit | `pip install ai-cost-guard` |
| [ai-decision-tracer](https://github.com/LuciferForge/ai-trace) | Ed25519 signed decision receipts — tamper-proof audit trails | `pip install ai-decision-tracer` |
| [agent-safety-mcp](https://github.com/LuciferForge/agent-safety-mcp) | MCP server wrapping all safety tools for any AI assistant | `pip install agent-safety-mcp` |
| [agent-safety-middleware](https://github.com/LuciferForge/agent-safety-middleware) | One-line FastAPI/Flask safety middleware | `pip install agent-safety-middleware` |
| [mcp-security-audit](https://github.com/LuciferForge/mcp-security-audit) | Security auditor for MCP servers — injection patterns, risky tools, misconfigs | `pip install mcp-security-audit` |

### Agent Identity (KYA)

| Library | What it does | Install |
|---|---|---|
| [kya-agent](https://github.com/LuciferForge/KYA) | Agent identity standard — Ed25519 signing, `.ai-starter.json` | `pip install kya-agent` |
| [agentcred](https://github.com/LuciferForge/agentcred) | Agent Credit Bureau — trust scoring from static signals | `pip install agentcred` |
| Framework adapters | [CrewAI](https://github.com/LuciferForge/crewai-kya) · [LangChain](https://github.com/LuciferForge/langchain-kya) · [AutoGen](https://github.com/LuciferForge/autogen-kya) · [LlamaIndex](https://github.com/LuciferForge/llamaindex-kya) · [DSPy](https://github.com/LuciferForge/dspy-kya) · [smolagents](https://github.com/LuciferForge/smolagents-kya) | `pip install {name}` |

### Trading & Markets

| Project | What it does |
|---|---|
| [polymarket-btc-autotrader](https://github.com/LuciferForge/polymarket-btc-autotrader) | Automated Polymarket trading bot — ARB, momentum, snipe strategies |
| [polymarket-odds-scanner](https://github.com/LuciferForge/polymarket-odds-scanner) | Cross-reference Polymarket vs sportsbook odds for edge detection |
| [polymarket-pnl](https://github.com/LuciferForge/polymarket-pnl) | P&L tracker and trade analytics for Polymarket |
| [polymarket-settlement-bot](https://github.com/LuciferForge/polymarket-settlement-bot) | Settlement monitoring and auto-claim bot |

### Developer Starters

| Project | What it does |
|---|---|
| [protodex.io](https://protodex.io) | Search 1,629+ MCP servers — the free, open source MCP directory |
| [vault-mind](https://github.com/LuciferForge/vault-mind) | Obsidian plugin — local AI semantic search using Ollama |
| [claude-code-memory](https://github.com/LuciferForge/claude-code-memory) | Persistent memory system for Claude Code |
| [telegram-bot-starter](https://github.com/LuciferForge/telegram-bot-starter) | Production Telegram bot template with commands, webhooks, deploy |
| [stripe-webhook-handler](https://github.com/LuciferForge/stripe-webhook-handler) | Stripe webhook handling with signature verification |
| [deploy-python-app](https://github.com/LuciferForge/deploy-python-app) | One-command Python app deployment to Railway/Render/Fly |
| [python-web-scraper](https://github.com/LuciferForge/python-web-scraper) | Production web scraper with rate limiting and proxy rotation |

---

Built from running autonomous AI agents in live financial markets. Every tool exists because something broke in production.
