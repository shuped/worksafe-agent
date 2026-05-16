---
title: 2026-05-14 — Initial landscape scan
parent: Log
nav_order: 2
---

# 2026-05-14 — Initial landscape scan

## Goal

Kickoff session: scan the AI/software landscape for products serving BC employers managing WorkSafe appeals and injured workers managing claims; identify competitors, their edges, and opportunities for domain experts.

## What was done

Ten web searches across:
- WorkSafe BC / WCAT / Review Division appeal process basics
- Bill 23 (2020) and Bill 41 (2022) statutory reforms
- BC-specific human services (Gosal & Co, WAO, EAO, UCDC, KSW)
- US workers' comp AI (Wisedocs, Origami, Gradient AI, CorVel, CLARA, CompIQ, DigitalOwl, ServisBot)
- Canadian legal AI (Spellbook, Alexi, Jurisage, CanLII Search+)
- Brief-writing AI (Clearbrief, BriefCatch, Briefpoint)
- Compliance/sanctions landscape post-*Mata v. Avianca*
- Worker-facing claim-tracking apps (mostly US: VA, SSDI)

## Key findings

1. **No software-native incumbent in BC** for WorkSafe appeals. Every BC player is a human service business.
2. **Wisedocs** (Toronto, Series A $12.7M) is the closest threat — Canadian, multi-line medical-record AI, expanding workers' comp coverage in 2026. Currently sells to carriers/TPAs/defense, not BC tribunal workflow.
3. **CanLII Search+** is the biggest "free baseline" risk — RAG case analysis is live in AB/SK/MB/PEI, BC tribunals not yet. Window to launch is open but probably 18–36 months.
4. **WAO and EAO** offer free representation. Any paid product must clearly outperform free government help.
5. **Bill 23 / Bill 41** expanded mental-injury claims and added employer compliance teeth — two underserved sub-niches.
6. **Compliance pressure** on lawyers (AI disclosure, hallucination sanctions) favours vertical retrieval-grounded tools over generic LLMs.

## What was written

- `README.md` — project framing & navigation
- `research/domain-primer.md` — how the BC appeal system works
- `research/landscape.md` — competitors in three concentric circles
- `opportunities/product-ideas.md` — six product hypotheses, sequenced
- `opportunities/defensible-edges.md` — what a domain expert uniquely brings
- `sources.md` — bibliography (this session's URLs)

## Open questions (for next session or user input)

- Who is the **domain expert** here — the user, a co-founder, or someone we need to recruit? Determines GTM dramatically.
- Is the goal a **single product** or a **portfolio**? Affects sequencing of A→F.
- Is there budget/intent to **buy or license a WCAT decision corpus**, or scrape & label from scratch?
- Worker-side vs. employer-side: pick one for v1, or build a shared infrastructure layer first?
- Any existing BC contacts at WAO, EAO, Gosal, UCDC, sectoral safety associations, unions?

## Next-session candidates

- Pull WCAT annual report and quarterly stats; quantify the market.
- Search Crunchbase / LinkedIn for Canadian workers'-comp-tech founders (signals of attempts that died).
- Read 5–10 sample WCAT decisions to confirm the labelling schema sketched in `defensible-edges.md`.
- Map the RSCM table of contents to understand corpus boundaries.
- Run a "what if Wisedocs entered BC tomorrow" stress test on each product hypothesis.
