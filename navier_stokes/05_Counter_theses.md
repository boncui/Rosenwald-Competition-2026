# 05 — Counter-theses

The arguments that killed findings in this project, kept together so nothing gets re-derived and
no pitch built on this research walks into one unprepared. Every item below defeated a live claim.

---

## 1. Jevons: "demand falls" carried the burden and failed everywhere it was tested

The metaprompt made "demand falls" the claim requiring proof. It was tested in four industries and
failed in all four.

| Domain | Free or cheap alternative arrived | What happened |
|---|---|---|
| CFD software | OpenFOAM, SU2 — free, production-grade, **20 years** | Market $10.0bn → $10.9bn (+8.8%) → $11.67bn (+8.5%) [A1, CIMdata] |
| Cat modelling | Oasis LMF — free, open-source, 90+ models, **a decade**, pushed by Aon itself | Every challenger under 5% take-up; Verisk Underwriting $2,025m → $2,180m; Moody's insurance $550m → $685m [A2] |
| Weather | ECMWF AIFS operational since 2025, output **CC-BY, commercially redistributable** | Vaisala Xweather subscriptions **+50%** in 2025 [A2] |
| Scholarly publishing | arXiv 1991, PMC 2000, NIH mandate 2008, Sci-Hub 2011, Plan S 2018 | RELX STM H1 margin **35.8% (2019) → 37.9% (2026)** [B2] |

These are not analogies. Each is a completed natural experiment in the exact industry at issue.

**But the pass-through breaks before it reaches the software P&L.** Ansys's own marketing: running
on 2,000 cores rather than 20 carries "a cost premium of only 1.5X — and not the 100X", and 2025 R1
"CFD HPC Ultimate" charges the same licence on one GPU or a large cluster. Faced with GPU
acceleration, the market leader **switched the volume meter off**. Ansys standalone grew
+10.9/+13.4/+8.3/+9.9/+12.1% FY2020-24 with no inflection through that window.

**Resolution of the A1/B3 conflict** (verified by the coordinator, `raw/B3_compute/35_…`): Synopsys
CEO Ghazi did say "we sell and we capture the entire value and uplift of the GPU" — the quote is
genuine, confirmed in four independent transcripts. But his next sentence is "the large deal is
large because of the benefit to the customer": value-based pricing on one negotiated deal, not a
consumption meter. Both findings stand once the two pricing regimes are separated. **Jevons operates
on run-volume and is absorbed before it reaches software revenue.**

---

## 2. The no-repricing pattern — the single most important finding in the project

Five tracks checked independently. The market has not repriced *anything* on this news.

| Name | Position after the announcement |
|---|---|
| Synopsys | **+26%** over 30 days |
| Cadence | Record $8.1bn backlog, +24% y/y |
| GE Aerospace | 34.9x forward, EV/EBITDA **149% above its own median** |
| Safran | Near 52-week highs |
| Verisk | −5.6% — while **Equifax −10.3% and TransUnion −9.3%**, with zero fluids exposure |

The Verisk line is the decisive one. A Navier–Stokes repricing of catastrophe models would make
VRSK an outlier *within* its complex. It is mid-pack, behind two credit bureaux.

**Consequence: expression (b), the wrongly-punished long, is structurally unavailable on this
vector.** There is no dislocation to buy, because nothing was dislocated. Every (b) candidate this
project surfaced was punished by something else.

---

## 3. Moat inversion: cheap analysis strengthens the corpus holder — where a regulator gates it

Confirmed in direction, in three independent regulated industries:

- **Aerospace.** FAR 33.87 requires 150 hours of physical engine operation; 33.94 permits analysis
  to replace **one** blade-out test, and only where based on "rig testing, component testing, or
  service experience" — **the FAA's own route to simulation credit runs through a proprietary
  validated corpus.** NASA: "CFD has not been directly utilized for engine CbA applications." Title
  14 was last amended 2026-09-15, nine days after the announcement. Nothing changed.
- **Catastrophe risk.** Florida acceptance attaches to the model *and the software build* — Moody's
  holds **sixteen** separate acceptance letters for one model across builds at six-week intervals.
  A compliance treadmill whose cost scales with incumbency, not compute. Aon's survey ranks
  "computational speed and ease of use" **10th of 13** selection criteria.
- **Nuclear.** The NRC accepts Westinghouse code qualification against validation data it agrees to
  keep permanently secret, published "Non-Proprietary Class 3" with the data redacted. A federal
  regulator formally treating a private corpus as a protected competitive asset.

**Scope limit, and it matters.** This is not a law about data. HVAC is the control group and it
fails — AHRI certification is voluntary, cycles are short, the physics is tractable, and there is
no moat. **The inversion holds only where a hard regulatory tier exists.**

---

## 4. Counter-theses that survived, and that any pitch inherits

**Illumina — volunteered by B3 against its own thesis.** Cost per genome collapsed for a decade
while Illumina went $4.58bn (2022) → $4.34bn (2025): four flat-to-down years. If a customer's
budget is appropriation-shaped rather than price-shaped, making the input cheaper means *fewer*
dollars, not more. Anyone building on the Jevons conclusion inherits this.

**Global Crossing.** IP transit fell from $1,200/Mbps to under $1. Traffic doubled annually,
exactly as forecast. WorldCom and Global Crossing went bankrupt **on correct demand forecasts.**
Being right about demand is not being right about a stock.

**The "AI deflation" attribution problem** [B1]. An Axis Capital analyst, on an HCLTech call, on
management's claimed AI-driven pricing deflation: "that's kind of what we see anyway even before
AI. In renewal deals, we were seeing 10% to 15% in pricing over the life of the deal… So it doesn't
look like with AI, there is anything significantly different, right?" Nobody has produced a number
separating AI deflation from twenty years of ordinary renewal give-back.

**The trend-predates-the-story problem, applied twice by the agents to their own work.** B3
self-audited and found CAE/EDA growth predates the AI narrative, downgrading it to defensive
evidence only. B2 found scholarly output compounding at 4–6.5% a year since long before ChatGPT and
concluded that **AI roughly doubled an already-favourable trend; it did not create it.**

**Gross Jevons, net unknown** [B2]. Submissions to RELX rose +20% while output rose +10% — the
signature of a rising rejection rate. Screening cost is borne on submissions; revenue is earned on
acceptances. **No publisher discloses screening cost.** The volume story is real on the top line and
unquantified on the bottom.

**The professional-engineer stamp protects the wrong part of the pyramid** [B1]. No AI can sign and
seal — but the seal requires a licensed human to *review*, not a given number of engineer-hours
behind it. One PE instead of five EITs plus a PE.

**Formal verification relocated trust, it did not eliminate it** [B2]. Palomar's nine founding
mathematicians state their registry is "not a peer-reviewed journal" and falls "well short of what a
proper human peer review would give." The proof at the centre of this project remains
`review: status: "self-assessed"`, and lean-dojo still lists Navier–Stokes as **Open**.

---

## 5. Disclosure walls hit repeatedly — a finding in itself

Four tracks independently could not size their exposure because the revenue line does not exist:

| Track | What could not be sized |
|---|---|
| A1 | No vendor has **ever** published a CFD revenue line; Ansys filed as one segment its whole public life |
| A2 | Verisk's 10-K (all 409,924 characters scanned) has no dollar line for catastrophe modelling |
| A3 | No aerospace company discloses a test-data corpus; there is no revenue line for it |
| B2 | RELX does not split Primary Research from Databases & Tools |

In every case the agent **refused to construct an estimate**. Under the metaprompt's "no revenue
line, no finding" rule, several otherwise-plausible theses are unconstructible from public
disclosure — not merely unproven. That is a structural obstacle to pitching this space at all, and
it is worth saying out loud to a judge who asks why the analysis stops where it does.
