# LuciferForge

**Security and safety infrastructure for AI agents. MIT licensed. Pure Python.**

When you run AI agents autonomously — trading bots, code assistants, document processors — three things break silently: costs explode from retry loops, inputs get poisoned by adversarial prompts, and decisions become untraceable when something fails at 3AM.

We built the fix. Five packages. All MIT. All offline-capable.

---

### The Stack

| Library | What it does | Install |
|---|---|---|
| [ai-cost-guard](https://github.com/LuciferForge/ai-cost-guard) | Hard budget cap — blocks LLM calls before they exceed your limit | `pip install ai-cost-guard` |
| [ai-injection-guard](https://github.com/LuciferForge/prompt-shield) | Prompt injection scanner — 22 patterns, 5 categories, entirely offline | `pip install ai-injection-guard` |
| [ai-decision-tracer](https://github.com/LuciferForge/ai-trace) | Decision logger — JSONL auto-save, Markdown reports, built-in CLI | `pip install ai-decision-tracer` |
| [agent-safety-mcp](https://github.com/LuciferForge/agent-safety-mcp) | MCP server — gives any AI assistant access to all three tools above | `pip install agent-safety-mcp` |
| [mcp-security-audit](https://github.com/LuciferForge/mcp-security-audit) | Security auditor — scan any MCP server for injection patterns, risky tools, misconfigs | `pip install mcp-security-audit` |

### Use all three together

```python
from ai_cost_guard import CostGuard
from prompt_shield import PromptScanner
from ai_trace import Tracer

guard   = CostGuard(weekly_budget_usd=5.00)
scanner = PromptScanner(threshold="MEDIUM")
tracer  = Tracer("my-agent", meta={"model": "claude-haiku-4-5"})

@guard.protect(model="anthropic/claude-haiku-4-5-20251001")
@scanner.protect(arg_name="prompt")
def call_llm(prompt):
    with tracer.step("llm_call", prompt_len=len(prompt)) as step:
        response = client.messages.create(...)
        step.log(tokens=response.usage.input_tokens)
    return response
```

---

Built from running autonomous AI trading agents in live financial markets. Every package exists because something broke in production.
