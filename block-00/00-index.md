# The State of Play

Before the architecture, before the code — why does any of this matter? This series sets the foundation: where AI infrastructure actually stands, what's broken, who's winning, and why the current trajectory leaves most people on the losing side.

---

## Articles

### 1. [The AI Reality Check](./01-the-ai-reality-check.md)
**~3 min read**

The gap between what's being marketed and what actually ships reliably is wide — and widening. Model capabilities are advancing faster than the infrastructure to deploy them. The demos work. The production systems don't. Understanding this gap is the first step toward closing it.

### 2. [The Infrastructure Bottleneck](./02-the-infrastructure-bottleneck.md)
**~4 min read**

AI doesn't run on software alone. It runs on silicon, power, cooling, and datacenter floor space — all of which are in critically short supply. GPU procurement timelines are measured in quarters. Power availability limits where datacenters can even be built. The bottleneck isn't the model; it's everything around the model.

### 3. [Two Worlds, One Problem](./03-two-worlds-one-problem.md)
**~3 min read**

Hyperscalers buy 100,000 GPUs at a time and negotiate their own power plants. Everyone else — independent engineers, open-source contributors, small companies, entire developing economies — gets scraps from the same API at per-token prices that reflect hyperscaler economics. Two fundamentally different worlds, sharing one technology stack, with radically different access to it.

### 4. [The Win-Win Thesis](./04-the-win-win-thesis.md)
**~4 min read**

The hypothesis: the things that make AI work better for hyperscalers — efficient inference, smart context management, specialized models, infrastructure discipline — are exactly the same things that make AI accessible to everyone else. Better architecture is not zero-sum.

### 5. [Why I'm Writing This](./05-why-im-writing-this.md)
**~4 min read**

Personal resources are limited. Time is limited. The work described in this blog — context architecture, supervisor loops, model health monitoring, specialized distillation — requires sustained effort on real hardware with real workloads. The motivation is simple: the infrastructure layer is where the leverage is, and it's being systematically underbuilt.

---

This series can be read on its own. It also forms the first half of a larger arc — the "why" — continued by [Building the Agentic Operating System](../block-01/00-index.md), which covers the "how."

*See also: [About](../common/01-about.md) · [Mission](../common/02-mission.md) · [Current State & Future](../common/03-current-state.md) · [How to Help](../common/04-how-to-help.md)*
