# Harden the Doctrine Representation — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.
>
> **Repo reality check:** this is a NON-CODE project. The deliverable is a *representation of an idea*, not software. "Test" therefore means a **verifiable read-back** (does a doc faithfully render a raw claim? does every raw section have a home? do terms stay consistent across docs?), not a unit test. There is **no `composer test` / `pytest` gate** here. Each task ends with an independently checkable deliverable described in its Step-2 "Expected" lines.

**Goal:** Make the Open Tools Doctrine representation so precise that a first-time reader cannot walk away misunderstanding it — by closing the known representation gaps, fully treating the hardest remaining sub-problem, and adding a permanent verification layer so the representation cannot silently drift from its source of truth.

**Architecture:** Audit the current 8 framework docs + front-end docs against the single source of truth (`raw/VERBATIM-RAW.md`, the only authority — all derived docs are presentations). Close three concrete gaps discovered in the audit: (1) the open-source-license mechanism is essentially unrepresented; (2) the fused-concern problem is only a "seed," not a full treatment; (3) there is no coverage/verification layer to stop drift. Along the way, harden the front door (plain-language entry) and add a shared glossary so the 120+ uses of "performance" and other core terms cannot drift. The plan is deliberately ordered so each task's deliverable is independently verifiable and reviewable.

**Tech Stack:** Markdown docs. `raw/VERBATIM-RAW.md` (source of truth) is read-only — derived docs must never alter it. No code anywhere.

**Spec:** The authoritative source is `raw/VERBATIM-RAW.md`. The doctrine's own representation rules (from that spec's "A Note on Decisions"): the assistant executes everything beyond doubt; the user decides only hard economic/philosophical questions. Tasks that touch a user-domain decision must **propose + flag for approval**, never decide unilaterally. Plan argumentation cites raw sections by name (e.g. "The Open Source License Advantage").

## Global Constraints

- **Raw is immutable.** `raw/VERBATIM-RAW.md` is the only source of truth. No task may edit it. Derived docs are corrected presentations; every claim must trace to a raw section.
- **Zero code.** This is a no-code repo. No scripts, no tests-framework, no build tooling. "Verification" is doc-based (checklists, coverage tables, read-backs), not executable.
- **Do not decide user-domain questions.** Naming, scope framing, the correctness of the fused-concern answer, and whether to launch the pledge are the user's calls. Where a task needs one of these, output a clearly-labeled *proposal* and ask the user before finalizing.
- **Term discipline.** "Tool" and "performance" must be used with exactly the definitions from the raw ("Input → Tool → Output" and "the doing/value act"). No doc may redefine them or introduce synonyms that change meaning.
- **No placeholders.** Every task below carries the actual content to write — no "TBD", no "add detail later".
- **Commit discipline.** Each task ends with a commit that only touches the files that task created/modified.

---

### Task 1: Build the raw → representation coverage map (the audit baseline)

**Files:**
- Create: `framework/00-coverage-map.md`
- Read-only (reference): `raw/VERBATIM-RAW.md`, all `framework/0X-*.md`, `MANIFESTO.md`, `IDEA.md`

**Interfaces:**
- Consumes: the 24 headed sections of `raw/VERBATIM-RAW.md` (listed verbatim below).
- Produces: `framework/00-coverage-map.md` — a table mapping each raw section to its representation home(s) and a status (full / partial / missing). Later tasks (2–5) update rows in this table as they fill gaps; Task 6 re-runs it as the consistency gate.

- [ ] **Step 1: Enumerate the raw sections**

Write `framework/00-coverage-map.md` beginning with this exact header, listing all 24 sections from `raw/VERBATIM-RAW.md` (`## ` headings, in raw order):

1. Core Thesis
2. The Open Source License Advantage
3. Why Open Source Projects Die
4. The Monopoly Solution
5. Beating Closed Source
6. The Idea (Not the Tools)
7. No Copyright or Patent
8. The Layer Separation Problem
9. The Layer Model
10. Mixed Concerns
11. The Formula
12. The Cross-Discipline Advantage
13. My Vision and Role
14. Division of Labor
15. The Poverty Trap
16. Tool Neutrality
17. The GNU/Linux Lesson
18. What We Have More Than Open Source Ideology
19. The Absolute Definition of a Tool
20. The Friction Cycle
21. Frictions Are Results of Higher Usage
22. How This Evolves the Poverty Line
23. The Missing Key — The Path, Not Just the Tool
24. On The On-Ramp (Not the Jungle Case)

- [ ] **Step 2: Verify the map captures the current thin coverage**

For each raw section, run a keyword probe across the derived docs (e.g. `grep -ri "license" MANIFESTO.md IDEA.md framework/` for section 2). Record in the map's table: home doc(s) `+` link, and a status of `full`, `partial`, or `missing`.

Expected (verified against the repo on 2026-09-02):
- Section 3,4,5,6,7,8,9,10,11,15,16,17,18,19,20,21,22,23,24 → `full` (well represented).
- Section 2 (Open Source License Advantage) → `partial` (only MANIFESTO.md:104 mentions "license"; the mechanism is otherwise absent).
- Section 12,13,14 (Cross-Discipline Advantage, Vision/Role, Division of Labor) → `partial` (present but thin; Cross-Discipline is in MANIFESTO only).
- Section 1 (Core Thesis) → `full` (it is IDEA/MANIFESTO's spine).

- [ ] **Step 3: State the three engine gaps the map exposes**

In `framework/00-coverage-map.md`, add a short "Gaps found" block listing exactly three, which the following tasks own:
- Gap A (Task 2): License-as-enforcement mechanism (section 2) is under-represented.
- Gap B (Task 3): Fused-concern problem (sections 8,10,11) is only a seed, not a full treatment.
- Gap C (Tasks 5,6): No verification layer or shared glossary exists to stop drift across the ~120 uses of "performance".

- [ ] **Step 4: Verify by re-reading**

Read `framework/00-coverage-map.md` top to bottom and confirm: every one of the 24 raw section titles appears in the table; every row has a status; the three gaps are stated.

Expected: all 24 rows present; no row left without a home doc; three gaps named.

- [ ] **Step 5: Commit**

```bash
git add framework/00-coverage-map.md
git commit -m "docs: add raw->representation coverage map and expose the three hardening gaps"
```

---

### Task 2: Represent the license-as-enforcement mechanism (Gap A)

**Files:**
- Create: `framework/08-license-enforcement.md`
- Modify: `framework/00-coverage-map.md` (flip section-2 row to `full`, link the new doc)
- Modify: `MANIFESTO.md` (add one crisp line under Law 2/3 region pointing at the mechanism)
- Read-only (reference): `raw/VERBATIM-RAW.md` section 2 "The Open Source License Advantage"

**Interfaces:**
- Consumes: raw section 2 text, and the requirement from Task 1 that this gap be closed.
- Produces: `framework/08-license-enforcement.md` (the durability mechanism for openness). Task 6's glossary links terms from it.

- [ ] **Step 1: Write the license-enforcement doc**

Create `framework/08-license-enforcement.md`. Content must be built only from the raw claim and its logical support — quote the raw exactly, then explain the mechanism. Minimum required blocks:

```
# The License — How Openness Is Made Durable

## The raw claim
> If the tool has an open source license, this prevents monopoly and keeps
> economy gain benefit at performing instead of making special close tools that
> take others from getting the externality of advanced tools.

## Why a license, not just a wish
A "we'll keep it open" promise can be silently re-closed. A license is the
mechanism that turns openness into a durable, enforceable fact: it binds
everyone, now and in the future, so openness cannot be quietly revoked. This is
what stops a tool that was opened from becoming a monopoly again.

## What the license protects
- It prevents monopoly — anyone can build on the tool and compete on performance.
- It keeps the economy earning at *performing*, not at owning.
- It lets others get the externality of advanced tools.

## How this closes the loop
Opening a tool only counts if it *stays* open. The license is the commitment
device that makes step 3 ("OPEN") of framework/07-the-full-cycle.md real and
permanent. Without it, openness is just a mood.
```

- [ ] **Step 2: Verify the mechanism reads back to the raw**

Run: `grep -n "open source license" framework/08-license-enforcement.md`
Expected: the raw's own line appears verbatim (quoted), proving the doc traces to source of truth.

- [ ] **Step 3: Wire it into the coverage map**

In `framework/00-coverage-map.md`, change section 2's status from `partial` to `full` and add the link `framework/08-license-enforcement.md`.

- [ ] **Step 4: Add one pointer line to the Manifesto**

In `MANIFESTO.md`, inside Law 2 ("why nothing can be monopolized"), append one sentence:

> The openness is made durable by the license — a binding, permanent mechanism, not a promise. See `framework/08-license-enforcement.md`.

- [ ] **Step 5: Verify and commit**

Re-read `framework/08-license-enforcement.md`; confirm it contains no claim not traceable to the raw. Then:

```bash
git add framework/08-license-enforcement.md framework/00-coverage-map.md MANIFESTO.md
git commit -m "docs: represent the license as the durability mechanism for openness (gap A)"
```

---

### Task 3: Give the fused-concern problem a full treatment (Gap B)

**Files:**
- Create: `framework/09-fused-concerns.md`
- Modify: `framework/00-coverage-map.md` (sections 8,10,11 → link this doc)
- Modify: `framework/03-separation-methodology.md` (replace the "open question" tail with a pointer to the new full doc)
- Read-only (reference): `raw/VERBATIM-RAW.md` sections 8, 10, 11

**Interfaces:**
- Consumes: raw sections 8 ("The Layer Separation Problem"), 10 ("Mixed Concerns"), 11 ("The Formula"); the current seed in `framework/03-separation-methodology.md`.
- Produces: `framework/09-fused-concerns.md`, a complete method for separating a tool that is fused into its performance. This is the doctrine's hardest sub-problem; the doc must be self-contained.

> **Domain rule:** the *correctness* of the fused-concern answer is a user-domain question. This task writes down the method that already exists (the seed in `framework/03`) into a full, coherent doc — it does **not** invent new doctrine. If, while writing, you find the method is incomplete and a genuinely new answer is needed, stop and flag it for the user; do not invent the answer yourself.

- [ ] **Step 1: Promote the seed into a full method doc**

Create `framework/09-fused-concerns.md`. It must contain, in order, and only drawing on the existing seed + raw sections 8, 10, 11:

```
# The Fused-Concern Problem — Separating a Tool Stuck Inside Its Performance

## The problem, from the raw
> There are a lot of performance that are dependent on tools that are integrated
> into performance. The question is: how to separate those?

(Quote raw section 8's probe law: "If we decrease the tool from performance, the
performance also degrades. But if we add tool, the performance evolves.")

## Why the probe seems to fail here
Removing the fused tool degrades the performance — so it looks like the thing is
not a separate tool. That is expected, not evidence of failure.

## The method
1. Ask: does the *same* integration repeat across many performances?
2. If yes, the repeated pattern is NOT the performance — it is a hidden tool.
3. The thing to extract is the **integration pattern itself**: a layer that does
   the integrating, which performances attach/detach on demand.
4. Extract it, open it (framework/08 makes it durable), keep the remaining
   performance as the money gate.

Quote raw section 11: "how to make a new tool by separating performance from the
pattern that the performance follows repeatedly."

## Worked example (auth integration)
State: every app fuses an auth sub-system into itself. Removing it degrades the
app (probe: yes). But the same auth integration repeats across every app. So the
integration pattern is the hidden tool. Extract it as an open auth layer; apps
detach their embedded auth and attach the open layer. The app (performance)
stays sellable; the auth integration (tool) becomes open.

## Where this lands in the loop
It is step 2 (SEPARATE) of framework/07 applied to the hardest case: when you
cannot pull the tool out, pull the pattern of integrating it out instead.
```

- [ ] **Step 2: Verify no new doctrine was invented**

Run: `grep -n "integration" framework/09-fused-concerns.md`
Expected: the "integration pattern" framing appears, and it is traceable to the existing seed in `framework/03-separation-methodology.md` (which already says "pull the *integration pattern* out and make *that* the open layer"). If the doc asserts anything not in the seed or raw, rewrite it until it does.

- [ ] **Step 3: Point the coverage map and the old seed at the new doc**

In `framework/00-coverage-map.md`: sections 8, 10, 11 → add link `framework/09-fused-concerns.md`.
In `framework/03-separation-methodology.md`: replace the final "open question" section body with a 2-line pointer:

> The full treatment of this hardest case now lives in `framework/09-fused-concerns.md`.

- [ ] **Step 4: Verify and commit**

Re-read the doc; confirm it is self-contained and needs no other file to be understood. Then:

```bash
git add framework/09-fused-concerns.md framework/00-coverage-map.md framework/03-separation-methodology.md
git commit -m "docs: full treatment of the fused-concern problem (gap B)"
```

---

### Task 4: Add a plain-language front door so a non-expert is not misled

**Files:**
- Create: `docs/plain-language.md` (a one-page plain explanation)
- Modify: `index.md` (lead with the human consequence, link the plain page)
- Modify: `README.md` (lead "read first" with the plain page)
- Read-only (reference): `MANIFESTO.md`, `IDEA.md` (for grounding; do not copy wholesale)

**Interfaces:**
- Consumes: the doctrine already represented in MANIFESTO/IDEA/framework.
- Produces: `docs/plain-language.md` — a no-jargon entry usable by someone who has never heard the idea. Tasks 5 and 6 link to / refer to it.

- [ ] **Step 1: Write the plain-language page**

Create `docs/plain-language.md`. Rules: no word "monopolize" as a first move; no MySQL in the opening; lead with a relatable consequence. Minimum structure:

```
# The Idea, In Plain Words

## The short version
There is a difference between the thing you make things WITH, and the thing you
actually DO. A stove is a tool; cooking dinner is the performance. Right now the
world treats the stove as the thing you pay for and lock up. This idea says:
make the stove free for everyone, and charge only for the cooking.

## Why it matters to you
- Tools get cheaper and better.
- The person who makes the finished thing — not the person who owns the machine —
  keeps the value.
- No single company can hold a lock on everyone who needs the tool.

## The one rule
Make the tool open. Sell the doing.

## What this does not mean
- It is not about software only. It is about any tool (a tool = input goes in,
  output comes out, you do not need to know what happens inside).
- "Free tools" does not mean "free work." Someone still has to do the doing, and
  that is what they are paid for.
```

- [ ] **Step 2: Verify the plain page has no first-page jargon**

Read the page's first 5 lines.
Expected: no "monopol", no "diminishing", no "externality", no "separation law" before "The one rule". If any of these appear in the first 5 lines, move them below "What this does not mean".

- [ ] **Step 3: Point the front door at it**

In `index.md`, after the existing "The answer in one sentence", add a first-priority read link:

> Don't want the theory first? Read the [plain-language version](docs/plain-language.md).

In `README.md`, add it as item 0 of the "Read first" list:
> 0. **`docs/plain-language.md`** — the idea in plain words (start here if you're new).

- [ ] **Step 4: Verify and commit**

Confirm both links resolve to `docs/plain-language.md`. Then:

```bash
git add docs/plain-language.md index.md README.md
git commit -m "docs: add a plain-language front door for new readers"
```

---

### Task 5: Add a shared glossary to stop term drift (part of Gap C)

**Files:**
- Create: `framework/10-glossary.md`
- Modify: `framework/00-coverage-map.md` (note the glossary as the drift guard)
- Read-only (reference): `raw/VERBATIM-RAW.md` — the definitions must come from raw, verbatim where possible.

**Interfaces:**
- Consumes: the raw's own definitions.
- Produces: `framework/10-glossary.md` with a canonical definition per core term. Task 6's consistency check uses these definitions as the oracle.

- [ ] **Step 1: Define the core terms from raw, verbatim**

Create `framework/10-glossary.md`. Every term's definition must be quoted from or directly traceable to a raw section. Minimum entries:

```
# Glossary — Canonical Terms

## Tool
From "The Absolute Definition of a Tool":
> Input (material) → Tool → Output (result), with the user free not to know what
> happens inside.
A tool is the reusable enabler that takes input and gives output.

## Performance
The act of creating value with tools — the doing. From "Core Thesis": performance
is what is paid for ("keeping performance as the money gate").

## Separation
From "The Layer Separation Problem": the act of removing a tool from a performance.
Probe: remove it → performance degrades; add it → performance evolves.

## Layer
From "The Layer Model": a tool that is itself built of tools and is itself a tool
to the layer above. Every layer can be opened.

## Externality
From "How This Evolves the Poverty Line": a benefit that a better tool gives to
the whole chain above it, without touching them.

## Diminishing returns as signal
From "The Friction Cycle": a compass pointing at the next friction, not a wall.

## Correct value
From "The Missing Key": people only value a tool after building it themselves;
use has levels you cannot skip.
```

- [ ] **Step 2: Verify each term traces to raw**

Run: `grep -n "from \"" framework/10-glossary.md`
Expected: at least 7 "from "<raw-section>"" markers, one per term.

- [ ] **Step 3: Note the glossary in the coverage map**

In `framework/00-coverage-map.md`, add under the Gap-C line: "Drift guard: see `framework/10-glossary.md` for canonical definitions."

- [ ] **Step 4: Verify and commit**

Re-read; confirm no term is defined by a synonym instead of the raw meaning. Then:

```bash
git add framework/10-glossary.md framework/00-coverage-map.md
git commit -m "docs: add canonical glossary, the drift guard for core terms (gap C)"
```

---

### Task 6: Run the full consistency + coverage gate (final verification)

**Files:**
- Modify: `framework/00-coverage-map.md` (final statuses + an audit log line)
- Modify: `PLAN.md` (reflect the hardened state; move open user questions into the plan)
- Read-only (reference): every `framework/0X-*.md`, `MANIFESTO.md`, `IDEA.md`, `docs/plain-language.md`, `raw/VERBATIM-RAW.md`

**Interfaces:**
- Consumes: all artifacts from Tasks 1–5.
- Produces: a completed, verified representation + an updated `PLAN.md` that records the audit result and the still-open user-domain decisions. Nothing later depends on this task except reviewers trusting the representation.

- [ ] **Step 1: Run the definition-consistency check**

For each term in `framework/10-glossary.md`, `grep -rn "<term>" framework/ MANIFESTO.md IDEA.md docs/ plain.md 2>/dev/null` and spot-check that no doc contradicts the glossary definition (e.g., no doc says "performance means the tool").

Expected: zero contradictions; where a doc's usage is loose, that is acceptable as long as it does not *deny* the glossary definition. Record any contradiction found as a fix before proceeding.

- [ ] **Step 2: Run the coverage-completeness check**

Re-read `framework/00-coverage-map.md`: every one of the 24 raw sections must now have status `full` (or be explicitly listed as a user-domain item in the gaps block).

Expected: sections 2, 8, 10, 11, 12 now `full` (Tasks 2, 3). Sections 13, 14 (Vision/Role, Division of Labor) may remain `partial` — flag them in the map as "user-domain framing, not a gap."

- [ ] **Step 3: Run the front-door consistency check**

Read `docs/plain-language.md` then `MANIFESTO.md`.
Expected: the plain page and the manifesto tell the same story (same core claim, same money-gate idea); no contradiction between them.

- [ ] **Step 4: Update PLAN.md to the verified state**

Rewrite `PLAN.md` so that:
- The status section lists the full doc set including `00`, `08`, `09`, `10`, and `docs/plain-language.md`.
- A short "Audit (2026-09-02)" block states: all 24 raw sections covered; definition-consistency passed; front-door consistency passed.
- The "Open questions to put to your brain" section now explicitly lists the *still-open user-domain* decisions: (1) naming, (2) scope (theory/strategy/movement), (3) correctness of the fused-concern answer, (4) whether to launch the pledge. These are deliberately NOT decided by this plan.

- [ ] **Step 5: Verify and commit**

Run `git status --short`; confirm only Task-6 files modified. Re-read PLAN.md top to bottom. Then:

```bash
git add framework/00-coverage-map.md PLAN.md
git commit -m "docs: run the final consistency+coverage gate; record audit in PLAN"
```

---

## Execution Handoff

After the plan is saved, offer execution choice:

**"Plan complete and saved to `docs/superpowers/plans/2026-09-02-harden-doctrine-representation.md`. Two execution options:**

**1. Subagent-Driven (recommended)** — I dispatch a fresh subagent per task, review between tasks, fast iteration.

**2. Inline Execution** — I execute tasks in this session using executing-plans, batch execution with checkpoints.

**Which approach?"**
