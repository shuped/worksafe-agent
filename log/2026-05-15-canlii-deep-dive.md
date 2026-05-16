# 2026-05-15 — CanLII deep-dive

## Goal

Verify and sharpen the competitive threat from CanLII Search+ and AI Case Analysis. The initial scan called CanLII the biggest disruption risk; this session was to confirm or revise.

## What was done

Six targeted searches + two WebFetch attempts (one succeeded on the Search+ blog post, two CanLII pages returned 403):
- CanLII coverage of WCAT decisions
- CanLII Search+ features, limits, pricing
- CanLII Connects AI Case Analysis (Baun v. WCAT example)
- BC-specific rollout caps for AI enrichment
- WCAT decision database access patterns (scraping/API)
- WorkSafeBC RSCM access patterns
- WCAT precedent system (s. 303(3), s. 251)
- Caseway AI lawsuit and minicounsel comparison

## Key findings (in order of strategic importance)

1. **The 30% cap is structural and public.** Lexum/CanLII has publicly committed to AI-enriching only ~30% of the BC, Ontario, and Quebec case law corpora — full coverage is "prohibitive investment." This is a permanent gap, not a phasing issue. ~70% of BC WCAT decisions will never get CanLII AI summaries.

2. **Five of nine critical BC corpora are not on CanLII at all.** Review Division decisions, RSCM Vol I & II, WCAT Manual of Rules of Practice and Procedure, and WCAT noteworthy decisions subject index live on `worksafebc.com` and `wcat.bc.ca` directly. CanLII Search+ literally cannot retrieve them.

3. **Search+ has hard daily limits**: 10 query generations + 4 deep analyses per `myCanLII` account per day. A BC lawyer doing real research hits the cap inside an hour.

4. **WCAT has a formal binding-precedent system** (s. 303(3)) distinguishing precedent-panel decisions (binding), noteworthy decisions (persuasive), and ordinary decisions. WCAT can also refuse to apply WorkSafeBC policy if "patently unreasonable" (s. 251). No generic AI tool tags any of this.

5. **Date-of-injury splits RSCM into Vol I (pre-2002-06-30) vs Vol II (current).** LLMs will fluently mix the two and produce wrong citations. Routing by date-of-injury is a one-line product policy that creates real accuracy differentiation.

6. **minicounsel proves willingness to pay.** $99/mo unlimited semantic-search service for Ontario law has paying users. Validates a $99–199/seat/mo BC-specialized tier.

7. **CanLII actively defends its corpus.** Caseway AI lawsuit (Nov 2024) settled 2026 on confidential terms. Implication: never bulk-scrape CanLII. Build the corpus from wcat.bc.ca and worksafebc.com directly.

8. **Review Division as overlooked entry point.** RD decisions live only on worksafebc.com (2013–present), higher volume than WCAT, the *first* appeal step. Most workers and small employers are unrepresented at this stage. A tool that helps prepare RD submissions could be a better entry point than chasing WCAT lawyers.

## What was written / updated

- `research/canlii-deep-dive.md` — new file. Detailed analysis of CanLII coverage, limits, precedent system, and competitive position table.
- `research/landscape.md` — updated CanLII row + Caseway and minicounsel rows; revised synthesis paragraph.
- `opportunities/defensible-edges.md` — rewrote edge #2 (WCAT corpus curation) with the 30% cap, precedent classification, date-of-injury routing, and Caseway lesson.
- `opportunities/product-ideas.md` — appended a 2026-05-15 update section revising product A, D, and E and floating a new "Review Division submission helper" angle as a top-of-funnel option.
- `sources.md` — appended new URLs.

## Open questions surfaced by this session

- How many WCAT decisions exist in the public corpus? (Need to scrape or query wcat.bc.ca to count — rough guess 30k+ since 2003.)
- What does the wcat.bc.ca terms-of-use say about automated retrieval? Want to confirm before any data work.
- What's the annual volume of Review Division decisions vs. WCAT? RD is "first level" so should be larger — by how much?
- Does anyone (academic, EAO/WAO, a law firm) already maintain a labelled WCAT corpus we could license?
- Is the WCAT MRPP itself versioned? If so, version-aware retrieval matters there too.

## Next-session candidates

- Sample 5–10 actual WCAT decisions of varying types (compensation, mental injury, RTW) to confirm the labelling schema is feasible.
- Quantify the WCAT corpus: rough decision count, decisions per year, distribution by issue type.
- Pull the WCAT noteworthy decisions subject index PDF and see how the tribunal itself categorizes.
- Quantify Review Division annual volume from the worksafebc.com search.
- Research wcat.bc.ca terms of use for data ingestion path.
- Reach out (informally) to minicounsel to understand their unit economics and customer profile.
