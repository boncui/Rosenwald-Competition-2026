# 02 — Transmission

Metaprompt dimension 2: trace the path from the result to a line on someone's income statement,
naming each hop. Two candidate paths were researched on strictly separate evidence, per the
proof-vs-solver firewall. **They reach opposite verdicts.**

---

## Path A — the PROOF to a P&L

**Verdict: there is no path. Reported as a negative result, per the metaprompt's Rules.**

Evidence base: `01_Claim.md` and `raw/00_claim/` only. No file cited here appears in Path B.

| Hop | Status |
|---|---|
| 1. A forced finite-time singularity exists on ℝ³ from rest | Established, Lean-checked, review **self-assessed** [01_Claim] |
| 2. Therefore some engineering workflow changes | **FAILS** |

Hop 2 fails on direct practitioner testimony. Roughly fifteen named practitioners were searched
for disconfirmation and none was found:

- **Tao**, 3 Sep 2026, five days *before* the announcement: the regularity problem "is not important
  for its direct physical application… Computational fluid dynamics is already a mature subject…
  would not radically transform the way we would, for instance, model weather prediction or climate change."
- **CloudHPC**, a vendor that sells CFD compute by the hour and is commercially incentivised to hype
  it, testifying against interest: "For engineering simulation, essentially nothing changes. Finite
  volume solvers never relied on global regularity of the continuum model in the first place… a
  mathematical pathology, not a condition that arises around a heat exchanger at Reynolds number 10⁵."
- **Karniadakis** supplies the physical reason: the singularity forms at a vortex width of **~70 nm**,
  about the mean free path of an air molecule — below the scale at which the continuum assumption
  underlying Navier–Stokes holds at all. The blowup lives in a regime no engineer ever modelled.
- **Beroz** (CEO, ReynKo, a turbulence engineering firm), asked what it means for engineering: **"not much."**

Corroborating, weakly: no CFD vendor — Ansys, Siemens, Cadence, Altair, Dassault, Hexagon — has
commented publicly at all, and neither Synopsys's Q3 FY2026 call (2026-08-26) nor Cadence's Q2 2026
prepared remarks (2026-07-27) mentions it.

**Market confirmation.** Five tracks independently checked for repricing and found none. Synopsys
+26% over 30 days; Cadence at a record $8.1bn backlog; GE at 34.9x forward with EV/EBITDA 149%
above its own median six to nine days after the announcement; Safran near 52-week highs. Verisk
fell 5.6% in the announcement window while Equifax and TransUnion — **zero** fluid-dynamics
exposure — fell 10.3% and 9.3%. A Navier–Stokes repricing would make the fluids-exposed names
outliers. They are mid-pack or better.

> **Quarantine note.** Beroz separately says a new airplane costs ~$30bn and "roughly half the time
> and half the cost is spent… in the wind tunnel—and the only reason you're doing that is that the
> software sucks." That is a claim about CFD software quality, not a consequence of this theorem,
> and the same speaker said the proof means "not much." It belongs to Path B only. Track A1 caught
> itself laundering proof-side reasoning into a commercial argument in the *flattering* direction and
> removed it; that correction is preserved in `03_Exposure_A_Fluids.md` §6.

---

## Path B — the METHOD to a P&L

**Verdict: a real path, but it is not this proof's path, and its timing sits outside a one-year horizon.**

Evidence base: `04_Exposure_B3_compute.md`, `04_Exposure_B1_services.md`, `04_Exposure_B2_knowledge.md`
and their raw directories. Cites no Path A source.

| Hop | Status |
|---|---|
| 1. ~10,000 agents × 88h produced a frontier result for ~$7M retail / ~$1M loaded | Established [B3] |
| 2. The architecture is parallel search **plus a cheap mechanical verifier** (Lean) | Established [B3] |
| 3. Therefore work carrying a cheap verifier is attackable | Holds — formal maths, code, chip design |
| 4. Therefore work *without* one is attackable | **FAILS** |
| 5. Timing | **2027–2028, outside a one-year holding period** |

Hop 4 is the load-bearing limit. McGreivy: "Anything which can be computationally verified can be
used as a reward function in RL… You cannot spawn ten thousand copies of an admin task and let a
compiler pick the winner, because nothing tells you which one is right." Production CFD is not
attackable this way — residual convergence is not physical validity, and turbulence closures are
empirical. Neither is clinical, regulatory or most enterprise work.

Hop 5 dates the risk. McGreivy expects LLMs to begin inventing state-of-the-art numerical methods
"sometime in the next year or two" — 2027–2028. A further constraint: the binding limit today is
**access, not price**. The model is unreleased; nobody can rent 10,000 copies at any price.

**The event was a compute sink, not a compute saving:** ~400,000 GB200 GPU-hours, no code, no
benchmark, no speedup. The circulating ">$40M" figure is the high-input case applied to all six
Millennium problems plus warm-ups, not to this proof.

---

## What this means for the vector

Path A is empty. Path B is real but early, bounded to verifier-rich domains, and access-constrained.

**Neither path reaches a 2026 income statement.** Every long candidate surfaced by this project
(see `06_Long_only_expressions.md`) traces to a *different* and dateable event — the 2026-02-03
information-services repricing — not to either path above.
