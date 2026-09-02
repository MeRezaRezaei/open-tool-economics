# Coverage Map — Raw Sections to Representation Homes

This table maps each of the 24 headed sections in `raw/VERBATIM-RAW.md` (the single source of truth) to its representation home(s) in the derived docs. Status reflects how fully the raw claim is rendered:

- **full** — the section's core claim is faithfully represented in one or more derived docs, with no material omission.
- **partial** — the claim appears but is thin, passing, or not given a dedicated treatment.
- **missing** — the claim has no representation in any derived doc.

| # | Raw Section | Home Doc(s) | Status |
|---|------------|-------------|--------|
| 1 | Core Thesis | [MANIFESTO.md](../MANIFESTO.md), [IDEA.md](../IDEA.md), [01-core-framework.md](01-core-framework.md), [04-game-theory.md](04-game-theory.md), [07-the-full-cycle.md](07-the-full-cycle.md) | full |
| 2 | The Open Source License Advantage | [MANIFESTO.md](../MANIFESTO.md) (line 104, passing mention), [08-license-enforcement.md](08-license-enforcement.md) | full |
| 3 | Why Open Source Projects Die | [MANIFESTO.md](../MANIFESTO.md), [IDEA.md](../IDEA.md), [04-game-theory.md](04-game-theory.md) | full |
| 4 | The Monopoly Solution | [04-game-theory.md](04-game-theory.md), [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md) | full |
| 5 | Beating Closed Source | [04-game-theory.md](04-game-theory.md), [IDEA.md](../IDEA.md) | full |
| 6 | The Idea (Not the Tools) | [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md) | full |
| 7 | No Copyright or Patent | [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md), [07-the-full-cycle.md](07-the-full-cycle.md) | full |
| 8 | The Layer Separation Problem | [01-core-framework.md](01-core-framework.md), [03-separation-methodology.md](03-separation-methodology.md), [09-fused-concerns.md](09-fused-concerns.md), [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md) | full |
| 9 | The Layer Model | [02-layer-model.md](02-layer-model.md), [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md) | full |
| 10 | Mixed Concerns | [02-layer-model.md](02-layer-model.md), [03-separation-methodology.md](03-separation-methodology.md), [07-the-full-cycle.md](07-the-full-cycle.md), [09-fused-concerns.md](09-fused-concerns.md), [MANIFESTO.md](../MANIFESTO.md) | full |
| 11 | The Formula | [01-core-framework.md](01-core-framework.md), [03-separation-methodology.md](03-separation-methodology.md), [09-fused-concerns.md](09-fused-concerns.md), [IDEA.md](../IDEA.md) | full |
| 12 | The Cross-Discipline Advantage | [MANIFESTO.md](../MANIFESTO.md) (lines 92–98) | partial |
| 13 | My Vision and Role | [IDEA.md](../IDEA.md) (lines 159–162) | partial |
| 14 | Division of Labor | [IDEA.md](../IDEA.md) (lines 159–162) | partial |
| 15 | The Poverty Trap | [05-macro-economics.md](05-macro-economics.md), [04-game-theory.md](04-game-theory.md), [06-missing-key.md](06-missing-key.md), [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md), [index.md](../index.md) | full |
| 16 | Tool Neutrality | [01-core-framework.md](01-core-framework.md), [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md), [index.md](../index.md) | full |
| 17 | The GNU/Linux Lesson | [04-game-theory.md](04-game-theory.md), [05-macro-economics.md](05-macro-economics.md), [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md) | full |
| 18 | What We Have More Than Open Source Ideology | [IDEA.md](../IDEA.md) (lines 90–96) | full |
| 19 | The Absolute Definition of a Tool | [01-core-framework.md](01-core-framework.md), [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md) | full |
| 20 | The Friction Cycle | [02-layer-model.md](02-layer-model.md), [04-game-theory.md](04-game-theory.md), [05-macro-economics.md](05-macro-economics.md), [07-the-full-cycle.md](07-the-full-cycle.md) | full |
| 21 | Frictions Are Results of Higher Usage | [02-layer-model.md](02-layer-model.md), [04-game-theory.md](04-game-theory.md), [05-macro-economics.md](05-macro-economics.md), [07-the-full-cycle.md](07-the-full-cycle.md), [index.md](../index.md) | full |
| 22 | How This Evolves the Poverty Line | [05-macro-economics.md](05-macro-economics.md), [04-game-theory.md](04-game-theory.md), [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md) | full |
| 23 | The Missing Key — The Path, Not Just the Tool | [06-missing-key.md](06-missing-key.md), [07-the-full-cycle.md](07-the-full-cycle.md), [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md) | full |
| 24 | On The On-Ramp (Not the Jungle Case) | [06-missing-key.md](06-missing-key.md), [07-the-full-cycle.md](07-the-full-cycle.md), [IDEA.md](../IDEA.md), [MANIFESTO.md](../MANIFESTO.md) | full |

## Gaps found

Three hardening gaps that the following tasks own:

- **Gap A (Task 2):** License-as-enforcement mechanism (section 2) is under-represented. The raw claims the license *prevents monopoly and keeps the economy earning at performing* — but the only derived mention is a passing line in MANIFESTO.md ("Give it a permissive open license"). The durability mechanism (why a license, not just a wish; what it protects; how it closes the loop) has no dedicated treatment. → Task 2 creates `framework/08-license-enforcement.md`.

- **Gap B (Task 3):** Fused-concern problem (sections 8, 10, 11) is only a seed in `framework/03-separation-methodology.md` (lines 59–72), not a full treatment. The hardest sub-problem — when a tool is integrated into a performance and removing it degrades the performance — needs a self-contained method doc. → Task 3 creates `framework/09-fused-concerns.md`.

- **Gap C (Tasks 5, 6):** No verification layer or shared glossary exists to stop term drift across the ~120 uses of "performance" and other core terms. Definitions are used consistently today, but there is no oracle document that a consistency checker can reference. → Task 5 creates `framework/10-glossary.md`; Task 6 runs the consistency gate. Drift guard: see `framework/10-glossary.md` for canonical definitions.

Sections 12, 13, 14 (Cross-Discipline Advantage, Vision/Role, Division of Labor) are flagged as `partial` — these are user-domain framing items, not representation gaps. They describe the author's role and do not require a dedicated framework doc.

## Support layer

Beyond the claim-by-claim homes above, `framework/11-literature.md` backs selected doctrine claims with verified academic literature (DOI-verified) separated by claim area. It is a support layer, not a representation home for any single raw section: it adds no doctrine, it only cites. Its purpose is to make the doctrine *standable* — arguable and defensible against the literatures it touches.

## Demonstration layer (2026-09-02)

The `separations/` ledger applies the Separation Law (sections 8, 11) and the
fused-concern method (section 8) to real recurring cases — proof the method works,
not new doctrine. See `separations/00-index.md`.

---

## Audit log

- **2026-09-02 (final gate):** Sections 2, 8, 10, 11 closed by Tasks 2–3 → `full`. Definition-consistency check passed (no doc denies a glossary definition). Front-door consistency passed (plain page and manifest tell the same story). Sections 12, 13, 14 intentionally remain `partial` — user-domain framing, not a gap; left for the user to decide scope/framing, deliberately NOT resolved by this plan.
