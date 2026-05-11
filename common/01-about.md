# About

I'm a systems engineer and solution architect with 24+ years of professional experience. The thing worth pointing at is the vertical reach: I do hands-on work from PCB signal traces and FPGA RTL up through embedded firmware, real-time systems, hyperconverged on-prem, hyperscaler cloud, and the AI agent frameworks built on top. Complex heterogeneous systems — where CPU, GPU, FPGA, accelerators, and now LLM inference all have to cooperate — are the natural habitat.

That span is not an accident, and it's not CV-padding. It's the consequence of treating every system as a system — with inputs, outputs, internal state, failure modes, and feedback loops — regardless of which layer you're looking at. Same discipline, different scale.

This is the lens for everything written here.

## The throughline: systems thinking, every layer

The foundation is aerospace control systems education at Saint Petersburg State University of Aerospace Instrumentation, 1996–2002. Six years of learning to build systems where failure isn't a ticket in the backlog.

A satellite doesn't get a retry when lost all correction fuel due to the fault. A flight controller doesn't get patched mid-air. Either the loop closes within its margins or the airframe departs controlled flight — no sprint planning, no hotfix, no "we'll address it next quarter." You internalize a particular kind of discipline under those constraints: build the model, prove it survives the worst case, instrument everything so you see trouble coming before the system does.

That discipline hasn't expired. Twenty-five years later, the same instinct applies — whether the thing under control is a microcontroller, a render farm, a database cluster, or an LLM provider quietly degrading under cost pressure. The vocabulary changes. The thinking doesn't: know your failure modes, close your loops, test at every boundary, and never ship without knowing where your margin is.

## The stack, layer by layer

- PCB signal traces and signal integrity
- Computer architecture and system design — RTL,FPGA implementation
- Bare-metal, RTOS, embedded systems, kernel drivers, userspace processing, tracing, analysis
- Systems software — low-level performance, compression, lock-free data structures
- Verification — co-simulation, test frameworks, formal and simulation-based validation
- Emulation and preservation — cycle-accurate and bit-accurate simulation of vintage chips, hardware controllers, retro-platforms
- Diagnostic tools authoring and improvements — debuggers, profilers, performance counters, visualization, pattern detection
- Real-time 3D, digital twins, render farms
- Common Full-stack software engineering — C++, Python, Java, .NET, web and mobile frameworks, APIs, databases, security, PKI
- On-prem hyperconverged infrastructure
- Hyperscaler cloud — batch ML inference, GPU farms, IoT at scale
- Distributed systems — consensus, replication, conflict resolution (who said Blockchain? - yeah, and that as well)
- AI and agent infrastructure — complex hierarchical agentic DAGs, RAGs, knowledge graphs, MCP orchestration...

Same discipline at every layer. Same architect's eye whether the system is a Motorola 68k family CPU pipeline, a render farm, a Raft cluster, or an agent loop. The [arguments in this series](../block-01/00-index.md) come from someone whose stack runs from logic analyzer probes to LLM provider APIs — and who has seen failure modes at every level in between.

## The career arc

Two+ decades of professional engagements, with dozens of S&P and NASDAQ clients. The trajectory started at application-level C++ and standard enterprise tiered architecture, then expanded in both directions: upward into cloud, distributed systems, and AI; downward into mobile, embedded, FPGA, and chip-level behavior reconstruction. Each year added another layer of understanding, not by plan but by following the hard problems wherever they lived. The discipline didn't change with the destination.

That arc includes consulting for both enterprises and startups — helping teams navigate exactly the kind of cross-layer complexity described above. Architecture reviews, technology selection, integration strategy, production readiness. I'm open to meaningful collaboration where the problem is genuinely hard and the people working on it are serious about getting it right.

Current engagement is in enterprise 3D visualization and digital twins. LinkedIn has the specifics for anyone who needs them.

## Why this matters for what I write here

Most engineers working on AI agent infrastructure come from a single layer. They write framework code, or tune prompts, or fine-tune models, or build product features on someone else's framework. That's how industries usually organize themselves, and it's mostly fine.

But the failure modes of real agent systems span the entire stack. An agent that hangs under load could be a context architecture issue, a tool-orchestration bug, an RPC framing problem, a kernel scheduling artifact, GPU memory fragmentation, a hardware quirk, or a model-quality regression at the provider. Debugging that whole tower in one head requires having spent real time at every level of it.

I'm not claiming to be the world's expert at any single layer. I'm claiming to be one of the people who can see — and build — across all of them. Systematic approach at every level. Same architect's eye whether the system is a 68k pipeline, a render farm, a Raft cluster, or an agent loop.

That's the perspective the writing here comes from.

Nothing here represents the views of any current or past employer. Everything here is built on personal time, with personal hardware, with personally paid subscriptions. See [Current State & Future](./03-current-state.md) for the details.
