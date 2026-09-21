# Track A1 — Simulation software

*Agent A1. Research completed 2026-09-19; revised 2026-09-19 after Agent 0's claim gate.
All claims dated. My own sources are in `raw/A1_software/`, cited **[A1-01] … [A1-09]**. Where I
rely on Agent 0's verified claim work I cite **`01_Claim.md` [0-n]**, using its numbering, rather
than re-asserting it; those sources live in `raw/00_claim/`. Every name below was run against
`docs/Vectors.md` before time was spent on it; filter results are stated per name in §7.*

---

## 0. Two events, one firewall — and what the claim gate settled

**Event 1 — the proof.** On 2026-09-08 OpenAI published a proof, machine-checked in Lean, that a
3D incompressible Navier–Stokes flow on ℝ³ starting **from rest** and driven by a **smooth,
compactly-supported external force** blows up in finite time — settling Fefferman alternatives
**(C) and (D)** and leaving unforced global regularity, **(A) and (B), completely open**
[0-1][0-2][0-4][A1-01]. Pure mathematics: no code, no benchmark, no speedup [0-2][0-6].

**Event 2 — the surrogates.** Separately and causally unrelated, ML surrogate models (neural
operators, FNO-style architectures, PINNs) and GPU-accelerated solvers have made some CFD
workloads 10–1000x cheaper per run.

### The gate result, and what it forecloses in this track

**Agent 0's claim verification (`01_Claim.md`, 27 citations) closes Event 1 as an exposure path,
and I adopt that finding rather than re-litigating it.** Agent 0 hunted for disconfirmation across
~15 named practitioners and found **zero** saying the theorem changes an industrial CFD workflow
[0-§8]. Accordingly:

> **No finding in Track A1 asserts that the proof damages CFD revenue. That path is closed.**
> §2 below records it as an evidenced *kill*, which is a result, not a thesis.

**What remains live for this track is Event 2 only:** does the ML-surrogate / AI-acceleration
trend threaten commercial CFD revenue, or are the vendors selling it? That is §3–§6, and it is
where the real work of this track now sits.

### The firewall, stated operationally

- **Proof-side files:** `raw/A1_software/01`, `02` — plus Agent 0's `raw/00_claim/`. Used only in
  §2.
- **Surrogate- and financial-side files:** `raw/A1_software/03`–`09`. **These cite no proof source
  and contain no proof-derived premise.** Every number in §1 and §3–§7 stands on filings, earnings
  calls and market data alone, and would read identically if the proof had never been announced.
  (Audited by grep: the only hits for proof vocabulary in `03`–`09` are (a) the firewall note at
  the top of `09`, (b) Cadence's **Millennium M2000** GPU appliance, an unrelated product name
  that coincides with "Millennium Prize", and (c) one use of "3-D Navier–Stokes" in `07` as the
  ordinary term of art distinguishing real CFD from Bentley's 1-D pipe hydraulics.)
- Neither side borrows the other's conclusions in either direction. That includes the *flattering*
  direction: I do **not** argue that the proof makes any vendor's verification moat more valuable.
  An earlier draft of §6 did exactly that; it has been rewritten to rest on surrogate evidence
  only.

Anyone pitching "AI solved Navier–Stokes, therefore CFD vendors are disrupted" has silently
substituted Event 2 for Event 1. That substitution is the single most likely-false claim in this
entire vector, so I lead with it.

---

## 1. ANSWER TO KEY QUESTION 1: is there any pure public CFD play left?

**No. Not one. The category no longer exists as an investable thing.**

Over an eighteen-month window, every independent CAE asset was absorbed into a diversified
EDA/PLM giant:

| Asset | Acquirer | Consideration | Status |
|---|---|---|---|
| **Ansys** (ANSS) | Synopsys | ~$34.9 bn | Closed FY2025 (Jul 2025). Delisted. [A1-04] |
| **Altair** (ALTR) | Siemens | $113.00/sh, ~$9.7 bn | **Closed 2025-03-26. Delisted.** [A1-06] |
| **MSC Software / Cradle CFD** (Hexagon D&E) | Cadence | ~€2.7 bn | Announced 2025-09-04, completed 2026. [A1-05][A1-07] |

What is left, and what fluids is worth inside it:

| Name | FY revenue | Fluids/CFD share of *that company* | Disclosure quality |
|---|---|---|---|
| **Synopsys** (SNPS) | FY2026 guide **$9.69–9.74 bn**; Ansys ~**$2.98 bn** (~31%) | **~6%** (inference) | Ansys is inside the *Design Automation* segment. No physics-level line. [A1-04] |
| **Cadence** (CDNS) | FY2025 **$5.297 bn**; SD&A 16% = **~$848 m** | **<3%** (inference) | SD&A also holds 3D-IC, PCB, thermal, EM. CFD never broken out. [A1-05] |
| **Siemens** (SIE GY) | FY2025 group **€78.9 bn**; DI **€17,788 m**; DI software ~**€6.3 bn** | **<1%** | Simcenter not disclosed. PLM vs EDA not even split. [A1-06] |
| **Dassault Systèmes** (DSY FP) | FY2025 **€6,239.6 m**; Industrial Innovation = 54% of software rev | **~1–2%** (inference) | SIMULIA bundled with CATIA + ENOVIA. Never separate. [A1-07] |
| **Hexagon** (HEXA B) | D&E was ~€265 m of 2024 revenue | **0% after divestment** | Sold the whole thing to Cadence. [A1-07] |
| Autodesk / PTC / Bentley | — | ~0 | Dismissed, §7. [A1-07] |

**The disclosure finding is as important as the revenue finding.** Ansys filed as **one reportable
segment** for its entire public life. Its 10-K names the portfolio — "Structures … Electronics …
**Fluids** … Semiconductors" — and attributes **no revenue to any of them**; revenue is
disaggregated only by contract type and geography [A1-03]. Siemens does not split PLM from EDA.
Dassault bundles SIMULIA inside a €-billions line with CATIA. Cadence stops at "System Design and
Analysis."

**Consequence: no vendor on earth publishes a CFD revenue number.** Under the metaprompt's rule
*"no revenue line, no finding,"* a fluids-software thesis is not merely weak — it is
**unconstructible from public disclosure**. You cannot size the thing you claim is at risk, you
cannot see it move when it moves, and you cannot defend a number to Jeff Meli because no number
exists. That alone should kill the sector as a thesis.

---

## 2. Finding A1-1 — The proof has no transmission path to any income statement

*Closed at the claim gate by Agent 0 (`01_Claim.md`). Recorded here as an evidenced kill; the live
question for this track is §3 onward.*

- **Exposure:** None. Zero dollars of disclosed revenue at any named public company.
- **Mechanism:** Trace the hops. (1) A forced-Navier–Stokes blowup theorem is established
  → (2) …nothing. There is no hop 2. Commercial CFD revenue is priced against *discretisation*,
  *turbulence closure*, *meshing*, *solver robustness*, *validation corpora* and *support*, none
  of which reference the existence-and-smoothness question. No solver's numerics change if
  statement C is true; every production code already assumes solutions may be rough and uses
  regularisation, limiters and RANS/LES closures that are agnostic to the theorem [A1-01].
  CloudHPC states the same mechanism from inside the industry: "Finite volume solvers never relied
  on global regularity of the continuum model in the first place: **discretization, physical or
  numerical viscosity, and grid scale all bound the computed solution**" [0-17]. **Ansys's own
  10-K does not mention the regularity problem as a risk, a dependency, or a capability** [A1-03] —
  the load-bearing disclosure point, since a 10-K is where a dependency would have to appear. I cannot draw the path without "could" or "eventually." **Per metaprompt
  dimension 2: there is no path. Saying so is the finding.**
- **Magnitude:** $0. Not "small" — zero, with no disclosure to attach it to.
- **Timing:** Never, on any observable trigger. The OpenAI result is eleven days old at writing and
  its priority and verification are already contested by mathematicians; even a clean Clay award
  moves no vendor's income statement.
- **Counter-thesis (argued at full strength):** Three real ones. (i) Bryngelson (Georgia Tech) is
  right that deep results have "knock-on effects … even though it's unclear sometimes how those
  knock-on effects will happen" [0-18] — the *method* (~10,000 coordinating agents, Lean-verified
  output) is a genuine capability signal, and if agentic systems can close a 90-year-old problem
  they can plausibly attack turbulence closure, which *is* commercially load-bearing.
  (ii) McGreivy predicts advanced LLMs "will begin to invent state-of-the-art numerical methods"
  within a year or two, because accuracy, speed and convergence are computationally verifiable and
  therefore RL-able [0-20] — that would reach solver revenue.
  (iii) A proven blowup mechanism could in principle inform adaptive-refinement criteria near
  near-singular vortex structures. **Why the counter-thesis loses:** all three are about *the
  method* and *the future*, not *the result*. None has a product, a customer, a contract cycle or a
  price. Dimension 1 requires separating the result from the method from the press release, and
  the investable content here is entirely in the press release. Agent 0 reaches the identical
  conclusion and flags (i)/(ii) as claims requiring a **separate** evidence base [0-§8].
- **Long-only expression:** **(d) unpitchable — no long expression.**
- **Severity:** **thesis-grade, as a kill.** This is a negative result reported as a result.
- **Evidence:** `01_Claim.md` [0-2][0-4][0-12][0-15][0-17][0-18][0-19][0-20]; [A1-01], [A1-02],
  [A1-03].

### The practitioner evidence — Agent 0's, not re-litigated here
The metaprompt asks for the practitioner saying "this changes nothing for us." Agent 0 searched
for disconfirmation specifically and **found none across ~15 named practitioners** [0-§8]. The
four that bear directly on *commercial software* revenue:

- **Terence Tao** (UCLA), posted 2026-09-03, five days *before* the announcement: "the regularity
  problem is not important for its direct physical application. **Computational fluid dynamics is
  already a mature subject** … A theoretical guarantee of regularity, or conversely a pathological
  instance of blowup … **would not radically transform the way we would, for instance, model
  weather prediction or climate change.**" [0-15]
- **CloudHPC** (a commercial cloud-HPC vendor that sells CFD simulation hours, i.e. a party with
  every incentive to hype it), 2026-09-15: "**For engineering simulation, essentially nothing
  changes.** Finite volume solvers never relied on global regularity of the continuum model in the
  first place … it is a mathematical pathology, not a condition that arises around a heat exchanger
  at Reynolds number 10⁵." [0-17] — **this is the single most probative quote in the whole vector,
  because it is a vendor testifying against its own commercial interest.**
- **George Karniadakis** (Brown): in air the singularity appears at a vortex width of **~70
  nanometres — about the mean free path of an air molecule**, i.e. below the scale at which anyone
  ever trusted the continuum model [0-12].
- **Justin Beroz**, CEO of ReynKo, asked what the proof means for engineering: **"not much"**
  [0-18][A1-02]. **Florian Schäfer** (NYU): the equations "are only an approximation" with "a
  certain regime of validity" [0-18]. *Scientific American*'s own framing: the scenario is "so
  contrived it's almost certainly unlikely to have any direct relevance to any physical system in
  the real world" [0-18].

**Supporting, and weak by construction — vendor silence.** As of 2026-09-19, **no CFD software
vendor — Ansys/Synopsys, Siemens, Cadence, Altair, Dassault or Hexagon — has issued any public
comment on the result** [0-§Open-questions-8]. Repeated searches by Agent 0 and by me returned
nothing; my own review of Synopsys's Q3 FY2026 call (2026-08-26) and Cadence's Q2 2026 prepared
remarks (2026-07-27) found no mention, and the proof post-dates both. For an industry that
issues a press release when a solver gets a new mesher, silence about a Millennium Prize result in
its own governing equation is consistent with irrelevance. **Agent 0 correctly flags this as weak
evidence and warns that no exposure claim should rest on it; I use it only as corroboration of a
conclusion already established by the quotes above, never as a load-bearing step.**

> **Laundering warning — read before reusing any quote from this section.** The same Beroz, in the
> same interview, says a new aircraft takes a decade and ~$30bn and that "roughly half the time
> and half the cost is spent building, testing, or finding physical prototypes in the wind
> tunnel — and the only reason you're doing that is that the software sucks" [0-18]. **That figure
> does not belong in this finding and is deliberately not used here.** It is a claim about the
> present quality of CFD *software*, true with or without the theorem, from a man whose answer on
> the theorem itself was "not much." Any pitch that runs "the proof unlocks $15bn of wind-tunnel
> spend" is laundering an unrelated number through an unrelated result. Where the figure is used
> at all in this track it appears once, in §3, explicitly tagged as **surrogate-side, not
> proof-side**, and with the "not much" answer attached to it.

---

## 3. Finding A1-2 — ANSWER TO KEY QUESTION 2: the incumbents are *selling* the surrogate, at a premium

This is my **single strongest finding**, and it is the one that inverts the whole vector.

- **Exposure:** The claim under test is that ML surrogates compress Synopsys/Ansys, Siemens
  Simcenter, Cadence Fidelity and Dassault SIMULIA fluids revenue.
- **Mechanism (the disconfirming evidence):** Every incumbent ships a surrogate product,
  **attached to** rather than replacing the solver seat, trained on **the customer's own prior
  high-fidelity runs** — an asset only the incumbent solver can generate [A1-09]:
  - **Ansys SimAI** (launched 2024-01-09): surrogate trained on the customer's prior simulation
    data, "10-100X" faster; now two paid tiers, SimAI Premium and SimAI Pro.
  - **Siemens Simcenter PhysicsAI 2026.1**: geometric deep learning, "trains AI surrogate models on
    your historical simulation data … **up to 1000x faster** than traditional solver simulations" —
    and it ships **into STAR-CCM+**, i.e. it is an add-on to the CFD licence, not a substitute.
  - **Cadence**: Fidelity CFD on GPU "reduces simulation runtimes by 20X"; the Millennium M2000
    Blackwell appliance lists at **~$2 million** for a 32-GPU config. Cadence's stated Q1 FY2026
    SD&A plan is literally "improve solver performance through … GPU acceleration and **AI
    surrogate models**."
  - **Synopsys**, Q3 FY2026 call (2026-08-26), the crux: *"A major Q3 deal for GPU-accelerated CFD
    delivered **40x to 60x speedups** compared to traditional CPU-based simulation. **Synopsys
    captures the value uplift from these speed improvements**, while the hardware requirement
    benefits partners like NVIDIA."* [A1-04][A1-09]
  - Same call, on the disruption thesis directly: management *"dismissed the threat of 'AI-native'
    design bypassing EDA, stating that AI models require the '**ground truth physics**' provided by
    Synopsys tools for accuracy and determinism. Autonomous workflows are expected to be
    complementary, **driving exponential consumption of underlying software licenses**."* [A1-04]
  - Not one of the four names surrogate models as a competitive risk factor in a filing. Ansys's
    final 10-K treats AI/ML purely as a product capability [A1-03].
- **Magnitude:** The direction of the number is what matters. Cadence's **System Design & Analysis
  grew +13% to ~$848 m in FY2025** [A1-05]; Synopsys raised FY2026 guidance to $9.69–9.74 bn with
  Ansys at ~$2.98 bn and "another strong quarter" for Ansys [A1-04]. A price-compressed product
  line does not do this.
- **Timing:** Already reported, through Q3 FY2026 (Aug 2026) and Q2 2026 (Jul 2026).
- **Counter-thesis (argued at full strength):** A surrogate priced as an add-on today can become a
  substitute tomorrow — the moment a customer's trained surrogate is good enough for 80% of design
  iterations, the *number of full-fidelity solver-hours* falls, and if the vendor's meter is
  solver-hours the revenue falls with it. The 1000x claim is Siemens' own marketing and is measured
  on inference, excluding the expensive training runs. And there is a genuine long-run risk that
  an open foundation model for fluids, trained on public datasets, erodes the data moat. **Why it
  loses, for now:** (i) the meter is *not* solver-hours — it is seats, multi-year subscription
  ACV, elastic units and now agent/workflow subscriptions [A1-03][A1-04][A1-05]; (ii) surrogates
  interpolate within their training distribution and require full-fidelity runs to generate and
  periodically re-validate that distribution, so they *consume* solver licences; (iii) no vendor
  has disclosed pricing pressure, and all four are raising guidance.
- **Long-only expression:** **(b) a wrongly-punished long whose moat survives — conditional, and
  currently not triggered.** If the proof headline ever knocks SNPS or CDNS down on a
  "CFD is obsolete" narrative, the baby-with-the-bathwater trade is well-evidenced. As of
  2026-09-19 it has not happened: SNPS rallied ~26% in 30 days post-Q1 FY2026, CDNS holds record
  $8.1 bn backlog [A1-04][A1-05]. **There is no discount to buy.** Absent a dislocation it is
  **(d) unpitchable**, and separately these are consensus large-cap AI longs, which `Vectors.md`
  §4 flags (see §7).
- **Severity:** **thesis-grade.**
- **Evidence:** [A1-04], [A1-05], [A1-09], [A1-03].

### The size of the prize the surrogates are chasing — used once, and fenced
> **Fencing statement.** The paragraph below is **surrogate-side evidence only**. It is not a
> consequence of the September 2026 theorem, it does not cite any proof source, and it must never
> be carried into §2 or into any proof-driven argument. It is included because the metaprompt
> requires the counter-thesis and the beneficiary case to be argued at full strength, and this is
> the strongest available statement of *why* anyone would pay for faster CFD.

Justin Beroz, CEO of ReynKo, to *Scientific American*, 2026-09-18: a new airplane takes a decade
and roughly **$30bn**, and "roughly half the time and half the cost is spent building, testing, or
finding physical prototypes in the wind tunnel — and the only reason you're doing that is that the
software sucks" [0-18]. **The same man, asked what the proof changes for engineering, answered
"not much"** [0-18]. Both statements are his, and they are consistent: CFD software is not good
enough to displace the wind tunnel, and a theorem about forced blowup does nothing to change that.

Read correctly, this is a **bull argument for the incumbents, not a bear one.** If half of a $30bn
aircraft programme is physical testing that better software could absorb, the addressable prize
sits *above* today's ~$2.8–3.5bn CFD software market [A1-08] — and the firms positioned to charge
for closing that gap are precisely the ones that own the validated solvers, the turbulence-model
corpora and the certification traceability the aerospace customer needs to sign off on replacing a
wind-tunnel campaign. Synopsys already sells into that motion: it "supports more than 90% of the
top 100 automotive suppliers," showcased Audi reducing physical prototyping at CES in January
2026, and names aerospace at 22% of Ansys's end-market mix [A1-04]. **This is Track A2/B1
territory (who captures the downstream saving), and I flag it rather than pitch it.** It changes
nothing about §1: there is still no pure CFD security to own, and the incumbents that would
capture it are still consensus large-caps at no discount.

---

## 4. Finding A1-3 — ANSWER TO KEY QUESTION 3: Jevons is confirmed, with a market-level number

- **Exposure:** The claim that simulation spend is falling.
- **Mechanism / evidence:** CIMdata, the industry's standard tracker, sizes the **Simulation &
  Analysis software market at $10.0 bn (2023) → $10.9 bn (+8.8%, 2024) → $11.67 bn (+8.5%, 2025)**
  [A1-08]. That ~8.5%+ compounding runs *straight through* the neural-operator/PINN wave. At the
  company level, **Ansys ACV growth: FY2019 +12% cc, FY2020 +20% cc, FY2021 +16%, FY2022 +14% cc,
  FY2023 +13%, FY2024 +11.4%** — 2022–24 CAGR 12.3% actual / 13.0% constant-FX [A1-03]. There is
  no inflection anywhere in that series. Synopsys management's framing is explicitly
  Jevons: autonomous AI workflows *"driving **exponential consumption** of underlying software
  licenses to train and inference design models"* [A1-04].
- **Magnitude:** Per the metaprompt, "demand falls" is the claim requiring proof. It is not proved.
  It is **disproved at the market level** by three consecutive years of ~9% growth.
- **Timing:** Already in reported numbers, 2023–2025.
- **Counter-thesis:** The mix is degrading even if the total is not — cheap surrogate seats could
  be growing while expensive solver seats stagnate, and the aggregate would hide it. Siemens' DI
  **software business revenue fell 25% y/y in Q3 FY2025** (€1,540 m vs €2,067 m) [A1-06], which
  looks like exactly that. **Why it loses — now primary-sourced from the Siemens Q4 FY2025
  earnings-release segment table:** the very next quarter, **Q4 FY2025 software business revenue
  grew to €1,900 m, +14% actual / +8% comparable** (vs €1,668 m), on DI revenue of €5,030 m (+10%)
  and DI orders of €5,511 m (+30%) [A1-06]. Siemens attributes that Q4 software growth
  specifically to the **PLM software business** — the line that contains Simcenter. The Q3 fall was
  a large-contract comparison, compounded by Altair/Dotmatics drag (−€68 m to Q4 DI profit, −2.0
  pts of margin). Software ARR ended FY2025 at **€5.3 bn**, cloud ARR 49%, Q4 software orders an
  all-time high >€2.5 bn, and DI is guided to **+5% to +10%** comparable revenue growth in FY2026
  [A1-06]. Full-year DI revenue of €17,788 m was −4%, but **no Siemens disclosure links that to
  simulation demand, let alone to AI surrogates.**
- **Long-only expression:** **(c) a de-risking constraint** — this is the evidence that kills any
  "simulation software is shrinking" premise anywhere else in the project. Not a trade on its own.
- **Severity:** **thesis-grade, as a kill.**
- **Evidence:** [A1-08], [A1-03], [A1-04], [A1-06].

---

## 5. Finding A1-4 — ANSWER TO KEY QUESTION 4: the licensing model makes them beneficiaries

- **Exposure:** Whether pricing structure converts cheaper simulation into lower revenue.
- **Mechanism:** It does the opposite. The industry has already migrated off perpetual seats.
  - **Ansys/Synopsys**: fixed-term leases, annual subscriptions, and **"elastic units"** — explicit
    pre-purchased consumption credits for cloud/HPC runs [A1-03]. More runs = more units burned.
  - **Cadence**: "We primarily license our software using **time-based licenses** … generally two
    to three years"; product & maintenance 91% of FY2025 revenue [A1-05].
  - **Siemens**: software **ARR €5.3 bn**, cloud ARR **49% of total** and rising [A1-06].
  - **Dassault**: FY2025 recurring revenue +6%, **subscriptions +11%**, cloud +8% [A1-07].
  - **Synopsys forward**: actively designing "subscription for agents, subscription for workflows,
    and **consumption-based pricing**," with 30+ live customer engagements [A1-04].
  A consumption meter attached to a workload that a surrogate makes 100x cheaper *per run* is a
  beneficiary of that surrogate, provided run-count rises faster than price-per-run falls — which
  §4 shows it has.
- **Magnitude:** Cadence SD&A ~$848 m growing 13% FY2025 on a time-based-licence book with record
  $8.1 bn total backlog [A1-05]; Siemens software ARR €5.3 bn [A1-06]; Synopsys Ansys ~$2.98 bn
  FY2026 [A1-04].
- **Timing:** Structural, already in place; the agent/consumption SKUs land FY2027 (Synopsys guides
  Multiphysics Fusion to contribute "meaningfully" from FY2027) [A1-04].
- **Counter-thesis:** Consumption pricing cuts both ways — it is precisely the model that *falls*
  when unit consumption falls, and it strips the incumbent of the perpetual-seat floor. If
  surrogates eventually displace 90% of solver-hours, a consumption vendor loses faster than a
  seat vendor. **Why it loses today:** the books are still overwhelmingly multi-year committed
  subscription and ARR, not spot consumption, and the vendors' stated plan is to charge for the
  *agent* and the *workflow*, not only the CPU-hour.
- **Long-only expression:** **(c) de-risking constraint** on any adjacent thesis.
- **Severity:** **supporting.**
- **Evidence:** [A1-03], [A1-04], [A1-05], [A1-06], [A1-07].

---

## 6. Finding A1-5 — Moat inversion (dimension 5): surrogates make the validation corpus *more* valuable

> **Firewall note.** An earlier draft of this finding argued that the *proof* raised the value of
> the incumbents' verification moat. That was proof-side reasoning smuggled into a commercial
> argument — the same error as the bear case, in the flattering direction — and it is removed.
> **Nothing below cites or depends on the theorem.** The argument rests only on how surrogate
> models are built and sold.

- **Exposure:** The incumbents' proprietary asset under the surrogate regime.
- **Mechanism:** A surrogate is not a solver; it is a **regression over a solver's output**. Every
  shipping product says so in its own marketing: Siemens' Simcenter PhysicsAI "trains AI surrogate
  models on **your historical simulation data**"; Ansys SimAI has engineers "leverage their
  **previous simulation and measurement data** to train and build a surrogate AI model" [A1-09].
  Three consequences follow, none of which requires any mathematics beyond that sentence:
  1. **The training set is an incumbent-generated asset.** The data that makes a surrogate good is
     the customer's own history of licensed high-fidelity runs. A competitor with a better
     architecture and no corpus cannot replicate it, and the customer cannot take it anywhere.
  2. **Surrogates interpolate; they do not extrapolate safely.** Outside the training
     distribution the model has no error bound, so new geometries, new regimes and periodic
     re-validation all send work *back* to the full-fidelity solver. Synopsys states the
     dependency plainly: AI models *"require the 'ground truth physics' provided by Synopsys tools
     for accuracy and determinism"* and autonomous workflows drive *"exponential consumption of
     underlying software licenses"* [A1-04].
  3. **Sign-off is not a numerical problem.** What lets a regulated OEM certify a result is the
     validated turbulence-model corpus, the certification traceability, the support SLA and the
     vendor's absorption of liability — none of which a surrogate supplies and all of which the
     incumbent sells.
  The cleanest natural experiment is open source: **twenty years of free, mature, production-grade
  OpenFOAM and SU2 — used in production by BMW, BASF and Intel — never collapsed commercial CFD
  pricing**, and the simulation market compounded ~8.5%+ right through it [A1-08]. What the
  incumbents sell was never the solver.
- **Magnitude:** Not separately disclosed; it is the explanation for why §4's numbers behave as
  they do.
- **Timing:** Continuous.
- **Counter-thesis:** Verification value only accrues if regulators and OEM sign-off processes
  actually demand it. In unregulated design-exploration workflows — which is where most of the
  run-count growth is — nobody asks for traceability, and that is exactly the volume a cheap
  surrogate can take without the incumbent ever refereeing it. This is the strongest version of
  the bear case and it is not fully refuted; it is bounded by the fact that design exploration is
  low-ASP work that was historically *not done at all*, i.e. it is incremental, not cannibalistic.
- **Long-only expression:** **(b)**, conditional as in §3 — no discount available today.
- **Severity:** **supporting.**
- **Evidence:** [A1-04], [A1-08], [A1-09].

---

## 7. Filter compliance (dimension 10) and resolution of every name

| Name | `docs/Vectors.md` result | Resolution |
|---|---|---|
| **Ansys (ANSS)** | n/a — delisted | Not investable. Acquired by Synopsys, FY2025. **(d) unpitchable** |
| **Altair (ALTR)** | n/a — delisted | Not investable. Closed 2025-03-26, Nasdaq halted 2025-03-25. **(d) unpitchable** |
| **Synopsys (SNPS)** | **Soft** — §4 "consensus mega-cap AI longs" (no variant view; ~$9.7 bn FY26 revenue, EDA is the most crowded AI-adjacent software trade); §6 "saturated" | Moat survives; fluids ~6% of revenue; **no discount exists** (+26%/30d post-Q1 FY26). **(b) only if dislocated — today (d) unpitchable** |
| **Cadence (CDNS)** | **Soft** — same §4/§6 flags; record $8.1 bn backlog, +24% y/y Q2 2026 | CFD <3% of revenue and growing. **(b) only if dislocated — today (d) unpitchable** |
| **Siemens (SIE GY)** | Clean on Hard items. **Non-USD → `Vectors.md` §1 requires FX addressed** (EUR) | Fluids <1% of an €78.9 bn conglomerate (DI revenue €17,788 m FY2025; DI software ~€6.3 bn). Not a fluids expression at all. **(d) unpitchable on this vector** |
| **Dassault (DSY FP)** | Clean on Hard. Non-USD, FX must be addressed (EUR) | SIMULIA never disclosed; fluids ~1–2%. **(d) unpitchable on this vector** |
| **Hexagon (HEXA B)** | Clean on Hard. Non-USD (SEK/EUR) | **Sold the CAE business to Cadence for ~€2.7 bn on ~€265 m of revenue (~10x sales) at the top of the AI-simulation narrative.** Zero remaining fluids exposure. A separate capital-allocation story, not a Track-A1 finding. **(d) unpitchable here** |
| **Autodesk (ADSK)** | Clean | Autodesk CFD ~2% tool share; no simulation revenue line in a $6.13 bn FY2025 book. **Dismissed. (d)** |
| **PTC** | Clean | **Owns no CFD solver.** Creo Ansys Simulation / Creo Simulation Live are Ansys code licensed into Creo. PTC is an Ansys *channel*, so cheaper embedded simulation is a CAD-seat tailwind. **Dismissed. (d)** |
| **Bentley (BSY)** | Clean | OpenFlows is 1-D pipe-network hydraulics, not 3-D CFD. **Dismissed. (d)** |

**Note on the disclosure problem as a filter in itself:** even for the names that clear
`Vectors.md`, none of them permits a CFD revenue line to be cited. Any pitch on this vector would
have to defend a triangulated number in front of a judge who will ask where it came from, and the
honest answer is "a third-party market-research estimate cross-multiplied by an unaudited share
figure." That is not defensible.

---

## 8. Second-order and dual-use (dimension 8, bounded)

Two beneficiaries are visible and belong to other tracks, not mine. (i) **Compute** — Synopsys
explicitly notes that the GPU-accelerated CFD deal's "hardware requirement benefits partners like
NVIDIA" [A1-04], and Cadence has productised that as a $2 m appliance [A1-05]; this is Track B3's
question, not A1's, and NVIDIA is a `Vectors.md` §4 Hard-flagged consensus mega-cap. (ii)
**Downstream cost capture** — the OEMs that stop building wind-tunnel prototypes keep the savings
(see the fenced §3 block, and note that this is **surrogate-driven, not proof-driven**); that is
Tracks A2/B1. Agent 0 independently surfaces the one adjacent mechanism with a real revenue path,
and it points the same way: agentic engineering workflows "consume far more compute than an
equivalent human-driven workflow ever would. **The underlying solvers are not being replaced** —
but the demand for the compute that runs them is growing" [0-17]. Risk rather than revenue:
faster, cheaper, more credible fluids simulation proliferates into weapons and hypersonics design
and raises the verification burden on safety-critical certification. Bounded here; it informs risk,
it is not a thesis.

---

## 9. Plain-language close

**What is solid.** The simulation-software industry has been bought up. Ansys is inside Synopsys,
Altair is inside Siemens, and MSC Software is inside Cadence — three deals closed between March
2025 and 2026. There is no longer a listed company whose fortunes rise and fall with fluid
simulation. In the survivors, fluids is roughly 6% of revenue at Synopsys, under 3% at Cadence,
under 1% at Siemens. And none of them will tell you the real figure, because not one has ever
published a fluids revenue line — Ansys reported as a single segment for its whole public life.

**Also solid: the two stories have been spliced together and should not be.** The OpenAI proof is
a statement about mathematics — that a fluid pushed by a carefully designed force can, in theory,
reach infinite speed in finite time. It says nothing about how anyone computes anything. Our claim
agent searched hard for someone in industry who disagreed and found nobody: Terence Tao said the
regularity problem "is not important for its direct physical application" five days before the
announcement; a cloud-HPC company that sells CFD compute by the hour, and had every reason to hype
it, wrote "for engineering simulation, essentially nothing changes"; and the blow-up happens at a
scale of about 70 nanometres in air, smaller than the distance an air molecule travels between
collisions. Not one CFD vendor has said anything about it at all. Meanwhile the genuinely disruptive
thing — AI models that approximate simulation 100 to 1000 times faster — is real, is happening, and
is being **sold by the incumbents themselves**: Ansys SimAI, Siemens Simcenter PhysicsAI, Cadence's
$2 m Millennium supercomputer. Synopsys told investors in August 2026 that it had just closed a
CFD deal delivering 40–60x speed-ups and that **it captures the value of the speed-up**. The total
simulation market grew 8.8% in 2024 and 8.5% in 2025 while all of this was happening. Cheaper
simulation is producing more simulation, and the vendors bill by subscription and consumption
credits, so more simulation means more revenue.

**What is speculative.** That surrogates eventually become good enough to replace, rather than
front-run, the full-fidelity solver — and that the vendors' data-and-validation moat erodes with
it. That is a real risk, on a horizon far longer than a one-year holding period, with no observable
trigger today.

**The single best idea from this track: there isn't one.** The honest output is a kill. No pure
CFD exposure exists to be long or to be hurt; the incumbents are beneficiaries, not victims; and
the only long-only expression available — buying Synopsys or Cadence as "wrongly punished" — fails
because **they have not been punished**. Synopsys rose ~26% in thirty days after its Q1 FY2026
print; Cadence carries a record $8.1 billion backlog and grew 24% year over year. There is no
discount, no dislocation, and no variant view — and both names are flagged as consensus AI
large-caps under our own filter. **Track A1 resolves to (d) unpitchable.** Its value to the
project is as a constraint: it forecloses the obvious thesis, and it supplies the evidence that
any other track claiming "simulation is being disrupted" must overcome.

---

## Sources — Track A1

**Upstream dependency.** Findings in §2 rely on Agent 0's claim verification,
`navier_stokes/01_Claim.md` (27 citations, sources in `navier_stokes/raw/00_claim/`), cited above
as **[0-n]** using that document's own numbering. Chiefly: [0-2] OpenAI's Navier–Stokes paper
(Theorem 1.1 verbatim), [0-4] Fefferman's official Clay statement (alternatives A–D), [0-12]
*Nature* / Karniadakis' ~70 nm figure, [0-15] Tao's Mathstodon thread of 2026-09-03, [0-17]
CloudHPC, [0-18] *Scientific American* (Beroz, Schäfer, Bryngelson), [0-19] the r/CFD practitioner
thread, [0-20] McGreivy. **I do not restate Agent 0's sources in my own `raw/` directory**, to
avoid double-counting a single evidence base as two.

**My own sources**, full text stored in `navier_stokes/raw/A1_software/`, all accessed 2026-09-19.
Files `03`–`09` are the surrogate/financial evidence base and cite no proof source, per §0.

1. [A1-01] `01_openai_navier_stokes_primary.md` — OpenAI, "On the Navier–Stokes Millennium Prize Problem," 2026-09-08. https://openai.com/index/navier-stokes-solution/ · paper: https://cdn.openai.com/pdf/32d9f210-8b73-45e0-91bc-82a30aef8a9a/navier-stokes.pdf · Lean: https://github.com/openai/NavierStokesAndEuler
2. [A1-02] `02_scientificamerican_practitioner_reaction.md` — Scientific American, "What does OpenAI's blockbuster mathematics Navier-Stokes proof mean for the real world?" https://www.scientificamerican.com/article/what-does-openais-blockbuster-mathematics-navier-stokes-proof-mean-for-the-real-world/ ; Quanta, 2026-09-08, https://www.quantamagazine.org/ai-has-solved-one-of-maths-1-million-millennium-prize-problems-20260908/
3. [A1-03] `03_ansys_10k_fy2024.md` — ANSYS Inc. Form 10-K FY2024, filed 2025-02-19. https://www.sec.gov/Archives/edgar/data/1013462/000101346225000009/anss-20241231.htm ; ACV history from https://investors.ansys.com/news-releases
4. [A1-04] `04_synopsys_ansys_fy2026.md` — Synopsys Q4 FY2025 (2025-12-10) https://news.synopsys.com/2025-12-10-Synopsys-Posts-Financial-Results-for-Fourth-Quarter-and-Fiscal-Year-2025 ; Q3 FY2026 (2026-08-26) https://news.synopsys.com/2026-08-26-Synopsys-Posts-Financial-Results-for-Third-Quarter-Fiscal-Year-2026 ; Q3 FY2026 call summary https://finance.yahoo.com/markets/stocks/articles/synopsys-inc-q3-2026-earnings-123000142.html ; Q2 FY2026 prepared remarks https://s201.q4cdn.com/778493406/files/doc_earnings/2026/q2/transcript/SNPS_Q226_Prepared_Remarks.pdf
5. [A1-05] `05_cadence_sda_and_hexagon.md` — Cadence 10-K FY2025 https://www.sec.gov/Archives/edgar/data/813672/000081367226000016/cdns-20251231.htm ; Q4/FY2025 results https://investor.cadence.com/news/news-details/2026/Cadence-Reports-Fourth-Quarter-and-Fiscal-Year-2025-Financial-Results/default.aspx ; Q2 2026 prepared remarks https://s206.q4cdn.com/597110084/files/doc_financials/2026/q2/CDNS-Q2-2026-Earnings-Conference-Call-Prepared-Remarks.pdf ; Hexagon D&E deal https://www.cadence.com/en_US/home/company/newsroom/press-releases/pr/2025/cadence-to-acquire-hexagons-design--engineering-business.html ; Millennium M2000 https://www.cadence.com/en_US/home/company/newsroom/press-releases/pr/2025/cadence-unveils-millennium-m2000-supercomputer-with-nvidia.html
6. [A1-06] `06_siemens_di_software.md` — Siemens Report fiscal 2025 https://www.siemens.com/siemensreport ; Q3 FY2025 earnings release https://assets.new.siemens.com/siemens/assets/api/uuid:4ca2342b-681a-4593-b631-df3c486cbb61/2025-q3-earnings-release-en.pdf ; Q4 FY2025 Earnings Release PDF (segment tables; primary source for DI FY2025 revenue €17,788 m and Q4 software business €1,900 m) https://assets.new.siemens.com/siemens/assets/api/uuid:7fdd21fb-c248-43a3-b475-f2e618fbae88/2025-q4-earnings-release-en.pdf ; Q4 FY2025 press release https://press.siemens.com/global/en/pressrelease/earnings-release-and-financial-results-q4-fy-2025 ; Altair closing https://news.siemens.com/en-us/siemens-altair-engineering-closing/ ; Nasdaq corporate action ECA2025-148 https://www.nasdaqtrader.com/TraderNews.aspx?id=ECA2025-148
7. [A1-07] `07_dassault_hexagon_peripherals.md` — Dassault Q4/FY2025 https://investor.3ds.com/news-releases/news-release-details/dassault-systemes-q4-revenue-growth-1-solid-operating-margin-and ; Dassault Q1 2026 https://investor.3ds.com/news-releases/news-release-details/dassault-systemes-reports-first-quarter-2026-results-line ; Hexagon Year-End Report 2025 https://hexagon.com/company/newsroom/press-releases/2026/hexagon-year-end-report-1-january---31-december-2025 ; Autodesk FY2025 https://adsknews.autodesk.com/en/pressrelease/autodesk-inc-announces-fiscal-2025-fourth-quarter-and-full-year-results ; PTC/Ansys https://www.ptc.com/en/products/creo/ansys-simulation
8. [A1-08] `08_market_sizing_and_opensource.md` — CIMdata S&A market reports (2024: https://www.cimdata.com/de/news/item/28195-cimdata-publishes-simulation-and-analysis-market-report ; 2025: https://www.cimdata.com/en/news/item/30365-cimdata-publishes-simulation-and-analysis-market-report) ; IMARC CFD market https://www.imarcgroup.com/computational-fluid-dynamics-market ; Future Market Insights CFD shares https://www.futuremarketinsights.com/reports/computational-fluid-dynamics-market ; OpenFOAM https://www.openfoam.com/ ; SU2 https://su2code.github.io/
9. [A1-09] `09_vendor_ai_surrogate_products.md` — Ansys SimAI launch https://ansys.synopsys.com/news-center/press-releases/1-9-24-ansys-launches-simai ; SimAI product page https://ansys.synopsys.com/products/ai/simai ; Simcenter PhysicsAI 2026.1 https://blogs.sw.siemens.com/simcenter/whats-new-in-simcenter-physicsai-2026-1 ; Siemens "From 'delve' to neural operators: how AI is reshaping our CFD" https://blogs.sw.siemens.com/simcenter/ai-accelerated-cfd ; Cadence Millennium https://www.cadence.com/en_US/home/tools/millennium.html

*End of Track A1 section.*
