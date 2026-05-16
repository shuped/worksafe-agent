---
title: Product ideas
parent: Opportunities
nav_order: 1
---

# Product hypotheses

Six concrete entry points, ranked roughly by ease-of-monetization × defensibility.

---

## A — "WCAT Copilot" for lawyers & consultants ⭐ best first wedge

**Who pays:** BC firms doing WCB work (Gosal & Co et al.), employer consultants (UCDC), independent reps. Seat-based SaaS, $200–500/mo/seat. Reference price point: minicounsel charges $99/mo for unmetered Ontario-focused AI legal search.

**Core capability:** RAG over the **nine BC-specific corpora** (Act, RSCM Vol I, RSCM Vol II, WCAT decisions, WCAT noteworthy index, WCAT MRPP, Review Division decisions, WorkSafeBC policy decisions, BCSC/BCCA judicial reviews) + LLM that drafts submission outlines, finds analogous precedent decisions, distinguishes binding precedent-panel decisions from persuasive noteworthy ones, routes to the correct RSCM volume by date of injury, and flags missing evidence categories per the policy that applies.

**Why it wins:**
- Five of the nine corpora are **not on CanLII at all** (see `research/canlii-deep-dive.md`). CanLII Search+ structurally cannot answer questions that require Review Division decisions, RSCM, or MRPP.
- CanLII has publicly capped BC AI enrichment at ~30% of corpus. The remaining 70% of WCAT decisions are accessible to whoever builds the full pipeline first.
- CanLII Search+ is free but limited to **10 queries / 4 analyses per day** — lawyers exhaust this in one research session.
- s. 303(3) precedent-panel tagging and date-of-injury / RSCM-volume routing are domain-specific moves no generic tool makes.
- Lawyer compliance pressure (citation verification) favours grounded, vertical tools.

**Risks:**
- Small market (a few dozen seats in BC). Need ACV high enough to justify build.
- WCAT Online filing integration is closed.
- CanLII actively defends its corpus (Caseway lawsuit). Ingest from wcat.bc.ca and worksafebc.com directly, not CanLII.

---

## B — Employer claims navigator for small/medium BC businesses

**Who pays:** SMBs with 10–500 employees, ~1–10 claims/year. Subscription per business, $99–399/mo.

**Core capability:** Conversational assistant that walks an HR/safety lead through "you just got a notice from WorkSafeBC — what now?" — deadlines, evidence to preserve, when to engage EAO vs. lawyer, return-to-work program builder, claim-cost forecaster.

**Why it wins:**
- Falls between EAO (free, generic, capacity-limited) and a $400/hr lawyer.
- Single avoided bad outcome (a $30k claim cost, a Bill 41 suppression fine) justifies a year of subscription.
- Distribution: industry associations, brokers, payroll providers.

**Risks:**
- High customer-education burden ("why pay when EAO is free?")
- Need bilingual / accessible UX.

---

## C — Worker claim companion (worker-side)

**Who pays:** Tricky. Workers themselves don't have budget. Options:
- B2B2C via plaintiff law firms (lead-gen and intake offload)
- Sponsored by unions (BCGEU, HSA, locals)
- Freemium + referral revenue to lawyers for complex cases

**Core capability:** Symptom diary, intake script, medical-records uploader with OCR + chronology, "what to ask your case manager," appeal deadline alerts, plain-language explainers of denial letters.

**Why it wins:**
- No worker-facing product exists in BC. Workers are systematically under-resourced.
- Trust-building data flywheel: anonymized claim outcomes inform A and D.

**Risks:**
- Monetization is the hard part. May be a loss-leader / mission-driven product that feeds paid products.
- Privacy and PHIPA-style obligations are serious.

---

## D — Medical-record summarization tuned for WCAT

**Who pays:** Law firms, IME providers, EAO/WAO if procurement allows.

**Core capability:** Wisedocs-style record summarization but specifically labelled for **RSCM impairment categories, presumptive coverage triggers, psychological-stressor patterns, return-to-work feasibility statements**. Outputs a WCAT-ready evidence digest with citations.

**Why it wins:**
- Wisedocs is generic across lines of business; tuning for WCAT-specific evidence framing is a real moat.
- Per-claim pricing model is proven (Wisedocs charges per record).

**Risks:**
- Wisedocs could close this in a quarter if they choose to.
- Need a stable supply of labelled BC claim files to fine-tune.

---

## E — Decision-precedent search (free funnel)

**Who pays:** No one directly — this is top-of-funnel for A and D.

**Core capability:** Better-than-CanLII search across **the union of WCAT decisions, Review Division decisions, RSCM, and WCAT MRPP** — none of which is fully covered on CanLII. Vector retrieval, issue tagging, outcome statistics ("appeals on chronic-pain quantum win 41% of the time when X policy is cited"), and precedent-panel-vs-noteworthy filtering.

**Why it wins:**
- Search+ has hard daily caps (10/4 per user) and explicitly excludes the long-tail 70% of BC case law. This is a permanent structural gap.
- Review Division decisions (the higher-volume first-instance appeal layer) are **not on CanLII at all** — they live on worksafebc.com. Indexing them is a unique offering.
- SEO and word-of-mouth in a small professional community.
- Demonstrates retrieval quality before asking anyone to pay.

**Risks:**
- CanLII may invest more in BC eventually, but the 30% cap is published policy. Bet against them reversing it.
- Build something CanLII can't or won't: cross-corpus retrieval, outcome analytics, panel/vice-chair patterns, time-series of policy interpretation.

---

## F — Mental-injury claim specialist tool

**Who pays:** Either firms specializing in psychological claims, or directly as worker-side after Bill 23/41 expanded this surface area.

**Core capability:** Structured intake for workplace stressors, bullying/harassment patterns, traumatic-event chronologies, with templated evidence asks (witness statements, contemporaneous notes, treatment records) and matching to the small but growing body of WCAT mental-injury precedent.

**Why it wins:**
- Bill 23 (no one-year cap) and Bill 41 expanded coverage; claims volume is rising but adjudication is inconsistent.
- Mental-injury claims are evidence-sparse — exactly where structured tooling helps most.
- Underserved by both lawyers (low ROI per case) and WAO (capacity).

**Risks:**
- Sensitive user population; needs trauma-aware design.
- Outcome data is noisy; precedent corpus is thin.

---

## Sequencing recommendation

1. Build **E** as a free corpus + search prototype. Forces you to build the data pipeline anyway.
2. Convert the corpus into **A** for paying lawyers/consultants. First revenue.
3. Use insights from A to inform **D** (record summarization), which has the biggest TAM.
4. Spin off **B** or **F** once you have brand/distribution in BC.
5. **C** is a long-term strategic asset, not a near-term revenue line.

---

## Update — after CanLII deep-dive (2026-05-15)

See [`../research/canlii-deep-dive.md`](../research/canlii-deep-dive.md) for the full analysis. Key revisions to the hypotheses above:

- **E (decision-precedent search) gets stronger, not weaker.** CanLII Search+ is capped at 10 queries/day per free user, and ~70% of BC case law will permanently lack CanLII AI enrichment. **minicounsel** in Ontario charges $99/mo for unlimited semantic search and has paying users — direct proof of willingness to pay for paid-tier Canadian legal AI. A BC-specialized equivalent priced $99–199/seat/mo is realistic.
- **A (WCAT Copilot) corpus moat is bigger than originally framed.** Five of nine critical BC corpora (Review Division decisions, RSCM Vol I/II, WCAT MRPP, WCAT noteworthy index) are not on CanLII at all. A vertical product integrating them is unreplicable by generic legal AI without a 6–12 month corpus build.
- **D (medical-record summarization) is less differentiated by retrieval and more by workflow.** Wisedocs already does generic medical-record summarization well. The BC-specific tuning (RSCM impairment categories, presumptive coverage triggers, mental-injury stressor patterns) is real but narrower than initially scoped.
- **New angle to consider — Review Division submission tool.** Review Division decisions live only on worksafebc.com, have higher annual volume than WCAT, and are the **first** appeal step. Building a tool that helps a worker or employer prepare a Review Division submission (cheaper, faster, more iterations, lower legal stakes than WCAT) could be a better top-of-funnel than going straight at WCAT lawyers. Workers' Advisers Office handles a fraction of these; everyone else is on their own.
- **Caseway-lawsuit lesson:** ingest from wcat.bc.ca and worksafebc.com directly, never bulk-scrape CanLII. This shapes the data pipeline architecture from day one.

Revised sequencing: **E → A** remains the right path; consider an **E.5** intermediate — a free Review-Division-submission helper that builds a worker-side data flywheel before charging the lawyer side.
