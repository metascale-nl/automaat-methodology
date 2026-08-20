# Automaat — Machine Labor Price Assessments
## Methodology & Instrument Specifications — v0.3.2 (CONSULTATION DRAFT)

| | |
|---|---|
| **Administrator** | Automaat (working name; legal entity TBD, pending trademark and trade-name clearance) |
| **Status** | Draft for public consultation — not yet in production |
| **Version** | 0.4 |
| **Date** | 10 August 2026 |
| **Contact** | n.simpson@metascale.nl |
| **Consultation window** | [open date] – [close date, ≥30 days] |

**About this document.** This document specifies the methodology for a family of price assessments and indices measuring the price of machine-delivered work relative to human-delivered work ("parity" instruments), and the secondary-market value of industrial robots ("residual value" assessments). Part A defines the framework common to all instruments. Part B opens with the rules governing admission, lifecycle, and proxies for all verticals (Annex 0), then specifies each instrument. Part C maps this methodology to the IOSCO Principles for Financial Benchmarks. Part D lists open questions on which the Administrator invites comment.

**Design intent.** These instruments are designed to be boring: reproducible, consistently produced, and conservative wherever judgment is required. Every published figure must be reproducible from archived inputs plus the logged judgments of the assessor. Where the data does not support a number, the instrument says so rather than inventing one.

---

# PART A — FRAMEWORK

## A1. Purpose and economic object

The instruments in this family measure, over time and per vertical market:

1. **Parity** — the ratio of the all-in price of a defined task delivered by an autonomous/machine provider to the all-in price of the same task delivered by a human provider, observed in the same market at the same time (the **MLP family**, Annexes 1–2).
2. **Residual value** — the secondary-market value of standard industrial robot configurations, absolutely (currency per unit) and as a fraction of reference new price, by model, class, age, and region (the **RRV family**, Annex 3).

The economic interest represented is the substitution frontier between human and machine labor: parity instruments track the *price* of that substitution as experienced by a buyer of the task; residual instruments track the *collateral value* of the machines performing it.

## A2. Definitions

- **Task**: a unit of delivered work defined per instrument (e.g., one completed point-to-point ride of specified distance class; one revenue-mile of full-truckload freight). Task definitions are fixed within a methodology version.
- **Machine leg**: the observed price of the task when delivered by an autonomous system (no human operator on board / in the loop for normal operation, per the instrument's annex).
- **Human leg (benchmark leg)**: the observed price or documented cost of the same task delivered by a human provider, adjusted only as specified in the instrument annex (e.g., gratuity).
- **Parity ratio (P)**: machine leg ÷ human leg. **P < 1.000** means the machine-delivered task is cheaper all-in. A **parity crossing** is defined as the trailing 4-period average of P falling below 1.000 and remaining below it for 4 consecutive periods.
- **Assessment**: a published figure incorporating expert judgment under §A5 (typical for RRV).
- **Index**: a published figure computed mechanically from inputs under the annexed formula, with judgment limited to input eligibility (typical for MLP).
- **Indicator**: a published contextual series (e.g., wait-time differential, time-on-market) that is not an assessment or index and must not be used as a settlement reference.
- **Indicative series**: any series flagged `[IND]`, published for information only, excluded from composites (e.g., humanoid list-price tracking).

## A3. Input data: eligibility and hierarchy

Inputs are used in the following strict order of preference. A lower tier may be used for a given observation window only when higher tiers are insufficient under the instrument's sufficiency rule, and the tier actually used is disclosed with each publication.

| Tier | Input type | Examples |
|---|---|---|
| 1 | **Concluded transactions** | Auction hammer prices; disclosed realized revenue ÷ disclosed delivered volume from audited filings; verified contributed sale records |
| 2 | **Firm, executable quotes** | Live bookable app fares; published rate cards under which the provider stands ready to transact; firm dealer offers |
| 3 | **Listings / indicative quotes** | Asking prices; advertised ranges; earnings-call price statements not yet contracted |
| 4 | **Survey inputs** | Structured contributor responses under the contributor terms in §A10 |
| 5 | **Assessor judgment** | Only under the protocol in §A5; never the sole basis for more than 3 consecutive publications of any figure |

Company **targets, guidance, and aspirational pricing are not inputs at any tier** and may appear only in commentary, clearly labeled.

**Contributor concentration limit.** No single contributor's data may account for more than 40% of the inputs to any single published assessment. Where unavoidable in a young instrument, the publication carries a concentration flag `[K]` and the limitation is disclosed.

## A4. Calculation conventions

- **Timestamps**: all observations recorded in UTC; publication times stated in CET/CEST (Amsterdam).
- **Currency**: each series is assessed in its home currency (USD for US verticals; EUR for EU RRV series). Cross-currency composites use the ECB reference rate for the observation date. No inflation adjustment is applied within a series; real-terms restatements may be published annually as commentary.
- **Aggregation default**: the **trimmed median** (discard highest and lowest 10% of eligible observations, take the median of the remainder) unless an annex specifies otherwise. Means are used only where an annex justifies them.
- **Precision**: parity ratios to 3 decimal places; currency assessments to whole units; percentages to 1 decimal place.
- **Both legs published**: every parity print is accompanied by the levels of both legs and the count and tier of inputs used, so that any subscriber can recompute the ratio.

## A5. Expert judgment protocol

Judgment is a documented input, not an override. Where an annex permits judgment (principally RRV):

1. Judgment may **adjust** an observation for a documented specification difference (using the published adjustment factors in the annex) or **exclude** an observation as non-arm's-length, damaged/parts-only, or manipulative.
2. Judgment may not move a published figure by more than 10% from the mechanically computed value without triggering an `[J]` flag and a written rationale published in the same release.
3. Every exercise of judgment is recorded in the **assessment rationale log**: input affected, action taken, reason, resulting delta. The log is retained per §A11 and available to auditors and, on request, to subscribers in redacted form.

## A6. Insufficient data, carry-forward, staleness

- Each annex defines a **sufficiency rule** (minimum observations / minimum basket coverage) per window.
- If sufficiency fails: the prior value is **carried forward** with flag `[C]` and a staleness counter (e.g., `[C2]` = second consecutive carry).
- After **3 consecutive carries**, the series moves to `[U]` (under review): publication continues with the flag, and the Administrator states publicly what would restore assessment (new inputs, contributor recruitment, or methodology consultation).
- A series in `[U]` for 6 months is a candidate for cessation under §A12.
- No value is ever interpolated silently. Model-based estimates, if ever introduced, require a methodology change under §A9 and carry a permanent `[M]` flag.

## A7. Publication

| Layer | Content | Access |
|---|---|---|
| Headline | Current value of each index/assessment + flags | Free, public, permanent archive |
| Data | Full history, both legs, input counts/tiers, sub-series, indicators | Licensed subscribers |
| Rationale | Commentary, judgment log extracts, methodology annexes' working data | Licensed subscribers |

- **Cadence** (v0): RIDE weekly (Wednesday 16:00 CET); FREIGHT quarterly within 10 business days of the last constituent filing, with intra-quarter updates on rate-card changes; RRV monthly (first Wednesday 16:00 CET) with weekly listings indicators.
- A publication calendar for the year ahead is posted and honored. **A missed publication is treated as an incident** and disclosed as such.

## A8. Corrections, revisions, restatements

- **Correction** (error in inputs or computation): published as soon as identified; if the corrected value differs from the published value by more than 0.5% (parities) or 2% (RRV), a correction notice accompanies the next release and the archive shows both values.
- **Revision** (late-arriving eligible data): parity indices are **not revised** — late data informs the next window. RRV assessments may be revised once, at the next publication, flagged `[R]`.
- Silent edits to the archive are prohibited. The archive is append-only.

## A9. Methodology changes

- **Material changes** (task definition, hierarchy, formula, basket, reference models): 30-day public consultation, then 30-day advance notice before effect; version number increments; parallel publication of old and new methodology for one transition period where feasible.
- **Non-material changes** (typo, clarification, source succession where the successor is equivalent): effective on notice, logged in the change register.
- The change register is public and permanent.

## A10. Governance, conflicts, contributors

- **No-trading policy.** The Administrator and assessor(s) do not trade, and do not hold positions in, instruments whose price is directly determined by these assessments, and do not trade the assessed physical assets (used robots) except as disclosed reference purchases for research. Any exception is disclosed prominently and permanently.
- **Separation from any future trading activity.** If the Administrator's affiliates ever trade in adjacent markets, the assessed instrument set and the traded instrument set are disjoint, and the conflict register says so, per market.
- **Restricted list.** The Administrator maintains a public restricted list comprising: (a) issuers whose prices, products, or disclosures constitute a leg of any live or shadow instrument (including all sampled ride-hail and robotaxi providers under Annex 1 and all constituents under Annex 2); (b) issuers added by the Administrator out of caution, with reason stated. [Whether Annex 3 reference-basket manufacturers belong on the list is Q14.] The Administrator, any assessor, and accounts they control hold no positions, long or short, direct or via single-name derivatives, in restricted-list securities. Broad diversified funds are exempt.
- **No pre-positioning.** No person with access to unpublished assessment values transacts in any security on the basis of those values before publication.
- **Priority of function.** Where a research or trading opportunity arises in a restricted-list issuer (e.g., a tender offer, exchange offer, or index event), the Administrator abstains from the transaction. Abstentions are logged in the conflict register (date, issuer, opportunity class) and are disclosable on the same basis as §A5 rationale logs. The benchmark function has priority over any trading or research activity of the Administrator in every case of conflict.
- **Separation of commentary.** Opinion, analysis, forecasts, and commentary are published under a separate masthead (working name: Metascale, metascale.nl). Nothing published under the Automaat masthead constitutes opinion, forecast, or recommendation. Cross-referencing between mastheads is permitted; shared bylines on assessments are not.
- **Contributor terms** (survey/Tier-4 inputs): individual contributions are confidential, used only in aggregate, never attributed; contributors receive the aggregate output for the instrument they contribute to at no cost; contributors attest that submissions reflect genuine transactions or firm quotes.
- **Complaints**: written complaints acknowledged in 5 business days, answered in 30; complaint log retained.

## A11. Quality control and audit trail

- **Reproducibility rule**: every published figure must be reproducible from (a) archived raw inputs, (b) the methodology version in force, and (c) the assessment rationale log. This is tested internally on a sample each quarter.
- **Anomaly quarantine**: automated collection flags observations >3 median absolute deviations from the window median; quarantined observations require assessor review before inclusion (an inclusion is a §A5 judgment).
- **Lineage**: every input stores source, collection timestamp, collection method, and transformation history.
- **Retention**: raw inputs, logs, and archives retained ≥5 years.

## A12. Cessation and transition

If an instrument must cease: ≥90 days' public notice; consultation on successor or transition arrangements if the instrument is known to be referenced in any contract; final values and full archive remain publicly available.

## A13. Regulatory posture

- The Administrator intends alignment with the **IOSCO Principles for Financial Benchmarks (2013)** proportionate to the instruments' use, mapped in Part C.
- **No instrument in this family is offered, licensed, or intended for use as a reference for financial instruments or financial contracts.** On the Administrator's current understanding of the EU Benchmarks Regulation as amended with effect from 2026, the Administrator does not fall within mandatory scope. Should any party seek to reference an instrument in a financial instrument or contract, the Administrator will (a) reassess regulatory status with counsel before consenting, and (b) treat the required governance uplift as a methodology change under §A9.
- Nothing in this document is investment advice; the instruments describe markets, they do not recommend transactions.

## A14. Operational continuity and succession
- **Single-assessor disclosure.** The Administrator currently operates with a single assessor; this is disclosed as a structural limitation and mitigated as follows.
- **Runbooks.** Each instrument's collection, computation, and publication procedure is documented such that a competent third party could produce the next scheduled publication from the runbook, the archived inputs, and the methodology alone. Runbooks are versioned with the methodology; a current copy is held under an escrow-lite arrangement: a private mirror of the full working repository, refreshed on every commit, with emergency access held by a designated individual who is aware of the arrangement. While the Administrator has no external dependent, no commercial escrow or estate formality applies; the first external dependent converts this to a formal escrow arrangement.
- **Degradation protocol.** If no assessor is available for a publication: automated collection continues uninterrupted; the publication issues as a carry-forward `[C]` with an incident notice per §A7 stating the cause class and expected resumption. No figure is published without assessor sign-off.
- **Maximum unattended period.** After 4 consecutive publications issued under this protocol, affected series move to `[U]` per §A6; §A12 timelines then apply.
- **Succession.** Any change of assessor is announced in the release in which it takes effect and recorded in the change register. Backup-assessor arrangement: runbooks current and the mirror current before the first non-shadow publication; the gate fails closed. The arrangement is reviewed on the first external dependent.

---

# PART B — INSTRUMENT SPECIFICATIONS

## Annex 0 — Vertical Admission, Lifecycle, and Proxy Classification

### 0.1 Purpose and principle
This annex governs how markets ("verticals") enter, progress through, and exit the instrument family. The family is designed to expand to any domain in which machine-delivered work acquires a price; admission is governed by the test in §0.2, not by the salience of a domain's automation narrative. A vertical that fails the test is staged, not ignored, and the reason it fails is itself published.

### 0.2 Admission test
A vertical is eligible for assessed (non-`[IND]`) instruments when all three conditions hold:

1. **Machine task price.** A price for the machine-delivered task is observable at Tier 1–3 of §A3 — that is, some party sells the *task* (a ride, a mile, a pick, a resolution, a transcribed minute), not merely equipment or software with which a buyer might perform the task.
2. **Human benchmark leg.** A contemporaneous price or documented cost exists for the same task delivered by human providers, from sources meeting §A3.
3. **Unit comparability.** A task definition exists under which both legs price the same deliverable, with all adjustments (quality, scope, gratuity, vintage) enumerable and publishable in the instrument annex.

Failure of any condition assigns the vertical to a stage under §0.3; it does not exclude it from the family.

### 0.3 Lifecycle stages

| Stage | Flag | Criteria | Treatment |
|---|---|---|---|
| Watchlist | `[W]` | Deployment or credible development exists; condition 1 of §0.2 fails | Named on the public watchlist with the failing condition stated; no series published |
| Indicative | `[IND]` | Vendor list prices, claimed rates, or announced pricing exist; no Tier 1–3 task prices | Series published under permanent `[IND]` per §A2; never assessments; never composite inputs |
| Provisional | `[P]` | Tier 1–3 task prices exist; sufficiency intermittent, or concentration/staleness flags persist | Full publication with flags; excluded from composites |
| Full | — | Annexed sufficiency met for 4 consecutive periods without `[C]` or `[K]` flags | Composite-eligible |
| Completed | `[Z]` | See §0.6 | Series closed with final value and date; archived permanently as completed |

Stage transitions in either direction are announced in the release in which they take effect and recorded in the change register. A Full vertical that fails sufficiency reverts to Provisional; silent demotion is prohibited.

### 0.4 Proxy classification
Where a direct machine task price is unavailable, proxies are typed and bound as follows:

1. **Constructed cost models** (component-stack builds: hardware amortization + energy + maintenance + supervision + integration). Publishable only as model series under the `[M]` flag regime of §A6, with every assumption published alongside every value; never assessments; never composite inputs. The Administrator assesses markets and models the rest, labeled.
2. **Input-price series** (prices of inputs to the supply of machine labor: teleoperation and demonstration-data wages, robot liability premiums, RaaS escalator terms, compute). Published as Indicators per §A2. They inform the family; they are not parity.
3. **Effect-side series** (observed repricing of human labor under machine competition: platform rate compression, posting-volume changes in exposed occupations). These measure the *consequence* of the substitution frontier, not the frontier itself, and are excluded from this family entirely. They constitute a companion family under a separate methodology, kept separate to prevent circularity: an effect used as a proxy for its cause would make any composite self-referential.

### 0.5 Instantiation procedure
Every new instrument follows, in order: (1) an admission memo testing the vertical against §0.2 and proposing the unit, both legs, and candidate sources; (2) a source census; (3) an annex drafted from the standard template; (4) pipeline construction; (5) a **shadow period** of no fewer than 8 weeks in which the instrument is produced internally to full specification without publication; (6) public consultation under §A9 where the instrument introduces methodology not already in force; (7) first publication. A first print is never restated except under §A8. The Administrator will not launch instruments faster than it can operate existing ones to the incident standard of §A7; assessor capacity, not collection capacity, is the binding constraint, by design.

### 0.6 Completion and backward admission
**Completion.** A vertical is Completed when its human leg fails sufficiency for 4 consecutive periods while its machine leg remains observable, and the Administrator determines, with published rationale, that the cause is the material exit of human provision from the task rather than a data-access failure. The final parity value, the completion date, and the full series are archived permanently. Completion is the designed terminal state of a parity series, not a failure mode.

**Backward admission.** Verticals whose parity crossing predates this methodology (e.g., autonomous mining haulage; automated container terminals) are admissible under the ordinary test using current disclosures. Their function includes anchoring the cross-vertical distribution; they receive no special treatment.

### 0.7 Retrospective assessment protocol (archival reconstruction)
For verticals — principally machine-delivered cognitive services — whose historical machine-leg prices are preserved in archival captures of public materials, the Administrator may publish reconstructed historical series and retro-dated crossings, under the following rules:

1. **Flagging.** Every reconstructed observation carries a permanent `[H]` flag. `[H]` values never enter composites; composites contain only values assessed live under this methodology.
2. **Sources.** Only archival captures with independently verifiable capture timestamps (public web archives, regulatory filings, dated printed price lists with documented provenance). Each `[H]` observation stores its capture identifier and capture date. Recollection and interviews are not inputs; they may corroborate, and are logged as corroboration only.
3. **Hierarchy.** §A3 applies by analogy: archived disclosed revenue ÷ delivered volume is Tier 1; archived executable rate cards are Tier 2; archived advertised ranges are Tier 3.
4. **Same-vintage rule.** The human leg for each historical window must come from sources contemporaneous with that window. Back-casting current wages or rates onto historical windows is prohibited.
5. **Crossing dating.** Retro-dated crossings apply the §A2 definition to the reconstructed series and are published with a dating-uncertainty interval reflecting capture density. Where capture density cannot bound the crossing within 2 quarters, the crossing is published as a range, not a date.
6. **Revision.** Reconstructed series are frozen on publication and revised only on discovery of new qualifying archival evidence; such revisions are flagged `[R]` and both versions remain in the archive.
7. **Publication of failures.** The Administrator publishes the list of attempted reconstructions that did not meet these rules, with the failing rule identified. The file drawer is public: reconstructions may not be selectively published for verticals whose histories flatter any narrative, including the Administrator's.

---

## Annex 1 — RIDE: Robotaxi / Ride-hail Parity family

### 1.1 Object
The all-in consumer price of a standardized point-to-point urban ride delivered by a fully driverless commercial robotaxi service, relative to the all-in price of the same ride delivered by a human-driven standard ride-hail service, per metro and in composite. **Machine-provider eligibility:** a provider is eligible where it operates a fully driverless commercial service, publicly bookable by ordinary consumers in the metro.

### 1.2 Series
| Code | Series | Type |
|---|---|---|
| RIDE-P-{metro} | Metro parity ratio (ex-gratuity; both legs as quoted) | Index |
| RIDE-P-T-{metro} | Metro parity ratio (gratuity-adjusted, §1.5) | Index |
| RIDE-P-{provider}-{metro} | Per-provider parity sub-series (ex-gratuity) | Index |
| RIDE-P-US | Composite parity (unweighted mean of eligible metros) | Index |
| RIDE-ETA-{metro} | Wait-time differential, minutes (machine − human) | Indicator |
| RIDE-SRG-{metro} | Surge incidence differential | Indicator |
| RIDE-ADM-{metro} | Administered-parity regime marker (§1.9; 1.000 by construction) | Indicator |
| RIDE-QPD-{metro} | Quote-versus-paid divergence (§1.10; median paid ÷ quoted, per leg) | Indicator |

### 1.3 Basket construction
Per metro, a fixed basket of **24 route–time cells**: 2 representative origin–destination pairs per distance class {short ≈1.5 mi, medium ≈4 mi, long ≈8 mi} × time blocks {weekday peak, weekday off-peak, weekend evening, weekend day} (2 × 3 × 4 = 24 scheduled sampling cells). Routes are chosen for (a) location within the service area of the human comparator and of at least one eligible machine provider, (b) diversity of district type, (c) stability (no construction/closure volatility), and are published. A cell is machine-served in a window if at least one eligible machine provider returns a quote. The basket is reviewed annually under §A9.

### 1.4 Collection protocol
- Simultaneous quote requests (Tier 2 inputs: live bookable fares) for each cell across providers within a ≤5-minute window, within scheduled blocks at randomized times within each block, ≥2 samples per cell per week.
- Machine leg per cell: the lowest all-in quoted fare among eligible machine providers returning a quote (the "frontier machine quote"). Human leg: the comparator service's quoted fare (§1.5), gratuity-adjusted only for the series so specified.
- Collection is automated, rate-limited, and conducted so as to impose no load distinguishable from ordinary consumer comparison behavior; no bookings are made. The collection **method** is disclosed to providers on request; exact sampling times are never disclosed. The Administrator will prefer partnered or licensed feeds where offered on reasonable terms.

### 1.5 Comparator and gratuity treatment
- Primary human comparator: the largest standard (non-premium, non-shared) human-driven ride-hail product in the metro. Secondary comparator retained as a sub-series.
- The headline series RIDE-P is computed **ex-gratuity**: both legs as quoted, with no adjustment parameters.
- Sub-series RIDE-P-T applies a gratuity adjustment to the human leg using metro-specific empirical unconditional tipping rates, with source and vintage stated on every print; where no qualifying source exists, a flat 15% fallback applies and is flagged. Source selection is Consultation Question Q3.

### 1.6 Calculation
Per cell: ratio of the frontier machine quote to the human quote (headline) and to the gratuity-adjusted human quote (RIDE-P-T), per sample; per metro per week: trimmed median of all cell-sample ratios; per-provider sub-series are computed identically from that provider's quotes alone. Composite: unweighted mean of metro values where both provider classes served ≥80% of basket cells that week; the machine class is "served" per the machine-served definition in §1.3. Volume weighting of the composite is deferred until reliable ride-volume disclosures exist (Q4). Crossing determinations under §A2 are made and announced **per series**; the headline (ex-gratuity) series determines the headline crossing; sub-series crossings are published alongside.

### 1.7 Sufficiency
A metro publishes if ≥80% of cells yielded valid paired quotes in the window; otherwise `[C]` per §A6. A provider entering/leaving a metro triggers a basket note, not a methodology change.

### 1.8 Known limitations (disclosed with every release)
Price ≠ producer cost: the machine leg embeds capital, fleet, and strategy effects, and either leg may be promotionally priced; the index measures the **delivered-task price frontier**, which is the economically relevant object for a buyer of the task, not either provider's unit economics. Service-area geometry differs across providers; the fixed basket controls comparability, not representativeness of all rides. A judgment parameter must not determine the dating of a crossing; the headline series therefore contains no adjustment parameters.

### 1.9 Administered-parity metros
Where a machine provider's service in a metro is bookable only through the human comparator's own platform at fares set by that platform, observed parity is administered, not discovered. Such metros are excluded from RIDE-P-US. They are listed in each release with the reason stated, and published as indicator `RIDE-ADM-{metro}` (administered-par regime; value 1.000 by construction).

### 1.10 Receipt contributor program
Riders may contribute fare receipts (machine or human leg) under §A10 contributor terms. Verified receipts are Tier 1 inputs. Uses: (a) quote-versus-paid divergence, published as indicator `RIDE-QPD-{metro}` (median paid ÷ quoted, per leg); (b) sufficiency supplementation where quote collection fails. Receipts are stripped of personal data on intake; origins and destinations are retained at district granularity only. Contributors receive the RIDE data layer for their metro per §A10.

---

## Annex 2 — FREIGHT: Autonomous Trucking Parity family

### 2.1 Object
The per-mile price/cost of full-truckload dry-van freight moved by driverless Class-8 operations relative to human-driven benchmark costs, in two decompositions, plus the utilization differential.

### 2.2 Series
| Code | Series | Machine leg | Human leg | Type |
|---|---|---|---|---|
| FRT-FOP | **Full-Operation Parity** | Realized/stated all-in autonomous $ per revenue-mile (TaaS-type) | Benchmark total marginal cost per mile (industry cost study, stated vintage) | Index |
| FRT-LCP | **Labor-Component Parity** | Stated driver-replacement $ per mile (DaaS-type) | Driver wages + benefits cost per mile (same study, same vintage) | Index |
| FRT-UTIL | Utilization ratio | Disclosed annualized miles per autonomous truck | Industry average annual miles per truck | Indicator |
| FRT-ECP | Effective capacity parity = FOP ÷ UTIL | derived | derived | Indicator |
| FRT-RATE | Spot-rate context (market $ per mile, licensed source) | — | — | Indicator |

FRT-LCP is the purest available market price of machine driving labor per se and is expected to be the family's most-cited series.

### 2.3 Machine-leg inputs
Tier 1: realized revenue ÷ disclosed driverless revenue-miles from constituents' public filings, where both are disclosed for the same period. Tier 2/3: rate cards and per-mile prices stated by constituents in filings, shareholder letters, and earnings calls, used where Tier 1 is unavailable, flagged by tier. Targets and long-run pricing ambitions are excluded per §A3. Constituent register (v0): public companies with commercial driverless Class-8 operations on US public roads and per-mile-relevant disclosure; currently [Aurora Innovation; Kodiak AI]; additions on meeting the same criteria, with notice.

### 2.4 Human-leg inputs
The most recent edition of the industry-standard operational cost study (currently the ATRI *Operational Costs of Trucking* series): total marginal cost per mile for FRT-FOP; driver wages + benefits per mile for FRT-LCP; average annual miles per truck for FRT-UTIL. The edition and data-year in use are stated on every print; on a new edition, both legs update in the same release. Where lane-segmented (long-haul van) figures are published, they are preferred to the all-fleet average (Q6). If the named study ceases or materially changes methodology, successor selection is a material change under §A9, with parallel publication of both human legs for one transition period where feasible.

### 2.5 Calculation and vintage alignment
Quarterly. Machine-leg observations within the quarter (trimmed median across constituents and disclosures) ÷ human-leg value from the in-force study edition. Vintage mismatch (machine leg current, human leg study-year) is disclosed as a limitation and not silently adjusted; a CPI-adjusted variant may be added by consultation (Q7).

### 2.6 Sufficiency and staleness
n is small by construction; this is a **constituent-disclosed benchmark** and is labeled as such. If a quarter yields no new machine-leg input, `[C]` applies; staleness counter per §A6. Concentration flag `[K]` applies while constituents < 3.

### 2.7 Known limitations
Constituent count; Sun-Belt lane mix vs national benchmark; TaaS-type prices embed equipment, fuel, and insurance whose shares are not separately disclosed; stated rates may be introductory. All limitations restated in every release. FRT-FOP's legs are asymmetric — the machine leg is a price (margin-inclusive), the human leg a cost (margin-exclusive); the asymmetry biases FOP upward, i.e., against early crossing, and is accepted as conservative.

---

## Annex 3 — RRV: Robot Residual Value family

### 3.1 Object
The secondary-market value of standard configurations of widely deployed industrial robots: model-level assessments (currency per unit), retention curves (% of reference new price by age band and payload class, plus a separate cobot curve class (§3.3)), a composite index, and liquidity indicators — assessed separately for the EU and North American markets.

### 3.2 Series
| Code | Series | Type |
|---|---|---|
| RRV-{model}-{EU\|NA} | Model assessment, standard configuration | Assessment (monthly) |
| RRV-CURVE-{class} | Retention % at age bands 0–3 / 3–6 / 6–10 / 10+ yrs | Assessment (monthly) |
| RRV-CURVE-COBOT | Retention % at age bands 0–3 / 3–6 / 6–10 / 10+ yrs | Assessment (monthly) |
| RRV-IDX-{EU\|NA} | Composite, installed-base-weighted | Index (monthly) |
| RRV-TOM-{EU\|NA} | Median time-on-market, listed units | Indicator (weekly) |
| RRV-HCT-{EU\|NA} | Ask-to-clear haircut estimate | Indicator (monthly) |
| RRV-ARB | EU–NA spread, matched models | Indicator (monthly) |

RRV-IDX weighting uses installed-base weights by model where available from [source TBD], with source and vintage stated on every print; where model-level installed-base data is unavailable, payload-class weights apply and are stated per print.

### 3.3 Reference basket (v0 — Consultation Question Q8)
Selected for observed listing frequency across major venues; payload classes: micro <10 kg, small 10–30 kg, medium 30–120 kg, heavy 120–300 kg, ultra >300 kg. The cobot class sits outside the payload ladder: the payload classes remain micro, small, medium, heavy and ultra, and the cobot class is additional to them.

| Class | Models (v0) |
|---|---|
| Micro | FANUC LR Mate 200iD; ABB IRB 120 |
| Small | UR10e; FANUC M-20iA; ABB IRB 2600 |
| Medium | Yaskawa GP25; KUKA KR 60-3 |
| Heavy | FANUC R-2000iB/iC 210F; ABB IRB 6640; KUKA KR 210 R2700; Yaskawa MA2010/AR2010 (welding) |
| Ultra | FANUC M-900; ABB IRB 7600 |

Cobots (the UR class and peers) remain in the family with a separate curve class (`RRV-CURVE-COBOT`); cobot observations never enter industrial class curves.

### 3.4 Standard configuration
Arm + matching controller + teach pendant; working condition, tested or sold as operational; **no** end-of-arm tooling, welding packages, tracks, or cells; ex-warehouse/ex-site, exclusive of VAT, freight, and rigging. Deviations are adjusted per §3.6 or excluded.

### 3.5 Input hierarchy (instrument-specific application of §A3)
1. **Auction hammer prices** (EU and NA industrial auction venues), including buyer's premium, excluding VAT.
2. **Verified dealer transactions** contributed under §A10 contributor terms.
3. **Listings** (dealer sites, marketplaces, classifieds): asking prices, admitted only via the haircut mechanism in §3.7 and never as the sole basis of an assessment for more than 2 consecutive months.
4. **Assessor judgment** per §A5.

### 3.6 Specification adjustments
Published adjustment factors, initially judgment-set and revised as matched data accrues, for: operating-hours band (unknown / <10k / 10–30k / >30k), controller generation (current / n−1 / older), included application package (e.g., welding kit), refurbished-with-warranty vs as-is. Each factor's current value appears in the data layer; every applied adjustment is logged per §A5.

### 3.7 Ask-to-clear haircut
Listings are tracked longitudinally. Where a listed unit is observed to sell (venue-confirmed) or is delisted following a price path, matched pairs estimate the median ask-to-clear discount per class and region (RRV-HCT). Tier-3 inputs enter assessments only after application of the current haircut, flagged. Time-on-market (RRV-TOM) is computed from the same tracking.

### 3.8 Reference new price
Per model: manufacturer list price where published; otherwise the most recent industry association average selling price for the class, with source and vintage stated. Retention percentages always disclose the reference basis. Absolute currency assessments are primary; retention percentages are derived series and always carry the reference-price basis.

### 3.9 Windows and sufficiency
Rolling 3-month observation window, monthly publication. Model assessment requires ≥3 qualifying Tier-1/2 observations in-window (haircut-adjusted Tier 3 counts as half an observation, maximum half the requirement); otherwise `[C]` per §A6. Curves require ≥2 assessed models per class-band.

### 3.10 Contributor program
Auction houses, dealers, lessors, and insurers may contribute transaction records under §A10 terms (confidential, aggregate-only, data-for-data: contributors receive the full RRV data layer for their region). Contributor recruitment status is reported annually.

### 3.11 Known limitations
Heterogeneity is irreducible; adjustments are estimates; early months will be listings-heavy pending contributor recruitment and are flagged accordingly; the EU and NA series are distinct markets and the composite is never blended across them.

---

## Annex 4 — COGNITIVE: Cognitive-Services Parity family

*New in v0.4. Two layers, deliberately independent: a posted-price parity
series that launches regardless, and a metered assay layer measuring
cost-to-perform. **No task family is specified yet** — see §4.1.1, which bars
an unspecified family from being published, piloted, or listed as
forthcoming. This annex launches promising nothing.*

### 4.0 WHAT THIS ANNEX MEASURES, AND THE ONE THING IT DOES NOT

The price of **machine-delivered cognitive work** against **human-delivered
cognitive work** — the same parity question Annex 1 asks of driving and Annex
2 of freight, applied to knowledge tasks.

**Two layers, deliberately independent.** This separation is the annex's most
important structural decision:

| layer | what it is | depends on the other? |
|---|---|---|
| **Posted-price parity** | published list prices for machine services against published human rates | **No — launches regardless** |
| **Assay** | measured **cost-to-perform**: what a task actually costs to run | No |

**The posted-price series launches whether or not the assay layer ever runs**
(WO-010). A budget failure, a cap, or a parked assay must not silently take
the parity series down with it. They are computed, flagged and published
separately.

**What this annex does not measure: what anyone actually pays.** Posted prices
are list prices. Negotiated enterprise rates are invisible to us and are not
inferred. Every figure is labelled for what it is.

### 4.1 THE ASSAY — cost-to-perform

**The method.** Run a frozen task specification against each model in the
roster; record **input tokens, output tokens, wall-clock, retries and success
outcome**; multiply tokens by the **posted price snapshotted at run time as a
dated input**.

**Failures are priced identically.** A run that fails still consumed tokens
and still cost money. Pricing only successes would report a fiction — the
cost of the successes — and would flatter every model that fails expensively.
**Success rate is published as its own series beside the cost**, never folded
into it.

**Reps: 2 baseline, +1 on material disagreement** (WO-010). Variance-adaptive
rather than fixed: a third rep buys information only where the first two
disagree.

**Every published assay figure carries `[M]`** — calculated, not observed —
**with the formula printed beside the figure**, per §A6's flag discipline.

### 4.1.1 THE SPEC IS THE SERIES

**Cobot-lesson rigor** (WO-009 item 1). v0.3 promised a `RRV-CURVE-COBOT`
series that no code path could reach; the lesson recorded at **R3/ADJ-002** is
that **a series with no executable definition is not a series**.

Therefore: **a task family is admitted only when its specification is complete
enough for a third party to execute it and get comparable numbers.** That
means, for each family — the frozen instances, the exact prompt or input, the
success criterion, the retry rule, and the scoring procedure. **A family whose
spec is aspirational is not published, not piloted, and not listed as
forthcoming.**

### 4.1.2 SEQUENCING — GATED, NOT PLANNED (A19)

1. **Transcription first.**
2. **One text-task family second.**
3. **Agentic verticals only by expansion argument from pilot data.**

**An expansion request without its specific marginal-dollar argument is not a
request** (A19). Stated here so the sequence cannot be read as a roadmap to be
worked through.

### 4.2 THE SIZING ARGUMENT, WHICH LANDS BEFORE THE SPEND

A19 requires the basket be **designed to the cap** with per-cell cost
projection **in this draft**. It is here.

**Cost per run** = `(input_tokens × price_in + output_tokens × price_out) ÷ 1e6`,
**halved** because A19 mandates the **Batch API** for all assay runs.

**At the one price point this program has verified** — `$1 / $5` per MTok,
`claude-haiku-4-5`, the rate measured across 1,137 classifier calls:

| input tok | output tok | $/run | $/run batched | runs within $25 |
|---:|---:|---:|---:|---:|
| 1,000 | 500 | 0.0035 | 0.0018 | 14,285 |
| 5,000 | 1,000 | 0.0100 | 0.0050 | 5,000 |
| 10,000 | 2,000 | 0.0200 | 0.0100 | 2,500 |
| 20,000 | 4,000 | 0.0400 | 0.0200 | 1,250 |
| 50,000 | 10,000 | 0.1000 | 0.0500 | 500 |

**A 4-model × 30-instance × 2-rep basket is 240 runs.** Where the cap binds:

| task size | $ per full pass | passes within $25/month |
|---|---:|---:|
| 5k in / 1k out | **$1.20** | 20 |
| 20k in / 4k out | **$4.80** | 5 |
| 50k in / 10k out | **$12.00** | 2 |

**The cap binds on task size, not on basket width.** A 240-run basket is
affordable at every size above; what the cap actually governs is **how large
an instance may be** and **how often the suite re-runs**. That is the
sizing argument, and it is the opposite of what one would assume.

> **Two honest limits on this table.**
>
> **It uses one model's price for all four roster slots.** `$1/$5` is the only
> price point this program has verified, by measurement. Real rosters mix
> tiers and the frontier costs multiples of Haiku. **The table is a shape, not
> a quote**, and the pilot's first output is the real per-cell figure.
>
> **Seat one's first attempt at this table was wrong and is not shown.** It
> anchored on the classifier's measured `$0.002240` per call — a rate for a
> 1,250-token prompt and a listing title, which is nothing like an assay task.
> It would have understated a 50k-token run by roughly **twenty-fold**. The
> classifier rate anchors *overhead*, never *work*.

### 4.3 THE DERIVED SERIES

**Posted-price series** — published machine list prices against published
human rates, per task family. Independent of the assay layer.

**Implied-margin RANGE** — a **derived** series: posted price against measured
cost-to-perform. **A range, never a point**, and **the method is disclosed on
every print**. It is an inference about someone else's economics from two
observable quantities, and a point estimate would assert precision the inputs
cannot carry.

### 4.4 ARCHIVE, TRIGGERS, OPS

**Raw run transcripts are archived** (book 3.2). **The extract-of-record
doctrine (A18) applies where size demands it**: the parsed extract becomes the
archived input of record, the raw held locally and pinned by sha256.

**STANDING TRIGGER — a model deprecation notice runs the full assay suite
immediately** (WO-009 item 2), ahead of any schedule and ahead of this annex's
own cadence. **A retired endpoint can never be re-measured.** This is the one
rule in the annex that overrides the budget **sequence**, and it should: the
data becomes unobtainable, not merely delayed.

### 4.4.1 THE DEPRECATION OVERAGE — a pre-registered exception, decided in advance

**The trigger does not override A19's cap.** A19 is ratified and the frozen
criterion governs (§3.4); a ruling cannot grant an exception to it. But a
collision left unresolved becomes a fire drill in a spent month, so it is
decided **once, in advance, while calm** — in the named-exception style of the
A18/A19 exceptions block.

> **PRE-REGISTERED EXCEPTION.** A deprecation-triggered full assay suite may
> exceed the monthly cap by at most **$30**, at most **2** times per calendar
> year. **Actual overage prints beside the run**, as measured.
>
> *Values set by the operator, 2026-08-20. They supersede the $15/twice
> answer recorded at ADJ-021 §3 from 2026-08-17 — a deliberate change of
> mind, confirmed as such, not a slip. Amendable later: this is a
> spend-governance number, not a series definition, so a future change is a
> change-register entry and a line (ADJ-021 §3). A setting, not a tattoo.*

**Scale, so the bracket is filled against a number and not a feeling:** a full
pass is **~$1.20** at the smallest instance shape in §4.2 and **~$12.00** at
the largest. An overage allowance below ~$12 buys a partial suite at large
instance sizes; above it, a whole one.

**Zeroing this bracket is a legitimate answer**, and is recorded as such
(ADJ-020 §5). Then the cap simply wins: a deprecation landing in a spent month
loses the measurement, **knowingly and by prior decision** rather than by
scramble. That is a worse data outcome and a better governance one, and it is
the operator's trade to make.

**Price lists are versioned as dated inputs and are NEVER recomputed against
current prices** (WO-009 item 4). A cost figure means the cost *on its date*.

**Alert-on-silence heartbeat** — a collection gap is the only unrepairable
damage, because the window closes. Silence must page, not pass.

**Per-cell `n` and monthly assay spend publish beside the figures** (12.1),
as measured, never as estimates.
---

# PART C — IOSCO PRINCIPLES MAPPING (summary)

| IOSCO area | Principle themes | Where addressed |
|---|---|---|
| Governance | Overall responsibility; oversight; conflicts | A10, A13, A14 |
| Quality of the benchmark | Design; data sufficiency; hierarchy; transparency of determinations | A3, A4, A6, Annex 0, Annex sufficiency rules |
| Quality of the methodology | Content; changes; consultation; cessation | A4–A6, A9, A12 |
| Accountability | Complaints; audit trail; record retention; auditability | A8, A10, A11, A14 |

A full clause-by-clause mapping is maintained in the change register and available on request.

# PART D — OPEN CONSULTATION QUESTIONS

1. **Q1 (naming).** Provisionally resolved: house working name **Automaat** (pending BOIP/EUIPO word-mark clearance in Nice classes 36 and 42, KvK trade-name search, and domain acquisition); working name for the cross-vertical composite: **the Maat** (see Q10); commentary masthead: **Metascale** per §A10. Ticker scheme remains open for comment.
2. **Q2 (RIDE basket).** Are 24 cells per metro sufficient? Should airport routes be a separate cell class or excluded?
3. **Q3 (gratuity source).** Source selection for the metro-level empirical unconditional tipping rates used by sub-series RIDE-P-T (the headline series no longer depends on the parameter); candidate sources invited.
4. **Q4 (RIDE composite weighting).** Administered-parity metros are excluded per §1.9; the remaining question is composite weighting: metro-count vs disclosed-volume.
5. **Q5 (FREIGHT constituents).** Criteria for adding non-US or private operators whose customers disclose on their behalf.
6. **Q6 (FREIGHT human leg).** All-fleet vs long-haul-segment cost benchmark; treatment of team-driver comparisons for >11-hour lanes.
7. **Q7 (vintage).** Whether to publish a CPI-aligned FREIGHT variant.
8. **Q8 (RRV basket).** Model list completeness; whether cobots (UR class) belong in the same family or a separate one; criteria for adding AMR and humanoid classes when secondary flow exists.
9. **Q9 (cadence).** Whether RRV monthly / RIDE weekly matches user needs.
10. **Q10 (composite).** Specification of the cross-vertical headline composite (working name: **the Maat**): inclusion rule and weighting — working proposal: publish both the wage-bill-weighted level and a companion crossed-share series (% of covered wage bill in verticals past their headline crossing); first publication at ≥[4] Full verticals including ≥1 cognitive-services vertical.
11. **Q11 (lifecycle).** Promotion and demotion thresholds in §0.3 (currently 4 consecutive periods); the evidentiary standard for declaring a vertical Completed under §0.6.
12. **Q12 (retro-assessment).** Acceptable archive classes beyond public web archives; minimum capture density for crossing-dating; whether an `[H]` series may graduate into a live series where the same source continues uninterrupted into the present.
13. **Q13 (companion family).** Scope and timing of the effect-side family (human-labor repricing under machine competition) referenced in §0.4(3): launched in parallel, or after N verticals reach Full.
14. **Q14 (restricted-list scope).** Whether Annex 3 reference-basket manufacturers belong on the §A10 restricted list, given the remoteness of RRV assessments from their securities' prices.

*Responses to [email] by [date]. All responses may be published in summary; respondents may request confidentiality.*

---
*Change register: v0.4 — **MATERIAL under §A9.** Annex 4 added: COGNITIVE, the cognitive-services parity family. It introduces a new vertical with new task definitions and new formulas (cost-per-run; the implied-margin range), which are named in §A9 as material categories, so this is classified material and NOT editorial. Two layers, deliberately independent: a posted-price parity series that launches regardless of the assay layer, and a metered assay layer measuring cost-to-perform with failures priced identically and success rate published as its own series. No task family is specified: §4.1.1 bars an unspecified family from being published, piloted, or listed as forthcoming, so the annex launches promising nothing. Assay spend is governed by a $25/month hard cap with a pre-registered deprecation-overage exception at §4.4.1, bracketed for the Administrator. No existing series, formula, basket, reference model or threshold is changed, and no figure is affected. Ruled at ADJ-020 (17 August 2026). v0.3.3 — five operator brackets resolved and one contact correction, editorial only under §A9. The four judgment and continuity parameters are adopted at the values they already carried, the brackets removed and nothing renumbered: §A3 Tier-5 limit 3 consecutive publications; §A5 judgment collar 10%; §A14 maximum unattended period 4 consecutive publications; Annex 1 §1.5 tipping fallback 15%. The v0.3 change-register entry takes its date, 11 August 2026. The Administrator contact address is corrected to n.simpson@metascale.nl, matching the registered entity. No task definition, hierarchy, formula, basket, reference model, threshold or series is changed, and no figure is affected — every parameter keeps the value it was consulted on. Deliberately NOT resolved: the consultation window and response dates (open until a publication is scheduled) and the three consultation questions held open by design — Q14 restricted-list scope, the Annex 2 constituent register, and the RRV-IDX weighting source. Non-material under §A9, effective on notice (16 August 2026). v0.3.2 — §A14 operator brackets resolved, editorial only: the escrow arrangement is specified as escrow-lite (a private mirror of the full working repository refreshed on every commit, emergency access held by a designated individual aware of the arrangement; no commercial escrow or estate formality absent an external dependent; the first external dependent converts it to a formal arrangement), and the backup-assessor arrangement is specified as an artifact gate (runbooks current and mirror current before the first non-shadow publication, failing closed) reviewed on the first external dependent. No task definition, hierarchy, formula, basket, or reference model is touched; non-material under §A9, effective on notice (11 August 2026). v0.3.1 — Annex 3, three touches, editorial only. (1) §3.2: the cobot curve class is listed in the series table as `RRV-CURVE-COBOT` — Retention % at age bands 0–3 / 3–6 / 6–10 / 10+ yrs; Assessment (monthly). (2) §3.1: the retention-curve definition now reads "% of reference new price by age band and payload class, plus a separate cobot curve class (§3.3)". (3) §3.3: the payload-class enumeration gains the sentence: "The cobot class sits outside the payload ladder: the payload classes remain micro, small, medium, heavy and ultra, and the cobot class is additional to them." No series changes value, no figure is affected, and the separation of cobot observations from industrial class curves was already specified at §3.3 in v0.3 (11 August 2026). v0.3 — added §A14 (operational continuity and succession); §A10 restricted list, no-pre-positioning, and priority-of-function clauses; Annex 1: ex-gratuity series made headline (tip-adjusted demoted to RIDE-P-T with empirical rates), basket cell count corrected, within-block randomized sampling, frontier machine-leg definition with per-provider sub-series, new §1.9 (administered-parity metros) and §1.10 (receipt contributor program); Annex 2: FOP asymmetry and human-leg succession clauses; Annex 3: index weighting source stated with class-weight fallback, cobot curve class separated; Part D: Q3/Q4 restated, Q10 amended, Q14 added (11 August 2026). v0.2.1 — working names adopted pending clearance (house: Automaat; composite: the Maat; commentary masthead: Metascale); separation-of-commentary clause added to §A10; Q1 provisionally resolved (10 Aug 2026). v0.2 — added Annex 0 (vertical admission test, lifecycle stages, proxy classification, instantiation procedure, completion & backward admission, retrospective assessment protocol); added Q11–Q13; IOSCO mapping updated (10 Aug 2026). v0.1 — initial consultation draft (10 Aug 2026).*
