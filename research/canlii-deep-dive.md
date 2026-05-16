# CanLII as competitor: deep dive

The previous landscape doc treated CanLII Search+ as the biggest free-baseline risk. Closer reading shows the picture is more nuanced — and more favorable to a BC-vertical product than first appeared.

## What CanLII actually has for BC WorkSafe

| Corpus | Where it lives | On CanLII? | AI-analyzed? |
|---|---|---|---|
| **WCAT first-instance decisions** (the appeal tribunal) | wcat.bc.ca + CanLII `bcwcat` database | Yes, indexed | **Only ~30% will ever be** (see cap below) |
| **WCAT noteworthy decisions index** | wcat.bc.ca (PDF subject index) | No | No |
| **WCAT Manual of Rules of Practice & Procedure (MRPP)** | wcat.bc.ca (chapters online) | No | No |
| **Review Division decisions** (first-level appeal, internal to WorkSafeBC) | worksafebc.com decision search (2013–present, format `R012345`) | **No** | No |
| **WorkSafeBC RSCM Vol I** (date of injury pre-2002-06-30) | worksafebc.com (PDF, searchable) | No | No |
| **WorkSafeBC RSCM Vol II** (current policies) | worksafebc.com (PDF, searchable) | No | No |
| **WorkSafeBC policy and regulation decisions** | worksafebc.com | No | No |
| **Workers Compensation Act (RSBC 2019, c 1)** | CanLII + BC Laws | Yes | Partial (Act-text, not annotations) |
| **Judicial reviews of WCAT** (BCSC, BCCA, SCC) | CanLII | Yes | Yes (these are higher-court decisions, prioritized) |

**Key takeaway: 5 of 9 critical corpora are NOT on CanLII at all** — they live on worksafebc.com and wcat.bc.ca. CanLII Search+ cannot retrieve them. A BC-vertical tool that integrates all 9 has an unreplicable retrieval moat from day one.

## The 30% cap — most important finding

> "AI enrichments in Quebec, Ontario, and British Columbia will be capped at roughly 30% of their total case law collections. This level will remain the target for those three large jurisdictions because producing AI-powered summaries for their entire historical corpus would require a prohibitive investment. In these three provinces, documents most likely of setting precedents will be processed in priority."
> — Lexum / CanLII rollout statement

Implications:
- ~70% of BC WCAT decisions will permanently have no CanLII AI summary.
- CanLII prioritizes "precedent-setting" decisions — meaning higher-court judicial reviews and binding precedent panels. The huge middle of "noteworthy + ordinary" WCAT decisions is the long tail CanLII will not invest in.
- A domain-expert product can comprehensively cover the full WCAT corpus (currently ~30k+ decisions since 2003) where CanLII never will.

## Search+ usage limits

- **10 query generations per day**, **4 deep analyses per day** per free `myCanLII` account.
- These are hard caps for free users.
- "Limits may change over time" but the cap exists because the AI inference is genuinely expensive.

Implications:
- A lawyer doing 5+ research sessions per day immediately runs out. Paid alternatives have headroom.
- minicounsel ($99/month, unlimited, Ontario-focused) already proves people pay for unmetered access to AI-grounded Canadian law search.
- A BC equivalent of minicounsel, but specialized for WCAT/RSCM, would clear $99–199/seat/month.

## Precedent system that CanLII doesn't capture

Under s. 303(3) of the Workers Compensation Act, **WCAT "precedent panel" decisions are binding on future panels**, while "noteworthy" decisions are persuasive but not binding. WCAT can also refuse to apply WorkSafeBC policy if "patently unreasonable" under s. 251.

CanLII's generic AI analysis does not flag:
- Whether a decision is a precedent panel decision (binding) vs. noteworthy (persuasive) vs. ordinary
- Which RSCM policy version was in force on the date of injury
- Whether the panel applied or refused policy under s. 251
- Whether the decision was judicially reviewed and the outcome

These are **the four things that actually determine whether you can cite a WCAT decision in a submission**. A vertical tool that surfaces them is differentiated.

## Date-of-injury / RSCM version routing

RSCM Vol I governs claims with date of injury before 2002-06-30; Vol II governs after. A generic AI tool will fluently mix policies from both volumes and produce wrong citations. A WCAT-aware tool routes by date-of-injury before retrieval — a one-line policy that the user can't get from CanLII or any US workers' comp tool.

## CanLII's data-defense posture (Caseway lawsuit)

In November 2024 CanLII sued Caseway AI for "bulk and systematic download and scraping" of its corpus. Settled 2026 on confidential terms with "move forward independently" language. Implications:

- Any BC-vertical product **cannot legally bulk-scrape CanLII** to build a corpus.
- Direct ingestion from `wcat.bc.ca` (decisions, MRPP) and `worksafebc.com` (Review Division, RSCM) is the lower-risk path.
- A partnership or licensed feed with CanLII is possible but slow.
- The wcat.bc.ca decision search does not appear to have a public API; ingestion will likely require respectful scraping + monitoring of their terms of use.

## Competitive position summary

| Dimension | CanLII Search+ | minicounsel | A BC-vertical product |
|---|---|---|---|
| Free? | Yes (capped) | Paid $99/mo | Probably paid |
| BC coverage | Partial (30% AI cap, no RD, no RSCM, no MRPP) | Ontario-focused | **Full BC corpus** |
| Workflow output | Boolean queries + key passages | Semantic search + answers | Submission drafts, precedent matching, evidence checklists |
| Source verifiability | Yes (links to docs) | Claims 99.9% | Strict citation discipline by design |
| Date-of-injury / policy versioning | No | No | **Yes** |
| Precedent-panel vs noteworthy tagging | No | No | **Yes** |
| Review Division decisions | **No** | No | **Yes** |
| Lawyer-day usage headroom | 10 queries/day | Unlimited | Unlimited |

## What this means for the project

The competitive thesis sharpens:

1. **The wedge is the corpus, not the model.** Aggregating RD + WCAT + RSCM + MRPP + judicial reviews into one labelled retrieval layer is a 6–12 month build that nobody else has done.
2. **The 30% cap is structural and permanent.** CanLII will not close this for BC even at frontier-model prices.
3. **Vertical workflow beats horizontal retrieval.** Search+ helps you find a case; a WCAT Copilot helps you write a submission. Different value props, different price points.
4. **Free baseline is real but partial.** Search+ commoditizes the floor (basic precedent lookup), but the ceiling (workflow output, full-corpus retrieval, version-aware policy) is wide open.
