# Vector: AI-driven mathematical advance and the repricing of cryptographic trust

*Drafted 2026-09-19. Companion to [Vectors.md](Vectors.md). Every candidate below has been run through that file's do-not-analyze filter; where a name fails or partially fails, it says so.*

---

## 0. Why we abandoned Navier-Stokes

The original brainstorm vector was "ChatGPT solved Navier-Stokes; what does AI solving mathematics do to the economy." We looked at it and moved off it. The reasoning matters, because a judge may ask why we chose this framing.

**The Clay Millennium problem for Navier-Stokes is global existence and smoothness of solutions to the 3D incompressible equations.** A proof would establish that solutions never blow up in finite time. It would **not** produce a faster solver, a closed form, or a better turbulence closure model. Engineers have computed with these equations for sixty years without the proof. The morning after a proof, nothing changes in any commercial CFD workflow.

Put plainly: **regularity of fluid flow harms no one.** There is no institution whose solvency depends on Navier-Stokes being unresolved. There is no asset whose value is a function of that open problem. The headline is spectacular and the economic transmission is close to nil. A pitch built on it is a narrative pitch, and per [Vectors.md](Vectors.md) §4 and the Meli profile, a narrative pitch with no cash-flow anchor is exactly what this panel punishes.

**Cryptography is the opposite case.** There is precisely one branch of mathematics whose *unsolved status is load-bearing for the world economy*: the hardness of integer factorization and the discrete logarithm problem. RSA, Diffie-Hellman and elliptic-curve cryptography are not merely useful applications of hard math. They are a standing bet that those problems stay hard. Every TLS session, code signature, firmware update, EMV payment card, passport chip, SIM card and blockchain signature rests on that bet.

If AI materially advances number theory, the damage is not metaphorical and not gradual. It is a solvency event for the trust layer of the internet. **That is the "changes reality" scenario the original brainstorm was reaching for, and it is investable in a way Navier-Stokes is not.**

We keep one idea from the Navier-Stokes work, because it carries over and it is the spine of this thesis:

> **When solving becomes cheap, value migrates from the solver to the validator.** If mathematical hardness stops being a reliable moat, trust has to be re-anchored in things that are not math: tamper-resistant hardware, physical key custody, certificate infrastructure, audited identity, and regulatory certification.

---

## 1. What actually breaks, and what does not

This section exists because the rules require "institutional details... which the judges may be less familiar with," and because getting it wrong in front of Meli would be fatal.

| Primitive | Status under a factoring/DLP break | Notes |
|---|---|---|
| **RSA** (key exchange, signatures) | **Broken** | Shor's algorithm, or any classical subexponential-to-polynomial advance |
| **Elliptic-curve: ECDSA, ECDH, Ed25519** | **Broken** | Same. This is most of modern TLS, SSH, code signing, and all major blockchain signatures |
| **Finite-field Diffie-Hellman** | **Broken** | |
| **AES-128 / AES-256** (symmetric) | **Survives** | Grover's algorithm gives only a quadratic speedup. AES-256 retains ~128-bit security. Doubling key length is a sufficient response |
| **SHA-2 / SHA-3** (hashing) | **Largely survives** | Same quadratic-speedup logic for preimage resistance |
| **Lattice-based PQC** (ML-KEM, ML-DSA) | **Unknown** | This is the actual tail risk. The replacement standards rest on *different* hard problems (Module-LWE), not proven-hard ones |

**The critical distinction: the break is asymmetric-only.** Bulk encryption survives; key establishment and identity do not. That means the fix is not "encrypt harder," it is a **forced global replacement of every key-exchange and signature mechanism in existence** — which is a hardware, certificate and integration problem, not a software patch. That is where the money goes.

**Two threat paths, and only one is priced:**

| | **Path 1: Quantum ("Q-Day")** | **Path 2: Classical / AI-driven advance** |
|---|---|---|
| Mechanism | Shor's algorithm on a cryptographically relevant quantum computer | AI finds a subexponential classical attack on ECDLP, or a structural break in lattices |
| Timeline | Telegraphed. Consensus 2030-2035+ | **No timeline. No warning. No runway.** |
| Market pricing | **Priced.** Migration is budgeted, standardized and scheduled | **Not priced.** No sell-side model contains it |
| Probability | Moderate and rising | Low |
| Shape of payoff | Slow annuity | Compression of a ten-year migration into a panic |

**This is our variant perception.** The consensus owns Path 1 as a decade-long, orderly, budgeted migration. Nobody is underwriting the possibility that the same AI systems now producing research-grade mathematics compress that schedule without notice. Same beneficiaries, radically different urgency, radically different payoff.

---

## 2. Why the trade works even if we are wrong about AI

This is the most important paragraph in the document, and it should be the most important slide in the deck.

**We do not need Path 2 to happen.** The spending is already legally mandated, dated, and under way because of Path 1 and because of "Harvest Now, Decrypt Later" — adversaries are recording encrypted traffic today to decrypt after the break. That makes the damage *retroactive*, which is why migration budgets are being spent now rather than in 2033.

So the structure is:

- **Floor:** regulatory deadlines already force a multi-year hardware and certificate refresh cycle, in cash-flowing incumbents with existing earnings.
- **Free option:** if AI accelerates the break on Path 2, that refresh goes from scheduled to emergency.

Dinan on Medivation: *"a couple of bucks down, but there's a lot of money up... you had a floor."* This is that structure. It is also the direct answer to his *"hope is not a strategy"* — the thesis does not require the speculative event to pay.

### Dated catalysts (the event calendar)

| Date | Event | Why it matters |
|---|---|---|
| Aug 2024 | **NIST FIPS 203 / 204 / 205 finalized** (ML-KEM, ML-DSA, SLH-DSA) | Standards exist, so migration is no longer optional or vague |
| Mar 2025 | HQC selected as backup KEM | *verify current status* |
| Nov 2024 | **NIST IR 8547 (draft):** RSA-2048 and ECDSA-256 **deprecated after 2030, disallowed after 2035** | A hard federal sunset date on every currently deployed public-key system. *Verify whether finalized* |
| — | **NSA CNSA 2.0**: PQC mandated across national security systems, phased to 2033 | Binds the defense supply chain and everyone selling into it |
| Dec 2022 | Quantum Computing Cybersecurity Preparedness Act; OMB M-23-02 | Requires federal cryptographic inventory (CBOM) — the discovery phase that precedes spending |
| Apr 2024 → | **EU Commission Recommendation / ENISA roadmap**: member states begin migration by end-2026, high-risk systems complete by 2030 | Parallel non-US mandate. Relevant to our European candidates |
| Apr 2025 | **CA/Browser Forum ballot SC-081**: TLS certificate lifetimes fall to 200 days (2026), 100 (2027), **47 days (2029)** | Independent of PQC entirely. Mechanically multiplies certificate operations ~8x. A second, already-certain tailwind |

Note the last row. **Even with zero progress in quantum computing and zero AI mathematics, certificate volume is contractually going up by roughly an order of magnitude.** That is a fact, not a forecast.

---

## 3. Where the value goes

| Layer | What it is | Investability |
|---|---|---|
| **A. HSMs & secure elements** | Tamper-resistant physical key custody. **Must be physically replaced** for PQC — larger keys, new algorithms, new firmware | **Best.** Hardware refresh under regulatory mandate. Mostly listed |
| **B. Certificate authorities / PKI / machine identity** | Every certificate reissued; lifetimes collapsing independently | **Thesis-pure but mostly private.** See §5 |
| **C. Network & encryption-in-transit** | VPN, firewall, tunnel vendors shipping PQC-capable stacks | Live. Diluted — PQC is a small part of each story |
| **D. Payments & EMV** | Every card, terminal and payment HSM uses RSA/ECC. Re-issuance is physical and mandated | Live, converges with A |
| **E. Telecom SIM / eSIM / 5G auth** | Every SIM holds keys | Live, converges with A |
| **F. Audit, inventory & certification** | CBOM discovery, migration program management, re-certification | Live. The "validator" layer from §0 |
| **G. Losers (for the variant-view slide)** | Assets whose value rests on ECDSA holding: blockchain signatures; long-dated encrypted archives (health, legal, government); legacy PKI-dependent models | Naming these establishes we understand the stakes |

---

## 4. Shortlist, scored against all five judges

Per the brief: this is cooked for five people, not one. No name is optimized for a single judge.

| | **Infineon** (IFX.DE) | **Thales** (HO.PA) | **Check Point** (CHKP) | **STMicro** (STM) | **Accenture** (ACN) |
|---|---|---|---|---|---|
| **Thesis link** | Secure elements, TPMs, smartcard/SIM chips. PQC-ready parts shipping. Segment: Connected Secure Systems | Thales Luna HSMs + payShield: #1 in HSMs globally. Digital identity | PQC-capable gateways; founder-led security incumbent | Secure MCUs, smartcard, automotive security | CBOM discovery + migration program management at scale |
| **Rosenwald** — discount, owner-operator, catalyst | ⚠️ Cheap and cash-generative, but **no founder/family owner** | ✅✅ Dassault family ~26% + French state ~26% *(verify)* | ✅✅ **Founder-led (Shwed); huge sustained buybacks = his "Cannibal"; net cash** | ✅ Very cheap; state overhang | ❌ No owner-operator, not cheap enough |
| **Dinan** — dated event, floor, complexity, liquidity | ✅✅ SOTP across 4 segments; NIST 2030 sunset is the date; deep liquidity | ✅✅ Defense + cyber + identity SOTP | ✅ Net-cash floor; Israel (cf. Psagot) | ✅ Complex, messy | ⚠️ Simple, no event |
| **Meli** — variant vs consensus, clean valuation, MPSIF-holdable | ✅✅ Tractable; consensus is measurably negative on the auto cycle | ⚠️ Valuation stretched — see warning | ✅ Very clean, slow-growth debate | ✅ Cheapest, hardest to model | ✅ Clean, but zero originality |
| **Knudsen** — why mispriced & persists, beats ACWI, bad case | ✅✅ **De-rated on the auto/industrial cycle — securities business ignored.** Her "bathwater" | ❌ Not mispriced; re-rated hard | ✅ Persists because it is boring | ✅✅ Deeply out of favour | ✅✅ Crushed on "AI kills consulting" |
| **Mena** — variant perception, catalyst, capital allocation | ✅ | ✅ | ✅✅ Capital-allocation story is the pitch | ⚠️ Poor capital-allocation record | ✅ |
| **FX work required** *(rules: USD returns)* | ✅ EUR | ✅ EUR | ⚠️ NASDAQ/USD — weak | ✅ EUR | ❌ None |
| **On a judge's book?** | No | No | No | No | No |

### Ranking

**1. Infineon (IFX.DE) — lead candidate.**
German listing forces the FX work the rules demand and satisfies Dinan's *"go to where the rocket scientists cannot go."* It is genuinely cash-flowing with real earnings, which clears [Vectors.md](Vectors.md) §4's hardest test (no pre-revenue narrative names). It has been de-rated on automotive and industrial weakness while the Connected Secure Systems franchise — secure elements, TPMs, SIM — is exactly the mandated hardware refresh. Two *independent* catalysts: the regulatory crypto sunset and an auto-cycle recovery. Sum-of-the-parts across four segments gives Dinan his complexity and his floor.
**Weakness, stated honestly:** no owner-operator, so Rosenwald's alignment test is only partly met. And see the bear case in §6.

**2. Thales (HO.PA) — highest thesis purity, biggest valuation trap.**
It is the global #1 in HSMs and it has the ownership structure Rosenwald wants. But European defense names have re-rated enormously on rearmament. Under [Vectors.md](Vectors.md) §6, *"price already reflects the bull case"* is a hard avoid. **The risk is that we pitch a defense stock and call it a cryptography stock.** Only viable if the numbers show the cyber/identity segment is being given away for free inside the defense multiple. Check that before spending time.

**3. Check Point (CHKP) — the Rosenwald-shaped one.**
Founder-led, net cash, relentless buybacks: his "Cannibals vs. Zombies" framing, on the right side. Israel connects to Dinan's Psagot history. Fails the FX requirement (USD-reporting, NASDAQ), and slow growth means we must prove it is a cannibal and not a zombie. PQC is a modest slice of the story.

**4. STMicroelectronics (STM) — the deep-value option.** Cheapest, most out of favour, Franco-Italian listing. State ownership and governance are a real overhang, and capital allocation is the weakest of the group.

**5. Accenture (ACN) — the elegant inversion, poor originality.** The market believes AI destroys consulting. The same AI advance creates a mandated global re-platforming that only a firm of that scale can execute. Genuinely clever, and Knudsen's bathwater question answered directly — but it is US mega-cap, no FX work, and covered by every analyst alive. First-round graders score on *originality*.

---

## 5. The pure-play problem

Most true PQC pure-plays are **private**: Entrust (Thoma Bravo), DigiCert (Clearlake/TA), Utimaco (SGT/EQT), IDEMIA (Advent), Keyfactor, Sectigo, PQShield, SandboxAQ. Venafi went into CyberArk, which is itself being absorbed by Palo Alto *(verify close)* — and merger-arb is banned by our filter and is Dinan's home turf regardless.

Read this two ways, and say both out loud in the pitch:

- **Supporting:** the public market has no clean instrument for this thesis. That is a structural reason the mispricing exists and persists — which is precisely Knudsen's central diligence question.
- **Against:** we must express it through a diversified incumbent, so the pure signal is diluted. Whichever name we choose, the crypto franchise is a minority of revenue. We have to quantify what percentage, and argue the market is valuing it at roughly zero.

### Explicitly banned — do not drift here

**Arqit, IonQ, Rigetti, D-Wave, Quantum eMotion** and every "quantum security" pure-play. These are pre-revenue narrative stocks; Arqit is a collapsed de-SPAC. [Vectors.md](Vectors.md) §3 and §4 rule them out, Dinan has SPAC scar tissue (Enovix, ScanTech, Iconic), and Meli's *"60 or 100 times earnings"* warning applies directly. **The quantum-threat story is correct; the quantum-threat stocks are the trap.** Our entire edge is taking a real thesis and expressing it through boring, profitable hardware.

---

## 6. The bear case — put this on a slide before Meli asks

Meli hosted a debate podcast for six years. Give him the strongest opposing case first.

1. **Timeline slippage is the base case, not the tail.** "Q-Day in five years" has been said for fifteen years. PQC migration can be deferred almost indefinitely in the private sector, because nobody is punished for deferring it until the break actually happens. Regulatory deadlines slip routinely.
2. **PQC may be a software upgrade, not a hardware one.** This is the thesis-killer for Infineon and Thales. If existing secure elements can be firmware-updated to ML-KEM/ML-DSA, the mandated *hardware* refresh evaporates and the beneficiary is nobody. **We must establish, from primary documentation, which deployed hardware generations are and are not PQC-capable in firmware.** Larger key sizes and memory requirements are the crux. This is the single number the pitch lives or dies on.
3. **Infineon is a cyclical semiconductor, and the auto cycle will swamp the thesis.** Honest framing: this is roughly 80% an auto/industrial semi cycle call with a crypto free option, not the reverse. If we pitch it as pure PQC, Meli finds that in ten minutes. Better to own it — the cycle provides the floor, the crypto franchise is the option.
4. **A real break might destroy value, not create it.** A sudden loss of trust in digital commerce is not obviously good for anyone, including the remediators. Correlations go to one — Knudsen's explicit stress-test question. Answer with sizing and a stop-loss, not with optimism.
5. **Lattice cryptography may itself be broken.** If AI is strong enough to break ECC, ML-KEM is not obviously safe. Then the migration we are underwriting has to happen *twice*. Arguably bullish for spending and bearish for confidence in any single standard.

---

## 7. Judge-balance check

Reading back against all five profiles, no single palate is being served:

- **Rosenwald** gets quantified discount, owner-operator structure (in Thales/Check Point), and a long-horizon 2030/2035 regulatory arc rather than a trade.
- **Dinan** gets a dated catalyst calendar, a sum-of-the-parts floor, complexity the crowd avoids, non-US mid/large caps, and deep liquidity.
- **Meli** gets institutional precision (the asymmetric-only break, Grover vs. Shor), a clean valuation with no stretched metrics, a full Flip Side slide, and a position a $3mm student fund could actually hold.
- **Knudsen** gets an explicit answer to why the mispricing exists and why it persists (no listed pure-play), an ACWI hurdle comparison after FX and withholding, and a correlation-stress plan.
- **Mena** gets a hedge-fund-format variant perception, a dated catalyst, base/bull/bear, capital-allocation analysis, and no collision with Luxor's book.

No candidate appears on any judge's disclosed holdings, and none repeats a 2025 finalist.

---

## 8. Next steps — verify before committing a week

1. **The decisive question:** which deployed secure-element and HSM generations can reach PQC by firmware update, and which require silicon replacement? Primary sources: Infineon, Thales and NXP product documentation and CC/FIPS certification listings.
2. Confirm **NIST IR 8547** final status and whether the 2030/2035 dates survived.
3. Size Infineon's Connected Secure Systems segment: revenue, margin, growth — and what multiple the market is implicitly assigning it inside the group.
4. Current multiples vs. 5-year history for IFX, HO, STM, CHKP. Is the de-rating still there as of today?
5. Thales: segment disclosure — is the cyber/identity business free inside the defense multiple, or is it not?
6. Latest 13Fs for Luxor and Dalton to confirm none of these names appeared since June 2026.
7. Sell-side check: has anyone published the "PQC as mandated hardware refresh" framing? If it is already a widely circulated note, the originality score drops and we reconsider.

---

*Sources for the regulatory calendar in §2 are public NIST, NSA, OMB, ENISA and CA/Browser Forum documents. Items marked "verify" were drafted from knowledge current to mid-2026 and have not been re-confirmed against live sources.*
