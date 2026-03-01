# LuciferForge

**Production safety tools for AI agents. Zero dependencies. Pure Python.**

When you run AI agents autonomously — trading bots, document processors, customer service agents — three things break silently:

1. **Cost explodes** — retry loops, model swaps, injection attacks rack up bills while you sleep
2. **Inputs get poisoned** — external data feeds carry adversarial prompts that hijack model behavior
3. **Decisions become untraceable** — when something fails at 3AM, you can't reconstruct why

We built the fix. Three libraries. All MIT. All zero-dependency. All local-only.

---

### The Stack

| Library | What it does | Install |
|---|---|---|
| [ai-cost-guard](https://github.com/LuciferForge/ai-cost-guard) | Hard budget cap — blocks LLM calls before they exceed your limit | `pip install ai-cost-guard` |
| [ai-injection-guard](https://github.com/LuciferForge/prompt-shield) | Prompt injection scanner — 22 patterns, 5 categories, entirely offline | `pip install ai-injection-guard` |
| [ai-decision-tracer](https://github.com/LuciferForge/ai-trace) | Decision logger — JSONL auto-save, Markdown reports, built-in CLI | `pip install ai-decision-tracer` |

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

Built from 8 months of running autonomous AI trading agents in live financial markets. Every library exists because something broke in production.
