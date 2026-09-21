# Track A2 — Physical test & forecasting

**Agent:** A2 · **Date of work:** 2026-09-19 · **Raw sources:** `navier_stokes/raw/A2_test_forecast/`

---

## 0. The breakthrough, in one line, and the separation I am obliged to keep

On 8 September 2026 OpenAI published a Lean-machine-checked construction of a smooth, finite-energy
solution of the **forced** 3D incompressible Navier–Stokes equations on ℝ³ that starts from rest and
blows up in finite time; it settles Fefferman alternatives (C)/(D) of the Clay statement and leaves
the unforced global-regularity question (A)/(B) untouched (Agent 0, `01_Claim.md`; cited here
as [14] throughout — Agent 0's own citation numbers are not reused in this file).
**It is an existence theorem about a reverse-engineered forcing term. It is not a solver, not a
faster solver, and not a surrogate model.**

Agent 0's claim gate closed this path explicitly, and I write no finding on either side of it in
which the *proof* damages test or forecasting revenue. Two facts from `01_Claim.md` foreclose it:

> **Terence Tao, 3 September 2026** (five days before the announcement, and therefore not a
> reaction to it): "the regularity problem is not important for its direct physical application.
> Computational fluid dynamics is already a mature subject, deployed extensively in the atmospheric
> sciences, for instance, and its empirical capabilities and limitations are already well
> understood. A theoretical guarantee of regularity, or conversely a pathological instance of
> blowup, for these equations would be intellectually interesting for such applications, but
> **would not radically transform the way we would, for instance, model weather prediction or
> climate change**." [14]

> **George Karniadakis (Brown), via Nature:** for air, the constructed singularity appears when the
> vortex "becomes around **70 nanometres** wide — so thin that its width spans the typical distance
> that one air molecule travels before hitting another one." [14] That is roughly the mean free path
> of an air molecule and some ten orders of magnitude below the finest grid any weather model or
> catastrophe hazard module resolves. The object in the theorem does not exist at the scale where
> this track's revenue is earned.

Agent 0 found roughly fifteen named practitioners and **zero** saying the result changes an
industrial workflow [14]. Tao's quote lands directly on Part 2 of my assignment and settles it.

Separately and independently, machine-learned weather emulators (GraphCast, GenCast, Aurora,
FourCastNet, and now ECMWF's own AIFS) have made medium-range global forecasting essentially free
at the point of use [10]. These are two different economic events. Everything in §§3–6 of this file
is about the **second** one. Nothing here draws a conclusion from the proof. The evidence for each
is in separate raw files: `ml_weather_nwp_status_2026.md` (surrogate trend) vs. `raw/00_claim/`
(the proof).

---

## 1. Lead with the claim most likely to be false

**The claim most likely to be false is the one this track was built on: that cheap, good fluid
simulation erodes the Verisk / Moody's-RMS catastrophe-modelling moat.**

It does not, and the industry's own buyers say so in a ranked survey. Aon's 2025 Global Catastrophe
Risk Management Survey — two-thirds of responses from C-suite or the ceded reinsurance buyer —
asked (re)insurers to rank thirteen factors when choosing which catastrophe model to license.
**"Computational speed and ease of use" ranked 10th of 13**, with a relative importance of 1.19
against a base of 1.00, versus 3.47 for "reasonableness of model methodology" [7].

| Rank | Factor | Relative importance |
|---|---|---|
| 1 | Reasonableness of model methodology | **3.47** |
| 2 | Agreement with loss experience | 1.82 |
| 3 | Model transparency | 1.71 |
| 4 | Reinsurer market acceptance | 1.53 |
| 5 | License cost | 1.48 |
| … | … | … |
| **10** | **Computational speed and ease of use** | **1.19** |
| 13 | Deployment flexibility | 1.00 (base) |

Cheaper physics attacks the tenth-ranked purchase criterion of a product whose top four criteria are
methodological credibility, agreement with realised losses, transparency, and *what your reinsurer
will accept*. That is not a moat made of compute.

The second claim most likely to be false is that better simulation displaces physical test. It
already did, twenty years ago. What is left is the certification residue, and its size is set
administratively, not economically (§3). **Both legs of my assignment fail. That is the finding.**

**And a third claim failed on re-test, which is the one I had myself provisionally believed.**
I initially graded Verisk a "wrongly-punished long". A dated price test kills that framing. Verisk
*has* de-rated — market cap -34.6% y/y — but the de-rating is **not attributable to this
breakthrough**. It happened on **3 February 2026, seven months before the announcement**, when the
entire information-services complex fell on a *legal*-AI product release: VRSK **-10.11% in one
day**, alongside TransUnion -12.5%, Equifax -12.1%, S&P Global -11.3% (its largest fall since March
2020), FactSet -10.5% and Moody's -8.9%, against SPY -0.85% [15][16]. In the actual announcement
window (4 → 18 Sep 2026) Verisk fell 5.6% — **less than Equifax (-10.3%), TransUnion (-9.3%) and
S&P Global (-8.6%), none of which has any catastrophe-modelling, meteorological or fluid-dynamics
exposure at all** [15]. A Navier–Stokes repricing of catastrophe models would make Verisk and
Moody's *outliers within* the complex. They are mid-pack. **There is no differentiated punishment
to buy on this vector, so expression (b) is unavailable and I am withdrawing it.** See §4.1 and §8.

This is the same pattern A1 found (Synopsys +26% in 30 days, Cadence at a record $8.1bn backlog),
A3 found (GE at 34.9x forward P/E with EV/EBITDA 149% above its own median) and B1 found (Accenture
-18%, but on a services-deflation narrative that predates and is unrelated to the proof). **Four
tracks, one result: the market has not repriced anything on this news.**

---

## 2. Filter compliance (metaprompt dimension 10) — run before anything else

| Name | `docs/Vectors.md` tier hit | Disposition |
|---|---|---|
| **Verisk Analytics (Nasdaq: VRSK)** | **No hit.** Not a Dalton/NAVF/UCITS/Luxor/York holding [Rosenwald profile §Portfolio]; not a 2025 finalist; US-listed, USD-reporting, $22.8bn cap, 3.2m shares/day — liquid. §6 "Inflated" fails in the *good* direction: -34.6% market cap y/y, EV/FY26E EBITDA 14.9x [11] | **Clean on the filter, and researched in depth — but fails the attribution test in §4.1 and reaches NO long-only expression on this track.** |
| Moody's Corp (NYSE: MCO) | **Soft §6 "Saturated"** — a consensus quality-compounder, heavily owned. No variant view available to me | Researched; **no finding**. See §4.2. |
| **Horiba (TSE: 6856)** | **No hard hit.** *Checked explicitly against the Rosenwald/Dalton book: Horiba appears in none of the 13F, NAVF top-10 or other-stakes, Longchamp UCITS top-10, Korea list or the student fund.* But **Soft §6 "Inflated"**: +43.4% YTD 2026, PB 2.63x, EV/EBITDA 11.15x, fwd PE 16.6x [12] | Researched; **not a victim and not a pitch on this track.** See §3.2. |
| Vaisala (Nasdaq Helsinki: VAIAS) | **Soft §1** — EUR reporter, FX must be addressed. No other hit | Researched; **supporting only**, no long expression (§5.2). |
| Ricardo plc | **Dead.** Acquired by WSP Global for £282m; effective 9 Oct 2025, LSE listing cancelled 10 Oct 2025 [4] | **Not investable. Cut.** |
| Element Materials Technology / NTS | **HARD §1** — private (Temasek, completed 5 Jul 2022) [4] | **Cut.** |
| AVL List GmbH, FEV Group GmbH | **HARD §1** — private [4] | **Cut** (evidence used, name not pitched). |
| MTS Systems | **Dead as a name.** Amphenol (APH) bought MTS 2021 and sold Test & Simulation to ITW, completed 1 Dec 2021 [4]. No disclosed revenue line inside ITW | **Cut** on the metaprompt's "no revenue line, no finding" rule. |
| DTN, StormGeo, Tomorrow.io, The Weather Company, AccuWeather | **HARD §1** — all private [4] | **Cut.** |
| Spire Global (NYSE: SPIR) | **HARD §3** "illiquid micro-cap" + **§4** pre-profit narrative. ~$58.5m continuing revenue, restated financials, disclosed material weaknesses [4] | **Cut.** |

---

## 3. PART 1 — Physical test infrastructure. Verdict: **already irreducible. The leg is dead.**

### 3.1 Finding A2-1 — Physical test was displaced decades ago; the remainder is certification-mandated

- **Exposure:** the thesis that cheaper/better simulation removes revenue from automotive,
  aerospace and materials physical-test providers (Horiba, Vaisala, Ricardo, AVL, FEV, Element,
  wind-tunnel operators, proving grounds).
- **Mechanism (hop by hop, and where it breaks):** hop 1, cheaper CFD → fewer *development*
  test hours. This already happened, continuously, from roughly 1995 onward; it is priced into
  twenty years of these companies' revenue lines. Hop 2, cheaper CFD → fewer *certification* test
  hours. **This hop does not exist.** US light-duty emissions certification is governed by
  40 CFR Part 1066, which requires emissions to be *measured* from a real vehicle on a chassis
  dynamometer; the regulation's own word "simulating" refers to the dynamometer reproducing road
  load, not to replacing the measurement [5]. In aerospace, the FAA's June 2026 NPRM "Transport
  Airplane and Propulsion Certification Modernization" is the *most* favourable datapoint the
  displacement thesis has, and it grants relief on one flight-test point: validated CFD may
  substitute for the flight test to V_DF/M_DF under §25.251(b), while "the applicant **would still
  be required** to perform a flight test to V_MO/M_MO" under §25.251(d) [5]. Note "**validated**"
  CFD — validated against physical test. Hop 3, the OpenAI result → anything above. **No hop
  exists at all:** a blowup theorem for a reverse-engineered forcing term is not a numerical method
  and changes no test schedule.
- **Magnitude:** Horiba FY2025 (y/e 31 Dec 2025): total net sales **¥333,081m**, operating income
  **¥53,040m** (15.9% margin), net income ¥37,090m, ROE 11.2%, equity ratio 67.1% [3]. The
  automotive-test-containing segment, **Energy & Environment, was ¥134,407m of sales (40.4% of
  group) but only ¥9,417m of operating income — 17.8% of group OP, on a 7.0% segment margin** [3].
  Materials & Semiconductor was ¥156,500m of sales and **¥44,517m (84%) of operating income** [3].
  **Even a total wipe-out of Horiba's automotive test profit removes under a fifth of group
  operating income.** And it is not being wiped out: E&E sales *grew* 5.5% and segment operating
  income grew **120.9%** in FY2025 [3].
- **Timing:** not applicable — there is no event. For completeness, Horiba's own 7 Aug 2026 FY2026
  guidance holds Energy & Environment **flat at ¥134,000m** while raising Materials & Semiconductor
  to ¥205,000m [3a]. Flat, not falling, and the flatness is attributed to end-market mix, not
  simulation.
- **Counter-thesis (argued at full force — i.e. the case that displacement IS happening):** the FAA
  NPRM is a genuine regulatory crack, and it is dated June 2026, i.e. current. Certification-by-
  analysis is an active NASA research programme (CR-20210015404) with an explicit roadmap [5]. If
  regulators generalise validated-CFD credit from one flight-test point to whole test campaigns,
  wind-tunnel and flight-test hours fall materially. **Why it loses:** (i) NASA's own guide states
  that "with wind tunnel and flight-testing **still expected to play a key role** in the design and
  certification process", the research priority is *merging* CFD with experimental data, not
  replacing it [5]; (ii) DLR's flutter researchers: "They are complementary technologies and it
  should stay like that" [5]; (iii) Aerospace America: "CFD reduces the scope of expensive wind
  tunnel testing, but time in tunnels is still required to validate far-reaching designs" — and MIT
  is spending **$18m on a new subsonic wind tunnel** [5]; (iv) the relief is an NPRM, applies to
  *modifications* of already-certified transports, and moves in units of individual test points
  over a decade-plus rulemaking cadence. A ten-year displacement is not a one-year catalyst
  (metaprompt dimension 7).
- **Moat inversion (dimension 5) — and it inverts decisively:** if regulators mandate physical test
  for certification, simulation cannot displace it *at any price*, and the owner of the qualified
  test apparatus, the accredited lab and the seat on the rule-making committee holds a
  price-insensitive annuity. AVL states it is "a member of all relevant rule-making groups like the
  UN-ECE GRPE" [5]. Cheaper simulation makes *validation data* scarcer relative to demand, which is
  the wind-tunnel operator's product. **The inversion wins.**
- **Long-only expression:** **(d) unpitchable — no long expression on this track.** The inversion
  is real but every clean way to own it is blocked: Ricardo is delisted into WSP [4]; Element, AVL,
  FEV and NTS are private [4]; MTS is an undisclosed line inside ITW [4]; there is no listed
  pure-play wind-tunnel operator or proving ground; and Horiba, the one liquid listed name, is a
  semiconductor-metrology company wearing an automotive-test coat, trading at +43.4% YTD, PB 2.63x
  and 16.6x forward earnings [12] — an inflated-side Soft hit under Vectors §6, and a pitch for it
  would be a semicap pitch dressed as a Navier–Stokes pitch.
- **Severity:** **thesis-grade as a kill.** It removes Part 1 of this track entirely.
- **Evidence:** `raw/A2_test_forecast/regulatory_mandated_physical_test.md` [5];
  `horiba_fy2025_tanshin.md` [3]; `ownership_traces_ricardo_mts_element_avl_fev.md` [4].

### 3.2 Note on Horiba and the Japan angle

Horiba is Japan-listed, owner-adjacent (the Horiba family), cash-rich (net cash ¥108.05bn, equity
ratio 67.1%) and raised its MLMAP2028 targets on 7 Aug 2026 to net sales ¥460bn, operating income
¥90bn and ROE 14% [3][3a][12]. **It is genuinely Rosenwald-shaped in character and it collides with
nothing in the Dalton book** (verified name-by-name against the 13F, NAVF, Longchamp UCITS, Korea
list and the student fund). But it fails on two counts here: (i) it is not a victim of this
breakthrough — the exposed segment grew and its profit more than doubled; (ii) at PB 2.63x,
EV/EBITDA 11.15x and +43.4% YTD it is not at a 50% discount to intrinsic value, and the thing
driving it is AI semiconductor capex, which belongs to a different track. **Recording it as
researched-and-rejected, not as a finding.**

---

## 4. PART 2 — Catastrophe modelling. Verdict: **the moat survives — and precisely because it survives, and because the selling was not caused by this news, there is no long here.**

### 4.1 Finding A2-2 — Verisk: the moat holds, the de-rating is real, and the two are not connected to this breakthrough

- **Exposure:** Verisk Analytics (Nasdaq: VRSK). Catastrophe and Risk Solutions (renamed from
  Extreme Event Solutions in Q1 2025) sits inside the **Underwriting** revenue category.
- **Magnitude, with the disclosure:** FY2025 total revenue **$3,073m** (+6.6%, +6.6% OCC);
  **Underwriting $2,180m = 70.9% of total** (+7.7%, +7.0% OCC); Claims $893m (+4.1%). Adjusted
  EBITDA **$1,727m, margin 56.2%** (up from 54.7%). Free cash flow $1,192m (+29.5%) [1].
  **Verisk does not separately disclose a dollar revenue line for Extreme Event / Catastrophe and
  Risk Solutions.** I downloaded the full FY2025 10-K and scanned all 409,924 characters of
  extracted text: "Extreme Event" appears twice and "Catastrophe and Risk Solutions" three times,
  all qualitative; "open-source" appears zero times and "Florida Commission" zero times; revenue
  disaggregation stops at Underwriting/Claims [1][14a]. The only hard cat-adjacent dollar figure the
  company has given recently is the divestiture note that **AER, a business within Underwriting,
  had $17m of 2024 revenue** and was sold on 2 Dec 2024. Per the metaprompt's "no revenue line, no
  finding" rule, **I will not invent a cat-modelling revenue estimate.** What I can say with a
  disclosure behind it is: the exposed line is a sub-component of a $2,180m category that grew 7.0%
  organically in the year the market marked the stock down 35%.
- **Mechanism, hop by hop, and where it breaks:** hop 1, cheap/commoditised physics → anyone can
  build a hazard module. Partly true. Hop 2, anyone can build a hazard module → insurers stop
  licensing Verisk. **This hop fails.** A catastrophe model is a stochastic event catalogue + a
  vulnerability curve + a financial module, defended link-by-link in front of a regulator, a rating
  agency and a reinsurer [8]. For US hurricane — the largest peril by premium — the hazard module is
  a parametric windfield over a synthetic storm catalogue, not a direct numerical solution of
  Navier–Stokes. Hop 3, the OpenAI proof → any of the above. **No hop exists.**
- **The three moat pillars, each evidenced:**
  1. **Reinsurer/broker acceptance.** Aon: "Since reinsurers largely license either Moody's RMS or
     Verisk, this influences why these vendors lead the market"; and "it is most common to rely on
     the **reinsurance broker's evaluation** of a catastrophe model, rather than doing an in-house
     evaluation" [7]. Challengers with technically accepted models — Cotality, KCC, JBA, Risk
     Frontiers — each sit at **under 5% take-up** [7].
  2. **Regulatory acceptance — and this is the single strongest piece of evidence on the track.**
     A hurricane model may be used in Florida residential rate filings only after the Florida
     Commission on Hurricane Loss Projection Methodology issues a **letter of acceptability** [6].
     I pulled the Commission's own current list ("Models Currently Determined Acceptable",
     rev. 25 Aug 2026) [6]. Three things in it decide the question:
     - **The accepted list is six organisations**, and it has barely moved: CoreLogic/Cotality,
       Florida International University (the state public model), Aon Impact Forecasting, Karen
       Clark & Company, Moody's Corporation and Verisk. All hurricane acceptances expire
       **1 November 2027**. For flood, only three organisations are accepted at all, and neither
       Verisk nor Moody's is among them.
     - **Acceptance attaches to the model *and the software build*, and must be re-earned for every
       point release.** Moody's currently holds **sixteen separate letters of acceptability for the
       same model** — "North Atlantic Hurricane Models Version 25.0 (Build 2450)" — one for each
       successive platform build: Risk Modeler 2.38.0 (12 Jun 2025), 2.44.0, 2.45.0, 2.46.0/2.46.1,
       2.47.0, 2.48.0 (22 Jan 2026), 2.49.0, 2.50.0, 2.51.0, 2.52.0, 2.52.1, 2.53.0, 2.54.0 and
       2.54.1 (25 Aug 2026) [6]. Verisk holds two, on Touchstone 2024A and Touchstone 2025 [6].
     - **Therefore the gate is a compliance treadmill, not a benchmark.** An entrant with a
       radically cheaper physics engine gets no access to the largest cat-exposed US residential
       market until it submits under the current Standards year, survives the Commission's
       professional-team audit, obtains a letter, and then re-obtains one roughly every six weeks
       for each new software build, indefinitely. That cost scales with incumbency, not with
       compute. **Commoditised physics does not cross this gate.**

     Aon adds the same point outside Florida: "Lloyd's Market and global insurers have comprehensive
     model approval processes, extending the model adoption process" — UK/EMEA and global adoption
     timelines are "1+ year" [7].
  3. **Switching cost and workflow lock.** Aon: "Many companies are constrained to licensing one
     model vendor due to the cost and resources required to maintain multiple catastrophe models"
     [7]. 83% of Verisk revenue is subscription [11].
- **What Verisk itself names as competition — and what it does not.** The 10-K's "Our Competitors"
  section names: insurers in-housing ("insurers that develop internal technology and actuarial
  methods for proprietary insurance programs"), other statistical agents and advisory organisations,
  "emerging providers in the InsurTech space", and consulting firms [14a]. **It never names cheap
  computation, open-source models, foundation models or commoditised physics.** The only two uses of
  "artificial intelligence" in the whole filing are about Verisk's own deployment of it and about
  the credentials of its staff [14a]. That is not proof of safety — a company will not advertise its
  own obsolescence — but it is evidence about how the party holding the customer-churn data frames
  the risk. Note also the stated FY2025 growth mechanism: "an annual increase in prices derived from
  continued enhancements to the models... as well as selling expanded solutions to new and existing
  customers within catastrophe and risk solutions" [14a] — **price and cross-sell, not compute
  volume.**
- **The natural experiment that settles it:** a free, open-source, industry-backed catastrophe
  modelling platform already exists. Oasis LMF — "free to use by anyone", "more than 18 suppliers
  covering over 90 models" — has been live since the mid-2010s, is actively pushed by **Aon's own
  Impact Forecasting** (Latin America rollout, 11 Dec 2025) and has live carrier adopters (Baloise)
  [8]. Over the same period Verisk Underwriting went $2,025m → $2,180m and Moody's MA Insurance went
  $550m → $598m → $685m [1][2]. **Free models were tried. They did not take the market.** The
  binding constraint is not the price of the model, so lowering it further changes nothing.
- **Incumbents are absorbing the technology, not being displaced by it:** Verisk is deploying AI
  diffusion models in cat modelling (FT, via [8]); Moody's uses CAPE Property Intelligence computer
  vision for roof condition, vegetation and defensible space at property level [8]; KCC says cat
  modelling is moving "towards physical models **enhanced by** AI" [8]. And Verisk bought the
  commoditisation layer itself: it acquired Nasdaq Risk Modelling for Catastrophes in 2025 and
  relaunched it as **Verisk Model Exchange**, "an open, multi-vendor catastrophe modeling platform"
  with "governed, vendor-neutral auditability", already signing third parties such as KatRisk [8].
  **If models commoditise, the rent migrates to the exchange, the exposure-data standard (CEDE/OED)
  and the audit layer — and Verisk owns all three.**
- **Timing and the observable trigger, if one were pitching it:** the de-rating already happened.
  Market cap **-34.6% y/y**;
  price **$175.41 at the 18 Sep 2026 close** against a 52-week range of $155.94–$253.35;
  **EV/FY26E adj. EBITDA 14.9x** on guidance of $3.19–3.24bn revenue and $1.79–1.83bn EBITDA;
  forward PE 21.5x; FCF yield 5.4%; ROIC 31.7%; beta 0.66 [11]. Rothschild & Co Redburn's 18 Jun
  2026 upgrade (Sell → Neutral) was reasoned explicitly on AI fear being "incorporated into the
  stock's valuation" [9]. **The trigger for re-rating is Q3 2026 earnings on 28 Oct 2026**, at which
  management has guided OCC growth to reaccelerate to 6–8% in H2 2026 [11]. A second, cleaner
  trigger is the FY2025 weather-frequency drag reversing: CFO Elizabeth Mann attributed FY2025's
  softness to "**a very low level of weather activity in the year**" [1] — a cyclical, mean-reverting
  headwind that the market appears to have read as structural.
- **Counter-thesis, argued at full force:** (i) Verisk's real AI exposure is **not** cat modelling
  at all — it is the *Claims* side, where property estimating (Xactimate) could in principle be
  attacked by generative-AI damage assessment, and Claims revenue **fell 0.7% in Q4 2025** [1].
  That is a genuine soft spot and it is where a bear should push. (ii) 83% US revenue concentration
  [9] means no geographic diversification if US P&C pricing turns. (iii) At 21.5x forward earnings
  with ~6% organic growth, this is not a 50%-discount-to-intrinsic-value stock in Rosenwald's sense;
  it is a quality compounder that has come back to a fair multiple, which is a weaker claim.
  (iv) The AccuLynx acquisition was cancelled and Verisk Financial and Wood Mackenzie were divested
  [9] — a shrinking perimeter can mask slowing organic growth. (v) Most seriously: **I cannot size
  the exposed revenue line**, because Verisk does not disclose it. A judge is entitled to ask what
  percentage of revenue is actually at risk and I would have to answer "the company does not say."
  **Where it lands:** the counter-thesis relocates the AI risk from Underwriting to Claims and
  weakens the valuation claim from "50% discount" to "fair multiple on a franchise with a
  misdiagnosed risk." It does not resurrect the cat-model-erosion claim.
- **Attribution test — and this is where the finding turns.** A "wrongly-punished long" requires a
  punishment attributable to the thing being analysed. I tested it with dated prices [15]:

  | Ticker | 4 Sep 2026 | 8 Sep 2026 (announcement) | 1-day % | 18 Sep 2026 | 4→18 Sep % |
  |---|---|---|---|---|---|
  | **VRSK** | 185.79 | 175.49 | -5.54 | 175.41 | **-5.59** |
  | **MCO** | 493.55 | 481.25 | -2.49 | 468.59 | -5.06 |
  | SPGI | 443.51 | 429.31 | -3.20 | 405.32 | **-8.61** |
  | FDS | 301.96 | 289.00 | -4.29 | 283.83 | -6.00 |
  | EFX | 177.05 | 171.62 | -3.07 | 158.87 | **-10.27** |
  | TRU | 79.88 | 77.65 | -2.79 | 72.43 | **-9.33** |
  | SPY | 770.19 | 765.96 | -0.55 | 761.69 | -1.10 |

  Verisk fell, but **Equifax and TransUnion — credit bureaux with no catastrophe modelling, no
  meteorology and no fluid-dynamics exposure — fell nearly twice as much**, as did S&P Global. A
  cat-model repricing would make VRSK and MCO outliers *within* the complex; they are mid-pack. The
  move is a common information-services factor.

  And the real de-rating is dated and identified: **3 February 2026**, when the complex fell on an
  Anthropic legal-AI product release — **VRSK -10.11% in a single day**, TRU -12.47%, EFX -12.11%,
  SPGI -11.27% ("its largest percent decrease since March 2020" per the WSJ), FDS -10.51%,
  MCO -8.90%, against SPY -0.85% [15][16]. **That is seven months before the OpenAI announcement and
  was triggered by contract review and compliance workflows, not fluid dynamics.**
- **Long-only expression:** **(d) unpitchable on this track — no long expression.** I had
  provisionally graded this (b) and I am withdrawing that grade. The moat survives (that part is
  well evidenced) but **the punishment is not attributable to this breakthrough**, so there is no
  Navier–Stokes dislocation to buy. Verisk remains a live (b) candidate on a *different* vector —
  the 3 Feb 2026 generative-AI information-services de-rating — but that vector belongs to whichever
  track owns the AI-services-deflation theme (B1's territory), not to a fluid-dynamics thesis.
  Pitching it here would be manufacturing exposure to justify the effort, which the metaprompt
  forbids.
- **Residual use: (c) a de-risking constraint.** The evidence in this section is worth keeping as a
  constraint on any *other* long that rests on "AI commoditises analytics". The Aon ranking, the
  Florida statutory gate and the decade-old Oasis natural experiment together say that in
  regulated, counterparty-accepted analytics, cheap compute does not dissolve moats — so any thesis
  that assumes it does needs to clear those three facts first.
- **Severity:** **thesis-grade as a kill, noise as an idea.** It is a clean negative result and is
  reported as one.
- **Evidence:** `raw/A2_test_forecast/vrsk_mco_price_reaction_test.md` [15][16];
  `vrsk_fy2025_earnings_release.md` [1]; `catmodel_moat_and_ai_adoption.md` [8];
  `aon_2025_cat_risk_survey.md` [7]; `fchlpm_model_acceptance.md` [6];
  `catmodel_regulatory_direction_check.md` [17]; `vrsk_derating_and_valuation_sep2026.md` [9][11].

### 4.1b Directed hunt for the pharma inverse — is any cat-model regulator LOWERING the bar?

A3 found that in pharma the FDA is actively dismantling a physical-evidence floor (ICH M15,
June 2026; CFD funding for generic inhalers; a 10 Sep 2026 event on modelling in place of in-vivo
testing). If the Florida Commission or the NAIC were moving the same way, my regulatory-moat
argument would collapse. **I looked for that specifically and did not find it. The evidence runs
the other way** [17]:

- **The NAIC's Catastrophe Modeling Center of Excellence is not an alternative approval route.** Its
  own FAQ states flatly: "**Models will not be reviewed**, nor would they be posted on the state
  insurance regulator-only website" [17]. The COE exists to give state regulators "technical
  training and expertise" so they can interrogate models better, and the NAIC Catastrophe Computer
  Model Handbook is being revised [17]. That raises the evidentiary burden; it does not lower it.
- **The Florida gate is statutory and on a two-year clock, and it is being renewed, not relaxed.**
  It was created by **Section 627.0628, Florida Statutes**; the Hurricane Standards Report of
  Activities as of 1 Nov 2025 documents the Commission's **twenty-eighth year**; standards are
  adopted **biennially**; 2025-Standards submissions are due **1 Nov 2026 and reviewed in 2027**
  [17]. An entrant arriving today with a better solver reaches the Florida market in 2027 at the
  earliest, and only if it passes.
- **Its reach is national.** "Organizations, agencies and regulators around the country, **including
  South Carolina, rely on the work performed by the Florida Commission**" [17].
- **The one regulator-adjacent trend runs the wrong way for the bear.** The NAIC COE reported at the
  Spring 2026 National Meeting that cat models "have not historically captured the full extent of
  severe convective storm risks", that SCS models have improved materially, and that it "expects
  insurers will begin relying on these models more frequently, **with such models likely to appear
  in rate filings**" [17]. A peril previously priced off historical experience is migrating *into*
  the modelled, filed regime — incremental licensable TAM for the accepted vendors.
- **The genuine softening pressure — open models — shifts cost onto the buyer.** The Society of
  Actuaries' 2026 review says proprietary tools are "gradually being **supplemented** by more
  transparent, open-source alternatives" — supplemented, not replaced — and that regulators
  "increasingly scrutinize exposure data quality" [17]. On Oasis LMF specifically: "requires
  engineering and modeling staff"; "**User owns validation; needs internal change control and
  oversight**" [17]. That is precisely why the free route has not taken the market: Aon's survey
  says most insurers "often do not have dedicated full-time model evaluation resources" [7], so a
  free model that transfers the regulatory-defence burden to them is *more* expensive, not less.

**Result of the hunt: the pharma inverse does not replicate.** Recorded as a deliberate, failed
search for disconfirming evidence, per the metaprompt's "prefer disconfirming evidence" rule.
Evidence: `catmodel_regulatory_direction_check.md` [17].

### 4.2 Finding A2-3 — Moody's RMS: the revenue line exists and is accelerating, but there is no pitch

- **Exposure:** Moody's Corporation (NYSE: MCO), Moody's Analytics → Decision Solutions →
  **Insurance** line of business, which contains RMS.
- **Magnitude, from the 10-K:** FY2025 MA Decision Solutions **Insurance revenue $685m**, vs $598m
  FY2024 and $550m FY2023 — **+14.5% y/y**. That is **8.9% of Moody's Corp total revenue of
  $7,718m**, 19.0% of the $3,599m MA segment and 40.5% of Decision Solutions [2].
  **Caveat that matters:** this line is the whole insurance business — RMS catastrophe models *plus*
  the AXIS life/actuarial software *plus* the acquired CAPE Analytics property intelligence. Moody's
  does not disclose catastrophe-model revenue separately, so **cat modelling is an undisclosed
  subset of 8.9% of revenue** [2].
- **Mechanism:** identical to A2-2 and it breaks at the same hop. Same Aon ranking, same FCHLPM
  gate (RMS v23 and v25 certified) [6][7].
- **Timing / counter-thesis:** there is no impairment to time. A line growing 14.5% is not being
  eroded. The honest counter-thesis to *owning* MCO here is that ratings (MIS, $4,119m, 53.4% of
  revenue) dominates the story, so a cat-model view expresses almost nothing.
- **Long-only expression:** **(d) unpitchable — no long expression.** Vectors §6 "Saturated":
  MCO is a consensus quality-compounder with no variant view available at 8.9% of revenue.
  Recorded as corroborating evidence for A2-2, not as an idea.
- **Severity:** supporting.
- **Evidence:** `raw/A2_test_forecast/mco_fy2025_10k_revenue_by_lob.md` [2].

---

## 5. PART 2b — Weather forecasting and risk data. Verdict: **the victims are private; the listed proxy is growing.**

### 5.1 Finding A2-4 — The forecasting industry that ML displaces is almost entirely unlisted

- **Exposure:** commercial NWP-derived forecasting.
- **Mechanism, which is real:** ECMWF's own AIFS has been operational since 25 Feb 2025
  (deterministic) and 1 Jul 2025 (ensemble), both upgraded to v2 on 12 May 2026, and its output is
  licensed **CC-BY — redistributable and usable commercially** [10]. ECMWF has "stopped producing
  graphical products from third-party experimental machine-learning models Aurora, FourCastNet,
  GraphCast and Pangu-Weather" [10]. World-class medium-range forecasting is now free. That is a
  genuine commoditisation event.
- **Magnitude / why there is no finding:** the total victim pool is a ~**$3.1bn** weather
  forecasting systems market, and DTN, StormGeo, Tomorrow.io (~$100m ARR, ~218 staff), The Weather
  Company (Francisco Partners) and AccuWeather are **all private** [4]. Spire Global is listed but
  is a ~$58.5m-revenue, loss-making micro-cap that restated its financials and disclosed material
  weaknesses in disclosure controls [4] — Vectors §3 and §4. **No named public company holds a
  material revenue line against this displacement.** Per the metaprompt: "No finding without a named
  public company and a named revenue line."
- **Counter-thesis / Jevons check (dimension 6):** the displacement is *also* weaker than it looks,
  because AIFS is "**initialised from the ECMWF operational analysis**" [10], i.e. the ML forecast
  still sits downstream of physics-based data assimilation, which still consumes ~5×10³ CPU
  node-hours/day at ECMWF and still needs observations [10]. Baron Weather states it plainly:
  "For now, AI forecasting sits downstream of traditional data assimilation" [10]. ECMWF: "Whether
  forecasts are physics-based, AI-enabled or hybrid, their quality still depends on accurate
  observations" [10]. **The scarce input is observation, not compute.**
- **Long-only expression:** **(d) unpitchable — no long expression.**
- **Severity:** supporting (it is a clean negative result).
- **Evidence:** `raw/A2_test_forecast/ml_weather_nwp_status_2026.md` [10];
  `ownership_traces_ricardo_mts_element_avl_fev.md` [4].

### 5.2 Finding A2-5 — Vaisala: the complement, not the victim — but not a pitch either

- **Exposure:** Vaisala Oyj (Nasdaq Helsinki: VAIAS), Weather and Environment business area.
- **Mechanism (and it runs the *wrong way* for the bear):** Vaisala sells the observation
  instruments — radiosondes, radars, lidars, aviation and road-weather sensors — that every ML
  forecast is ultimately initialised from, plus the Xweather subscription that packages forecast
  data into decisions. Free AIFS output raises the value of the input and of the packaging; it
  attacks neither.
- **Magnitude, from the release:** FY2025 net sales **€596.9m** (+6%, +7% cc), EBITA **€94.2m**
  (15.8%), EBIT €85.1m [13]. Weather and Environment net sales **grew 4% in constant currencies**;
  **"Subscription sales increased by 50% in 2025, with organic growth in constant currencies at
  11%"** [13]. Q1 2026: "The Xweather business area continued its **double-digit growth** in
  constant currencies" [13]. The company's actual 2025 headwind was the collapse of the
  **renewable-energy / wind-resource-assessment market** (~€20m negative net sales impact) [13] —
  nothing to do with ML forecasting. FY2026 guidance: net sales €600–630m, EBITA €95–110m [13].
- **Counter-thesis for owning it:** the observation-complement argument is real but it does not
  produce an attractive security. FY2026 guidance implies **0.5–5.5% revenue growth** on a ~16%
  EBITA margin hardware-and-subscription hybrid; order intake **fell 9% in 2025** [13]; the growth
  driver management actually points to is Industrial Measurements into data centres, semiconductors
  and life science, which is again a different track. And it is a EUR reporter: Vectors §1 requires
  the FX to be addressed, and an unhedgeable ~16%-margin €600m business is a poor vehicle for
  carrying that risk.
- **Long-only expression:** **(d) unpitchable — no long expression.** The *argument* (observations
  are the bottleneck; the ML forecast is downstream) is worth keeping as a de-risking point for any
  other weather-linked long.
- **Severity:** supporting.
- **Evidence:** `raw/A2_test_forecast/vaisala_fy2025_release.md` [13];
  `ml_weather_nwp_status_2026.md` [10].

---

## 6. Jevons check (dimension 6), stated explicitly

The metaprompt requires "demand falls" to be the claim carrying the burden of proof. On this track
it carries it and fails, twice:

- **Forecasting:** ECMWF gives away a state-of-the-art ML forecast under CC-BY [10], and in the same
  period Vaisala's weather subscription revenue rose 50% (11% organic cc) [13]. Free raw forecasts
  raised demand for packaged, decision-ready weather intelligence. **Jevons regime.**
- **Catastrophe modelling:** a free open-source platform with 18 suppliers and 90+ models has been
  available for a decade [8], and over that period both incumbents' insurance lines compounded
  (Verisk Underwriting +7.7% in FY2025; Moody's MA Insurance +14.5%) [1][2]. **No displacement
  regime is observable at all.**

---

## 7. Second-order and dual-use (dimension 8), bounded

Two risk notes, not thesis:

1. **Model monoculture.** If reinsurers largely license only RMS or Verisk [7], and if both
   increasingly feed the same AI-derived hazard and property layers (Fathom-style diffusion hazard,
   CAPE-style computer-vision exposure) [8], correlated model error becomes a systemic risk to
   industry capital adequacy. The Federal Reserve working paper "Model Uncertainty and the Pricing
   of Hurricane Risk" (FEDS 2026-016) is the place to pursue this; I did not read it and do not rely
   on it. **Flagged, not used.**
2. **Verification burden.** The FAA's own relief is conditional on *validated* CFD [5]. As
   certification-by-analysis expands, the bottleneck moves from running the simulation to
   *qualifying* it — which increases demand for validation data, i.e. for physical test. This is the
   dual-use twist that makes the physical-test inversion (§3.1) durable.

---

## 8. Answers to the three questions I was sent to answer

1. **Does the Verisk / Moody's-RMS moat survive commoditised physics?** **Yes, and the evidence is
   not close.** Buyers rank computational speed 10th of 13 (1.19 vs 3.47 for methodology
   reasonableness) [7]; the gate on commercial use in Florida is an administrative letter of
   acceptability, not a solver benchmark [6]; reinsurer acceptance is the real distribution channel
   and reinsurers license RMS or Verisk [7]; a free open-source alternative has existed for a decade
   and holds under 5% take-up for every challenger [7][8]; and both incumbents are absorbing AI
   into their models while Verisk has bought the multi-vendor exchange layer outright [8].
2. **Is physical test already irreducible?** **Substantially yes.** The development-test
   displacement happened twenty years ago. What remains is gated by 40 CFR Part 1066 and equivalent
   regimes, and the one live regulatory relaxation (FAA NPRM, 26 Jun 2026) trades a single
   flight-test point for *validated* CFD while leaving the adjacent test mandatory [5]. This is a
   moat inversion, and it kills the leg.
3. **Which name reaches a long-only expression?** **None.** This track returns a negative result.
   Verisk was my candidate and it fails the attribution test: the moat survives, but the de-rating
   is a generative-AI information-services de-rating dated **3 February 2026** — seven months before
   the announcement, triggered by a legal-AI product release — in which VRSK fell 10.11% *alongside*
   TransUnion -12.47%, Equifax -12.11% and S&P Global -11.27%, none of which has any fluid-dynamics
   exposure [15][16]. In the announcement window itself Verisk underperformed the market but
   **outperformed those same peers**. There is no Navier–Stokes dislocation to buy. Everything else
   is dead (Ricardo), private (Element, AVL, FEV, DTN, StormGeo, Tomorrow.io, The Weather Company),
   buried in a conglomerate with no disclosed revenue line (MTS inside ITW), or a different thesis
   wearing this one's clothes (Horiba, Vaisala). **Best residual use of this track is (c): a
   de-risking constraint on any other long that assumes cheap compute dissolves an analytics moat.**

---

## 9. Plain-language close

Two things were supposed to be threatened here: the companies that test physical objects, and the
companies that sell forecasts and disaster models. Neither is.

Testing real hardware did lose most of its work to computers — but that happened in the 1990s and
2000s. What is left is the part the law requires: an emissions number has to come off a real car on
a real dynamometer, and an aeroplane still has to fly. Regulators, not engineers, decide how much of
that there is, so making the software cheaper does not shrink it. The companies that would have been
the victims are mostly not buyable anyway: Ricardo was taken over and delisted last October, and
AVL, FEV and Element are private.

The disaster-modelling business looked more promising and turned out to be the strongest evidence
against the whole idea. Aon asked insurers what actually decides which catastrophe model they buy.
Computing speed came tenth out of thirteen. What comes first is whether the method is credible,
whether it matches real past losses, whether it is transparent, and — crucially — whether your
reinsurer will accept it. On top of that, Florida will not let you use a hurricane model in a rate
filing at all until a state commission issues a letter saying you may. A free, open-source
catastrophe modelling platform has been sitting there for ten years with ninety models on it, and
the challengers still have under 5% of the market while Verisk and Moody's kept growing. Cheap
physics attacks none of that.

**So I went looking for the inversion: a good business wrongly sold off as a victim.** Verisk
looked exactly like it. Its market value is down about 35% in a year on a fear that AI will dissolve
its data moat, while the business grew 5.8% organically last quarter, lifted its margin to 57.5%,
grew free cash flow 58% and is buying back stock, at roughly 15x this year's guided EBITDA with a
5.4% free-cash-flow yield and a 32% return on capital.

**Then I checked whether the selling had anything to do with this discovery, and it does not.** The
fall happened on 3 February 2026 — seven months before the Navier–Stokes announcement — on the day
an AI company launched a *legal* assistant. Verisk dropped 10% that day; so did TransUnion, Equifax
and S&P Global, which drop by more. Those are credit bureaux and a ratings company. They do not
model hurricanes, they do not employ meteorologists, and no amount of cheap fluid dynamics touches
them. They were all sold for the same reason: a general fear that AI eats companies whose product is
analysis. When the actual Navier–Stokes news broke in September, Verisk fell less than they did.

That matters, because the whole appeal of a "wrongly punished" idea is that you can name the
punishment and explain why it is wrong. Here I can explain why the fear is wrong for catastrophe
models — insurers rank computing speed tenth out of thirteen reasons for choosing one, Florida will
not let you use a hurricane model in a rate filing without a state licence that Moody's has had to
renew sixteen times for a single model, and a free open-source alternative has been sitting there
for a decade while challengers stayed under 5% of the market — but I cannot honestly claim the
market punished Verisk *for that*. It punished a whole sector for something else, and Verisk was
not even the worst-hit. Buying it here is a bet on the AI-and-information-services argument, not on
this equation.

**So the honest answer is that this track produces no trade.** The physical testing idea dies
because the law, not the software, decides how much testing happens, and because the companies that
would have been hurt have mostly been taken private or taken over. The disaster-modelling idea dies
twice over: the moat is not made of physics, and the stock was not sold because of physics. What the
work is worth keeping for is the opposite purpose — as a check on anyone else's pitch that assumes
cheap computing dissolves an analytics business. In regulated markets where a counterparty has to
accept your numbers, it does not. And the proof itself reaches none of this: it describes a vortex
about seventy nanometres across, roughly the distance an air molecule travels between collisions,
and Terence Tao said five days before it was announced that a result of exactly this kind "would not
radically transform the way we would, for instance, model weather prediction or climate change".

---

## Citations

| # | Source | Raw file |
|---|---|---|
| [1] | Verisk, "Verisk Reports Fourth-Quarter and Full-Year 2025 Financial Results", press release 2026-02-18. https://s29.q4cdn.com/767340216/files/doc_news/Verisk-Reports-Fourth-Quarter-and-Full-Year-2025-Financial-Results-2026.pdf | `vrsk_fy2025_earnings_release.md` |
| [2] | Moody's Corporation FY2025 Form 10-K, filed 2026-02-18, revenue-by-line-of-business detail (R57). https://www.sec.gov/Archives/edgar/data/1059556/000162828026009136/mco-20251231.htm | `mco_fy2025_10k_revenue_by_lob.md` |
| [3] | HORIBA, Ltd., "Summary of Consolidated Financial Statements for the Year Ended December 31, 2025 (Japanese GAAP)", 2026-02-12. Via https://www.marketscreener.com/news/horiba-summary-of-consolidated-financial-statements-for-the-year-endeda--ce7e5dd8df8bfe23 | `horiba_fy2025_tanshin.md` |
| [3a] | HORIBA, "Updates Mid-Long Term Management Plan (MLMAP2028)", 2026-08-07, and H1 FY2026 tanshin segment guidance (2026-08-07). https://static.horiba.com/fileadmin/Horiba/Company/News_and_Events/News/IR/20260807_NE_en_Mr6.pdf ; https://www.marketscreener.com/news/horiba-summary-of-consolidated-financial-statements-for-the-six-months-endeda--ce7859d8db89f124 | `horiba_fy2025_tanshin.md` (addendum) |
| [4] | Ownership traces: Ricardo/WSP, MTS/Amphenol/ITW, Element/Temasek, AVL, FEV, DTN, StormGeo, Tomorrow.io, The Weather Company, Spire Global. Multiple primary sources listed in the file. | `ownership_traces_ricardo_mts_element_avl_fev.md` |
| [5] | Regulator-mandated physical test: 40 CFR Part 1066 (eCFR); FAA NPRM "Transport Airplane and Propulsion Certification Modernization", 2026-06-26 (govinfo full text); NASA CR-20210015404; Aerospace America; Aerospace Testing International (DLR); AVL and Horiba product pages. | `regulatory_mandated_physical_test.md` |
| [6] | Florida Commission on Hurricane Loss Projection Methodology — model submissions, model acceptability, June 2025 meeting summary; Moody's RMS v23/v25 certification; Insurance Journal 2025-06-12. | `fchlpm_model_acceptance.md` |
| [7] | Aon, "2025 Global Catastrophe Risk Management Survey", 2025-08-06. https://www.aon.com/getmedia/8d001a7c-277d-4833-a1af-1c2ae7e37384/20250806-global-catastrophe-risk-mgmt-survey.pdf | `aon_2025_cat_risk_survey.md` |
| [8] | Cat-model moat, Oasis LMF open source, Verisk Model Exchange / KatRisk, Moody's CAPE AI, Fathom/Verisk diffusion models (FT via AI Weekly), KCC via Reinsurance News, Actuaries Institute CARS 2026 panel. | `catmodel_moat_and_ai_adoption.md` |
| [9] | VRSK AI-disruption narrative: Rothschild & Co Redburn upgrade 2026-06-18 (via GuruFocus); Tickeron; SimplyWall.st. **Aggregator sources — used only as evidence of market narrative.** | `vrsk_derating_and_valuation_sep2026.md` |
| [10] | ECMWF AIFS Machine Learning data; ECMWF "From space to forecast" (2026); ECMWF "Machine learning opens new opportunities for global reanalysis" (2026); arXiv 2601.17636v2 (HealDA); Baron Weather. | `ml_weather_nwp_status_2026.md` |
| [11] | Verisk market data and Q2 2026 8-K (2026-07-29). https://stockanalysis.com/stocks/vrsk/ ; https://stockanalysis.com/stocks/vrsk/statistics/ ; https://s29.q4cdn.com/767340216/files/doc_financials/2026/q2/2Q-2026-8-K.pdf | `vrsk_derating_and_valuation_sep2026.md` |
| [12] | HORIBA market data and valuation, close 2026-09-18. https://stockanalysis.com/quote/tyo/6856/statistics/ | `horiba_fy2025_tanshin.md` (addendum) |
| [14] | Agent 0, `navier_stokes/01_Claim.md`, and its raw captures `raw/00_claim/terence_tao_mathstodon_thread_2026_09_03.md` (Tao, 2026-09-03) and `raw/00_claim/nature_what_does_that_mean_for_physics.md` (Karniadakis via Nature). **Cited only to establish that the PROOF reaches nothing on this track — never as evidence for the ML-surrogate trend.** | `raw/00_claim/` (Agent 0) |
| [14a] | Verisk Analytics FY2025 Form 10-K, full-text scan: segment disclosure, competitor section, AI language. https://www.sec.gov/Archives/edgar/data/1442145/000143774926004452/vrsk20251231_10k.htm | `vrsk_fy2025_10k_segment_disclosure_check.md` |
| [15] | Daily adjusted closes for VRSK, MCO, SPGI, ICE, FDS, EFX, TRU, ACN, SPY pulled 2026-09-19 from `query1.finance.yahoo.com/v8/finance/chart/<ticker>`; announcement-window and 3 Feb 2026 event-study tables computed from them. | `vrsk_mco_price_reaction_test.md` |
| [16] | Wall Street Journal live markets coverage, "Data-Provider Stocks Tumble on AI Competition Fears", 2026-02-03. https://www.wsj.com/livecoverage/stock-market-today-dow-sp-500-nasdaq-02-03-2026/card/data-provider-stocks-tumble-on-ai-competition-fears-C97KvtPTsT9H3joFwS7C | `vrsk_mco_price_reaction_test.md` |
| [17] | Regulatory-direction hunt: NAIC CIPR "Catastrophe Models (Property)" and Catastrophe Model Center of Excellence FAQ; Mayer Brown, NAIC Spring 2026 National Meeting highlights (Mar 2026); SOA Research Institute, "Catastrophe Modeling Insights" (2026); Council Fire, "Catastrophe Modeling And Risk: Guide 2026"; FCHLPM Hurricane Standards Report of Activities as of 1 Nov 2025 and model-submissions page; South Carolina DOI explainer. | `catmodel_regulatory_direction_check.md` |
| [13] | Vaisala Oyj, Financial Statement Release January–December 2025, 2026-02-12; Interim Report January–March 2026, 2026-04. | `vaisala_fy2025_release.md` |
