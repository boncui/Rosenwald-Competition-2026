# Track B3 — Compute & Jevons

**Agent:** B3 (Compute & Jevons) — the project's counter-thesis engine, metaprompt dimension 6
(Jevons check) and the first half of dimension 8 (who captures the freed value).
**Date of work:** 2026-09-19. Event is 11 days old; every claim below is date-stamped.
**Raw sources:** `navier_stokes/raw/B3_compute/` (files 01-50). Cross-track: `navier_stokes/raw/00_claim/`.

---

## One line on the technical content

On 2026-09-08 OpenAI announced that an **unreleased internal model** — "significantly more capable
than GPT-6 Astra," training begun 28 Aug 2026 — orchestrated ~10,000 concurrent agents for 88 hours
to construct a **finite-time blowup for the 3D incompressible Navier-Stokes equations in the FORCED
setting**, establishing Clay statements (C) and (D), Lean-formalized in a further 17 hours. The
unforced global-regularity question, statements (A) and (B) — the thing everyone means by "the
Navier-Stokes problem" — is **untouched**, and OpenAI is not claiming the $1M prize [raw/B3/01,
accessed 2026-09-19; page silently edited 2026-09-10].

---

## BOTTOM LINE UP FRONT

1. **The run cost ~$1M in real resources and ~$6-10M at retail list price.** Not $40M. I derive
   this two ways and it converges with the only credentialed independent estimate. (B3-1)
2. **This is a repeatable economic regime, not a stunt — but only inside a hard boundary:
   problems that carry a cheap MECHANICAL VERIFIER.** The swarm architecture is brute-force search
   plus an oracle. No oracle, no swarm. (B3-3)
3. **Total spend on simulation and analysis goes UP, not down — but the claim splits in two, and
   only one half survives.** *Run volume* is clearly elastic and *aggregate compute spend* is
   rising fast (measured live in 2026, B3-2). *CAE vendor revenue* is NOT elastic, because the
   licence meter is deliberately sublinear — Ansys prices a **100x** core increase at **1.5x**, and
   its 2025 R1 "CFD HPC Ultimate" SKU charges **the same licence cost on one GPU as on a large
   cloud cluster** (B3-5). **Jevons is real on the physical workload and is being absorbed before
   it reaches the software P&L.** I corrected this against my own initial thesis.
4. **The literal "AI solved Navier-Stokes, CFD is disrupted" thesis is dead** — and B3's evidence
   kills it independently of the claim track. The event was a compute **sink**, not a compute
   saving. (B3-4)
5. **The obvious beneficiaries are unpitchable under `docs/Vectors.md`.** I say so plainly rather
   than manufacture a name. The one survivable long-only idea is a *wrongly-punished* one. (B3-8)

**THREE INDEPENDENT TRACKS, UNRELATED INDUSTRIES, SAME DIRECTION.** A1 (simulation software) found
vendors capturing the speed-up rather than being disrupted by it. B1 (services) found Accenture
selling *token-optimisation* as a new practice because clients over-consume. B3 (compute) finds
unit prices collapsing while volumes rise faster. None of the three was looking at the others'
evidence. That convergence is the strongest thing this project produces — **and I state its limit
in B3-9: convergent direction is not a measured elasticity, and at least part of what all three
tracks are observing predates the AI story entirely.**

**THE HURDLE STANDARD I ADOPT AND HOLD EVERYONE TO.** CIMdata — the industry's standard tracker —
sizes the Simulation & Analysis software market at **$10.0bn (2023) → $10.9bn (+8.8%, 2024) →
$11.67bn (+8.5%, 2025)** [verified at `raw/A1_software/08_market_sizing_and_opensource.md`;
cimdata.com releases 28195 and 30365]. **That series runs straight through the neural-operator and
surrogate-model wave and never inflects.** Any track in this project claiming simulation is being
disrupted must first explain that number. As the designated skeptic I will apply this to my own
findings too — see B3-9.

---

## B3-1 — What the 88-hour run actually cost, and what that settles
### *(Lead finding. This is the single number that determines whether "agents do frontier research" is an economic regime or a press release.)*

**Exposure:** Not a company line item. This is the **regime determinant** on which Tracks A1-A3 and
B1-B2 implicitly depend. If frontier agentic research costs eight figures per result, it is a
prestige burn by three labs. If it costs five figures, it is a new line in every R&D budget.

**Mechanism — the arithmetic, shown so a judge can check it.** Full working in
`raw/B3_compute/07_B3_cost_derivation.md`. Inputs are OpenAI's own disclosure [raw/B3/01] and
OpenAI's own published price list, scraped from `platform.openai.com/docs/pricing` and
`openai.com/api/pricing/` on **2026-09-19** [raw/B3/04].

*Step 0 — is the disclosure even coherent?* 130B output tokens / 2.7M messages = **48,148 output
tokens per message**. 130B / (88 x 3600s) = **410,354 output tokens/second** aggregate, or **41.0
tok/s per agent** across 10,000 agents. Astra's independently measured output rate is ~51 tok/s
(llm-stats.com, read 2026-09-19). So the disclosure implies 10,000 agents generating at ~80% duty
cycle for 88 straight hours. **It checks out.** The numbers are not an inflated headline.

*Step 1 — output tokens at list price.* 130,000 million-token units x $50/M = **$6.50M**.
(Long-context tier $75/M would be $9.75M.) This is the floor everyone quotes.

*Step 2 — input tokens, where the entire public spread lives.* Nobody disclosed input tokens.
Three bracketing scenarios, each stated so it can be attacked:

| Scenario | avg input ctx/msg | cache hit | input tokens | input $ | output $ | **TOTAL** |
|---|---|---|---|---|---|---|
| LOW | 50K | 90% | 135B | $0.26M | $6.50M | **$6.8M** |
| MID | 150K | 80% | 405B | $1.13M | $6.50M | **$7.6M** |
| HIGH (long-ctx rates) | 400K | 50% | 1,080B | $11.88M | $9.75M | **$21.6M** |

*Step 3 — this reconciles every circulating headline.* Run the same model on **all problems
attempted** (4.9M messages, 300B output tokens): LOW $15.5M / MID $17.1M / **HIGH $44.1M**. So the
">$40M" headline (latent.space) is the HIGH-input case applied to *everything OpenAI tried across
six Millennium problems plus warm-ups* — **it is not the cost of this proof**, and the "$22M"
figure is the HIGH case for Navier-Stokes alone. Nobody has published the derivation; I have.

*Step 4 — retail price is not what OpenAI spent.* Bottom-up from hardware: 410,354 tok/s at ~10,000
output tok/s per GB200 NVL72-class rack = **41 racks**; ~$3.0M/rack = $123M of equipment; amortised
over a 4-year life (35,040 h) = $3,513/hr x 88h = **$309K**; energy 41 x 130kW x 88h x PUE 1.25 =
587 MWh at $0.08/kWh = **$47K**. **Raw resource cost ~$0.36M; ~$1.1M loaded** for utilisation slack,
orchestration, the 17 Lean hours and researcher time.

*Step 5 — batch-rate sensitivity nobody has applied.* OpenAI's Batch API bills at **exactly half**
the standard rate [raw/B3/04, primary]. An 88-hour offline research sweep is the textbook Batch
workload. At Batch rates the whole band halves to $3.4M-$10.8M. Conversely Fast mode doubles it.
Honest statement: **the retail-equivalent price is known only to within about a factor of six.**

**Magnitude — and the independent check.** Karthik Duraisamy (Prof. of Aerospace Engineering,
Michigan; cited by *Science* as an independent cost estimator) published his own back-of-envelope
~2026-09-09 [raw/00_claim/karthik_duraisamy_blog_navier_stokes_compute_cost.md]:

> "130B tokens over those 88 hours across ~10,000 agents, i.e. **40 tokens/sec per agent. A normal
> decode rate.**" … "the output alone would cost (at Astra list price) **~$6M**, and input at a
> reasonable ratio with caching takes you to **~$10M total**." … "The cost to OpenAI to inference it
> would be something like **400k GPU-hours on GB200s ~$1M** (not at market rates!)."

| Quantity | **B3, derived independently** | Duraisamy | Agreement |
|---|---|---|---|
| Output tok/s per agent | 41.0 | 40 | exact |
| Output-only retail | $6.50M | ~$6M | exact |
| All-in retail | $7.6M MID (band $6.8-21.6M) | ~$10M | inside band |
| OpenAI internal resource cost | $0.36M raw / $1.1M loaded | ~$1M | same order |
| GB200 GPU-hours | ~260K | ~400K | within 1.5x |

Re-running my bottom-up on **his** 400K GPU-hour anchor: amortisation 400,000 x ($41,667/35,040) =
$476K; energy 400,000 x 1.8kW x 1.25 = 900 MWh = $72K; **total $548K**. Two methods from different
starting points land within a factor of two.

**Corroborating on-the-record figures:** Sébastien Bubeck, OpenAI — "**several million dollars**"
[raw/B3/02, Quanta, 2026-09-08]. Noam Brown, OpenAI — "millions of dollars" [raw/B3/05, 2026-09-08].
NYT 2026-09-10 — "millions of dollars in computation and electricity."

**THE NUMBER NOBODY IS QUOTING.** OpenAI also disclosed that the **unforced 3D Euler** blowup — a
genuinely open problem in PDE, and the result Duraisamy says he is *more* excited about — took
**~100 agents for ~50 hours** [raw/B3/01]. That is 1/176th the agent-hours of Navier-Stokes:
~**$45K at retail, ~$6K in resources**.
*** FLAG — UNRECONCILED PRIMARY SOURCES: OpenAI's blog says "nearly 100 agents"; Bubeck told
Science and Nature the figure was **1,000**. On the conservative Bubeck reading it is ~$455K retail
/ ~$57K internal. B3 reports both and picks neither. ***
**Either way, the economically decisive number in this whole event is five or low-six figures, not
$40M.** That is the finding.

**Timing:** already landed. The run completed 2026-09-05, announced 2026-09-08.

**Counter-thesis (argued at full force):** *The dollar cost was never the binding constraint —
access was.* The model that did this is **unreleased** and "significantly more capable than GPT-6
Astra" [raw/B3/01]. No customer can rent 10,000 copies of it at any price. Jamin Ball (Altimeter)
makes exactly this point [raw/B3/03]: "There are models that exist today that are already
meaningfully more performant than what's out in the public." A $1M price tag on a capability only
three labs possess is not a market. Further: this was an **opportunistic prestige scramble**, not a
research programme — OpenAI's own text says it launched on 2026-09-01 "inspired by **rumors**" that
Anthropic had cracked a Millennium problem. And the selection bias is real: 300B tokens across all
six Millennium problems produced **two** results; five remain unsolved. Finally, "$1M is cheap" is
cheap *for OpenAI*, which owns the racks; for anyone renting, the number is $6-10M.

**Long-only expression:** (c) a **de-risking constraint** on every other long in this project. Any
thesis that assumes frontier agentic research is prohibitively expensive is wrong by an order of
magnitude; any thesis that assumes it is *freely available* is wrong on access.

**Severity: thesis-grade.**

**Evidence:** `raw/B3_compute/01, 02, 03, 04, 05, 07`; `raw/00_claim/karthik_duraisamy_blog_navier_stokes_compute_cost.md`.

---

## B3-2 — The Jevons question is not an analogy in 2026. It is being measured, and it points up.

**Exposure:** The load-bearing assumption under every "who is harmed" finding in this project.
Metaprompt dimension 6 says to treat "demand falls" as the claim requiring proof. It has not been
proved, and the live data runs hard the other way.

**Mechanism, hop by hop:** unit price of inference falls → tokens consumed per task rises faster →
total spend rises. Each hop has a 2026 number.

*Hop 1 — unit price is collapsing, confirmed.* Constant-capability inference deflates ~10x/yr:
GPT-3-class $60/M → $0.06/M in three years; GPT-4-class down ~300x since March 2023 [raw/B3/40].
ARC-AGI-1 at 87.5% cost ~$500,000 with o3 in Dec 2024 and ~$20 with Astra in 2026 — Noam Brown's
own framing, ~20,000x in 17 months [raw/B3/05].

*Hop 2 — tokens per task is exploding, which is the specifically NEW thing.* OpenRouter's
100-trillion-token study, late 2023 → late 2025: median prompt 1,500 → 6,000+ tokens; completions
tripled; **reasoning models went from negligible to >50% of all tokens**; programming from 11% of
volume to >50%. Stanford's Digital Economy Lab measured **agentic coding tasks at ~1,000x the tokens
of a code-chat query** [raw/B3/40]. The OpenAI run is the extreme instance of exactly this: 48,148
output tokens *per message*, 2.7 million messages.

*Hop 3 — total spend is rising anyway, in audited-adjacent data.* Blended enterprise cost of AI fell
**67% YoY** ($18.40 → $6.07 per million tokens, Q1'25 → Q1'26, from 2.4 billion enterprise API
calls) while bills rose [raw/B3/41]. Ramp Economics Lab: **AI token spend per firm up 13x since
January 2025**. Gartner: worldwide AI spending 2026 **$2.59 trillion, +47% YoY**; GenAI model spend
+110%. Google's own disclosure: monthly tokens 9.7T (May 2024) → 480T (May 2025) → **3.2 quadrillion
(May 2026)**, 330x in two years [raw/B3/40].

*Hop 4 — the cleanest natural experiment already ran.* DeepSeek, January 2025: **$589 billion of
Nvidia market cap erased in a day** on the thesis that efficiency kills demand. Eighteen months
later Nvidia's order book had **doubled to $1 trillion** [raw/B3/40]. Satya Nadella's same-day
"Jevons paradox strikes again" is now consensus.

*Hop 5 — Google published both halves of the identity.* Energy per median Gemini prompt fell **33x
in twelve months** to 0.24 Wh. Total Google electricity rose **37% in 2025 anyway**, to ~3.5x its
2019 level, with the largest emissions increase the company has ever reported [raw/B3/40]. That is
Jevons with quarterly disclosure.

*Hop 6 — the same pattern, independently, in two unrelated industries.*
- **Simulation software (Track A1's evidence, verified at source).** CIMdata S&A market: **$10.0bn
  (2023) → $10.9bn (+8.8%) → $11.67bn (+8.5%, 2025)** — growth straight through the surrogate-model
  wave, no inflection [`raw/A1_software/08`]. Ansys annual contract value growth never inflected
  either: **+12/+20/+16/+14/+13/+11.4% across FY2019-FY2024**.
- **Services (Track B1's evidence, verified at source).** **Julie Sweet, Accenture CEO, Q3 FY2026
  call** [`raw/B1_services/ACN_Q3FY26_call_fixed_price.md`]: *"we have a whole practice that we're
  starting to grow now is on **how to help clients optimize their use of tokens**. It feels a lot
  like the cloud scenarios… people were moving to the cloud and then they were like, 'oh, wait a
  minute, **we're spending a lot more on the cloud than we thought**' and we built a whole FinOps
  practice on helping optimize cloud… our tokenomics platform internally, we're now taking to
  clients."* **This is Jevons observed as a P&L line, not asserted as theory: a consultancy is
  monetising the fact that cheap tokens produced overspending.** The cloud-FinOps precedent it
  invokes is a genuine analogue — same shape, same lag, same remedy — and its quality is graded in
  B3-5's table.

**Magnitude:** Big Four capex guided near **$740B for 2026, up from $410B in 2025**; ~**$1.7
trillion** of contracted, unrecognised backlog (Microsoft RPO $678B +84%, AWS $496B, Google Cloud
$514B) [raw/B3/40, raw/B3/20]. Amazon raised 2026 cash capex from ~$200B to **~$220B** and Andy
Jassy said on 2026-07-30: *"Even at that amount, we will still not have enough capacity to meet all
the demand we have in 2026"* [raw/B3/20].

**Timing:** already in reported financials, every quarter since mid-2025.

**Counter-thesis (argued at full force):** Three real attacks. **(i) The measurement is a stack of
different proxies** — revenue, spend, tokens, orders — not a controlled demand curve; the source
that assembles them concedes this shows "direction rather than a measured elasticity" [raw/B3/40].
**(ii) Demand may be capability-seeking, not price-seeking**, which is a *different* mechanism from
Jevons: Menlo's survey finds 66% of enterprise workloads upgrade to the newest model within months,
only **11% switch vendors to save money**, and open-source share *fell* from 19% to 13% despite far
lower prices. "Buyers pay for capability, not tokens." If that is the driver, a price cut is not
what is causing the volume, and the Jevons framing is mislabelled even though the conclusion holds.
**(iii) Budget-constrained buyers break Jevons outright** — see B3-6, where sequencing did exactly
that.

**Long-only expression:** (c) **de-risking constraint** on the whole project — plus it is the
premise under B3-8.

**Severity: thesis-grade.**

**Evidence:** `raw/B3_compute/40, 41, 05, 20`.

---

## B3-3 — The boundary of the regime: no mechanical verifier, no swarm
### *(My most important analytic contribution. It is what makes "repeatable regime" a defensible answer rather than a hype statement.)*

**Exposure:** Determines which industries can and cannot be attacked by the 10,000-agent method,
and therefore which of this project's "who is harmed" candidates are actually exposed.

**Mechanism:** The architecture is **massively parallel search plus a cheap oracle**. You spawn
10,000 branches precisely because a machine can tell you which branch is right. Lean is that oracle
here — and the 25 Fields Medalists who signed "A Severe Misalignment of AI in Mathematics" on
2026-09-11 **do not dispute the proof's correctness**; the Lean verification settled that. Their
objection is to research culture [raw/B3/06]. The independent statement of the principle, from Nick
McGreivy (PhD in numerical methods), 2026-09-08 [raw/00_claim/nick_mcgreivy_how_openai_found_a_singularity.md]:

> "The key concept in this new paradigm is, for now, **verifiability**. Anything which can be
> computationally verified can be used as a reward function in reinforcement learning… Math proofs
> are largely verifiable, thanks to the Lean programming language. Unsurprisingly, frontier LLMs are
> now superhuman at math proofs. **Numerical methods… are also verifiable. Accuracy, speed, and
> convergence are all properties of an algorithm that can be verified computationally. I expect
> that, sometime in the next year or two, advanced LLMs will begin to invent state-of-the-art
> numerical methods.** … many scientific problems aren't easily verifiable… determining whether an
> AI-designed drug is safe and effective takes years of human trials, and so isn't fully amenable to RL."

And the sharpest statement of the negative case, from the cost commentary [raw/B3/ derived,
thecherrycreeknews.com 2026]: *"You cannot spawn ten thousand copies of an admin task and let a
compiler pick the winner, because nothing tells you which one is right."*

**So the taxonomy is:**

| Domain | Mechanical verifier? | Swarm-attackable? |
|---|---|---|
| Formal mathematics | **Yes** — Lean | Demonstrated, 2026-09 |
| Software / code | **Yes** — tests, compilers | Already commercial |
| Chip design | **Yes** — DRC/LVS, formal equivalence, timing sign-off | Already commercial (see B3-5) |
| **Numerical methods R&D** | **Yes** — accuracy, speed, convergence | **McGreivy: 1-2 years** |
| **Production CFD / engineering sim** | **WEAK ONLY** — residuals converge, but convergence ≠ physical validity; turbulence closures are empirical and validated against wind tunnels and flight test | **No** |
| Clinical/regulatory, most enterprise work | **No** — verification takes years and humans | No |

**Magnitude:** This is the line that separates ~$50K-per-open-problem economics from ordinary work.
The three conditions the method requires are a mechanical verifier, a high-value problem, and — as
of 2026-09-19 — an unreleased frontier model.

**Timing:** numerical-methods invention is McGreivy's 1-2 year call, i.e. **2027-2028**. That is
outside a one-year holding period. State it plainly.

**Counter-thesis:** Verifiers can be *manufactured*. Every domain that builds a good simulator or a
good test harness converts itself into an RL-able domain, and simulation vendors are in the business
of selling exactly that harness — which would make them the *enablers* of the regime rather than its
victims. Also, McGreivy is forecasting, not reporting; nothing has been built yet.

**A second-order demand channel the verifier constraint creates.** If the method's binding input is
a *verifier*, then scaling the method scales demand for verification — including the human,
liability-bearing kind where no machine oracle exists. Track B1 found the commercial instance:
**Accenture and Anthropic signed a deal dated 2026-09-18, ~$1bn each over five years, for embedded
evaluators to red-team and audit frontier models** [`raw/B1_services/ACN_Anthropic_partnership_2026-09-18.md`].
Agentic frontier work is generating paid demand for human verification labour *alongside* the
compute, not instead of it. That is consistent with the Fields Medalists' complaint in B3-6's
sibling file — Tao: *"They're expecting us to prepare the food and cook it and eat it. All that work
is left to us"* — which is, economically, a description of an unpriced verification burden that
someone will eventually be paid to carry.

**Long-only expression:** (c) **de-risking constraint**. It is the reason to refuse any finding that
assumes agentic AI walks into CFD or certification the way it walked into Lean.

**Severity: thesis-grade** (as a constraint, not as an idea).

**Evidence:** `raw/B3_compute/06`; `raw/00_claim/nick_mcgreivy_how_openai_found_a_singularity.md`;
`raw/B3_compute/50`.

---

## B3-4 — A proof is not a solver. The event was a compute SINK.

**Exposure:** The transmission path from this theorem to any CFD vendor's income statement.
**There is none.** Per metaprompt rule: "Never conflate a proof with a solver."

**Mechanism:** The metaprompt demands the practitioner saying "this changes nothing for us." Here he
is — CloudHPC, an HPC provider that sells CFD cycles (OpenFOAM, FDS), 2026-09-15 [raw/B3/50]:

> "**For engineering simulation, essentially nothing changes.** Finite volume solvers never relied
> on global regularity of the continuum model in the first place: discretization, physical or
> numerical viscosity, and grid scale all bound the computed solution… The singular solution
> described by OpenAI was constructed with a specific, hand-tuned external forcing — **it is a
> mathematical pathology, not a condition that arises around a heat exchanger at Reynolds number
> 10⁵.**"

Corroborated independently: *"it does not give engineers a general closed-form Navier-Stokes solver,
nor does it change anything about CFD, turbulence"* (Moses Lua, LinkedIn); *"nothing in the current
episode changes how an aircraft is designed or a storm is predicted"* (siai.org). And Duraisamy —
the most credentialed fluid dynamicist to comment at length — writes extensively about the compute
and the research enterprise and **never once claims a change to a CFD workflow** [raw/00_claim].

**And the direction of the compute is the opposite of the headline.** This result *consumed*
~400,000 GB200 GPU-hours and ~130B output tokens and produced **no code, no benchmark, no speedup**.
Duraisamy: the FLOP count is *"much larger than any scientific computation ever."* The same CFD
provider draws the Jevons conclusion directly [raw/B3/50]:

> "AI agents that set up, mesh, run, and post-process simulations are starting to **consume far more
> compute than an equivalent human-driven workflow ever would. The underlying solvers are not being
> replaced — but the demand for the compute that runs them is growing.**"

**Magnitude:** Zero dollars of identified revenue displacement. No named company, no named revenue
line — therefore, per the metaprompt, **no finding of harm exists here.**

**Timing:** n/a.

**Counter-thesis:** The *method* may matter even though the *theorem* does not — see B3-3 and
McGreivy's numerical-methods forecast. But that must be evidenced separately and is a 2027-2028
story, not a 2026 one.

**Long-only expression:** **unpitchable — no long expression.** Reported as a negative result,
which the metaprompt explicitly calls valuable.

**Severity: thesis-grade as a kill.**

**Evidence:** `raw/B3_compute/50`; `raw/00_claim/cloudhpc_cloud_what_it_means_for_cfd.md`,
`karthik_duraisamy_blog_navier_stokes_compute_cost.md`.

---

## B3-5 — The EDA analogue, which is the good one, and what it actually proves

**Exposure:** Whether cheap simulation shrinks or grows the simulation-vendor revenue pool. Named
companies, named revenue lines.

**Why EDA is the right analogue and most others are not.** EDA shares four structural features with
engineering simulation that rendering, storage and database queries do not: (1) the customer is a
capital-intensive engineering organisation, not a consumer; (2) the output is a *design decision*
with a sign-off/liability gate attached; (3) demand is bounded by engineering headcount and project
cycles, not by appetite; (4) the tool is sold on a subscription/seat basis to a concentrated buyer
set. It is also the only case where AI tooling has *already* been deployed at scale and we can read
the vendor's income statement afterwards.

**Mechanism — the unit cost collapsed and total spend rose ~8x.**
- Semiconductor **revenue per transistor has been declining ~32% per year** for decades (Wally
  Rhines data, via Cadence, 2020-05-05) [raw/B3/14].
- Over the same era **EDA industry revenue rose from $2.703B (1997) to $21.22B (2025)** — ESD
  Alliance / EDA Consortium Market Statistics, the industry's own primary series [raw/B3/10]. Q1
  2026: **$5.748B, +12.7% YoY**.
- Per-*design* cost went the other way: **7nm $222.3M → 5nm $436.3M → 3nm $650M** (IBS via
  Semiconductor Engineering) [raw/B3/14].
- And the closest sub-category to our question — **CAE, i.e. simulation — is the fastest-growing
  line in the whole industry right now: +15.5% YoY to $2,018.4M in Q1 2026**, four-quarter average
  +13.1% [raw/B3/10].

**The value-capture fact that matters more than the growth rate.** EDA revenue has been a
strikingly **stable ~2% of semiconductor revenue** for 25+ years — Rhines: *"semiconductor R&D is a
constant 14% of semiconductor revenue, and 1/7th of that goes to EDA. So EDA is basically 2% of
semiconductor revenue, rain or shine"* [raw/B3/12]. My own check confirms the ex-IP ratio sits in a
1.5-2.0% band from 2000 to 2025; on an inclusive definition it has *risen* from ~1.9% to ~2.7%,
driven by semiconductor IP. **Read correctly: the tool vendor does not capture the productivity
windfall. It collects a stable toll on the customer's total R&D budget — which grows with the
customer's scale.** That is a royalty on industrial complexity, not on unit compute.

**Mechanism, restated by management, on the record.** This is the part that answers the CFD
question directly, because Synopsys now owns Ansys.
- **Sassine Ghazi, Synopsys CEO, Q3 FY2026 call, 2026-08-26** [raw/B3/31]: *"as these agents take on
  more engineering work, they **orchestrate our underlying EDA tools at a significantly higher
  rate**. That allows customers to **run more design and verification workloads**, creating an
  incremental growth opportunity for Synopsys."* And: *"the **consumption of these assets is
  exponential**."* And on agents: *"**the need is for more licenses**."*
- **The CFD datapoint, from the same call:** *"In Q3, our **largest Ansys deal** was for
  **GPU-accelerated Ansys CFD** to support a company-wide digital twin at a multinational
  electronics component maker."* Cheaper-per-run CFD produced the **largest** deal of the quarter,
  not a smaller one. Also cited: a leading automaker using Ansys SimAI at ~98% prediction accuracy
  to move crash analysis to near real-time; a heavy-equipment maker achieving >10x faster motor design.
- **John Wall, Cadence CFO, Q4 2025 call, 2026-02-17** [raw/B3/13]: *"**What AI does is it changes
  how much customers run the tools**… There's more automation. There's more iterations, **there's
  more compute**. So we'll attach more usage-based pricing for incremental capacity."* And: *"our
  view of the AI era is that it **increases workload faster than headcount grows**."*
- **Anirudh Devgan, Cadence CEO, same call:** agentic AI will be priced *"like a virtual engineer or
  agent. So that would be **extra business**… **and then on top of that… it will call the base tools
  and they become a lot more licenses or usage will happen on our base tool**."*
- **Dassault Systèmes, FY2025 release, 2026-02-11** [raw/B3/32]: *"**As AI adoption accelerates,
  business models are evolving beyond traditional seat-based pricing toward usage- and value-based
  models.**"* — the vendor conceding that seats no longer capture the value, and moving to bill
  volume. ARR €4.50B, +6%.

**Magnitude (named companies, named lines, named disclosures):**

| Company | Simulation-relevant line | Figure | Period / disclosure |
|---|---|---|---|
| **Synopsys (SNPS)** | Ansys contribution (inside Design Automation segment) | **~$711M in the quarter; ~$2.98B FY2026 guided** | Q3 FY2026, quarter ended 2026-07-31; 10-Q + 2026-08-26 release [raw/B3/30] |
| Synopsys | Total revenue | **$2.477B, +42.4%**; FY26 guide raised to $9.69-9.74B | same |
| Synopsys | EDA organic, ex-Ansys | **+8.5% YoY**; backlog $10.9B | same |
| **Cadence (CDNS)** | Core EDA revenue | **+13% in 2025**; IP +25%; total $5.30B (+14.1%); backlog $7.8B | Q4 2025 call, 2026-02-17 [raw/B3/13] |
| **Dassault Systèmes (DSY.PA)** | Industrial Innovation (contains SIMULIA) | **€3,134.5M FY2025, +6% cc**, 56% of software revenue; *"CATIA, SIMULIA and ENOVIA were the strongest contributors to growth"* | FY2025 release 2026-02-11 [raw/B3/32] |
| Industry | **CAE (simulation) category** | **$2,018.4M in Q1 2026, +15.5% YoY** | ESD Alliance EDMD via SEMI, 2026-07-13 [raw/B3/10] |

*Correction to a common premise, for the record:* **Dassault does NOT disclose SIMULIA separately.**
Any standalone SIMULIA dollar figure in circulation is a market-research estimate, not a disclosure
[raw/B3/32]. Similarly, **Ansys is no longer a separate reportable segment** — Synopsys closed the
$34.9B acquisition on 2025-07-17 and folds it into Design Automation [raw/B3/30].

**Timing:** Already reported. Synopsys Investor Day 2026-09-30 is a near-term observable trigger —
Ghazi pre-announced he will detail *"how we are thinking how to model the long-term growth"* of
consumption-based agentic pricing there.

**COUNTER-THESIS — and the one that forced me to correct my own reading.**

*** THE PINNED-DENOMINATOR PROBLEM. I originally read the EDA series as "unit cost fell, total
spend rose 7.85x, therefore Jevons." That reading is wrong, or at least unproven, and I am
correcting it in place rather than quietly dropping it. EDA revenue has been a fixed ~2% of
semiconductor revenue for 25+ years. **A ratio that does not move is evidence that the total was
set by the DENOMINATOR, not by the price of the tool.** EDA spend grew 7.85x because semiconductor
revenue grew, not because tools got cheap. If CFD and math tooling are similarly pinned to a fixed
share of aerospace, auto and energy R&D budgets, then a unit-cost collapse **redistributes** value
rather than expanding it — and the Jevons conclusion does not follow from this series at all. The
EDA data proves total spend did not FALL. It does not prove cheapness CAUSED the rise. ***

Four further attacks, each real:
1. **This is vendor management talking its own book on its own calls.** There is no independent seat-count or per-design-spend audit anywhere in
   these sources, and every quoted executive is selling the story that AI expands their TAM.
2. **The commoditising sub-line is genuinely shrinking.** EDA's **IC Physical Design & Verification**
   category — the classic "tool seat" business, and the one closest to pure automated sign-off —
   **declined 2.6% in Q4 2025 with a four-quarter moving average of -5.1%** [raw/B3/10], roughly
   flat at ~$750-780M/quarter. Industry growth has migrated to **Semiconductor IP**, which went from
   $124M in 2000 (3.3% of the industry) to **$2,332.5M in Q1 2026 (40.6%)**. If you are looking for
   evidence that automation eats a tool category, it is right there in the industry's own data.
3. **Chip design may be structurally special in exactly the way CFD is not.** Devgan's own argument
   is that RTL is a *formal language* with thirty years of verification tooling built to check it —
   *"in some other industries, there is no like formal languages to design things."* That is the
   B3-3 verifier boundary, stated by the CEO whose quotes I am relying on, and it cuts against
   transferring his conclusion to fluid dynamics.
4. **EDA has an unusually concentrated, unusually rich customer set;** general engineering
   simulation does not.

### Analogue quality, graded — because a weak analogue is worse than none

| Analogue | Unit price | Total spend | Grade | Why |
|---|---|---|---|---|
| **EDA** | revenue/transistor **-32%/yr** | $2.703B (1997) → **$21.22B (2025)**, 7.85x, CAGR 7.6%, unbroken through every cycle [raw/B3/10] | **A, with the pinned-denominator caveat above** | Same buyer (engineering R&D budget), same good (physics/math solver licences), same seat-plus-compute pricing. Nearly a direct case, not an analogue — **Ansys *is* CFD and now sits inside an EDA vendor being sold on exactly this logic.** |
| **Cloud storage (S3)** | 15c/GB (2006) → **just over 2c/GB (2026)**, -85%, AWS's own statement 2026-03-14 | ~1 PB (2006) → **>500 trillion objects, hundreds of exabytes** (~10^8x); AWS segment net sales $35.0B (2019) → **$128.7B (2025)** per 10-K [raw/B3/16] | **B+ arithmetic, C analogue** | Cleanest Jevons arithmetic anywhere. **But bytes are an automatic byproduct of other activity — no human decides to store each object.** A CFD run requires someone to decide to run it *and read the result*. |
| **VFX / rendering** | RenderMan Pro Server **$3,500 → $2,000/seat in one step, Nov 2010**, explicitly so customers could "expand their render farms" | **No total-spend series exists** (estimates span 5x) | **B mechanism, F evidence** | Blinn's Law is the purest demonstration of the psychology: hours per frame went **3-4h (Toy Story, 1995) → 29h (Monsters U, 2013) → ~50h (Luca, 2021)** while hardware got ~10,000x cheaper. Practitioners spent **100% of the windfall on quality.** Maps onto mesh refinement, LES-vs-RANS and DOE breadth — but carries no quantitative weight. |
| **Cloud FinOps → token optimisation** | n/a | Accenture building a practice on client *over*-spend, twice [raw/B1_services] | **A for mechanism** | Same industry, same firm, same remedy, one cycle apart. The strongest *behavioural* analogue in the set. |
| **Genomic sequencing** | $95.3M (2001) → **$524.62 (May 2022)**, 181,600x — but only **2.6x from Jan 2015 to May 2022** | **Illumina flat-to-down four straight years** | **C — use as counter-example only** | See B3-6. |

**The single structural argument that should worry this project most** (and it is my own subagent's,
not mine): **if the binding constraint is engineer attention rather than FLOPs, cheaper simulation
floods a fixed-width channel and total spend is capped by headcount.** Cadence's answer — *"it
increases workload faster than headcount grows"* — is **a claim, not evidence.** Note, though, that
the industry's own headcount data cuts the other way: EDA vendor employment went 26,767 (Q4'10) →
**72,544 (Q1'26)**, 2.7x, while tools got radically more automated.

### *** SELF-CORRECTION: I had this half wrong, and the correction matters more than the finding ***

I set out to show that cheaper simulation means more simulation spend. **My own researcher came
back with evidence that splits the claim in two, and only one half survives.**

**Half that survives — physical run-volume IS elastic. Documented, with customer names:**
- **Volvo Cars**, Torbjörn Virdung (technical leader, CFD): runtime **24h → 6.5h** on 8 Blackwell
  GPUs vs 2,016 CPU cores — *"the added NVIDIA infrastructure supercharges the computation, **so we
  can consider a greater number of design possibilities** and reach an optimal car design faster"*
  [raw/B3/42].
- **Cadence Millennium M2000** (80x vs CPU, 20x lower power): *"customers can **explore more design
  scenarios and iterations** within tighter deadlines"* [raw/B3/34]. MediaTek: *"we are able to run
  **previously impossible** simulations."*
- **Synopsys/Ghazi**, Q3 FY2026: *"**In CFD, we are seeing 40, 50, 60x speed up.** The bottleneck
  for our customers is the time to results."*

**Half that FAILS — vendor revenue is NOT elastic, because the licence meter is sublinear BY DESIGN.**
This is the single most damaging fact I found, and it is in Ansys's own marketing [raw/B3/37]:

> **"Running on 2,000 cores instead of 20 cores incurs a cost premium of only 1.5X — and not the 100X!"**

And **Ansys 2025 R1 "CFD HPC Ultimate"**: *"**Unlimited cores and GPUs with no extra HPC add-ons**"* /
*"**The same license cost whether running on one GPU or a large cloud cluster.**"*

**Read that again: faced with GPU acceleration, the CFD market leader's commercial response was to
switch the volume meter OFF.** A 100x increase in runs yields roughly 1.5x — or, on the Ultimate
SKU, **1.0x** — of vendor revenue. **This flatly contradicts Ghazi's *"we capture the entire value
and uplift of the GPU."* Both cannot be fully true. I flag the tension rather than pick the quote I
prefer.**

**And the clean quantitative test fails.** Ansys was a pure-play — its revenue *is* the simulation
line. FY2020→FY2024: **$1,681M / $1,907M / $2,066M / $2,270M / $2,545M, i.e. +10.9%, +13.4%, +8.3%,
+9.9%, +12.1%** [raw/B3/36, Ansys 10-K]. **Steady, no inflection, across exactly the window when GPU
solvers, cloud HPC and per-run cost collapse arrived.** Same shape as CIMdata's 8.5-8.8%. Cheaper
simulation neither accelerated nor depressed the growth rate. **That is the HCLTech test (see B3-9)
applied to my own thesis, and my thesis does not pass it.**

**The ceiling, named by an insider rather than a critic.** Jean-Claude Ercolanelli, SVP Simulation &
Test Solutions, **Siemens Digital Industries Software**, September 2024 [raw/B3/38]:

> *"**simulation technology in its current state has matured and hit a scalability ceiling.** We have
> transitioned from a paradigm of computational limitations, where access to appropriate compute
> resources was a major hurdle… to one where **human expertise is becoming a scarce commodity.
> Accessibility to experts able to operate complex simulation software is the bottleneck.**"*

And Siemens' own blog: *"we can predict physics behavior in seconds, run high-fidelity simulations
on GPUs in minutes… **And yet, engineering cycles are still slower than they could be. Which
suggests that simulation itself is no longer the limiting factor.** … **Simulation is no longer the
bottleneck — your organization might be.**"*

**Two more disconfirmers I will not bury:**
- *"**More iteration does not produce a better design.** … In practice, **faster iteration can reduce
  validation depth.**"* (Machine Design, "Why CAE Simulations Fail") [raw/B3/38].
- **A rival voted with its balance sheet.** **Hexagon sold MSC Software** to Cadence (announced
  2025-09-04, closed 2026-02-23, $2.9B) to *"sharpen future investment behind core business areas."*
  A diversified owner **exited simulation during the supposed boom** [raw/B3/35].
- **Every "more simulations" claim traces to a SELLER, not a buyer.** Of the five Cadence M2000
  customer quotes, **none claims more runs or more spend** — they claim shorter runtimes and earlier
  decisions. Volvo's is hedged ("has the potential to", "can allow us"). **My researcher searched
  specifically for a named executive saying "faster simulation reduced our simulation budget" and
  found none — but also found no buyer attesting to higher spend.** The elasticity evidence is
  one-sided testimony from people selling the tools.

### REVISED VERDICT ON B3-5
**Jevons is operating on run-volume and being ABSORBED by sublinear licence pricing rather than
converted into vendor revenue.** The freed value is therefore *not* landing on the CAE software
vendor's P&L. It is landing (i) with the customer, as faster engineering cycles, and (ii) with the
compute supplier, as the volume Ghazi himself conceded *"benefits partners like NVIDIA."* That is a
cleaner dimension-8 answer than the one I started with, and it is worse for the long-only idea.

**The genuinely bullish signal is prospective and narrow: the pricing-model migration.** Synopsys is
in advanced discussions on consumption pricing for agents; Dassault is moving to *"usage- and
value-based models"* and began reporting ARR (Q4 2025 €4.50B, +6%). **If** those land, vendors begin
capturing volume they currently give away. Synopsys says Multiphysics Fusion contributes meaningfully
only from **2027**. Observable trigger: **Synopsys Investor Day, 2026-09-30.**

**Long-only expression:** (b) a **wrongly-punished long** — but **materially weaker than I first
wrote, and I am downgrading it.** The defensive half holds: the evidence says simulation demand is
not collapsing and CAE grew 8.5-8.8% straight through the surrogate wave, so "AI killed CFD" is
wrong. The offensive half does not: **there is no evidence that cheaper compute expands the CAE
vendor's revenue, and the market leader's own price list is built to prevent it.** Anyone pitching
this must pitch *stability wrongly priced as decline*, **not** *Jevons upside*. It belongs to Track A1
and needs a valuation and catalyst I have not done.

**Severity: downgraded from thesis-grade to supporting.**

**Evidence:** `raw/B3_compute/10, 12, 13, 14, 30, 31, 32, 34, 35, 36, 37, 38, 39, 42`.
*** Source-quality flag: the Ghazi Q3 FY26 quotes come from a third-party Investing.com transcript,
not Synopsys's own posted PDF, which returned empty. **Re-verify before making load-bearing.** The
Cadence SD&A dollar figures are derived arithmetic from rounded percentages, ±$10M. ***

---

## B3-6 — The analogue that FAILS, and why I am reporting it against myself
### *(Metaprompt: prefer disconfirming evidence. This is the strongest evidence against my own track.)*

**Exposure:** Genomic sequencing is the analogue most often reached for — "cost per genome collapsed
and total spend exploded." **For 2013-2021 that is true. For 2022-2025 it is false, and the failure
is instructive.**

**Mechanism and magnitude.** NHGRI cost per genome fell from $4,920 (Oct 2013) to $524.62 (May
2022), a 9.4x collapse [raw/B3/11]. Illumina revenue rose from ~$1.42B (2013) to $4.53B (2021) —
textbook Jevons. Then [raw/B3/15, Illumina Q4/FY2025 release, 2026-02-05]:

| FY | Revenue | Change |
|---|---|---|
| 2022 | $4.58B | +1.3% |
| 2023 | $4.50B | -1.8% |
| 2024 | $4.37B | -2.9% |
| 2025 | **$4.34B** | **-0.7%, "flat compared to 2024"** |

**Four consecutive years of flat-to-declining revenue, -5.2% from the 2022 peak, while unit cost
kept falling and Illumina launched NovaSeq X promising a "$200 genome."** FY2025 R&D *fell* to $967M
from $988M. That is a direct counter-example at the firm level.

**Three competing explanations, and the one that should worry this project:**
1. **Budget-constrained buyers break Jevons outright.** Academic and NIH sequencing budgets are set
   by appropriation, not by price. **If the buyer's budget is fixed, a price cut reduces total spend
   by construction.** The NHGRI curve itself flattened after 2015 (only 2.6x in 7.3 years).
2. **Firm ≠ market.** Illumina lost share (Element, Ultima, MGI, ONT, PacBio) and lost China
   (ex-China revenue +2% in 2025 vs flat total). Stagnation at Illumina is not stagnation in sequencing.
3. **Value migrated downstream** to interpretation and clinical testing — invisible in the
   sequencer vendor's line, and GRAIL was spun off in Q2 2024.

**Why this matters for us:** explanation (1) is a live risk for engineering simulation. **A defence
prime's CFD budget, or a certification programme's simulation budget, may be appropriation-shaped
rather than price-shaped.** If so, cheaper runs mean *fewer dollars*, not more runs. This is the
strongest available argument against B3-2 and B3-5 and I am not going to bury it.

**Also flagged:** commercial NGS market-size estimates for 2025 span **$10.44B to $25.7B** — a 2.5x
spread for the same year across five research houses [raw/B3/15]. **None of them can be used as
evidence.** The same caution applies to every "global CFD market size" number this project encounters.

**Counter-thesis to my own counter-thesis:** enterprise engineering budgets are *not* appropriations
— they are set against product programmes and competitive pressure, and the 2026 enterprise AI data
(B3-2) shows corporate buyers *raising* budgets as unit prices fall, which is precisely the
behaviour NIH did not exhibit.

**Long-only expression:** (c) **de-risking constraint** on any Jevons-based long.
**Severity: supporting, but weighted heavily.**
**Evidence:** `raw/B3_compute/11, 15`.

---

## B3-7 — Who captures the freed value: three historical endings, and the one everyone forgets

**Exposure:** Metaprompt dimension 8, first half. If simulation and analysis get cheap, the savings
accrue to *someone*. Tracing it is where a long-only idea would have to come from.

**Mechanism — unit deflation has never shrunk the aggregate, but the winner differed every time**
[raw/B3/40]:

| Case | Unit price | Aggregate | **Who kept the money** |
|---|---|---|---|
| Transistors | fell ~**1 billion-fold** 1971-2022 | revenue ~$1B → **$791.7B** | **The deflation manufacturers** (Intel, then TSMC, Nvidia) — "making the next cheap unit was itself the monopoly" |
| Electricity | real prices fell ~**48x** across C20th | consumption rose ~**630x** | **Nobody, for long** — regulators converted utilities to rate-of-return; surplus flowed to everything electrified |
| **Bandwidth / IP transit** | **~$1,200/Mbps → <$1** | traffic doubled annually **through the bust** | **NOT the infrastructure owners. WorldCom and Global Crossing went bankrupt on CORRECT demand forecasts.** Value moved up to Google, Netflix, AWS |

**The bandwidth case is the one this project must respect.** *Jevons can be completely true at the
level of aggregate demand and still destroy the equity of the firms supplying the capacity.*
"Demand rises" and "the supplier's stock works" are different claims. Anyone pitching a compute
beneficiary on Jevons logic alone is repeating the Global Crossing thesis, which was *right about
demand*.

**Where the scarcity actually sits in 2026.** The honest read [raw/B3/40]: *"deflation does not move
value up or down the stack so much as **toward whatever cannot be deflated**. At the top, that is
frontier capability and distribution. At the bottom, **watts**."*
- **Power is the only layer with rising unit prices.** PJM capacity cleared **$28.92/MW-day** for
  2024/25, then $269.92, $329.17, **$333.44** — and would have hit ~$530 without the federal cap.
  The market monitor attributes **46% of the last four auctions' $63.6B cost to data centers**.
  Northern Virginia vacancy **0.3%**, rents ~doubled since 2022. GE Vernova turbine backlog **116
  GW, sold out into 2031**. Median interconnection-queue wait **>5 years**. Goldman: US data centre
  power 31 GW (2025) → 66 GW (2027).
- **The labs do NOT capture it.** Reported gross margins: OpenAI ~40% (2024) → **33% (2025)**,
  missing its own 46% forecast; Anthropic -94% (2024) → ~40% (2025). Inference margin is improving
  (SemiAnalysis: Anthropic ~38% → ~70% by mid-2026) but blended margins remain far below the 75-85%
  software benchmark [raw/B3/40].
- **The application layer captures most, conditionally, and not yet.** Enterprise application spend
  reached **$19B in 2025 — larger for the first time than the model spend beneath it**. But Cursor
  ran **-23% gross margin** for the quarter ended January 2026; Perplexity's 2024 compute spend was
  **164% of revenue**. The windfall is coming, it has not arrived.
- **Memory is a trade, not a holding.** SK hynix revenue +257% at a **76% operating margin**; Micron
  HBM sold out through 2026 at gross margins in the 80s. Against that: "three well-capitalized
  suppliers adding capacity into 70%+ margins has always, eventually, mean-reverted" [raw/B3/40].
  Amazon confirmed the cost side on 2026-07-30: capex raised to $220B because of *"the higher cost
  of memory"* [raw/B3/20].
**THE ONE PLACE A VENDOR NAMES WHO GETS THE FREED VALUE.** Synopsys, on a GPU-accelerated CFD deal
delivering 40-60x speed-ups [verified at `raw/A1_software/04_synopsys_ansys_fy2026.md`]:

> *"**Synopsys captures the value uplift from these speed improvements, while the hardware
> requirement benefits partners like NVIDIA.**"*

That is the whole of dimension 8 in one sentence, from the party best placed to know: **the
software vendor keeps the productivity uplift, and the compute supplier keeps the volume.** It also
lands the freed value squarely on a name that `docs/Vectors.md` §4 marks **Hard avoid**. I am not
going to pretend otherwise — see B3-8.

- **The hardware mix genuinely changes, and there is now a hardware artefact proving it.** Agentic reasoning is memory-bandwidth and KV-cache bound
  before it is FLOP bound: H100 80GB at 3.35 TB/s (2022) → Rubin 288GB HBM4 at 22 TB/s (2026),
  capacity +3.6x and bandwidth +6.6x; memory is now ~45% of a Blackwell GPU's build cost (Epoch AI).
  **The decisive evidence: Google bifurcated its accelerator line at Cloud Next on 2026-04-22 into
  TPU 8t (training) and TPU 8i (inference)** — Pichai: *"For the first time, we've taken a dual chip
  approach… **Two chips for the agentic era.**"* The spec inversion is the proof: **the INFERENCE
  chip has MORE HBM (288GB vs 216GB) and MORE bandwidth (8.60 vs 6.52 TB/s) but FEWER peak FLOPs
  than the training chip**, plus 384MB of on-chip SRAM (3x prior gen) so that *"KV caches for
  long-context reasoning can sit on silicon rather than spilling to host memory,"* and it abandons
  the 3D torus for a topology cutting network diameter 16→7 hops. For agentic decode, **memory and
  network diameter beat raw throughput.** [raw/B3/23 — *flag: the 8.60 TB/s figure and the MediaTek
  design attribution appear only in secondary sources; verify against Google Cloud's spec page
  before making load-bearing.*]
- **How big is the agentic multiplier?** Three independent sources converge on a band and I would
  not narrow it further: Deloitte TMT Predictions 2026 — *"long thinking uses more than **100 times**
  the compute of a simple inference"*; NVIDIA management, Q2 FY2027 call, 2026-08-26 — *"the amount
  of compute necessary for an agent versus a human using it is probably **15 to 100 times**"*;
  Crusoe/NVIDIA, 2026-07-23 — *"agents can use **10 to 100x** more tokens per task than a standard
  chat exchange."* Stanford's ~1,000x for agentic *coding* is the high end. **Call it 10-100x, and
  note the OpenAI run sits far above even that.** [raw/B3/21, 22]
- **The mix has already tipped.** Deloitte TMT Predictions 2026 (published Nov 2025, forward-looking
  — flagged as such): inference is *"roughly **two-thirds of all compute** [in 2026], up from a
  third in 2023 and half in 2025,"* and *"post-training in aggregate uses **30 times** the compute
  needed to train the original model."* NVIDIA's Kress, Q1 FY26: *"The AI workloads have
  transitioned strongly to inference."* [raw/B3/21]
- **Supply is the binding constraint, unanimously, and it is reflexive.** C.C. Wei, TSMC, 2026-07-16:
  *"**our packaging capacity is so tight that now it's limiting my customers' growth**."* Kwak
  Noh-jung, SK Hynix CEO, Reuters 2026-07-10: *"**We forecast that next year will be the worst year
  in the industry's history from the supply perspective.**"* NVIDIA's Kress, 2026-08-26: *"we are
  experiencing **extreme pricing conditions in memory**… headed even higher into next year,"* with
  gross margin guided down from 74% to a **71-72% trough**, and the reflexivity line: *"**Memory
  scarcity today is being driven in large part by the AI build-out itself.**"* [raw/B3/24]
  *** One-sidedness flag: my researcher found **no credible 2026-dated oversupply argument
  anywhere.** An evidence base with no bear case is a warning about the evidence base, not a
  confirmation of the thesis. ***
  Microsoft CFO Amy Hood, 2026-07-29: *"**Roughly 2/3 of our CapEx was for short-lived assets,
  primarily CPUs and GPUs**"* — a mix shift toward serving silicon [raw/B3/20]. Alphabet's Sundar
  Pichai, 2026-07-22: *"**our core serving for our core products across consumers and enterprises is
  where the compute is primarily going**"* [raw/B3/20]. That is the training→inference shift stated
  by the buyers.

**Timing:** PJM auction results and quarterly capex guides are the observable triggers; both print
on a quarterly cadence.

**Counter-thesis:** Power is the most crowded "non-obvious" trade of 2026 and fails the *saturated*
test in `docs/Vectors.md` §6. Capacity prices that rose 11x can mean-revert; PJM disputes the market
monitor's data-centre attribution; and the federal cap is itself evidence of political willingness
to intervene in exactly this price. Further, `docs/Vectors.md` §4 bars pure commodity-direction calls
and §1 bars direct commodity exposure — a "watts go up" pitch is close to that line.

**Long-only expression:** see B3-8. Mostly **(d) unpitchable** for us.
**Severity: supporting** (it is risk-framing and idea-sourcing, not a thesis).
**Evidence:** `raw/B3_compute/40, 20`.

---

## B3-8 — Long-only inversion, run honestly against `docs/Vectors.md`

Metaprompt dimension 10 requires every named security to be checked against the do-not-analyze list
before more time goes into it. Run:

| Candidate | Vectors.md tier | Verdict |
|---|---|---|
| NVDA, MSFT, AMZN, GOOGL, META, Mag-7 | **HARD** — §4 "Consensus mega-cap AI longs… no variant view, and Dinan says the edge is judgment, not information. Dalton already owns NVDA" | **Stop. Unpitchable.** Not researched further. |
| Micron, TSMC | **SOFT** — §5, held by the Dalton/Rosenwald student fund | Avoid absent a genuinely new angle. Also "a trade, not a holding" on the merits (B3-7). |
| Oracle, CoreWeave / neocloud tier | §4-adjacent; and B3-7's bandwidth case is precisely the neocloud risk — debt collateralised by a depreciating asset | **Avoid.** This is the Global Crossing seat. |
| Pure-play power / IPPs | §4 bars pure commodity-direction calls; §5 names **NRG** (Luxor) and Dinan's energy scar tissue; §6 *saturated* | **Avoid** as a direction call. |
| Arista, networking | Not listed. Genuine merits: 62-64% gross margins on software moats and switching costs; guidance raised to $12.6B; CEO says the component problem runs "till 2028" | **Open, but not mine** — it is a compute-infrastructure idea, and it still has to clear §6 *saturated*. Hand to whoever owns infrastructure. |
| **Simulation/CAE incumbents wrongly sold as "AI killed CFD"** | Not listed. **Synopsys/Ansys, Cadence, Dassault Systèmes** | **The one live long-only expression from my track: (b) wrongly-punished long — but DOWNGRADED after self-correction.** The *defensive* half holds strongly: CIMdata +8.5-8.8% and Ansys pure-play +8-13%/yr straight through the surrogate wave say "AI killed CFD" is simply wrong. The *offensive* half fails: Ansys's own SKU charges **the same licence on one GPU as on a cloud cluster**, so cheaper compute does **not** expand vendor revenue. **Pitch it as stability mispriced as decline, never as Jevons upside.** Track A1's to own; needs a valuation and catalyst I have not done; **Dassault is EUR-denominated, so `docs/Competition_rules.md` requires the FX risk addressed explicitly.** Near-term trigger: **Synopsys Investor Day, 2026-09-30.** |

**And note where the freed value demonstrably went.** Synopsys, on its own call, said it out loud:
*"Synopsys captures the value uplift from these speed improvements, **while the hardware requirement
benefits partners like NVIDIA**."* The vendor names the beneficiary — and `docs/Vectors.md` §4 marks
that name **Hard avoid**, no variant view, Dalton already owns it. **The single best-evidenced
beneficiary in my entire track is the one security this project is forbidden to pitch.** That is
not a failure of research; it is the research result.

**My honest output, per the constraint I was given:** if the conclusion is that compute demand
rises, the useful answer is either a non-obvious beneficiary further down the stack **or an honest
statement that the obvious beneficiaries are unpitchable.** It is the latter. **Every layer where
the Jevons windfall is largest — accelerators, hyperscale cloud, memory, power — is either a hard
avoid under §4, a soft avoid under §5, or saturated under §6.** I am not going to manufacture a
fifth-derivative name to get around that. The idea that survives from B3 is not a compute long at
all; it is B3-5's *wrongly-punished simulation incumbent*, handed to Track A1 with the evidence attached.

---

## B3-9 — Self-audit: holding my own work to the HCLTech standard

Track B1 surfaced the right disciplinary test and I am applying it to myself. On an HCLTech call, an
**Axis Capital** analyst put it to management [`raw/B1_services/Management_quotes_AI_deflation.md`]:

> *"you talked about 3% to 5% deflation — that's kind of what we see anyway even before AI. In
> renewal deals, we were seeing 10% to 15% in pricing over the life of the deal… So **it doesn't
> look like with AI, there is anything significantly different**, right?"*

Nobody on that call produced a number separating the two. **Here is the same question asked of my
own findings, honestly.**

| My claim | Does it predate the AI story? | Honest verdict |
|---|---|---|
| CAE/simulation spend keeps growing | **YES.** CIMdata: +8.8% (2024), +8.5% (2025). Ansys pure-play: +10.9/+13.4/+8.3/+9.9/+12.1% FY2020-24. EDA: unbroken growth since 1996 | **The growth is the pre-existing trend continuing. It is NOT evidence that AI or cheap compute caused it.** The correct use of this series is *defensive* — it refutes "simulation is being disrupted" — **not** offensive. I have rewritten B3-5 accordingly. |
| EDA total spend rose 7.85x as unit costs collapsed | **YES, and worse: the ratio was pinned.** EDA held ~2% of semiconductor revenue for 25+ years | **The denominator drove it, not the price of the tool.** Corrected in place in B3-5. |
| Token spend is exploding as prices fall | **NO — this one is genuinely new.** Reasoning models went from negligible to >50% of tokens; Google's token volume is 330x in 24 months; agentic tasks are 10-100x chat | **Survives.** This is the one place where the 2026 data is not a continuation of anything. |
| Hyperscaler capex is rising | Partly. The buildout predates agentic inference | Survives on the *mix shift* (Hood: "2/3 for short-lived assets"; Pichai: "core serving… is where the compute is primarily going"), not on the level. |

**Three further audits of my own method, stated rather than hidden:**
1. **My cost arithmetic is the number most likely to be challenged in this project.** Every step is
   in `raw/B3_compute/07_B3_cost_derivation.md`, including a falsification list. The places the
   primary sources are **silent** and I assumed: input-token count, cache-hit rate, batch-vs-
   interactive tier, rack-level throughput, GPU useful life, and electricity price. **The 400,000
   GB200 GPU-hour figure is Duraisamy's, not OpenAI's** — OpenAI disclosed tokens and agents, never
   GPU-hours. My own bottom-up gave ~260K; I report both and the 1.5x gap.
2. **The agent-count discrepancy affects my per-result cost by 10x and I did not paper over it.**
   OpenAI's blog says "nearly 100 agents" for Euler; Bubeck told *Science* and *Nature* **1,000**.
   That is the difference between **~$45K and ~$455K** per frontier result. **Both are reported in
   B3-1; neither is chosen.** Note also that OpenAI **silently edited the announcement page on
   2026-09-10** — every citation to it is date-stamped "accessed 2026-09-19."
3. **My elasticity evidence is one-sided testimony.** Nearly every "more simulations get run" quote
   comes from a company selling simulation. My researcher searched specifically for a buyer-side
   statement in *either* direction and found neither a "we cut our simulation budget" nor a "we
   raised it." **That is a gap in the evidence base, not a confirmation.** Likewise, no credible
   2026-dated *oversupply* argument exists anywhere in the semiconductor evidence — an evidence base
   with no bear case is a warning about the evidence base.

---

## Findings that contradict other tracks

**Blunt, as instructed. If the rest of this project is hunting for who gets hurt, here is where my
evidence says you will be wrong.**

0. **THE HURDLE. Any track claiming simulation is being disrupted must first beat the CIMdata
   number.** S&A software: **$10.0bn (2023) → $10.9bn (+8.8%) → $11.67bn (+8.5%, 2025)**, straight
   through the neural-operator and surrogate wave, no inflection [`raw/A1_software/08`]. Ansys as a
   pure-play grew **+10.9/+13.4/+8.3/+9.9/+12.1%** across FY2020-24 [raw/B3/36]. Industry CAE was
   **+15.5% YoY in Q1 2026** [raw/B3/10]. **If your finding requires simulation demand to be
   collapsing, produce the number that shows it. Nobody in this project has.**

1. **"Cheaper simulation shrinks the CAE vendors' revenue" is contradicted by the live income
   statements.** Synopsys's **largest Ansys deal of Q3 FY2026 was GPU-accelerated CFD** — the
   cheaper-per-run product produced the *biggest* deal [raw/B3/31]. Ghazi: *"In CFD, we are seeing
   40, 50, 60x speed up"*; *"the consumption of these assets is exponential"*; *"the need is for
   more licenses."* Cadence's CFO: *"There's more iterations, there's more compute."* **If a track
   concludes Ansys or Cadence is harmed, it must first rebut these quotes.**

1b. **BUT I ALSO CONTRADICT MY OWN SIDE, AND THIS CUTS AGAINST TRACK A1.** A1 concludes vendors are
   *capturing* the speed-up. **Ansys's own price list says they are giving it away.** "Running on
   2,000 cores instead of 20 cores incurs a cost premium of only **1.5X — and not the 100X!**"; and
   **CFD HPC Ultimate charges "the same license cost whether running on one GPU or a large cloud
   cluster"** [raw/B3/37]. Ghazi's *"we capture the entire value and uplift of the GPU"* and that
   price list **cannot both be fully true.** Anyone building a long on vendor value-capture must
   reconcile them, and a third-party transcript quote does not outrank a published SKU.

2. **"AI agents displace the licensed tool" inverts the actual mechanism.** Devgan, on the record:
   the agent *"will call the base tools and they become a lot more licenses or usage will happen on
   our base tool"* [raw/B3/13]. The agent is a **caller** of the paid engine, not a substitute for
   it. Automating the human step *increases* billed tool invocations. Any displacement finding that
   assumes the opposite is backwards.

3. **The event was a compute SINK, not a compute saving.** ~400,000 GB200 GPU-hours, ~130B output
   tokens, no code, no benchmark, no speedup, FLOPs *"much larger than any scientific computation
   ever"* (Duraisamy). **Any "this makes engineering cheaper" framing has the sign wrong.**

4. **"$40M proves only mega-labs can do this" is a misread of a number that was never derived.**
   $40M is the HIGH-input scenario applied to **all six Millennium problems plus warm-ups**, not to
   this proof. The proof is ~$6-10M retail / ~$1M internal, and **the Euler result — arguably the
   better science — cost ~$45K-$455K retail** [raw/B3/07]. Any track resting on "prohibitively
   expensive, therefore rare" is resting on a factor-of-100 error.

5. **Do not let a "global CFD market size" number into the deck.** Commercial estimates of the 2025
   NGS market span **2.5x** ($10.44B to $25.7B) across five houses [raw/B3/15]. The same firms
   produce the CFD numbers. Use vendor disclosures or ESD Alliance/SEMI primary data, or use nothing.

6. **Counter-warning against my own side — the one place B3 *supports* a harm finding.** The
   verifier boundary (B3-3) cuts both ways. **Numerical-methods R&D *is* RL-verifiable**, and
   McGreivy expects LLM-invented state-of-the-art numerical methods "in the next year or two." If a
   moat rests on *proprietary solver algorithms* rather than on validated test corpora, regulatory
   qualification, or customer trust, that moat is genuinely exposed — **but in 2027-2028, which is
   outside a one-year holding period.** Do not pitch it as a 2026 catalyst.

7. **Illumina is the disconfirming case my own track must own** (B3-6). Four straight years of
   flat-to-down revenue while unit costs fell. **If engineering simulation budgets turn out to be
   appropriation-shaped rather than price-shaped, cheaper CFD means fewer dollars, not more runs.**
   Anyone building on my Jevons conclusion inherits this risk.

8. **The ceiling has been named by a vendor SVP, and every track should stop citing "more
   simulations" as if it were settled.** Jean-Claude Ercolanelli, SVP Simulation & Test, **Siemens
   Digital Industries Software**: *"**simulation technology in its current state has matured and hit
   a scalability ceiling** … **human expertise is becoming a scarce commodity. Accessibility to
   experts able to operate complex simulation software is the bottleneck.**"* And Siemens' own blog:
   *"**Simulation is no longer the bottleneck — your organization might be.**"* [raw/B3/38].
   **If the binding constraint is engineer attention rather than FLOPs, cheaper simulation floods a
   fixed-width channel and total spend is capped by headcount.** Cadence's rebuttal — *"it increases
   workload faster than headcount grows"* — is a claim, not evidence.

9. **A rival voted with its balance sheet, and nobody in this project has explained it.** **Hexagon
   sold MSC Software to Cadence** (announced 2025-09-04, closed 2026-02-23, $2.9B) to *"sharpen
   future investment behind core business areas"* [raw/B3/35]. A diversified industrial owner
   **exited simulation during the boom.** Any bullish simulation finding owes an answer to that.

10. **Do not cite the Gartner "55% of AI IaaS spend to inference" figure, the "$725B combined 2026
    capex" figure, or any "global CFD market size."** My researchers traced the first two to content
    farms and could not reach an original; CFD market estimates for 2025 span $2.52-2.90B while
    **Ansys alone booked $2.54B in FY2024**, which is arithmetically impossible. Flagged in
    raw/B3_compute/21, 39.

---

## Plain-language close

A judge who is not an engineer should take away four things.

**What is solid.** OpenAI really did buy a correct, machine-checked piece of frontier mathematics
with money and electricity. I can tell you what it cost, two different ways, and the two ways agree:
roughly **$1 million of actual hardware and power**, or **$6-10 million if you had to buy it at
OpenAI's own list prices**. The "$40 million" number in the press is real arithmetic applied to the
wrong thing — it is everything OpenAI attempted across six problems, not this proof. And the number
that should have made the headlines is the small one: a second open problem, in the Euler equations,
was resolved by a hundred-odd agents in fifty hours for something on the order of **fifty thousand
dollars**.

**What that means.** This is not a stunt. At five figures per attempt, "point a swarm of agents at
an unsolved problem" is cheaper than a postdoc, and the cost of a fixed capability has been falling
roughly ten-fold a year for four years. But it is a regime with a hard fence around it. The method
works by launching ten thousand guesses and letting a machine tell you which one is right. Where
that machine exists — formal proofs, software tests, chip-design sign-off — the economics are
already extraordinary. Where it doesn't — most engineering, most medicine, most ordinary work —
you cannot run the play at all, because nothing tells you which of your ten thousand answers is correct.

**What is speculative.** That this reaches production engineering. Today it does not: the theorem
itself changes nothing about how anyone designs an aircraft or runs a simulation, and the people who
sell CFD cycles for a living say so in plain English. The credible forward claim is narrower — that
AI will start inventing better numerical algorithms, because speed and accuracy are things a
computer can check. The person making that forecast puts it at one to two years away. That is 2028,
not next quarter.

**The thing I got half wrong, and fixed.** I started out expecting to show that cheap simulation
means more money spent on simulation software. Engineers do run far more simulations when compute
gets cheap — Volvo went from a 24-hour run to a 6.5-hour run and says it now explores more designs.
But the software companies **deliberately do not charge for that.** Ansys's own marketing boasts
that running on 2,000 processors instead of 20 costs only 1.5 times as much rather than 100 times,
and its newest CFD product charges the same licence fee whether you run it on one chip or a whole
cloud. So the saving flows to the customer and to whoever sells the hardware — not to the software
vendor. A senior Siemens executive says the real bottleneck stopped being computers years ago and is
now the shortage of engineers who can interpret the results. I have written that correction into the
findings rather than quietly dropping the claim.

**The single best idea — and why it isn't mine to pitch.** My work says total spending on
*computation* goes **up**, not down: unit prices are collapsing and volumes are rising faster, which
is visible in Google's own electricity bill and in enterprise AI invoices. The trouble is that
everyone who obviously benefits — the chip
makers, the cloud giants, the memory suppliers, the power companies — is on this project's
do-not-analyze list for good reasons, and I refuse to invent a fifth-derivative name to dodge that.
Indeed, the one company a vendor explicitly named as the beneficiary of faster
simulation is the exact company this project is barred from recommending. So my output is
deliberately two-sided: **the obvious beneficiaries are unpitchable, and the one idea that survives
is purely defensive** — if the market sells a simulation software incumbent on the story that "AI
solved physics, so who needs simulation," the evidence says that is backwards, because that market
grew 8.5% last year and 8.8% the year before while exactly that story was being told. **That is an
argument for stability being mispriced as decline. It is not an argument that these companies are
about to grow faster.** I have attached the evidence, marked the difference clearly, and handed it
to the track that owns it.

**And the warning I would give loudest.** Being right that demand explodes is not the same as being
right about a stock. Bandwidth prices fell from $1,200 per megabit to under a dollar, traffic
doubled every year exactly as forecast, and the companies that built the fibre went bankrupt anyway.
Cheap does not mean profitable, and correct does not mean paid.

---

*Prepared by Agent B3. Inference is marked as such throughout; the cost model in
`raw/B3_compute/07_B3_cost_derivation.md` states its assumptions, shows every step, and lists what
would falsify it.*
