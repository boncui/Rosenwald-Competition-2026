# Track B2 — Knowledge & research businesses

*Agent B2. Compiled 2026-09-19. All sources in `raw/B2_knowledge/`, cited as `[Bn]` by file number. Prices are the closes of 2026-09-17/18 unless stated. Every non-USD name carries an FX note because the competition scores in USD.*

---

## 0. The breakthrough, in one line, and what it does NOT contain

On 2026-09-08 an OpenAI multi-agent system announced a proof of finite-time blowup for the 3D incompressible Navier–Stokes equations (with forcing), accompanied by a Lean 4 formalization of **641,332 lines across 2,659 files with zero `sorry` in the proof files and zero non-standard axioms** [Agent 0, `raw/00_claim/github_openai_NavierStokesAndEuler_repo.md`]. **It is not peer-reviewed.** The repository's own `formalization.yaml` records `review: status: "self-assessed"`, and the independent `lean-dojo/LeanMillenniumPrizeProblems` registry **still listed Navier–Stokes as `Open` on 2026-09-19** [B10].

My track is not about fluids. It is about businesses that sell *analysis itself*. The transmission I am testing is: **machines produce research-grade output at scale → what happens to the firms that sell peer review, curation, prestige, benchmarks and analytical judgement?**

---

## LEADING WITH THE CLAIM MOST LIKELY TO BE FALSE

**The claim: "AI commoditizes research output, so academic publishers and analytics vendors are structurally impaired."**

It is false in the form it is usually stated, and I can show why with reported numbers rather than argument.

1. **Publishers get paid per accepted article under open access.** Cheaper manuscript production raises their unit volume. In FY2025 RELX STM reported **article submissions up more than 20% and output up 10%** [B7 §E, B1]; Taylor & Francis reported **over 20% growth in research submissions** [B7 §B]; Springer Nature reported **published articles up over 12% overall and 25% in full-OA journals** [B7 §C]. Three separate issuers, same direction, already in reported results.
2. **The de-rating that actually happened was not about content commoditization at all.** It was triggered on **2026-02-03** by Anthropic shipping a **legal-workflow** plug-in: RELX −12/−13%, Wolters Kluwer −9.9%, LSEG −8.1%, Experian −7.4%, and US information-services names down 5%+ [B6, B2, B8]. RELX's STM segment — 28.3% of revenue, 31.0% of adjusted operating profit, the group's **highest-margin** segment at 38.1% [B1] — was marked down for a product event in a different division.
3. **In the half that followed the panic, the punished division accelerated.** RELX H1 2026 (reported 2026-07-23): Legal underlying revenue **+10%**, adjusted operating profit **+13%** — "a further step up"; STM **+6% / +8%**, also a step up; group margin 34.8% → **35.5%** [B6].

**But here is the disconfirming half, stated with equal prominence, because the coordinator is right to demand it: the volume trend predates the AI narrative entirely.** Scholarly article output has compounded at **4% a year (2018 STM Report)** and **5–6.5% a year over 2015–20**, driven by R&D spending and researcher headcount; open-access output was already growing at **12.5% a year in 2019–22**, before ChatGPT existed [B11]. Springer Nature's +25% full-OA growth is roughly **2x a pre-existing 12.5% trend**, not a step-change from zero. Anyone who tells a judge that AI created publishers' volume growth will be corrected. The defensible claim is narrower: **AI has roughly doubled an already-favourable volume trend on the gross line, and opened an undisclosed cost line underneath it.**

---

## FINDING 1 — RELX / Elsevier STM: **beneficiary**, and the de-rating is a Legal-segment fear priced onto an STM-and-Risk business

- **Exposure:** RELX PLC (LSE: REL; NYSE ADR: RELX). Scientific, Technical & Medical segment: **FY2025 revenue £2,714m** (28.3% of group £9,590m), **adjusted operating profit £1,035m** (31.0% of group £3,342m), **adjusted operating margin 38.1%** — the highest of the four segments (Risk 37.4%, Legal 23.0%, group 34.8%) [B1].

- **Mechanism, hop by hop.**
  1. LLM agents lower the cost of producing a research manuscript → submissions to Elsevier journals rise. **Observed: +20% submissions, +10% output, FY2025** [B7 §E].
  2. Under gold open access the publisher is paid an APC **per accepted article** → volume converts to revenue. RELX: "In Primary Research, good growth continues to be driven by **volume growth**, with article submissions growing very strongly across the portfolio" — repeated verbatim in both FY2025 and H1 2026 [B1, B6].
  3. Rising volume of unvetted machine-generated claims raises the value of a trusted filter → the subscription/prestige side holds. Note STM revenue mix shifted **to 80% subscription / 20% transactional in 2025, from 74/26** [B7 §E] — the recurring share went *up*.
  4. A separate hop, in the opposite direction: general-purpose models with vertical plug-ins substitute for **workflow** products. This lands on **Legal (LexisNexis)**, £1,806m revenue / £415m profit = 18.8% / 12.4% of group — not on STM.

- **Magnitude.** Group FY2025: revenue £9,590m (+7% underlying), adjusted operating profit £3,342m (+9% underlying), margin 34.8%, adjusted EPS 128.5p (+10% cc), cash conversion 99%, ROIC 15.4%, net debt/EBITDA 2.0x, **£2,250m of buybacks intended in 2026** after £1,500m in 2025 [B1]. H1 2026: revenue £4,871m (+7%), adjusted operating profit £1,727m (+9%), margin 35.5%, EBITDA margin 40.9% [B6].
  **Valuation (ADR close 2026-09-18):** **$33.41**; market cap **$58.4bn**; **52-week price change −29.05%**; 52-week range $27.57–$48.40; dividend yield 2.63%; **beta 0.26** [B8].

  **The de-rating is real and it does not predate the AI story — this is the test the coordinator demanded, and RELX passes it** [B12]. RELX's PE by fiscal year end: **31.5x (FY21) → 26.7x (FY22) → 32.9x (FY23) → 34.8x (FY24, the peak) → 26.6x (FY25) → 19.45x now.** EV/EBITDA: 24.0 → 19.1 → 22.1 → **24.3 (FY24 peak)** → 19.4 → **16.03 now — 34% below the FY2024 peak and below every year in the five-year series.** P/FCF 26.0x (FY24) → **15.24x**. There is no multi-year downtrend to explain this away as normalisation: the multiple was at its five-year *high* eighteen months ago and broke in two steps, and the two largest single-day moves are contemporaneously attributed by the WSJ, Bloomberg and Reuters to a named AI product launch on a named date.

- **Timing and trigger.** Already in reported numbers — this is not a forecast. The de-rating is dated: 2026-02-03 (Anthropic legal plug-in), 2026-02-12 (RELX **−32% YTD** in London at 2,015p per Bloomberg) [B6]. The re-rating triggers are the **FY2026 results in February 2027** (guidance is "good to strong underlying revenue growth with underlying adjusted operating profit growth exceeding underlying revenue growth" for STM) and the completion of the 2026 buyback.

- **The natural experiment — free full text already existed for three decades and the margin went UP.** The right test of "does free content destroy the publisher" is not a forecast; it has already been run [B12]. **arXiv** has given away physics/maths/CS preprints since **1991**; **PubMed Central** since **2000**, made mandatory for NIH-funded work in **2008**; **Sci-Hub** has made essentially the entire paywalled corpus free since **2011**; **Plan S** launched in **2018**; open access went from minority to majority (Springer Nature: **53% of primary research articles OA** in FY2025). Over that period RELX's STM adjusted operating margin, on a consistent H1 basis from RELX's own interim releases:

  | | H1 2019 | H1 2020 | H1 2025 | H1 2026 |
  |---|---|---|---|---|
  | STM adjusted operating margin | **35.8%** | **36.6%** | **37.1%** | **37.9%** |

  **+2.1 percentage points across seven years in which the content became progressively free.** The publisher was never selling scarce content. It was selling certification, the brand of the title, and the bundled institutional subscription. Free copies of the identical PDF did not touch any of those — and an LLM that can write the paper does not touch them either. *(Caveat stated so it cannot be used against me: RELX **restated its 2024 segment figures** "to reflect business area reporting changes," so FY2024 STM appears as £3.05bn/38.4% on the old perimeter and £2,624m/37.4% on the new. Those cannot be spliced into one series; the H1 series above is taken from consistently-presented interim releases.)*

- **Where a bear should actually attack — naming it myself rather than leaving it to be found.** Not Primary Research. **Databases, Tools & Electronic Reference**, which RELX stated on the H1 2026 call is "**around 40% of divisional revenue**." Scopus and ScienceDirect discovery are **retrieval and search** products, and retrieval is precisely what a model with tool access does well. If any part of STM is substitutable, it is that ~40%, not the journals. **And I must say plainly what I cannot say: RELX does not disclose a revenue split between Primary Research and Databases/Tools in its results statements.** The ~40% figure is management commentary from an earnings call, not a reported segment line. I am not going to construct a dollar estimate of the exposed sub-segment from it, and anyone who does is making it up. The second attack surface is **Legal** — 18.8% of revenue at a 23.0% margin, a workflow product facing a named competitor with a shipped product.

- **Counter-thesis, argued at full force.**
  1. **The bear was not obviously wrong.** LexisNexis is a legal-research workflow product; a general model with a legal plug-in is a genuine substitute candidate for part of it. One good half (H1 2026) does not refute a five-year substitution thesis — enterprise software contracts are multi-year, and a customer who decides to leave shows up at renewal, not at announcement.
  2. **Submissions ≠ profitable revenue.** Submissions +20% against output +10% is a **10-point wedge**, the signature of a rising rejection rate. Screening cost is borne on *submissions*; APC revenue is earned on *acceptances*. Neither RELX nor Springer Nature discloses screening cost as a line item [B11]. RELX's own principal risks say: "There is a risk that we may not detect some erroneous or fraudulent research papers that are submitted to our journals" [B1]. One serious integrity failure at a flagship title is a reputational event, and reputation is the product.
  3. **The pay-to-publish transition is a disclosed risk, not a free option.** RELX itself flags that "payment models... are evolving, with 'pay-to-publish'... becoming a larger share relative to 'pay-to-read'. Rapid changes in customer choice, regulation, or technologies in this area could impact the revenue mix and growth in primary publishing" [B1]. Library budgets are flat; APC inflation has a political ceiling.
  4. **RELX refuses to license its corpus.** Asked on the 2026-02-12 call about licensing content into AI tools like Claude, the answer was "a resounding **no**"; limited licensing "only at the margins" [B7 §E, practitioner call notes — secondary source, flagged as such, though its segment figures match the press release exactly]. This forfeits the Wiley/T&F licensing cheque and bets the archive's value on RELX building better tools (Scopus AI, Sherpath AI, **LeapSpace**) than the labs can. If that bet is wrong, RELX has both no licensing revenue and a losing product.
  5. **Growth is mid-single-digit.** STM underlying revenue +5% (FY25) / +6% (H1 26). This is not a growth story; it is a quality-compounder-at-a-discount story, and it needs the multiple to do the work.

- **FX (mandatory).** RELX reports in **GBP**; the competition scores in **USD**. This is not academic: in H1 2026 currency movements **reduced revenue growth in GBP by 2pp and adjusted operating profit by 2pp** [B6]. The NYSE ADR (ticker RELX) is USD-denominated and liquid at $60bn market cap, but the ADR's USD return = GBP total return × GBP/USD move. A USD-based holder is long sterling. This must be sized and disclosed, not waved at.

- **Long-only expression: (b) wrongly-punished long whose moat survives.** This is the cleanest instance of Knudsen's "babies thrown out with the bathwater" in my track: a 38.1%-margin, 99%-cash-conversion, 0.26-beta business marked down ~29% because a *different segment* faces a product threat, while its own volume driver accelerates. The residual question is whether ~29% is the right price for a risk concentrated in ~19% of revenue.
- **Severity: thesis-grade.**
- **Evidence:** `raw/B2_knowledge/01_relx_fy2025_results.md`; `06_relx_h1_2026_and_anthropic_derating.md`; `07_publishers_ai_licensing_and_submissions.md`; `08_analytics_ratings_valuation_and_events.md`; `11_article_output_base_rate.md`; `12_multiple_history_and_natural_experiment.md`.

---

## FINDING 2 — Does formal verification kill peer review as a product? **No — and the people who built the verifier say so in writing**

- **Exposure:** the "trust" component of STM publishing revenue — the reason a library pays a subscription and an author pays an APC rather than posting to a preprint server.

- **Mechanism.** A Lean-checked proof is trustworthy without a referee. If machine-checked certification generalises, the journal's correctness-checking function is disintermediated.

- **What the evidence actually says.** The **Palomar registry of Lean-verified mathematics** opened for submissions on 2026-08-18, incubated by the Lean FRO and ICARM, scientific board including Tao, Avigad, Kra, Vakil, Venkatesh [B3].
  - Palomar's founding statement: "The role of the registry in the research publishing pipeline is **similar to that of a repository or preprint server**... the appearance of a work in the registry **does not constitute a certificate of novelty, nor a certification of relevance, nor a certification that the verified statement matches the informal statement**."
  - And the decisive line: "**It is our hope that the registry will serve as useful infrastructure for traditional journals.** As with arXiv overlay journals... **By firmly establishing a minimum standard for verification, Palomar frees traditional journals to aim higher — allowing referees to focus their scarce time on conceptual novelty and elegance, rather than grinding through baseline logic.**"
  - Tao, in the comment thread (2026-08-30): the automated checks are "**not a substitute for genuine human review, which we do not have the resources to conduct on the volume of submissions received**. There are plans by other parties to implement a '**Palomar overlay journal**'."
  - The proof at the centre of this project is itself the proof of the point: 641,332 machine-checked lines, `review: status: "self-assessed"`, and **still listed `Open`** by the independent registry eleven days later [B10].

- **Magnitude.** Formal verification substitutes for **one** component of refereeing — logical soundness — in **one** discipline. Mathematics is a rounding error in STM publishing revenue; the money is in clinical medicine, life sciences, materials and engineering, where "formalization" is not even definable. **There is no revenue line to attach to this, so under the metaprompt's own rule it is not a finding about a company.** It is a constraint on other findings.

- **Timing.** arXiv has existed since 1991 and has not destroyed a physics journal's revenue. The overlay-journal model is 20 years old. Lag: decades, not quarters. Not a catalyst.

- **Counter-thesis (the case that it *does* matter).** If (i) formalization tooling generalises beyond mathematics to, say, verified statistical analysis or verified computational biology pipelines, and (ii) funders begin mandating machine-verifiable artefacts as a condition of grant reporting, then the "we checked it" premium collapses across a much wider slice of the literature. Neither condition is currently observable. Also genuinely negative for publishers: the 25 Fields Medallists' declaration (2026-09-11, three days after the announcement) says the mass production of "true/false" statements "**could destroy fertile ground**" and that **solving a famous problem is no longer "a certain sign of new insights"** [B4]. If prestige-per-result is falling, the prestige franchise is worth less in the long run. That is a real, if slow, erosion.

- **The direction the evidence actually points.** The Fields Medallists' complaint is not that there is too much curation — it is that there is **too little**: "Often these solutions are announced in a rush, leaving no time for a proper writeup, the isolation of new methods and ideas, and **citing relevant previous work of others**. As in all creative professions, this raises **severe attribution and plagiarism questions**" [B4]. Palomar's statement says the surge of unvetted claims is "**eroding our current standard for what constitutes an 'established mathematical fact'**" and that "press releases, social media posts, and company websites are insufficient mechanisms" [B3]. Write-up, attribution, citation, refereeing and integration are the exact services a publisher charges for. The community's response to machine-generated proof was **to build another institution**, not to abolish one.

- **Long-only expression: (c) a de-risking constraint on Finding 1** — it removes the single scariest tail risk to the RELX thesis, and it supplies the verification-demand argument. It is **not** an independent trade.
- **Severity: supporting.**
- **Evidence:** `raw/B2_knowledge/03_tao_palomar_registry.md` (incl. the Palomar statement appendix); `04_fields_medallists_declaration.md`; `10_verification_as_the_new_product.md`.

---

## FINDING 3 — Corpus licensing: **real money, but non-recurring, and it is not a thesis**

- **Exposure:** disclosed AI content-licensing revenue at scholarly publishers.
- **Magnitude, with the disclosure cited** [B7]:
  - **Wiley (NYSE: WLY):** AI revenue **$23m FY2024 → $40m FY2025 → $49m FY2026 (+23%)**; **lifetime AI revenue has surpassed $110m**; "recurring revenue rapidly scaling." Against FY2026 adjusted revenue of $1,677m that is **2.9% of revenue**. Research segment $1,130m (+4% cc); adjusted EBITDA $440m at a record **26.2%** margin. Acquired **Emerald Publishing for $452m**, guided to add $78m of FY2027 revenue. FY2027 guidance: EBITDA margin 26.5–27.5%, adjusted EPS $4.60–5.05, FCF $205m.
  - **Informa / Taylor & Francis (LSE: INF):** the Microsoft deal announced 2024-05-08 at a reported **$10m initial access fee plus recurring payments**; Informa sold **$75m+ of non-recurring data access in 2024**. In FY2025 that base effect turned T&F's underlying growth from **+3.6% (ex non-recurring data contracts) to −2.1% (including them)**. Informa's annual report confirms a further archive-licensing contract with "another AI technology provider."
  - **Springer Nature (FSE: SPG):** no AI revenue figure disclosed; sells **ARC3**, a data-licensing product for corporate R&D, plus growing TDM revenue. FY2025 group revenue €1,926.4m (+6.2% underlying), adjusted operating profit €543.6m (+9.2%); Research segment €1,517.2m (+7.4%) / €486.4m AOP (+9.9%).
  - **RELX/Elsevier:** explicitly **declines** to license, "only at the margins" [B7 §E].
- **Counter-thesis / the honest read.** **Informa proves these are one-off items, not annuities**: their absence flipped a division from +3.6% to −2.1%. Wiley's own framing ("recurring revenue rapidly scaling") is a claim about the *future* mix, not the reported one. A pitch built on the licensing line is a pitch built on a non-recurring item, and Meli will say so before the Q&A is two minutes old.
- **Timing.** Deal-by-deal and unforecastable. No contract cycle to anchor on.
- **Long-only expression:** for Wiley, **(a) beneficiary long — but marginal.** WLY is **up 33% over 52 weeks**, trades at **9.6x forward earnings** with a **3.0% yield** and 2.1x leverage [B8] — cheap and already working, which is the problem: the mispricing has substantially closed and the AI line is 2.9% of revenue. **Not pitchable as a primary idea.** For Informa and Springer Nature: **(d) unpitchable** here — Informa's story is B2B live events (a different thesis), and Springer Nature is a 2024 Frankfurt IPO with EUR reporting, thin float and a Holtzbrinck control block.
- **Severity: supporting.**
- **Evidence:** `raw/B2_knowledge/07_publishers_ai_licensing_and_submissions.md`.

---

## FINDING 4 — Ratings and indexes: **the moat is a licence and a network effect, and cheap analysis does not touch it**

- **Exposure:** Moody's (MCO), S&P Global (SPGI) ratings; MSCI and S&P Dow Jones Indices.

- **Mechanism the bears assume:** cheap machine credit analysis → issuers and investors stop paying for ratings; cheap index construction → asset managers self-index.

- **Why that mechanism does not reach the revenue — the SEC's own words** [B8 §D, SEC Office of Credit Ratings annual NRSRO staff reports]:
  > "**Barriers to entry continue to exist in the credit ratings industry**, presenting competitive challenges for the small and medium NRSROs."
  > "**Both DBRS and KBRA have identified index inclusion requirements as a structural barrier to competition.**"
  > "One such **regulatory barrier to entry is the requirement in Section 15E(a)(1)(B)(ix) and (C)** that a credit rating agency applying to register as an NRSRO furnish written [QIB certifications]."
  > "**Many investment management contracts and investment guidelines require the use of specific large NRSROs.**"

  Not one of those is a claim that rating a bond is *analytically* hard. They are: a statutory registration gate with a track-record test; **index-inclusion rules that require a Big-Three rating**; and **IMAs and client guidelines that name specific agencies**. A model that produces a better credit opinion for free still cannot get that opinion written into an indenture, an index methodology or an investment mandate. Changing that requires coordinated action across issuers, index providers, regulators and thousands of asset owners.

- **Magnitude — and the pricing data is the proof, not the assertion.** From the Substantive Research / BCG Expand joint study, 2026-03-11 [B5]:
  - **Index vendor revenues grew 9.3% in 2025**, the fastest category in market data, on a **5-year CAGR of 8.9%** against an overall market rate of 7.3%. **Ratings vendor revenues +7.4% in 2025** (vs +6.0% in 2024).
  - Average renewal uplifts at major vendors: **14% (2022), 18% (2023), 15% (2024), 10% (2025)** — against client market-data budget growth of 3.0%, 2.11%, 2.01%, 4.1%.
  - **Index price dispersion: some firms pay up to 13x more than others for the same product from the same vendor. Ratings: 502%. Terminals: 493%.** That degree of dispersion is only sustainable where the buyer has no substitute.
  - Morningstar Equity Research (2026-02-04): "we see credit ratings, indexes, Verisk's insurance data, and FICO scores as benefiting from a **network effect. Even if a better solution emerges, their use in contracts and in the capital markets would require complex coordination to disrupt**" [B2] — *note this is Morningstar writing about a peer group that includes Morningstar, so treat the moat call as a house view; the price action it reports is fact.*

- **Timing / trigger.** No observable trigger for moat erosion. The genuine, dated risk is **price, not substitution**: renewal uplifts fell 18% → 15% → 10% across 2023–25, and Substantive's CEO attributes part of that to "**the rise of AI adoption and cloud-based infrastructure, together with professionalised approaches in data procurement**," warning of "a future impasse and crunch point" [B5]. **This is the disconfirming datapoint in my track and I flag it as prominently as B1 flagged its own**: I cannot separate the AI effect from twenty years of normal buyer pushback and procurement professionalisation, and Carrodus names the non-AI causes in the same sentence. The correct statement is that **the pricing-power peak may be in; nothing in the data says the franchise is.**

- **Counter-thesis at full force.** (i) Regulatory moats can be legislated away — Dodd-Frank §939A already removed statutory references to NRSRO ratings, and the EU has periodically threatened the same; if index providers dropped the Big-Three requirement, the structural barrier the SEC names would go. (ii) Ratings revenue is **issuance-cyclical**: a shut primary market hurts MCO and SPGI far more than any model ever will, and Meli — who spent 25 years in corporate credit — will ask about issuance, not about AI. (iii) MSCI at **30x trailing / 26x forward** and **+5.5% over 52 weeks** is not punished at all, so there is no mispricing to buy [B8].

- **Long-only expression:** **MSCI — (d) unpitchable.** The moat holds, but the market agrees: +5.5% over 52 weeks at 26x forward. No variant view. **Moody's — (d) unpitchable** at −6.2% and 26x forward; same reason. **S&P Global — (d) unpitchable as framed, for a specific technical reason**: SPGI **completed the Mobility Global spin-off on 2026-07-01**, so its headline "−25.5% 52-week price change" mixes a genuine de-rating with a mechanical share distribution and is not comparable to peers without spin-adjustment [B8]. Anyone quoting that −25.5% to a judge as evidence of AI punishment is quoting a broken number. It is also a $119bn mega-cap with 2026 guidance already cut (2026-02-10: adjusted EPS $19.40–19.65 vs $20.02 consensus; stock −9.7% to $401.08, worst in the S&P 500 that day, per WSJ/Reuters) — the issue there is guidance, not commoditization.
- **Severity: thesis-grade as a *constraint*** (it kills the "short the ratings agencies" instinct and validates the moat), **noise as a trade.**
- **Evidence:** `raw/B2_knowledge/05_substantive_research_budgets_and_analysts.md`; `08_analytics_ratings_valuation_and_events.md`; `02_morningstar_ai_bear_case_infoservices.md`.

---

## FINDING 5 — FactSet and Verisk: one de-rating that predates the AI story, and one that does not

- **Exposure:** FactSet (FDS) sells a workstation and analytical workflow; Verisk (VRSK) sells insurance underwriting/claims analytics. Both are, on the face of it, "AI does the analysis" candidates — retrieval, aggregation and presentation are what a model with tool access does.

- **The punishment, dated** [B2, B8]: Gartner **−28% in one day on 2025-08-05** was the sector's "tipping point"; 2026-02-03 took the whole group down 5%+. Over 52 weeks: **FDS −15.2%, MORN −18.2%, VRSK −28.7%** against MSCI **+5.5%** and MCO **−6.2%**. The market has drawn the line between *benchmark franchises* and *workflow tools* and punished the second group specifically. That is a coherent, not a panicked, distinction.

### FactSet — the de-rating is real, but it LARGELY PREDATES the AI story. I am downgrading it.

The coordinator was right to insist on this test, and FactSet fails it. FDS **forward PE by fiscal year end (August)** [B12]: **32.9x (FY21) → 30.4x (FY22) → 27.2x (FY23) → 25.1x (FY24) → 20.9x (FY25) → 14.83x now.** Trailing PE: 36.0 → 41.5 → 35.6 → 30.0 → 23.6 → **18.69**. **The multiple has compressed in every single year since FY2022**, beginning well before generative AI was a market narrative, and is better explained by decelerating ASV growth and normalisation from a 2021–22 peak. Attributing that to an eleven-day-old proof — or even to the February 2026 Anthropic launch — would be exactly the error B1 flagged: a trend indistinguishable from years of ordinary give-back, with nobody producing a number to separate them. **I cannot produce that number either, so I will not make the claim.**

The operating data is genuinely good and I report it because it is true, not because it rescues a thesis [B8 §C]: **Q3 FY2026** (to 2026-05-31, 8-K): revenue $622.9m **+6.4%**, organic +7.0%; **organic ASV $2,485.6m, +7.1% — accelerating for a fourth consecutive quarter**; **ASV retention above 95%**; Q3 renewals **extended 30% in length**; **>90% of the Top 50 clients use four or more FactSet AI products**; shipped an **MCP server**. Valuation: **18.7x trailing / 14.8x forward**, P/FCF 14.25x, beta **0.71**, 1.77% yield.

**But three things stop this being a pitch.** (i) The de-rating predates the story, so there is no AI-fear dislocation to buy. (ii) **ASV is a contracted backlog measure** — it records what clients already committed to and therefore **lags a switching decision by one full renewal cycle**; renewals lengthening 30% locks revenue in *and* delays the evidence of churn. (iii) The sell side is not calling it cheap: consensus rating **Hold**, mean price target **$261 against a $284 price** [B8]. **Long-only expression: (d) unpitchable as an AI-dislocation idea.** It may well be a good cheap-compounder idea; it is not *my* idea, and it does not belong in this track.

### Verisk — deferring to Track A2, which did the deeper work

A2 resolved VRSK to a genuine **(b) wrongly-punished long** on a much fuller evidence base than mine: a named sell-side downgrade reasoning explicitly on generative-AI disruption (Redburn, 2026-06-18); a moat shown to be regulatory and distributional rather than computational (the Aon 2025 cat-risk survey ranks "computational speed and ease of use" **10th of 13** model-selection criteria, against "reasonableness of model methodology" **1st**); a decade-long natural experiment in which **Oasis LMF — free, open-source, 90+ models — failed to displace the incumbents**; and a compliance treadmill (Florida Commission acceptance attaching to model *and* software build, sixteen acceptance letters for one Moody's model across successive builds). **I defer to that and do not restate it.**

*Reconciliation note, because our numbers differ:* A2 reports VRSK **−34.6% y/y**; I measure **−28.67%** from stockanalysis.com's 52-week price change field dated 2026-09-18. Different measurement dates and windows. Both say the same thing directionally; the discrepancy should be resolved to one convention before anything is pitched.

What my own work adds to A2's case, from the sell-side-data angle: Verisk **reaffirmed** FY2026 guidance (revenue $3.19–3.24bn; adjusted EBITDA $1.79–1.83bn = **~56–56.5% margin**; adjusted EPS $7.45–7.75); Q2 **core subscription revenue +8.0% OCC**; **XactAI users up ~10x since March 2026**; buyback authorisation raised **$2.5bn to $9bn**. And the single most useful fact in my whole track: **Verisk put its insurance analytics inside Anthropic's Claude via Model Context Protocol connectors.** The incumbent is distributing *through* the thing that was supposed to kill it. **And A2 named the right place for a bear to attack — the Claims/Xactimate side rather than the cat side; my data agrees, in that Verisk's transactional revenue is falling −4.2% on a softening P&C market.**

### Morningstar — the most genuinely exposed, and the least attractive
MORN sells analytical judgement as the product, plus ratings and PitchBook data. At **19.4x trailing / 15.8x forward** and −18.2% it screens cheap, but its operating margin is **22.7%** versus 31% at FDS and 45% at VRSK, and 2.55x leverage is the highest of the three. Lower quality, no clearer mispricing. **(d) unpitchable.**

- **Timing / trigger.** **FactSet reports Q4 FY2026 on 2026-09-30** with FY2027 ASV guidance — the nearest observable trigger in my track, and worth watching even though I am not pitching the name. Verisk reports 2026-10-28.
- **Long-only expression:** **FactSet — (d) unpitchable as an AI-dislocation long** (de-rating predates the story). **Verisk — (b), per Track A2**, which owns this name. **Morningstar — (d) unpitchable.**
- **Severity: supporting.** This finding's value is mostly negative: it removes a name I was initially inclined to carry.
- **Evidence:** `raw/B2_knowledge/08_analytics_ratings_valuation_and_events.md`; `02_morningstar_ai_bear_case_infoservices.md`; `12_multiple_history_and_natural_experiment.md`; and Track A2's `raw/A2_test_forecast/` for Verisk.

---

## FINDING 6 — Sell-side and investment research: **no investable expression exists. This is the finding.**

*Written knowing Jeff Meli led Barclays' MiFID II response and research pricing in 2017 and ran Barclays Research (~700 staff) 2018–2024. I would rather report a clean negative than be corrected on his own subject.*

- **Exposure:** none that resolves to a public revenue line.

- **Why.** The major producers of sell-side research — Goldman, Morgan Stanley, JPMorgan, BofA, Citi, UBS, Barclays, Jefferies — run research as a **cost centre** funded out of the equities and FICC commission pool. **None discloses research revenue or research cost as a reportable segment.** There is no 10-K or 20-F line item that moves with research economics. Per this project's own rule — *"No finding without a named public company and a named revenue line"* — there is nothing here. The adjacent businesses are owned or private: **Substantive Research was acquired by Euronext in September 2024** and is immaterial inside it; independent research providers are **9% of a roughly flat budget pool**; expert networks and alt-data vendors are private.

- **What the numbers actually say, so the negative is evidenced rather than asserted** [B9]:
  - **The decline long predates AI — this is the most important calibration in the section.** Euromoney (2017): budgets across the ~600 research-producing firms fell **40%, from $8.2bn at the pre-crisis peak to $4.8bn in 2013**; analysts per global stock fell **~50% between 2007 and 2012, from ~4 to ~2**. The SEC's own staff report (2022-02-18) cautions that "it is unclear whether this was due to the legislation **since this downward trend existed before MiFID II went into effect**."
  - **MiFID II magnitudes, as compiled by SEC staff:** AMF — asset managers cut research budgets **25–50% in 2018 and a further 30–50% in 2019**; FCA — "a material reduction of around **20%–30%** in the budgets firms set for externally produced equity research"; The Trade (2021) — banks lost "**7,500 years of analyst experience**"; McKinsey/Bloomberg (2017, a consultancy estimate, flagged as such) — the top-10 banks' **$4bn** research spend to fall **30%**, cash-equity research headcount already down **12% to 3,900 since 2011**. Guo & Mota (JFE 2021): post-MiFID II, "analysts who produce worse research are more likely to leave the market" and those who remain "produce better research."
  - **The regulatory tide has since REVERSED, and most write-ups miss this.** The FCA's rules permitting **bundled ("joint") payments** took effect **2024-08-01** and were extended to fund managers in **May 2025**. In the EU, the **Listing Act** removed the €1bn SME threshold; the implementing Delegated Directive was adopted **2026-02-20**, published in the Official Journal **2026-06-02**, in force **2026-06-22**, applying from **2026-06-06**. Substantive expects European CSA-funded research payments to "begin in earnest in **H2 2026**."
  - **Where budgets are now:** global research budgets **grew ~1% in 2025 — the first global rise since MiFID II — with the growth entirely from US firms.** US budgets have recovered 40bps since 2022 versus 2bps in Europe; for managers >$150bn AUM, **US budgets run $8.6m/yr above UK/EU peers, in extreme cases 5x**. **55% of a budget goes to the top 10 providers; 24% to the top 3.**
  - **Headcount, precisely:** **736 mid-tier analysts left the market between 2023 and 2026**, leaving "senior analysts and junior support teams." **The middle was cut, not the bottom** — the opposite of the popular "AI eats the junior analyst" story.
  - **AI's effect on demand is positive, not negative, on the evidence available.** **77% of large asset managers have organisation-wide generative-AI deployments; 77% name broker research as the most valuable machine-readable input** (ahead of transcripts at 57% and market data at 42%); and **the single biggest barrier to using it is broker/data licensing restrictions (69%)**. **70% expect AI-generated "maintenance" coverage to become the baseline, with payment reserved for access to top analysts**, whom they expect to become "scarce and valuable." Substantive's CEO: "in an AI-driven investment world, **the sell side retains its core role in enabling the buy side to scale**... **direct analyst access even more crucial now than ever before**."
  - **On bank headcount, the popular claim does not survive contact with the numbers.** Dimon (JPMorgan, July 2026 call): AI has eliminated **30–40% of headcount in specific units**, with most staff **redeployed**; total headcount roughly flat at ~318,500 — a statement about unnamed operational units, **not** about equity research. Goldman expects **net headcount to increase in 2026** and hired 2,400–2,500 interns. J.P. Morgan Asset Management's own strategists: AI-cited job cuts are "**equal to just 0.08% of the labor market**" and "**some of this messaging may be 'AI washing'**."

- **Counter-thesis.** The strongest bull case for an investable expression would be the **exchanges** — Euronext bought Substantive, and rebundling routes research payments back through commissions, which touches volume-linked revenue. But this is third-order: Substantive is immaterial to Euronext, and exchange volumes are driven by volatility, not by research payment mechanics. It does not survive as a thesis.
- **Timing.** The EU rebundling application date was 2026-06-06 and H2 2026 is the first period in which it bites. If anything, the pool is about to grow.
- **Long-only expression: (d) unpitchable — no long expression exists.** Reported as a result, not as a gap.
- **Severity: thesis-grade as a negative** — it closes the largest-looking opportunity in the brief and prevents a bad pitch on the judge's home turf.
- **Evidence:** `raw/B2_knowledge/09_sellside_research_economics.md`; `05_substantive_research_budgets_and_analysts.md`.

---

## FINDING 7 — Clarivate: the one business actually being destroyed, and it is unpitchable

- **Exposure:** Clarivate (NYSE: CLVT) — Web of Science, ProQuest, Alma; segments Academia & Government, Intellectual Property, Life Sciences & Healthcare.
- **Magnitude** [B7 §D, B8]: FY2025 revenue **$2,455.2m, −4.0%** (organic **−0.1%**); adjusted EBITDA $1,001.8m; **GAAP net loss $201.1m**, with 2026 guidance still projecting a **net loss of $124–189m**. Organic transactional revenue **−4.8% FY2025, −11.9% in Q4**. **Total debt $4,469.9m** against $329.2m cash. Market cap **$1.21bn** against enterprise value **$5.26bn** — the equity is a **23% sliver** of the capital structure. **Debt/EBITDA 4.52. Share price $1.89, −53.8% over 52 weeks.**
- **The interesting nuance, stated because it disconfirms the easy story:** Academia & Government — the STM-exposed segment — grew **organic +2.0% in Q1 2026 and +0.3% in Q2 2026**. Reported declines are driven by **disposals**, not by AI eating Web of Science. Clarivate is not dying of AI; it is dying of a balance sheet.
- **Counter-thesis.** At 2.9x forward earnings and $327.6m of free cash flow against a $1.21bn equity, the deleveraging math is spectacular if organic growth ever turns positive. This is the classic levered-equity option.
- **Long-only expression: (d) unpitchable.** `docs/Vectors.md` §4 makes "value traps / zombies: cheap, but no catalyst and no aligned management" a **Hard avoid**, and Rosenwald's own syllabus teaches "Cannibals vs. Zombies." A GAAP-loss-making, 4.5x-levered, revenue-declining company at $1.89 with no named catalyst is the textbook zombie. Dinan's "good businesses with bad balance sheets" requires the *business* to be good; organic revenue is negative.
- **Severity: noise** (as a trade). **Supporting** as evidence that the AI story is not what is killing the weakest name in the sector.
- **Evidence:** `raw/B2_knowledge/07_publishers_ai_licensing_and_submissions.md`; `08_analytics_ratings_valuation_and_events.md`.

---

## FINDING 8 — Hard-math IP moats: no finding, deliberately

- **Question asked:** are there public companies whose value rests on proprietary mathematical or algorithmic IP that agents could now replicate?
- **What I found, and why I am not building on it.** The only serious candidates are the EDA and simulation vendors (Synopsys, now owning Ansys; Cadence). Synopsys CEO Sassine Ghazi addressed it directly on the Q1 FY2026 call: "Our deep tech solutions power the world's most complex engineering efforts. Synopsys' **decades of deep domain expertise, proprietary code-bases and solvers, and native foundry design technology co-optimizations deliver optimal, deterministic, silicon-proven results that probabilistic AI models do not**." That is a *management assertion*, not evidence, and it is self-serving.
- **Why this is not my finding.** Two reasons. First, the metaprompt's own rule: *"Never conflate a proof with a solver. A regularity or blowup result and a 1000x cheaper surrogate model are different economic events."* A Navier–Stokes blowup theorem does not make anyone's solver obsolete; the two live in separate evidence files for a reason. Second, this is **Track A1/A3's territory** (software and flow moats) and I have no business borrowing their conclusions. Testing whether an agent can replicate a foundry-qualified solver requires evidence I have not gathered.
- **General principle, stated and not extended beyond the evidence:** across every case in this track, the durable moats were **contractual, regulatory or network-based** (NRSRO status, index inclusion rules, investment-management contracts, foundry qualification, installed benchmarks) and the fragile ones were **workflow and retrieval**. Where a company's only asset is a clever algorithm with no contract, licence or dataset attached, I would expect it to be exposed — but **I did not find a listed company that fits that description**, and I am not going to invent one.
- **Long-only expression: (d) unpitchable — no evidenced candidate.**
- **Severity: noise.**

---

## `docs/Vectors.md` filter compliance — every named security

| Name | Ticker | Tier hit | Disposition |
|---|---|---|---|
| RELX | REL LN / **RELX** (NYSE ADR) | **Clean.** §1 non-USD FX rule **engaged** — addressed in Finding 1 (GBP reporting; currency cut H1 2026 revenue growth 2pp; USD ADR, $60bn cap, liquid). Not a judge holding; not a 2025 finalist; not a consensus mega-cap AI long | **Carried — (b) wrongly-punished long** |
| FactSet | FDS | **Clean** on the list, but §6 **Deflated** test now decides it: the forward PE has fallen in **every fiscal year since FY2021** (32.9x → 14.8x), so the compression predates the AI story and there is no AI dislocation to buy | **(d) unpitchable as an AI-dislocation long** — downgraded from a provisional (b) after the multiple-history check [B12] |
| Wiley | WLY | **Clean** but §6 "deflated/inflated" test partly engaged: already **+33% over 52 weeks**, so the mispricing has largely closed | Carried as (a), **not a primary pitch** |
| Verisk | VRSK | **Clean**; 22.9x forward is not a screen-cheap discount, but **Track A2 owns this name and resolved it to (b)** on a fuller evidence base | **(b) per Track A2** — I defer; see Finding 5 reconciliation note |
| MSCI | MSCI | §6 **Saturated/Inflated** — +5.5% over 52 weeks at 26x forward, no variant view | **(d) unpitchable** |
| Moody's | MCO | §6 same — −6.2%, 26x forward | **(d) unpitchable** |
| S&P Global | SPGI | **Clean on the list**, but the headline 52-week decline is **contaminated by the 2026-07-01 Mobility spin-off**; $119bn mega-cap; issue is guidance not AI | **(d) unpitchable as framed** |
| Morningstar | MORN | §6 **Deflated** — cheap, but lowest margin (22.7%), highest leverage (2.55x), most genuinely exposed | **(d) unpitchable** |
| Clarivate | CLVT | §4 **Hard — value trap / zombie**: GAAP losses, 4.52x leverage, negative organic growth, no catalyst | **(d) unpitchable — stopped here** |
| Springer Nature | SPG GY | §1 non-USD FX; 2024 IPO, thin float, Holtzbrinck control block | **(d) unpitchable** |
| Informa | INF LN | §1 non-USD FX; the real story is B2B live events, not AI | **(d) unpitchable** |
| Synopsys / Cadence | SNPS / CDNS | **Not analysed** — Track A1/A3's territory; no evidence gathered | **(d) no finding** |
| Goldman, JPM, MS, BofA, Citi, UBS, Barclays, Jefferies | — | No research revenue line disclosed anywhere | **(d) unpitchable** |
| Euronext | ENX FP | §1 non-USD FX; Substantive Research immaterial to it | **(d) unpitchable** |
| NVDA / MSFT / Mag-7 | — | §4 **Hard — consensus mega-cap AI longs** | Not analysed, by rule |

No short, no derivative, no leveraged or inverse ETF, no options overlay, no SPAC, no crypto, no private company, no sanctioned market appears anywhere in this track.

---

## Jevons check (dimension 6), stated explicitly

**Which regime applies?** For scholarly publishing, the **Jevons regime**, with a caveat. Making manuscript production cheaper raised submissions **+20% (RELX, T&F)** and output **+10–12% (RELX, Springer Nature)** against a long-run base rate of 4–6.5% [B11]. Under gold OA the publisher is paid per accepted article, so cheaper inputs raise units sold. **The caveat that keeps this honest:** submissions grew twice as fast as output, and the publisher bears screening cost on submissions while earning revenue on acceptances. **Gross Jevons, net unknown, because screening cost is undisclosed.**

For market data and ratings, **also Jevons, on the buyers' own testimony:** 77% of large asset managers say broker research is the most valuable input for their AI, and 69% say licensing terms are what stops them buying more [B5]. When the complaint is "we want to buy more and you won't sell it to us in the format we need," demand is not falling.

**Treating "demand falls" as the claim requiring proof, as instructed: nobody produced that proof.** Not one company in this track reported decelerating volume, decelerating ASV, or falling retention attributable to AI. The only quantified negative anywhere in my evidence is **renewal-uplift compression from 18% to 10% across 2023–25** — and the source names non-AI causes in the same sentence [B5].

---

## Second-order and dual-use (dimension 8), bounded

**Who benefits from the harm.** The buy side captures the cost savings: 70% of large asset managers expect AI-generated maintenance coverage to become free-at-the-margin, letting them reallocate spend to top analysts rather than expand budgets [B5]. Researchers capture faster literature synthesis. Neither is a listed beneficiary.

**Where capability proliferates into risk rather than revenue.** Three, and all three are *costs*: (i) research-integrity failure — RELX's own risk factor on undetected fraudulent papers [B1], COPE's warning that fake submissions "threaten to overwhelm editorial processes", the audit finding roughly **1 in 277 PubMed-indexed papers in the first seven weeks of 2026 cited a nonexistent paper**; (ii) the attribution and plagiarism problem the 25 Fields Medallists named [B4]; (iii) the verification-labour burden — which is exactly what **Accenture and Anthropic are each committing at least $1bn over five years to supply** (2026-09-18, embedded evaluators, red-teaming, alignment assessments) [B10]. That deal is strong cross-industry evidence that **trust, not content, is the scarce good.**

**The limit of that analogy, because it matters.** Accenture is *paid* for verification. A journal publisher is *not* — peer review is donated labour, and the publisher earns a subscription or an APC. Verification demand raises a publisher's **cost** and only raises its **revenue** insofar as the resulting trust signal preserves pricing power. So the correct conclusion is directional, not quantitative: publishers that own the trust signal (Nature, Cell, The Lancet, Science) keep pricing power; publishers that own only volume do not. RELX owns Cell and The Lancet. Clarivate owns neither.

---

## Cross-track reconciliation

My track is the **only one of the five where a large, AI-attributable de-rating actually occurred**, which is why RELX carries the weight here and why I report most other names as negatives.

| Track | Their finding | What it does to mine |
|---|---|---|
| **A1** (EDA / compute) | Synopsys **+26% in 30 days**; Cadence at record backlog | The market is paying *up* for the tooling that makes AI, and paying *down* for businesses that sell analysis. My sector is on the losing side of that rotation — which is the precondition for a (b), not evidence against it |
| **A3** (industrial / aero) | GE at **34.9x forward**, EV/EBITDA 149% above its own median; Safran near highs. A3 **graded this a negative result rather than forcing a long** | The standard I held Finding 5 to. FactSet and Morningstar screen cheap but fail the dislocation test, so they are (d), not manufactured (b)s |
| **A2** (test & forecast) | **Verisk a genuine (b)**: named AI-reasoned downgrade (Redburn, 2026-06-18), Aon survey ranking computational speed 10th of 13, the Oasis LMF natural experiment, Florida Commission compliance treadmill | I defer entirely on VRSK and do not restate it. Our 52-week numbers differ (−34.6% vs my −28.67%); one convention must be chosen before any pitch |
| **B1** (services / verification) | Accenture **−18% on services deflation unrelated to the proof**; the Lean artefact is `review: status: "self-assessed"` | Two things. (i) The discipline that a de-rating with an ordinary cause must not be dressed as an AI dislocation — the exact test that killed FactSet for me. (ii) The proof at the centre of this project is **still self-assessed and still listed Open eleven days on**, which is the ground under Finding 2 |

**One precedent borrowed from A3, because it is the strongest single support for Finding 1's counter-intuitive claim.** A3 documented the NRC accepting Westinghouse code qualification against **validation data that stays permanently secret**, published as "Non-Proprietary Class 3" with the data redacted — a US federal regulator formally recognising a private data corpus as a protected competitive asset. That is the closest available precedent for the RELX decision that most confused me when I found it: asked whether Elsevier would license its corpus into AI tools, management answered "**the short answer a resounding 'no'**," with "limited licensing only at the margins" [B7]. Wiley sells its corpus for $49m a year; RELX refuses. **Inference, marked as such:** RELX is behaving like a firm that believes the corpus is the durable asset and the licence fee is a one-time sale of it — which is the same judgement the NRC precedent validates in a regulated industry, and the opposite of the judgement implied by the share price.

---

## Plain-language close

**What is solid.** Three separate publishers have now reported, in audited or reviewed results, that submissions and published output are growing sharply — RELX submissions +20% and output +10%, Taylor & Francis submissions +20%, Springer Nature articles +12% and full-open-access articles +25%. Because open-access publishing charges a fee per accepted paper, more papers means more revenue, and RELX's scientific division is its highest-margin business at 38.1%. It is also solid that machine-checked proof does not replace peer review: the mathematicians who built the Lean verification registry wrote, in their own founding statement, that it is "useful infrastructure for traditional journals" that "frees traditional journals to aim higher." And it is solid that the credit-rating and index businesses are protected by legal documents rather than by clever analysis — the SEC's own annual report says entry is blocked by registration rules, index-inclusion requirements and investment-management contracts. A cheaper analyst does not rewrite a bond indenture.

**What is speculative.** Whether the extra papers are worth having. Submissions grew twice as fast as accepted output, which means more rejections, and screening costs money that no publisher discloses. Whether FactSet's accelerating contracted revenue is evidence the fear is wrong, or simply evidence that its customers have not yet reached their renewal dates — contracted backlog is exactly the number that would hide a problem for one more year, which is one reason I did not pitch it. And whether the slowdown in data-vendor price increases — from 18% a year to 10% — is AI biting, or just twenty years of normal customer pushback finally landing; the people who collected that data name both causes in the same breath, and I cannot separate them.

**What I want to be straight about.** The growth in scientific publishing is not an AI phenomenon. Scientific output has grown 4–6.5% a year since the 1940s because research budgets and researcher headcount grow. AI has roughly doubled that rate. That is a real and useful fact; it is not a new world.

**And one clean negative.** There is no way to invest in the decline of Wall Street research. Research sits inside banks as a cost, not a product; no bank reports a research revenue line; the one good data provider was bought by Euronext in 2024; and the regulation that shrank research budgets has been reversed — bundled payments have been legal in the UK since August 2024 and in the EU since June 2026, and global research budgets rose in 2025 for the first time since MiFID II. Anyone pitching this theme would be pitching into a rising tide with no security to buy.

**The single best idea is RELX, and I would hold it provisionally rather than enthusiastically.** A business converting 99% of profit into cash, compounding revenue at 7% and profit at 9%, buying back £2.25bn of stock this year, with a beta of 0.26, fell 29% over twelve months because Anthropic launched a legal-research tool. The legal division that caused the fear is 19% of revenue, and in the half after the fear it grew faster, not slower — 10% revenue, 13% profit. The scientific division that was sold alongside it has the opposite exposure: more machine-written papers means more papers to publish. That is Knudsen's "baby thrown out with the bathwater" in its most literal form. The two things that would stop me: it reports in sterling and the competition is scored in dollars, so a holder is long the pound whether they want to be or not; and one bad half in Legal would show that the market was early rather than wrong. **There is no second idea, and I want to be explicit that I removed one.** I initially carried FactSet — 95%+ retention, 0.71 beta, 14.8x forward earnings, contracted revenue accelerating for four straight quarters. Then I checked whether its cheapness was actually caused by AI fear, and it was not: FactSet's forward multiple has fallen in every single year since 2021, from 33x to 15x, long before generative AI was a market story. Calling that an AI dislocation would be attributing four years of ordinary give-back to an eleven-day-old event. It may still be a good cheap business; it is not this thesis, and I would rather hand over one idea I can defend than two I cannot. Verisk belongs to Track A2, which did more work on it than I did, and I defer to their verdict rather than duplicating it.

