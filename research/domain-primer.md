# BC WorkSafe domain primer

## The system at a glance

WorkSafe BC is the provincial workers' compensation board. Decisions about claims flow through a three-stage path:

1. **WorkSafeBC case manager** — adjudicates the claim, makes initial decisions on entitlement, wage loss, return-to-work, permanent functional impairment, etc. Governed internally by the **Rehabilitation Services and Claims Manual (RSCM)**.
2. **Review Division (RD)** — first level of appeal, internal to WorkSafeBC. Most case manager decisions must go here first.
3. **Workers' Compensation Appeal Tribunal (WCAT)** — second and final level. Independent body. **30-day deadline** to file Notice of Appeal after the RD decision date. Hearings are by written submission or oral hearing. The vice chair/panel decision is final (only judicial review remains).

Either workers **or employers** (or their representatives) can initiate appeals.

## Volume signal

WCAT received ~650 new appeals/applications in Q2 2024 — roughly **2,500–2,800 appeals per year** flow through WCAT. This excludes Review Division volume (which is larger), and excludes the claim-management volume upstream (tens of thousands of active claims).

## Key statutes & recent changes

- **Workers Compensation Act (RSBC 2019, c 1)** — primary statute.
- **Bill 23 (2020)**: Removed the one-year window for filing mental-health claims; expanded mental-injury coverage.
- **Bill 41 (2022, in force 2023)**:
  - Workers and employers in a WCAT appeal can request review by an **independent health professional**.
  - Indexing changes to inflation adjustments.
  - **Claim suppression** by employers is now a violation (fines up to $777,601 + jail).
  - Maximum non-traumatic hearing-loss compensation raised.

These reforms have produced two notable side-effects:
- More **mental-injury / psychological claims** are being filed — a relatively undocumented, evidence-sparse claim type that's hard to adjudicate.
- Employers face higher compliance pressure around claim suppression and return-to-work conduct.

## Built-in "free competitors"

These are the price-floor anchors for any paid product:

- **Workers' Advisers Office (WAO)** — independent BC government branch. Free advice and *sometimes* representation for workers contesting WorkSafeBC decisions. Known to be capacity-constrained; cannot represent every applicant.
- **Employers' Advisers Office (EAO)** — same structure for employers. Free duty line, eight regional offices, prepares submissions to RD/WCAT for employers.

Both offices set the bar: any paid solution must clearly outperform free government help on **speed, depth, or coverage**.

## Information sources for any tool

A well-built BC-specific AI product will likely need to integrate:

- **Workers Compensation Act** (free, CanLII)
- **RSCM** (Rehabilitation Services and Claims Manual — WorkSafeBC's internal policy/practice manual)
- **WCAT past decisions** (publicly searchable; growing precedent corpus)
- **WCAT decisions of interest / annual digests**
- **BC Supreme Court judicial reviews of WCAT decisions** (CanLII)
- **WorkSafeBC policy bulletins and assessment manual**

CanLII's **Search+** AI tool now does RAG-style case analysis, but BC is not yet in the rollout (Alberta, Saskatchewan, Manitoba, PEI live first). A BC-specific corpus + tuning is currently a wedge.
