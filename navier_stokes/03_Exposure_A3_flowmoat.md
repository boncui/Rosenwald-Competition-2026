# Track A3 — Flow-data moats & dual-use

**Agent:** A3 · **Date of work:** 2026-09-19 · **Raw sources:** `navier_stokes/raw/A3_flowmoat/`

---

## 0. The breakthrough, in one line, and the separation I am obliged to keep

On 8 September 2026 OpenAI published a Lean-formalized construction of a finite-time singularity
for the **forced** 3D incompressible Navier–Stokes equations: a velocity field `u` is built to be
singular while the derivative terms cancel so that `D[u]` stays smooth, and the forcing is then
*defined* as `f = D[u]` [1][2][3]. It is a pure-mathematics existence result about a
reverse-engineered forcing term. **It is not a solver, not a faster solver, and not a surrogate.**

Track 00's claim gate (`navier_stokes/01_Claim.md`, 27 citations) closed this and I adopt its
verdict rather than re-deriving it: ~15 named practitioners, zero disconfirmation. Terence Tao,
five days *before* the announcement: "Computational fluid dynamics is already a mature subject."
CloudHPC, a commercial CFD/HPC vendor with every incentive to hype it: "For engineering
simulation, essentially nothing changes. Finite volume solvers never relied on global regularity
of the continuum model in the first place." And the number that settles it, from George
Karniadakis (Brown): in air, the singularity appears at a **vortex width of ~70 nanometres,
roughly the mean free path of an air molecule** — below the scale at which the continuum
assumption behind Navier–Stokes holds at all. The blowup lives in a regime no turbine or airframe
engineer has ever modelled.

**Accordingly, this file contains no finding in which the proof damages a flow-data moat.**

Separately and independently, ML surrogate models (Ansys SimAI, Siemens Simcenter PhysicsAI) are
making design-space exploration much cheaper [4][5]. My question — does cheap simulation destroy
or strengthen a proprietary flow-data moat — is **entirely a question about the second thing**.

**Explicit guardrail.** Justin Beroz's figure — a new airplane takes a decade and ~$30bn, half of
it physical prototyping, "only because the software sucks" [26] — is quoted twice below. It belongs
**only** to the surrogate-solver argument and must never migrate into a proof-driven thesis: the
same Beroz, asked what the proof means for engineering, said **"not much"** [26]. And as Finding
A3-1 shows, the figure cuts *against* the surrogate argument anyway, because certification mandates
the test cell regardless of how good the software gets.

**The gate result strengthens rather than weakens this track.** If the mathematics was never what
engineers relied on, then what they *do* rely on is exactly the asset I was sent to investigate:
discretisation, turbulence models tuned against wind-tunnel data, and answers checked against
physical test. That is the flow-data moat, and the claim gate is independent evidence for it.

---

## 1. Lead with the claim most likely to be false

**The claim most likely to be false is the one I was sent to test in its strong form: that
GE / Safran / RTX / Rolls-Royce are being *wrongly punished* by this news and are therefore a
"baby thrown out with the bathwater" long.**

They are not being punished at all. As of 14–17 September 2026, six to nine days after the
announcement, GE Aerospace traded $317.56–$323.66 on a **trailing P/E of 37.4–44.1x** and a
**forward P/E of 34.9x**, with EV/EBITDA of 27.3x — *149% above its own historical median* [6][7][8].
Safran's ADR sat near a 52-week high with a market cap of ~$135bn [9][10]. The only rating action
I found in the window went the other way: Melius cut GE from Buy to Hold on 14 September 2026 [11].
I searched specifically for an aerospace or simulation-software drawdown attributable to the
Navier–Stokes news and found none [12].

**Consequence, stated plainly: expression (b) — the wrongly-punished long — is unavailable on this
track, because there is no punishment.** Anyone pitching GE Aerospace off this story is pitching a
34.9x forward-P/E compounder at 149% above its own EV/EBITDA median and calling it a dislocation.
That fails Rosenwald's ~50% discount-to-intrinsic-value test and walks straight into Vectors.md §6
("Inflated: price already reflects the bull case"). I say this first because it kills the most
attractive-sounding version of my assignment.

What *does* survive is a narrower, more defensible statement about the moat itself, and one name
where a real dislocation mechanism exists that has nothing to do with the proof. Both below.

---

## 2. Filter compliance (metaprompt dimension 10) — run before anything else

| Name | Vectors.md tier hit | Disposition |
|---|---|---|
| GE Aerospace (GE) | **Soft** §6 "Inflated" — 34.9x fwd P/E, EV/EBITDA 149% above own median [6][7][8] | Researched; **not pitchable long on valuation**. De-risking constraint only. |
| Safran (SAF.PA / SAFRY) | **Soft** §1 "non-USD idea that ignores currency" — EUR reporter; becomes **Hard** if FX is not addressed. Not inflated (~16.4x) [9][10] | Researched; survives with FX treatment. Best of the European trio. |
| RTX (RTX) | No hit | Clean. |
| Rolls-Royce (RR.L / RYCEY) | **Soft** §1 FX (GBP) + **Soft** §6 "Inflated" after a multi-year re-rating | Researched briefly; no finding. |
| MTU Aero Engines (MTX.DE / MTUAY) | **Soft** §1 FX (EUR). Liquidity OK — top-5 EUAD ETF holding [13] | Researched; supporting finding. |
| Honeywell Aerospace (HONA) | No hit. Spun 29 Jun 2026 [14][15]. Not a judge holding, not a 2025 finalist, not a consensus AI long | Clean. **Only candidate reaching a long-only expression.** |
| SLB / Halliburton / Baker Hughes | **HARD** §4 "Upstream oil & gas / E&P" — Dinan's 2018-20 energy losses; NYU and Knudsen's endowment divested from fossil-fuel extraction | **CUT.** See §7. Services are not extraction, but SLB's revenue is levered to E&P capex and the pitch would be read as an E&P pitch. Stopped per Rule 10. |
| Westinghouse (thermal-hydraulics) | Private company — **Hard** §1. Cameco (CCJ) holds 49% but that pitch is a uranium-price call — **Hard** §4 "pure commodity-direction calls". Vectors.md also bans pre-revenue SMR pure-plays | **Unpitchable.** Evidence used, name not pitched. |
| Carrier / Trane / Daikin | No tier hit, but **no moat** — AHRI certification is *voluntary* [16][17] | **No finding.** Control group. |
| ASML | **Soft** §4 consensus mega-cap semi; and flow modelling is not its moat | **Unpitchable on this track.** Not researched further. |
| Chinese/Korean/Japanese shipyards | §1 sanction/investability risk for PRC yards; equity story is orderbook not hull IP | **Not pursued.** |

---

## FINDING A3-1 — The certification floor is real and it is written into the analysis-credit clause itself

- **Exposure:** GE Aerospace CES, $26.9bn revenue, 74% services, 49K-engine installed base [18];
  Safran FY2025 €31.33bn revenue, ROI €5.197bn (16.6%) [9]; RTX Pratt & Whitney FY2025 sales
  $32.9bn [19][20]; Honeywell Aerospace FY2025 $17.5bn revenue, $4.3bn segment profit [21][22].

- **Mechanism, hop by hop:**
  1. 14 CFR 33.87 requires **"at least 150 hours of operation"** of physical engine endurance
     testing, run as the prescribed 6-hour sequence 25 times, at specified power, temperature and
     rotor speed. No analytical substitution is offered [23].
  2. 14 CFR 33.94 requires that it "be demonstrated **by engine tests**" that the engine contains
     a failed fan/compressor blade *and* a failed turbine blade for ≥15 seconds at maximum rpm [24].
  3. The analysis carve-out in 33.94 is the load-bearing detail: analysis may substitute for
     **one** of the two tests, only for the test producing the **least rotor unbalance**, and only
     where the analysis is "based on **rig testing, component testing, or service experience**"
     and "shown to be equivalent to the test" [24].
  4. Therefore the *regulatory route to using simulation runs through a proprietary validated-data
     corpus*. Free, infinitely cheap simulation buys an entrant nothing at the FAA unless the
     entrant also has the rig-test, component-test or service-experience corpus to anchor it.
     The incumbent has it. The entrant does not, and cannot buy it.
  5. 33.76 bird ingestion likewise mandates physical ingestion of specified bird masses [25].
  - Independent corroboration from a *hostile* witness: Justin Beroz, CEO of turbulence firm
    ReynKo, complaining about the status quo — on drag and lift design, "the key thing is
    **it's always done experimentally** ... We don't have good computational tools to simulate
    these things in advance, and this really separates fluid engineering from other kinds of
    engineering" [26].

- **Magnitude:** the exposure protected is essentially the whole of the commercial aero-engine
  aftermarket annuity, because the annuity is downstream of type certification. GE: 70% of a
  ~$35bn adjusted revenue base is services; 80% of widebody revenue is services [18]. RTX: net
  *services* sales rose $3.3bn in 2025, of which **+$2.7bn at Pratt & Whitney** alone [19]. MTU:
  commercial MRO €6.0bn of €8.7bn group revenue in FY2025 — **~69%** — growing 18% (23% in USD) [27].
  Honeywell Aerospace commercial aftermarket **$7.66bn in 2025, +7.2%** [22]. I am not claiming
  cheap simulation threatens these lines; I am sizing what the floor protects.

- **Timing:** no trigger. This is a standing regulatory condition, not an event. The observable
  that would *end* it is an FAA/EASA rulemaking or Special Condition granting 33.87/33.94/33.76
  credit to pure analysis with no validation-data predicate. None exists as of 2026-09-19 [28].

- **NASA says this in its own words.** NASA/CR-20210015404, "A Guide for Aircraft Certification by
  Analysis," is the authoritative CbA document and it splits the airplane from the engine in one
  paragraph [46]:
  > "For the **engine**, certification testing represents only part of the overall testing
  > objectives, the most important of which is **to validate that the product is robust to its
  > mission** ... Thus, **with the possible exception of fan blade-out testing, which destroys the
  > engine test asset, CbA is not expected to eliminate a significant amount of engine testing in
  > the near term.**"
  > "**To date, CFD has not been directly utilized for engine CbA applications.**"
  And on the one engine test CbA *does* target, the condition attached is the moat itself:
  > "Fan blade containment can be predicted with sufficient accuracy today with transient
  > structural analysis ... **Significant validation work versus legacy engines or current programs
  > will be required.**"
  A new entrant has no legacy engines to validate against. The top technical roadblock NASA's own
  survey identified is **separated flow at the edges of the operating envelope**, with surface
  roughness and laminar-turbulent transition — precisely the regime where surrogates extrapolate
  and only rig data settles the answer [46].

- **The scope check that kills the loose version of the counter-thesis.** EASA's M&S framework,
  **CM-S-014**, is titled "Modelling & Simulation – **CS-25 Structural** Certification
  Specifications" and is authored by EASA's CS-25 *Structures* coordinator, covering static
  strength, fatigue, loads, aeroelasticity and crashworthiness [47]. It does not touch CS-E 740
  (150-hour endurance) or CS-E 810 (blade failure). EASA's live AI rulemaking, **RMT.0742**, is
  about **AI systems onboard the aircraft** (Level 1 assistance, Level 2 human-AI teaming, AI
  assurance, ethics), second NPA in 2026, publication targeted Q1/2027 — not about granting AI
  surrogates certification credit in place of physical test [48]. And eCFR states Title 14 "was
  last amended 9/15/2026"; 33.94 still carries **Amdt. 33-10, 49 FR 6854, Feb. 23, 1984** [24].
  **Nothing has moved, in either jurisdiction, in the direction the bear case needs.**

- **Counter-thesis (argued at full strength):** Certification by Analysis is a real, funded,
  regulator-engaged programme with a NASA roadmap that explicitly sequences "representative
  airplane maneuver **and engine test** certification applications" by maturity need date, mirroring
  CFD Vision 2030 [28]. EASA has already issued CM-S-014 formalising how modelling and simulation
  are reviewed, and both FAA and EASA have granted CFD credit in narrow cases (a fuselage radome
  addition on a previously certified airplane) [28]. Rolls-Royce itself says digital twins "save
  time and money in the rigorous testing of new engines that need to gain certification" [29] —
  i.e. the *cost* of the floor is falling even if the floor is not. And Beroz's number is the bear
  case in one sentence: on a ~$30bn, decade-long airplane programme, "**roughly half the time and
  half the cost is spent building, testing, or [refining] physical prototypes in the wind tunnel —
  and the only reason you're doing that is that the software sucks**" [26]. If the software stops
  sucking, that is the prize, and it accrues to whoever can most credibly stop testing.
  **My judgement:** the counter-thesis wins on *aircraft-level* flight-mechanics credit and loses
  on *engine block tests*. 33.87/33.94/33.76 are destructive full-scale demonstrations of
  containment and survival, not flow-field predictions; no CbA document proposes simulating a
  fan-blade-off. The RAeS's own framing is that "physical testing may always be needed to
  **validate the models**" [28] — which is the moat restated, not removed.

- **Long-only expression:** **(c) a de-risking constraint.** This finding does not generate a buy;
  it removes a specific bear case (an "AI kills the engine OEMs" narrative) from any aerospace
  long. It is what you say in Q&A when Meli asks why cheap simulation doesn't commoditise GE.

- **Severity:** **thesis-grade** as a *defensive* fact; noise as a source of alpha, because it was
  never priced as a risk in the first place (see §1).

- **Evidence:** `raw/A3_flowmoat/01_FAA_part33_certification_floor.md` [23][24][25];
  `raw/A3_flowmoat/08_certification_by_analysis_counter.md` [28];
  `raw/A3_flowmoat/03_practitioner_reality_SciAm.md` [26].

---

## FINDING A3-2 — Moat inversion: the surrogate vendors have built the inversion into their product architecture

This is the crux of the assignment, and it is the finding I would defend hardest.

- **Exposure:** the same names as A3-1, plus MTU Aero Engines (commercial MRO €6.0bn of €8.7bn
  FY2025 revenue [27]) as the purest data-holder in the group.

- **Mechanism, hop by hop:**
  1. An AI surrogate is trained on a corpus. Ansys states its own architecture: "A customer is
     provided with a workspace that only individuals from their company can access. **All new
     models are started from scratch and fully initialized so there is no data contamination
     across customers.**" There is a "Customer Hosted" tier that runs inside the customer's own
     infrastructure [4].
  2. Siemens Simcenter PhysicsAI is the same shape: engineers "**train and validate AI surrogate
     models using simulation results** ... and **retain easy access to high-fidelity CFD simulation
     as the validation reference**" [5].
  3. So the licence is commoditised and the *corpus* is not. Every buyer pays roughly the same for
     the engine; only the data holder has the fuel. NAFEMS titles its treatment of this
     "**Transforming Legacy Data into Scalable Surrogate Models**" [30].
  4. Accuracy is bounded by the corpus. The published failure mode is unambiguous: surrogates
     interpolate, they do not extrapolate; "if geometry or input/design variables deviate
     significantly from the training data, the surrogate model is likely to fail" [31]. And the
     scarcest quantities in turbulence — high-order statistics such as Reynolds stresses — "are
     usually unavailable from experiments" [32], so whoever *does* have them holds something the
     open literature cannot supply.
  5. Independent constraint statement on safety-critical use: "Training data is **proprietary
     geometry and simulation IP**"; "safety-critical designs such as aircraft structures and crash
     cases require full-fidelity solver sign-off; **surrogates accelerate exploration but cannot
     replace certification runs**" [33].
  6. Regulatory confirmation that validated flow data is a legally-recognised proprietary asset:
     Westinghouse's NRC topical report WCAP-18965 publishes its thermal-hydraulics validation
     (FRIGG pressure drop, FRODE lift force on TRITON11 fuel) as "Westinghouse **Non-Proprietary**
     Class 3" with the data redacted behind `[a,b,c]` proprietary brackets [34]. A US federal
     regulator accepts code qualification *against data it agrees to keep secret for the vendor*.
     Its scarcity is increasing, not decreasing: the OECD-NEA launched SYSTHER specifically because
     Europe has **lost** key thermal-hydraulic test infrastructure such as the PKL facility [35].

  **Conclusion of the mechanism: cheap simulation makes the data holder stronger.** It converts a
  cost centre (decades of rig tests, paid for long ago, already expensed) into the sole scarce
  input to a newly-cheap capability. This is textbook metaprompt dimension 5.

- **Magnitude:** I cannot put a dollar figure on it, and I will say so rather than manufacture one.
  **No company in this peer group discloses the size, cost or carrying value of its test-data
  corpus.** GE Aerospace's 2025 Investor Update does not contain the phrase "digital twin" at all;
  the word "proprietary" appears attached to its *lean operating model* (FLIGHT DECK), not to data;
  the only quantified data-like assets are "**2.3B flight hours**" and the 49K/29K engine counts
  [18]. Rolls-Royce claims to be "pioneers in the capturing and use of engine data" and to process
  "huge quantities of data from in-service engines in real-time" but discloses no corpus size,
  no flying hours and no valuation [29]. **There is no revenue line for "test data."**
  Per the metaprompt's own rule — *no revenue line, no finding* — this is therefore a finding about
  **why a revenue line is protected**, not a finding of a revenue line at risk. That is the honest
  framing and it caps the severity.

- **Timing:** none. There is no trigger, no contract cycle, no guidance event. A moat that is
  getting quietly stronger does not show up in reported financials on any identifiable date.
  This is precisely the "displacement that takes ten years is not a catalyst" case the metaprompt
  warns about, applied in reverse.

- **Counter-thesis (argued at full strength):**
  1. **Scope error on my own evidence.** Ansys and Siemens both describe training on *simulation
     results*, i.e. prior CFD runs, not on rig-test or flight data [4][5]. Prior CFD runs are
     reproducible by anyone who owns a solver and compute. If the surrogates only need simulation
     data, then the moat is *compute and time*, which is exactly what is getting cheap — and the
     entrant catches up. The strong form of my thesis (that *experimentally validated* data is the
     scarce input) is **inference, not vendor disclosure.** Marked as inference. This is the single
     biggest hole in the finding.
  2. **Open corpora erode scarcity.** NASA/AIAA/NEA and the DOE labs publish large validation
     datasets; the NEA's own MISTRA data "has been extensively used for code validation" [35], in
     public. Some of the corpus is a commons.
  3. **The corpus depreciates.** Seventy years of CF6 and CFM56 rig data is a corpus of yesterday's
     architectures. An open-rotor, hydrogen-combustion or high-bypass-ratio transition partly
     *invalidates* it, and at that boundary the incumbent's surrogate is extrapolating too.
  4. **The economics may be a Jevons trade, not a moat trade.** If simulation gets cheap enough,
     you may generate the validation data you need rather than inherit it, and then the advantage
     accrues to whoever has the most compute — not to whoever has the most history.
  5. **Nobody is paying for it.** The market has not marked the moat up, down or at all (§1). A
     moat nobody disputes is a moat nobody pays you to identify.
  **My judgement: the inversion direction is right — cheap simulation helps proprietary flow-data
  holders more than it hurts them — but the magnitude is unprovable from public disclosure and
  the market is not mispricing it.** Direction: confident. Tradeability: low.

- **Long-only expression:** **(c) a de-risking constraint**, plus a partial **(a)** on the one name
  in §3 where an independent dislocation exists. Not (b): there is no punishment to arbitrage.

- **Severity:** **supporting.** It would be thesis-grade if any company disclosed a corpus, or if
  any of these names had actually sold off. Neither is true.

- **Evidence:** `raw/A3_flowmoat/04_surrogate_vendors_customer_owns_the_data.md` [4][5][30][33];
  `raw/A3_flowmoat/02_GE_Aerospace_investor_day_2025.md` [18];
  `raw/A3_flowmoat/06_adjacent_industries_brief.md` [34][35];
  `raw/A3_flowmoat/05_peer_revenue_lines.md` [29].

---

## FINDING A3-2b — The two-tier bear case, answered head-on

Track A1 handed over the strongest argument against moat inversion and I am obliged to meet it:
*in unregulated design-**exploration** work nobody demands traceability or validated data, and that
is exactly where run-count growth is concentrated. So the validated-flow-data moat protects a
static certified tier while all the growth happens in a cheap unvalidated tier.*

**The bear case is largely right about where the runs are, and wrong about where the money is.**

1. **Conceded: the run-count growth is in the unvalidated tier.** Siemens sells PhysicsAI on
   "explore more designs with less computing power" [5]; Ansys SimAI's pitch is design-space
   exploration [4]. Nobody is selling surrogates as a certification tool — the constraint summaries
   say so explicitly: "surrogates accelerate exploration but **cannot replace certification runs**"
   [33]. Exploration is where the seats and the cycles go.
2. **But exploration is not a revenue pool anyone captures.** It is internal R&D. GE Aerospace
   spends ~$3bn a year on R&D against ~$35bn of revenue [18]; Safran's whole programme spend sits
   inside a €31.3bn revenue base [9]. Even a large proportional cut to design-iteration cost is
   low-single-digit percent of revenue, undated, and unannounced. **There is no revenue line at the
   end of this hop**, which by the metaprompt's own rule means no finding — for the bull *or* the
   bear.
3. **The tiers are not independent; the cheap tier's output must eventually cross into the
   expensive one.** Every design that reaches production passes through 150 hours of endurance
   running, a destructive blade-off, and bird ingestion [23][24][25]. A firm that explored 100x more
   cheaply and then failed a block test has converted a cheap saving into an expensive programme
   slip. NASA names the discipline this requires: as tools proliferate, "**enhanced tools will be
   required to manage the traceability of analysis data and artifacts** and to ensure that
   established procedures and processes are used in the generation and **archiving** of the provided
   analysis results" [46]. Traceability arrives at the tier boundary whether the exploration tier
   wants it or not.
4. **The decisive asymmetry: who can act on an unvalidated answer.** A surrogate result is a
   *hypothesis*. Its value is realised only by a firm that can cheaply decide whether to believe it.
   For the incumbent that decision costs a database lookup against 2.3 billion flight hours [18] and
   decades of rig data; for the entrant it costs a rig build. Both parties get 100x more hypotheses
   at the same licence price; only one gets a matching increase in the rate at which hypotheses are
   *resolved*. **Cheap exploration therefore widens the gap between the tiers rather than routing
   around the moat** — the bottleneck moves from "generate a candidate" to "adjudicate a candidate,"
   and adjudication is what the corpus does.
5. **Where the bear case genuinely wins, and I concede it:** in industries with **no certified
   tier at all** — consumer products, buildings, general industrial, most automotive aero — the
   unvalidated tier *is* the whole market, and there the moat is worthless. That is exactly the
   result I got for HVAC (§A3-4): a voluntary certification scheme [16][17], short product cycles,
   tractable physics, no moat. **The moat inversion is therefore not a general law about flow data.
   It is a claim about industries with a hard regulatory tier, and it should only ever be pitched
   in those.**

**Net:** the bear case does not overturn A3-2's direction, but it does cap it, and it is the reason
A3-2 is marked *supporting* rather than *thesis-grade*. It also explains why nobody is paying for
this insight: the tier where the moat bites is not growing, and the tier that is growing is not a
revenue pool.

- **Long-only expression:** **(c) a de-risking constraint**, and a scope limit on any pitch built
  on A3-2 — never pitch flow-data moats outside a certified industry.
- **Severity:** supporting.
- **Evidence:** `raw/A3_flowmoat/09_NASA_CbA_guide_and_AC335_verbatim.md` [46];
  `raw/A3_flowmoat/04_surrogate_vendors_customer_owns_the_data.md` [4][5][33];
  `raw/A3_flowmoat/06_adjacent_industries_brief.md` [16][17].

---

## FINDING A3-3 — Honeywell Aerospace (HONA): the one name where a real dislocation exists, and it is not caused by the breakthrough

- **Exposure:** Honeywell Aerospace Inc. (NASDAQ: **HONA**), spun out of Honeywell on
  **29 June 2026**, one HONA share per two HON shares, 316,939,750 shares distributed [14][15].
  FY2025 (as a Honeywell segment): revenue **$17.5bn**, +13%; segment profit **$4.3bn**;
  **commercial aftermarket revenue $7.66bn, +7.2% y/y** [21][22]; commercial aviation aftermarket
  organic sales +15% / +7% / **+19%** in 1Q/2Q/3Q 2025 [36].

- **Mechanism:** HONA holds the same class of asset as the finding above — decades of qualified
  aerospace flow and systems hardware (APUs, ECS, propulsion for business/regional aviation,
  avionics) sitting behind the same FAA/EASA type-certification floor described in A3-1, with a
  ~44% aftermarket revenue mix that is the direct cash expression of that qualification. What is
  *different* about HONA is the price-formation mechanism: a ten-week-old spin-off, distributed to
  a shareholder base that owned it for the automation business, with the usual forced-seller and
  index-orphan dynamics, and no independent trading history against which to anchor a multiple.
  That is a dislocation Rosenwald and Dinan both recognise; it is *not* the AI story.

- **Magnitude:** $17.5bn revenue, $4.3bn segment profit, $7.66bn aftermarket. FY2025 segment margin
  was held back by identified one-offs including Flexjet-related litigation charges [21] — i.e.
  there is a stated, non-structural reason reported margin understates the business.

- **Timing:** first full standalone reporting periods, Q3 2026 and Q4 2026, plus the first
  standalone guidance and first standalone capital-allocation framework. Those are named,
  dated triggers inside a one-year holding period. Contrast with A3-1 and A3-2, which have none.

- **Counter-thesis:** (i) The flow-data moat is *not* the reason to own HONA and I should not
  dress it as one — this is a spin-off/aftermarket-annuity idea that the moat argument merely
  defends. (ii) Spin-offs are a well-known anomaly and therefore a crowded one; the forced-seller
  window may already be closed ten weeks in. (iii) HONA's portfolio is systems and avionics, where
  the proprietary-flow-corpus argument is materially weaker than for a fan or a turbine — APUs and
  ECS are the flow-heavy parts, not avionics. (iv) Commercial aftermarket growth of +19% in 3Q25
  is a recovery comp, not a run rate. (v) **I did not complete a valuation.** Without a multiple and
  a price target this is a candidate, not a pitch.

- **Long-only expression:** **(a) — beneficiary long, candidate only.** The long-only inversion is
  clean (no short, no derivative, USD-reporting US listing, adequate liquidity), and it hits no
  Vectors.md tier. Hand to whoever runs valuation.

- **Severity:** **supporting**, and the highest-value output of this track. Flagged explicitly as
  *not* derived from the breakthrough.

- **Evidence:** `raw/A3_flowmoat/05_peer_revenue_lines.md` [14][15][21][22][36].

---

## FINDING A3-4 (negative result) — HVAC and pharma CFD: the moat is ordinary, and in pharma the regulator is moving the other way

Reported as a result per the metaprompt's instruction to treat negatives as findings.

- **HVAC (Carrier, Trane, Daikin).** There is no certification floor. AHRI's own page states
  "AHRI Certification is Voluntary" and describes a "**voluntary** program" [16]; Carrier's own
  customer FAQ says "AHRI certification is **not legally required**" [17]. DOE test procedures under
  10 CFR 430 mandate physical *rating* tests of finished units, but a rating test is not a barrier
  to designing one. Product cycles are 2–3 years, not ten, and duct/coil/refrigerant flow is far
  more tractable to a surrogate than a transonic fan stage. **No finding. Unpitchable on this track.**

- **Pharma CFD (inhaler / nasal / bioreactor).** The direction here is the *inverse* of aerospace:
  FDA is actively lowering the physical-test burden. ICH M15, "General Principles for
  Model-Informed Drug Development", became available in June 2026 [37]; FDA has funded CFD models
  explicitly "to Aid the Development of **Generic** Inhalation Products" to reduce the in-vivo
  burden in the weight-of-evidence bioequivalence approach [38]; and an FDA event on 10 September
  2026 covered "alternative approaches that use modeling and simulation ... and how to determine
  when in vivo studies may be needed" [39]. A regulator lowering a test floor *to help generic
  entrants* is moat **erosion** for branded inhaler/nasal franchises. I did not size a named
  branded revenue line within budget; direction noted, magnitude not established.
  **Severity: supporting, incomplete.** Worth handing to another track if anyone is covering pharma.

- **Reservoir simulation (SLB / Halliburton / Baker Hughes).** See §7 — cut on the filter.

- **Long-only expression for all of the above: unpitchable — no long expression.**

- **Evidence:** `raw/A3_flowmoat/06_adjacent_industries_brief.md` [16][17][37][38][39].

---

## 3. Practitioner reality (metaprompt dimension 3) — the disconfirming quotes

The metaprompt asks me to hunt for the practitioner who says "this changes nothing for us." I found
three, in a *Scientific American* piece published **18 September 2026** — one day before this file
was written [26]:

- **Justin Beroz, CEO, ReynKo** (a turbulence engineering firm), on what the proof means for
  engineering: **"not much."**
- **Florian Schaefer, assistant professor, New York University**: the result "doesn't really change
  how they will be used, because the equations themselves are only an approximation of how a fluid
  will react." "The Navier-Stokes equations have a certain regime of validity in which we think
  that they're basically enough at describing what the physics will do."
- *Scientific American*'s own framing: the blowup scenario "is so contrived it's almost certainly
  unlikely to have any direct relevance to any physical system in the real world."
- **Spencer Bryngelson, Georgia Tech**, gives the most optimistic view available and it is still
  hedged into meaninglessness: knock-on effects "useful, even though **it's unclear sometimes how
  those knock-on effects will happen**."

Per the metaprompt's transmission test — if you cannot draw the path without "could" or
"eventually," there is no path. **For the proof, there is no path.** For the surrogates, the path
exists but runs through corporate R&D budgets, not through a certification requirement.

---

## 4. Jevons check (metaprompt dimension 6)

The Jevons regime applies, and the evidence for it is Beroz's own complaint: fluid engineering is
*already* rationed by the cost of experiment — "it's always done experimentally ... we don't have
good computational tools to simulate these things in advance" [26]. Demand for flow answers is
enormously unsatisfied at current prices. Cheaper surrogates will therefore be consumed as *more
design exploration*, not as *less spend* — Siemens' own pitch is "explore more designs with less
computing power" [5]. Nothing I found supports the demand-falls case, and per the metaprompt
"demand falls" is the claim requiring proof. **Regime: Jevons. Total flow-simulation spend rises.**

The second-order consequence matters for A3-2: if every design team runs 100x more cases, the
binding constraint moves from *compute* to *which of the 100x answers you are entitled to believe* —
which is the validation corpus. Jevons and moat-inversion point the same way.

---

## 5. Dual-use (metaprompt dimension 8) — bounded, as instructed

The proliferation that has actually materialised is general-purpose LLM assistance to weapons
programmes, *not* the release of a cheap high-fidelity CFD solver. From Anthropic's threat
intelligence report of 10 September 2026, as reported by Reuters on 11 September 2026 [40]:

- **Yemen:** a threat-actor cell used Claude for "coding, **simulation** and troubleshooting" on a
  guided rocket, a planned >2,000 km ballistic missile, and "a missile variant incorporating a
  **hypersonic glide vehicle**", including after a guided-rocket test appeared to fail. Anthropic:
  "Our safeguards blocked many of their requests, but not all of them." No operational weapon
  evidenced.
- **China/Taiwan:** an actor linked to the PLA Academy of Military Sciences built an EW and
  air-defence-suppression suite and altered a **simulation** to include 12 Taiwan targets.
- **China:** fire-control software for a navy anti-torpedo system; high-power microwave weapons
  research and supply-chain tracing.

**Policy response since Sept 2026:** US lawmakers are seeking new AI rules following these
disclosures [40]; that is legislative interest, not a promulgated rule. **I found no new export
control specifically covering CFD or flow-surrogate models as of 2026-09-19.** Existing ITAR/EAR
coverage (USML Cat. IV; gas-turbine design/test software and technology) and the MTCR Annex already
reach most of this indirectly. Meanwhile hypersonics simulation capacity is being built as
*classified physical infrastructure*, not open capability: SMDC's Digital Simulation and Analysis
Center at Redstone Arsenal (opened Aug 2025, covering hypersonics M&S) [41] and AFRL's $20m,
186,000-core hypersonics supercomputer (June 2026) [42].

**Investment consequence:** export-control tightening is a risk to the AI labs and to open-weight
model distribution, and is mildly *positive* for incumbents whose design data is already
ITAR/EAR-controlled and air-gapped — one more reason a challenger cannot buy a surrogate off the
shelf. **No long expression. Section closed.**

---

## 6. Second-order (dimension 8, first half) — where the freed value goes (the question A1 handed over)

Track A1 established that there is no pure public CFD exposure left (Ansys→Synopsys, Altair→Siemens,
Hexagon CAE→Cadence), that vendors are *selling* the surrogate rather than being killed by it, and
that simulation-software spend grew +8.8% then +8.5% straight through the surrogate wave. It asked
me where the freed value lands. Answering from primary certification sources, not commentary:

**Split the answer by regulation, because the regulation splits it.**

- **Airplane level (14 CFR Part 25 / CS-25): a real and quantified pool exists.** NASA's CbA guide
  reports "industry-wide consensus that **current certification flight tests could be reduced by
  approximately 50% by utilizing CbA**", against flight-test programmes costing "tens to hundreds
  of millions of dollars" and an aggregate certification process "approaching one billion dollars"
  per programme [46]. That is the disciplined version of the Beroz anecdote, and it is sized.
  **But it is conditioned** — "if all existing CbA technical and logistical impediments were
  adequately addressed" — with no date, no rulemaking and no trigger. It also accrues to airframers
  (Boeing, Airbus, Embraer), not to the engine names on this track.
- **Engine level (Part 33 / CS-E): the pool is essentially closed.** NASA, in its own words: "with
  the possible exception of fan blade-out testing ... **CbA is not expected to eliminate a
  significant amount of engine testing in the near term**", and "to date, **CFD has not been
  directly utilized for engine CbA applications**" [46]. The engine test cell is legally and
  practically irreducible. **So for GE, Safran, RTX, RR and MTU, the "software gets better so
  testing collapses" story dies here.**
- **What remains is design iteration**, which is discretionary R&D, not certification. GE's total
  R&D is ~$3bn on ~$35bn of revenue [18]; an implausibly aggressive 30% cut is ~2.6% of revenue,
  spread over years, never announced. **No catalyst, no finding.**
- **And the prerequisite even for the airplane-level pool is the moat.** NASA's condition for
  displacing a blade-off test is "**significant validation work versus legacy engines or current
  programs**" [46]. The freed value is unlocked *by* the proprietary corpus, so to the extent it
  exists it accrues to the incumbent holding the programme P&L — not to the simulation vendor,
  whose licence is a rounding error against a test campaign, and not to an entrant, who must still
  build the physical article for 33.87 and 33.94 [23][24].

**Net answer to A1: the freed value is real at airframe level, closed at engine level, and in both
cases gated on a proprietary validated corpus. It is not a tradeable event on any datable trigger.**

---

## 7. The reservoir-simulation collision, stated explicitly and then cut

I was instructed to research this briefly and to flag the collision. Doing both:

- **The collision.** Vectors.md §4 lists **"Upstream oil & gas / E&P"** as a **Hard** avoid, on two
  independent grounds: Jamie Dinan's energy losses in 2018-20 and his deliberate hedging out of
  energy beta, and NYU's (and Knudsen's endowment's) divestment from fossil-fuel extraction.
- **The distinction I was asked to consider, and why it fails.** SLB, Halliburton and Baker Hughes
  sell *services and software*, not barrels; they are not extractors. But SLB's FY2025 revenue of
  **$35,708m** is composed of Well Construction $11,856m (**-11% y/y**), Production Systems
  $13,325m, Reservoir Performance $6,820m (-5%) and Digital $2,660m [43][44]. The revenue is a
  direct derivative of E&P capex, the declining lines are the drilling lines, and a pitch built on
  it would be read in the room as an E&P pitch. That is a judge-risk I cannot argue away.
- **What the research would have shown had I continued.** Digital is $2,660m, **7.4% of revenue**,
  with **ARR of $1.0bn at 31 Dec 2025** (+15% y/y) [43], and grew 18% y/y in Q2 2026 to $697m [44].
  ECLIPSE and INTERSECT sit inside that, but the simulator licence line is **not separately
  disclosed** — so there is no revenue line and, by the metaprompt's own rule, no finding even
  before the filter bites. Third-party sizing puts the *entire* reservoir-simulation software
  licence market at ~$2.4bn in 2025 across SLB, Halliburton (Nexus), CMG and Rock Flow Dynamics
  (market-research vendor, low reliability, order-of-magnitude only) [45].
- **Disposition: CUT on Vectors.md §4 (Hard).** Research stopped at Rule 10. Unpitchable.

---

## 8. Plain-language close

Here is the whole thing without jargon.

A jet engine company's advantage was never that it can solve the equations of fluid flow. Anyone can
buy software that does that. Its advantage is seventy years of burning real engines on real test
stands, which is how it knows *which answers from the software to believe*. The interesting question
was whether making simulation cheap destroys that advantage or increases it.

**It increases it, and the reason is mundane rather than dramatic.** The new AI tools that make
simulation cheap have to be trained on somebody's data, and the two big vendors have deliberately
built their products so that each customer trains a private model on its own data, starting from
scratch, with nothing shared between customers. The tool is cheap and available to everyone; the
data is not. On top of that, US aviation law still requires an engine maker to physically run an
engine for 150 hours and to physically destroy one by blowing a fan blade off it — and the one place
where the rules *do* let you substitute a computer calculation for a test, they require that the
calculation be backed by your own rig-test data or service history. So the legal shortcut to using
simulation is only open to the company that already has the test data. NASA's own official guide to
replacing tests with computation says flatly that for engines this "is not expected to eliminate a
significant amount of engine testing in the near term," and that computational fluid dynamics "has
not been directly utilized for engine" certification at all. Europe's equivalent framework covers
aircraft *structures*, not engines. And the US regulation was last amended four days before I wrote
this, with the blade-off rule untouched since 1984. So the answer to the certification question is:
**yes, physical test is still required, it is not moving, and the analysis-credit clause makes the
data moat load-bearing rather than incidental.**

There is one honest qualification. At the *airplane* level — not the engine — NASA reports an
industry-wide view that certification flight testing could eventually be halved, against a process
that costs about a billion dollars per aircraft programme. That is a real prize. But it has no date
attached, it belongs to Boeing and Airbus rather than to the engine makers, and NASA's condition for
unlocking it is "significant validation work versus legacy engines" — which is, once again, the
proprietary data.

The strongest argument against all of this, which I should state because it is good: all the *growth*
in simulation is happening in cheap, early-stage design exploration where nobody asks for validated
data at all. That is true. But exploration is a company's own R&D budget, not a market anyone sells
into, and everything that reaches a production aircraft still has to cross the certified line. The
real point is simpler: cheap tools hand everyone a hundred times more ideas, and only the company
with seventy years of test data can afford to work out which of them are true. I also have to concede
the boundary — in industries with no certification tier at all, like air conditioning, this moat is
worth nothing, and the argument should never be pitched there.

**What is speculative** is how much any of this is worth. Not one of these companies tells you how
big its test-data archive is or what it cost. GE Aerospace's own 2025 investor presentation never
uses the phrase "digital twin", and the word "proprietary" appears next to its manufacturing system,
not its data. So the strong version of the argument — that *experimentally validated* data is the
scarce ingredient — is my inference, not their disclosure. The vendors actually say they train on
past *simulation* runs, which are far easier to reproduce. That is the weakest link and I have
flagged it as inference throughout.

**And here is the part that kills the trade.** The premise I was sent to test was that these names
might be wrongly sold off — bought cheap while the market panics about AI. They have not been sold
off. GE Aerospace trades at roughly 35 times next year's earnings and an EV/EBITDA multiple 149%
above its own long-run median, nine days after the news, and the one analyst action in the window
was a *downgrade on valuation*. There is no bathwater and no baby. Meanwhile the fluid-dynamics
practitioners quoted in the press the day before I wrote this say the mathematical result means, in
the words of one CEO of a turbulence engineering firm, "not much."

**The single best idea from this track is not the moat argument at all.** It is
**Honeywell Aerospace (HONA)** — spun out of Honeywell on 29 June 2026, $17.5bn of revenue, $4.3bn
of segment profit, $7.66bn of commercial aftermarket revenue growing 7%, ten weeks old as an
independent company, handed to shareholders who bought it for a different business, with no trading
history and reported margins depressed by identified one-off litigation charges. That is a
dislocation with named catalysts inside a one-year horizon: its first standalone results and its
first standalone guidance. The flow-data moat is the *defence* of that idea in Q&A — the reason
cheap AI simulation will not commoditise its aftermarket annuity — and not the reason to own it.
I did not value it. It is a candidate, not a pitch.

**Everything else on this track is unpitchable:** reservoir simulation is cut on the fossil-fuel
filter, nuclear thermal-hydraulics has the best evidence and no listed vehicle, HVAC has no
certification floor and therefore no moat, pharma CFD is moving the *wrong* way for incumbents,
and the dual-use risk attaches to the AI labs rather than to anyone holding flow data.

---

## Verdict summary

| Question | Answer |
|---|---|
| Does cheap simulation destroy or strengthen the proprietary flow-data moat? | **Strengthen.** Direction confident; magnitude unprovable from public disclosure; market not mispricing it. |
| Is physical test still required for engine certification? | **Yes, and it is not moving.** 33.87 / CS-E 740 (150 hours of running), 33.94 / CS-E 810 (at least one full-scale destructive blade-off), 33.76 (bird ingestion at ≥100% takeoff power). eCFR confirms Title 14 last amended 2026-09-15 with 33.94 still on its 1984 amendment. NASA's own CbA guide: "**CbA is not expected to eliminate a significant amount of engine testing in the near term**" and "**CFD has not been directly utilized for engine CbA applications**." EASA's M&S memorandum CM-S-014 is scoped to **CS-25 structures**, not engines; RMT.0742 is about onboard AI, not simulation credit. And the 33.94 analysis carve-out is conditioned on "rig testing, component testing, or service experience" — which makes the data moat regulatory, not merely commercial. |
| Where does the freed value go (A1's handover)? | **Airframe level: real and sized** — NASA reports industry consensus that certification *flight* tests could fall ~50%, against a process costing ~$1bn per programme; but undated and accruing to airframers. **Engine level: closed.** What remains is discretionary design-iteration R&D (~$3bn/yr at GE on ~$35bn revenue) — no revenue line, no trigger. Both are gated on "significant validation work versus legacy engines", i.e. on the corpus. |
| Does the two-tier bear case break the moat thesis? | **It caps it, and scopes it.** Run-count growth genuinely is in the cheap unvalidated exploration tier — but that tier is internal R&D, not a revenue pool, and everything that reaches production still crosses the certified tier. The real asymmetry is that both parties get 100x more hypotheses while only the corpus holder gets a matching increase in the rate of *resolving* them. **Concession: outside industries with a hard regulatory tier (e.g. HVAC), the moat is worthless.** Never pitch flow-data moats outside a certified industry. |
| Any name reaching a long-only expression? | **HONA (candidate, (a)).** GE = (c) only, and fails on valuation. Safran/RTX/MTU/RR = (c). SLB/HAL/BKR = cut (Hard). Westinghouse/ASML/HVAC/shipyards = unpitchable. |
| Was the "wrongly punished long" available? | **No.** Nothing was punished. Reported as a negative result. |

---

## Citations

1. https://openai.com/index/navier-stokes-solution — OpenAI, "On the Navier–Stokes Millennium Prize Problem", 8 Sep 2026
2. https://www.alphaxiv.org/abs/2609.navier-stokes — "Finite Time Blowup for Navier–Stokes", submitted 8 Sep 2026
3. https://nickmcgreivy.substack.com/p/how-openai-found-a-singularity-in — "How OpenAI found a singularity in Navier-Stokes", 10 Sep 2026 (explains the f = D[u] construction)
4. https://www.ansys.com/products/ai/simai — Ansys SimAI product page and FAQ (data isolation, cold-start per customer, customer-hosted tier)
5. https://semiwiki.com/forum/threads/siemens-introduces-new-simcenter-physicsai-add-on-for-ai-powered-cfd-design-exploration.25183 — Siemens Simcenter PhysicsAI launch
6. https://www.gurufocus.com/term/forward-pe-ratio/GE — GE forward P/E 34.90, 14 Sep 2026
7. https://www.gurufocus.com/term/enterprise-value-to-ebitda/GE — GE EV/EBITDA 27.26, 149% above median; price $323.66, TTM P/E 38.12, 14 Sep 2026
8. https://www.macrotrends.net/stocks/charts/GE/ge-aerospace/pe-ratio — GE P/E 44.09 as of 17 Sep 2026
9. https://www.safran-group.com/download/media/450393 — Safran FY2025 Results & Investor Update, 13 Feb 2026
10. https://pitchbook.com/profiles/company/51738-94 — Safran market data as of 11 Sep 2026 (secondary, cross-checked against [13])
11. https://www.marketbeat.com/stocks/NYSE/GE/forecast — Melius Research, Buy → Hold, $350 target, 14 Sep 2026
12. Searches run 2026-09-19 for an aerospace/simulation-software drawdown attributable to the 8 Sep 2026 announcement returned no such event. Negative result.
13. https://www.bestetf.net/etf/EUAD/holdings — EUAD (Select STOXX Europe Aerospace & Defense ETF) holdings, MTUAY ~4.97%
14. https://www.honeywell.com/us/en/news/press-releases/2026/06/honeywell-board-of-directors-approves-spin-off-of-honeywell-aerospace — board approval, 15 Jun 2026; completion 29 Jun 2026
15. https://www.sec.gov/Archives/edgar/data/2089271/000208927126000021/hona-20260627.htm — Honeywell Aerospace Inc. Form 10-Q, spin completed 29 Jun 2026, 316,939,750 shares distributed
16. https://www.ahrinet.org/certification — "AHRI Certification is Voluntary"
17. https://www.carrier.com/us/en/residential/hvac-resources/ahri — Carrier: "AHRI certification is not legally required"
18. https://www.geaerospace.com/sites/default/files/geaerospace_webcast_presentation_07172025.pdf — GE Aerospace 2025 Investor Update, 17 Jul 2025 (CES $26.9bn/74% services/49K engines; DPT $9.5bn/56% services/29K engines; ~$35bn adj. revenue, 70% services; "Over 2.3B flight hours"; no "digital twin" language)
19. https://www.sec.gov/Archives/edgar/data/101829/000010182926000006/rtx-20251231.htm — RTX FY2025 Form 10-K
20. https://investors.rtx.com/static-files/ea90bddd-958c-455f-a934-ff6aa96fab62 — RTX Annual Report 2025 (net sales $88,603m; services $24,432m)
21. https://www.sec.gov/Archives/edgar/data/773840/000077384026000013/hon-20251231.htm — Honeywell FY2025 Form 10-K (Aerospace Technologies $17.5bn, +13%; segment profit $4.3bn)
22. https://fiscal.ai/company/NasdaqGS-HONA/metrics/segments-and-kpis/commercial-aftermarket-revenue — Honeywell Aerospace commercial aftermarket revenue $7.66bn 2025, +7.2%
23. https://www.law.cornell.edu/cfr/text/14/33.87 — 14 CFR 33.87, endurance test, "at least 150 hours of operation"
24. https://www.law.cornell.edu/cfr/text/14/33.94 — 14 CFR 33.94, blade containment and rotor unbalance tests, including the "rig testing, component testing, or service experience" analysis carve-out
25. https://www.ecfr.gov/current/title-14/chapter-I/subchapter-C/part-33/subpart-E/section-33.76 and https://www.faa.gov/documentLibrary/media/Advisory_Circular/AC_33.76-1B.pdf — 14 CFR 33.76 bird ingestion; AC 33.76-1B
26. https://www.scientificamerican.com/article/what-does-openais-blockbuster-mathematics-navier-stokes-proof-mean-for-the-real-world — Scientific American, 18 Sep 2026 (Beroz "not much"; "it's always done experimentally"; "roughly half the time and half the cost ... wind tunnel"; Schaefer; Bryngelson)
27. https://www.mtu.de/newsroom/press/latest-press-releases/press-release-detail/figures-for-2025-mtu-stays-on-course-for-growth and .../mtu-aero-engines-remains-on-track-with-growth-in-first-half-of-2026-and-raises-free-cash-flow-guidance — MTU FY2025 and H1 2026 figures
28. https://ntrs.nasa.gov/api/citations/20210015404/downloads/NASA-CR-20210015404%20updated.pdf ; https://ntrs.nasa.gov/api/citations/20250005704/downloads/AIAA_CbA_CoI_Aviation_Paper-forReview_06092025.pdf ; https://www.aerosociety.com/media/8864/15-cert-by-analysis.pdf ; EASA CM-S-014 — Certification by Analysis literature
29. https://www.rolls-royce.com/innovation/digital/digital-twin.aspx — Rolls-Royce digital twin ("pioneers in the capturing and use of engine data"; digital twins "save time and money in the rigorous testing of new engines that need to gain certification")
30. https://www.nafems.org/downloads/dropbox/nologin/nrc25-in/extended-abstracts/pres-0007671.pdf — NAFEMS, "Transforming Legacy Data into Scalable Surrogate Models"
31. https://www.mdpi.com/2311-5521/10/8/193 — "Rapid CFD Prediction Based on Machine Learning Surrogate Model in Built Environment: A Review" (surrogates fail on extrapolation beyond training geometry)
32. https://arxiv.org/pdf/2301.09443 — "Probabilistic Machine Learning to Improve Generalisation of Data-Driven Turbulence Modelling" (high-order statistics such as Reynolds stresses usually unavailable from experiment)
33. https://case-studies.ai/use-cases/engineering-and-research/ER-009-ai-surrogate-models-simulation — constraint table: proprietary geometry/simulation IP; surrogates cannot replace certification runs
34. https://www.nrc.gov/docs/ML2508/ML25085A362.pdf — Westinghouse WCAP-18965 NRC pre-submittal slides, thermal-hydraulics validation data redacted behind [a,b,c] proprietary brackets
35. https://www.oecd-nea.org/jcms/pl_111255/strengthening-thermal-hydraulics-research-in-nuclear-safety — OECD-NEA; MISTRA data used for code validation; SYSTHER created in response to loss of European test infrastructure (PKL)
36. https://finance.yahoo.com/news/strength-aerospace-segment-drives-honeywell-155200128.html — Honeywell commercial aviation aftermarket organic growth 1Q/2Q/3Q 2025
37. https://www.fda.gov/drugs/development-resources/model-informed-drug-development-paired-meeting-program — ICH M15 MIDD guidance available June 2026
38. https://grants.nih.gov/grants/guide/rfa-files/RFA-FD-21-015.html — FDA RFA, CFD models to aid development of generic inhalation products
39. https://www.fda.gov/drugs/news-events-human-drugs/advancing-generic-drug-development-modernizing-bioequivalence-approaches-topical-transdermal — FDA, 10 Sep 2026
40. https://www.reuters.com/world/china/how-anthropic-says-claude-was-used-weapons-spying-cyber-operations-2026-09-11 — Reuters, 11 Sep 2026, on Anthropic's 10 Sep 2026 threat intelligence report; also "US lawmakers seek new AI rules after Anthropic researchers' warnings"
41. https://thedefensepost.com/2026/08/13/lockheed-us-missile-defense-simulation — SMDC Digital Simulation and Analysis Center, Redstone Arsenal
42. https://interestingengineering.com/military/new-us-air-force-supercomputer — AFRL $20m, 186,000-core hypersonics supercomputer, 22 Jun 2026
43. https://investorcenter.slb.com/static-files/f65b65ce-3607-438d-a980-cb2d1af044ae — SLB Q4 and FY2025 results (FY2025 revenue $35,708m; Digital $2,660m; Digital ARR $1.0bn)
44. https://investorcenter.slb.com/news-releases/news-release-details/slb-announces-second-quarter-2026-results — SLB Q2 2026 (Digital $697m, +18% y/y)
45. https://dataintelo.com/report/reservoir-simulation-software-market — market-research vendor; ~$2.41bn 2025 reservoir-simulation software licences. **Low reliability; order of magnitude only.**
46. https://ntrs.nasa.gov/api/citations/20210015404/downloads/NASA-CR-20210015404%20updated.pdf — NASA/CR-20210015404, "A Guide for Aircraft Certification by Analysis", May 2021. **PRIMARY.** PDF downloaded and text-extracted 2026-09-19. Source of: ~50% flight-test reduction consensus; "aggregate cost of the certification process approaching one billion dollars"; "CbA is not expected to eliminate a significant amount of engine testing in the near term"; "CFD has not been directly utilized for engine CbA applications"; "significant validation work versus legacy engines or current programs will be required"; separated flow as top technical roadblock; traceability/archiving requirement.
47. https://www.easa.europa.eu/en/document-library/product-certification-consultations/proposed-certification-memorandum-modelling and https://www.nafems.org/events/nafems/2024/modelling-and-simulation-supporting-certification-in-the-aerostructures-domain — EASA CM-S-014, "Modelling & Simulation – **CS-25 Structural** Certification Specifications" (author: Wim Doeland, EASA CS-25 Structures coordinator). Scope is CS-25 structures, not CS-E engines.
48. https://www.easa.europa.eu/en/newsroom-and-events/news/easas-first-regulatory-proposal-artificial-intelligence-aviation-now-open ; https://www.easa.europa.eu/en/downloads/144159/en (EASA AI Days 2026) ; https://www.easa.europa.eu/en/domains/research-innovation/ai — EASA RMT.0742, AI-based onboard systems (Levels 1-2), second NPA 2026, publication targeted Q1/2027. Not simulation-credit rulemaking.
49. https://www.faa.gov/documentLibrary/media/Advisory_Circular/AC_33-5.pdf — FAA AC 33-5, "Turbine Engine Rotor Blade Containment/Durability", 06/18/90. **PRIMARY.** PDF downloaded and extracted 2026-09-19. §6b(3) "analysis of the critical blade"; "development experience with the subject type design, or service experience with a similar type design"; §6c "Engine Tests" (type-design engine, critical blade released at maximum permissible rpm, high-speed photography and witness shields).
50. https://www.easa.europa.eu/sites/default/files/dfu/Easy%20Access%20Rules%20CS-E%20%28Amendment%204%29.pdf and https://www.easa.europa.eu/sites/default/files/dfu/CS-E%20Amendment%205.pdf — EASA CS-E 740 basic **150-hour endurance test** plus additional 2-hour test and physical strip inspection under CS-E 740(h); blade failure at CS-E 810. Second jurisdiction, same floor.
51. eCFR page header retrieved 2026-09-19: "Displaying title 14, up to date as of 9/17/2026. **Title 14 was last amended 9/15/2026.**" — i.e. the Part 33 test requirements are current as of two days before this file, nine days after the OpenAI announcement, and 33.94 still carries Amdt. 33-10 (1984).
