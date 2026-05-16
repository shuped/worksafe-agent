---
title: Defensible edges
parent: Opportunities
nav_order: 2
---

# Defensible edges for a domain expert

A non-domain-expert building from generic AI primitives can clone any of these products in 3–6 months. The moat is **what they can't see** — local procedural knowledge, trust signals, and labelled data.

## 1. Procedural & policy depth

The BC system has a dense set of rules that don't appear in LLM training data with any granularity:
- When a Review Division decision is required vs. a direct appeal route
- Which RSCM policy applies to which adjudication question (and which policy version was in force on the date of injury — versioning matters)
- The order in which evidence must be filed at WCAT
- What kinds of evidence vice chairs actually credit vs. reject
- Independent Health Professional pathway under Bill 41 — when to invoke it

A domain expert can encode this as system prompts, retrieval filters, and decision trees that a generalist literally cannot reproduce without years of practice.

## 2. The full-corpus + labelled-precedent moat

CanLII has formally committed to AI-enriching only **~30% of the BC case law corpus** (cost reasons; published policy). Review Division decisions, RSCM Vol I/II, the WCAT Manual of Rules of Practice and Procedure, and the WCAT noteworthy decisions subject index are **not on CanLII at all** — they live on worksafebc.com and wcat.bc.ca.

A BC-vertical product that ingests and labels the **full** corpus across both source sites has a permanent structural advantage:

- Issue category (entitlement, wage loss, PFI, RTW, vocational rehab, mental injury, etc.)
- **Precedent classification under s. 303(3): binding precedent-panel vs. persuasive noteworthy vs. ordinary** — the single most important attribute when citing a WCAT decision, and one no generic tool captures
- Date-of-injury / RSCM Vol I vs Vol II routing (LLMs will otherwise mix policy versions)
- Policy version cited and whether the panel applied or refused it under s. 251 ("patently unreasonable")
- Outcome (allowed, dismissed, partially allowed, varied)
- Vice chair / panel
- Time to decision
- Whether judicially reviewed and the result
- Linked Review Division decision number and outcome (where available)

This labelled corpus is a private asset that powers everything from precedent search to outcome prediction, doesn't expire, and **CanLII has publicly stated it will not invest in matching it for BC** at the deep-enrichment level.

**Important constraint:** CanLII actively defends its corpus (Caseway AI lawsuit, 2024–2026). Build the corpus from wcat.bc.ca and worksafebc.com directly, not by scraping CanLII.

## 3. Trust signals and a human face

Workers and small employers don't trust black-box software with high-stakes decisions. A domain expert attached publicly to the product (former case manager, retired vice chair, longtime worker-side rep) creates trust no big-tech entrant can replicate quickly. WAO/EAO have institutional trust; Wisedocs has none with end users.

## 4. Compliance-grade source grounding

Lawyers face real sanction risk for AI use. Tools that produce **verifiable citations to the Act, RSCM section, or WCAT decision number** — and refuse to generate uncited assertions — are differentiated. This requires the labelled corpus from edge #2.

## 5. Workflow integration that matches how people actually work

WCB lawyers and consultants still operate in PDF + Word + paper claim files. A tool that ingests a real claim package (decision letter, claim notes, medical records) and outputs a real submission draft — with the right header style, the right policy citations, the right paragraph structure — beats generic AI on time-to-completion by an order of magnitude.

## 6. Distribution access

Domain experts have warm contacts:
- The handful of BC WCB law firms
- EAO/WAO procurement
- Employer associations (Construction Labour Relations, BC Business Council members, sectoral safety associations)
- Unions and labour councils
- IME / medical-legal report providers

Cold outbound into this market is slow. Existing relationships compress the GTM by 12+ months.

## What is NOT a moat

- **Model quality.** Frontier LLMs commoditize quarterly. Don't bet here.
- **Generic legal-AI features** (citation, summary, redlining). Spellbook, Alexi, CanLII, Clearbrief are spending tens of millions to lead these.
- **"We have a chatbot."** Everyone has a chatbot.
- **Cost-savings claims without measurement.** Employers and firms have heard this; need real metrics.

The bet: combine **edge #1 + #2 + #5** into product A (WCAT Copilot), use **edge #6** for distribution, and let **#3 + #4** compound over years.
