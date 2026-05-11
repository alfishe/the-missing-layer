# The Infrastructure Bottleneck: Power, Silicon, and Cooling

AI doesn't run on software alone. It runs on silicon, power, cooling, and datacenter floor space — all of which are in critically short supply. The bottleneck isn't the model. It's everything around the model.

## The GPU Procurement Problem

Training a frontier model requires tens of thousands of GPUs running for months. Inferencing at scale requires continuous GPU capacity. The demand for AI compute has outstripped supply to a degree that reshapes corporate strategy:

- NVIDIA's H100 had a 36-52 week lead time at peak. The newer B200 is following the same pattern.
- Meta ordered 350,000 H100s. Microsoft committed to a similar scale. These aren't purchases — they're resource grabs that determine who can even participate in the frontier race.
- The secondary market for enterprise GPUs is thin. You can't just buy H100s on eBay. TSMC's advanced packaging capacity (CoWoS) is the actual bottleneck — it limits how many chips NVIDIA can produce regardless of demand.

For hyperscalers, this is a procurement problem solved with billions of dollars and multi-year contracts. For everyone else, it's a wall.

## The Power Crisis

A single H100 draws 700W at peak. A rack of them draws 40-60 kW. A datacenter full of racks draws tens of megawatts. The numbers compound fast:

| Scale | Power Draw | Cooling Requirement |
|---|---|---|
| Single H100 | 700W | Standard air cooling sufficient |
| 8× H100 node | ~10 kW | Directed airflow, raised floor |
| Full rack | 40-60 kW | In-row cooling or rear-door heat exchangers |
| AI training cluster (1000+ GPUs) | 5-10 MW | Dedicated cooling plant |
| Frontier training run | 20-50 MW | Purpose-built facility |

The constraint isn't the hardware — it's getting power to the building. Datacenter construction is now limited by power grid capacity, not by real estate or capital. Northern Virginia, the world's largest datacenter market, is hitting transmission limits. Ireland paused new datacenter connections. Singapore imposed moratoriums. The Pacific Northwest's cheap hydro power is already allocated.

Microsoft and Amazon are now negotiating directly with nuclear plant operators. Microsoft signed a deal to restart Three Mile Island Unit 1 to power a datacenter. This is not normal procurement — this is the energy profile of heavy industry, not software.

## The Cooling Problem

Traditional datacenter cooling (raised floors, CRAC units, hot/cold aisle containment) tops out at about 10-15 kW per rack. AI workloads need 3-5x that. The options are:

- **Direct liquid cooling (DLC):** Cold plates on every GPU, liquid pumped through. Effective but requires retrofitting entire facilities. Most existing datacenters don't have the plumbing.
- **Rear-door heat exchangers:** Easier retrofit, but lower capacity per rack.
- **Immersion cooling:** Submerge entire servers in dielectric fluid. Highest density, highest complexity, smallest installed base.

The cooling problem creates a geographic constraint: you can only build AI datacenters where you have both power and water (for evaporative cooling) or are willing to invest in closed-loop liquid systems. This eliminates large portions of the planet from consideration.

## The Hardware Lifecycle Trap

AI hardware has a shorter useful life than traditional servers. A 3-year-old GPU is still perfectly good for many workloads, but for frontier training, it's obsolete. This creates a constant capital expenditure treadmill:

- **Training hardware:** Needs the latest generation. Each new model generation requires a new hardware generation. The capital outlay is in the billions.
- **Inference hardware:** More forgiving — older GPUs, quantized models, and mixed-precision work well. But the demand is growing faster than capacity.
- **Consumer hardware:** The used enterprise hardware eventually trickles down. A NVIDIA Tesla P40 (originally a $5,000 datacenter card) now costs $200-$350 on eBay and runs quantized 7B models at 15-20 tok/s. This is the democratization pathway — but it depends on hyperscaler upgrade cycles.

The lifecycle trap means: hyperscalers must keep buying new hardware to stay competitive. Their discarded hardware becomes the foundation of the consumer/open-source ecosystem. The trickle-down economics work, but on a 2-4 year delay.

## What This Means for Software Architecture

The hardware constraints have direct implications for how software should be designed:

**Smaller models matter more.** A 1.5B specialized model running on consumer hardware outperforms a 70B generalist in narrow domains. The VRAM savings (1.1 GB vs 40+ GB) mean you can run more concurrent workloads or run on cheaper hardware. Distillation isn't just an optimization — it's an access strategy.

**Context efficiency is compute efficiency.** Every token sent to a model costs compute. Long, bloated contexts cost proportionally more. The context architecture described in [Building the Agentic Operating System](../block-01/01-why-agents-waste-context.md) — shadow compaction, selective commit, reference graphs — is an infrastructure optimization disguised as a software pattern. Less context per turn means more concurrent users per GPU, which means lower cost per outcome.

**Local inference is the frontier for open-source.** The open-source community can't outspend hyperscalers on hardware. But it can out-innovate on software that makes consumer hardware productive. ktransformers running 671B-parameter MoE models on a single 4090 + system RAM is a software achievement that democratizes capability without requiring hardware scale.

The bottleneck isn't going away. Power grids won't expand overnight. GPU production won't double next year. Datacenter cooling won't become trivial. The only lever that moves fast enough is software architecture — making every watt and every byte of VRAM count.

This creates two fundamentally different worlds, operating on the same technology but with radically different economics.

---

*Part of [The State of Play](./00-index.md). Previous: [The AI Reality Check](./01-the-ai-reality-check.md). Next: [Two Worlds, One Problem](./03-two-worlds-one-problem.md)*
