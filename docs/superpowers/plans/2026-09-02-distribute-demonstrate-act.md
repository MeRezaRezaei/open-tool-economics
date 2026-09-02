# Distribute, Demonstrate, and Act — Continuation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.
>
> **Repo reality check:** this is a NON-CODE project. The deliverable is a *representation of an idea*, not software. "Test" therefore means a **verifiable read-back** (does a doc faithfully render a raw claim? does every link resolve? do terms stay consistent?), not a unit test. There is **no `composer test` / `pytest` gate**. Each task ends with an independently checkable deliverable described in its Step-2 "Expected" lines.

**Goal:** Take the now-hardened Open Tools Doctrine representation and put it to work in the world — publish it, demonstrate it with concrete worked examples, and give others a first-class surface to act on it — entirely without consuming the founder's time.

**Architecture:** Three dependent phases in one plan. (A) Publish: merge the `harden-doctrine-representation` branch (6 commits) onto `master` so the hardened docs go live on GitHub Pages, and commit the previously-untracked plan doc. (B) Demonstrate: add a **Separations Ledger** — an index of real tools found by applying the Separation Law to concrete cases — proving the method with worked examples rather than argument alone. (C) Act: add a `CONTRIBUTING.md` and wire the pledge + separation-proposal surfaces so people can participate. Finally re-run the consistency + coverage gate so the hardening already done does not drift.

**Tech Stack:** Markdown docs, GitHub Pages (live site at `https://merezarezaei.github.io/open-tool-economics/`). `raw/VERBATIM-RAW.md` remains the read-only source of truth. No code anywhere.

**Spec:** The authoritative source is `raw/VERBATIM-RAW.md`. The doctrine's own representation rules (from that spec's "A Note on Decisions"): the assistant executes everything beyond doubt; the founder decides only hard economic/philosophical questions. The raw also assigns the *distribution* function to the assistant explicitly: "From that point, your work begins: the part that starts the chain reaction in the world, that brings the answer to people's heads so they can act on it and solve problems using the answer. In precise terms: you do whatever is needed, instead of me, so others know the answer." This plan is that function. The founder has directed that all directions be pursued, that order/timing are my call, and that it must consume none of the founder's time.

## Global Constraints

- **Raw is immutable.** `raw/VERBATIM-RAW.md` is the only source of truth. No task may edit it. Derived docs are corrected presentations; every claim must trace to a raw section.
- **Zero code.** This is a no-code repo. No scripts, no tests-framework, no build tooling. "Verification" is doc-based (checklists, coverage tables, link-resolution checks, read-backs), not executable.
- **No new doctrine.** The correctness of the doctrine's hard intellectual claims is the founder's call, not this plan's. Worked examples and all written content must APPLY the existing method and definitions; nothing here invents or changes the doctrine.
- **Term discipline.** "Tool" and "performance" must be used with exactly the definitions from `framework/10-glossary.md` (which traces to raw): Tool = "Input (material) → Tool → Output (result), with the user free not to know what happens inside"; Performance = "the act of creating value with tools — the doing." No doc may redefine them.
- **No placeholders.** Every task below carries the actual content to write — no "TBD", no "add detail later".
- **Commit discipline.** Each task ends with a commit that only touches the files that task created/modified.
- **Does not require the founder.** This plan executes end-to-end with zero founder input. Where a decision is mine to make (the raw delegates naming/structure/channels/representation to the assistant), the plan makes it.

---

### Task 1: Publish the hardened representation onto `master`

**Files:**
- Modify: (via git merge) merge branch `harden-doctrine-representation` into `master`
- Modify: `docs/superpowers/plans/2026-09-02-harden-doctrine-representation.md` (add to git — currently untracked)
- Read-only (reference): `git status`, `git log`, `raw/VERBATIM-RAW.md`

**Interfaces:**
- Consumes: the 6 already-committed hardening commits on branch `harden-doctrine-representation` (`c5a705b`…`1fcc92d`): coverage map, license doc, fused-concerns doc, plain-language page, glossary, consistency gate.
- Produces: `master` containing the full hardened representation, pushed to `origin`. Everything in later tasks builds on this merged foundation.

- [ ] **Step 1: Confirm branch holds the intended work and is clean**

Run: `git branch --show-current` and `git log --oneline master..harden-doctrine-representation`
Expected: current branch is `harden-doctrine-representation`; the log shows exactly 6 commits (coverage map, license, fused-concerns, plain-language, glossary, final gate). No unrelated commits.

- [ ] **Step 2: Commit the plan doc that was left untracked**

```bash
git add docs/superpowers/plans/2026-09-02-harden-doctrine-representation.md
git commit -m "docs: archive the hardening plan in superpowers plans"
```

- [ ] **Step 3: Merge the branch into master**

```bash
git checkout master
git merge --no-ff harden-doctrine-representation -m "Merge harden-doctrine-representation: reveal gaps, license durability, fused-concern treatment, plain-language front door, glossary, consistency gate"
```

- [ ] **Step 4: Verify the merge is complete and raw is untouched**

Run: `git log --oneline -3` and `git diff master~1 master -- raw/VERBATIM-RAW.md`
Expected: HEAD on `master` has the merge commit; `raw/VERBATIM-RAW.md` diff is **empty** (raw immutable, confirmed).

- [ ] **Step 5: Push to origin**

```bash
git push origin master
```

- [ ] **Step 6: Commit (no-op unless merge produced pending state)**

If `git status` is clean, this task needs no further commit — Steps 2 and 3 already committed. Record the publish in PLAN.md is deferred to Task 5's gate.

---

### Task 2: Verify the live front door end-to-end

**Files:**
- Modify: `index.md` (only if a link or wording needs correction — do not change structure)
- Read-only (reference): `docs/plain-language.md`, `MANIFESTO.md`, `README.md`, `index.md`, `.github/ISSUE_TEMPLATE/`

**Interfaces:**
- Consumes: Task 1's merged, pushed `master`.
- Produces: confidence that a new reader hitting the live site lands in `docs/plain-language.md` (the no-jargon door), then flows to the manifesto, and can see the pledge and separation-proposal actions. Task 3's ledger is linked from here.

- [ ] **Step 1: Confirm every "Read" link in `index.md` resolves**

For each link target in `index.md` (MANIFESTO.md, framework/07-the-full-cycle.md, PLEDGE.md, raw/VERBATIM-RAW.md, IDEA.md, docs/plain-language.md) run: `test -f <path>` 
Expected: every target file exists on disk. Record the result.

- [ ] **Step 2: Confirm the plain-language door is reachable from the top**

Re-read `index.md` lines 1–12.
Expected: the `> Don't want the theory first? Read the [plain-language version](docs/plain-language.md).` line sits directly under "The answer in one sentence", before "The three laws". A new reader can enter via plain words.

- [ ] **Step 3: Confirm `docs/plain-language.md` opens jargon-free**

Read the first 5 lines of `docs/plain-language.md`.
Expected: no "monopol", "diminishing", "externality", "separation law" appears before "## The one rule". No fix needed unless Step 1 or 2 revealed a problem — if it did, make the minimal edit and note it.

- [ ] **Step 4: Verify the action surface exists**

Run: `test -f .github/ISSUE_TEMPLATE/pledge.yml` and `test -f .github/ISSUE_TEMPLATE/separation.yml`
Expected: both templates exist (pledge + separation proposal). These are the channels by which readers act on the doctrine.

- [ ] **Step 5: Commit any fix made**

If Steps 1–4 found and fixed a broken link or wording:

```bash
git add index.md
git commit -m "docs: fix front-door link/wording found in live verification"
```

If nothing changed, make no commit (this task is verification-only and should produce a clean diff).

---

### Task 3: Build the Separations Ledger — demonstrate the method with real examples (Gap A for action)

**Files:**
- Create: `separations/00-index.md` (the ledger landing page)
- Create: `separations/01-auth.md`, `separations/02-user-schema.md`, `separations/03-logging.md`, `separations/04-payments.md`, `separations/05-notifications.md`
- Modify: `framework/00-coverage-map.md` (add a section at the end noting the ledger as the demonstration layer)
- Modify: `index.md` (link the ledger under "Read")
- Read-only (reference): `framework/01-core-framework.md` (Separation Law), `framework/09-fused-concerns.md` (the hardest-case method), `framework/10-glossary.md` (term definitions), `raw/VERBATIM-RAW.md` sections 8, 11

**Interfaces:**
- Consumes: the Separation Law (raw section 8, framed in `01-core-framework.md`: "remove it → degrades; add it → evolves"), the fused-concern method (`09-fused-concerns.md`: extract the repeated integration pattern), and glossary definitions (`10-glossary.md`).
- Produces: `separations/00-index.md` is the canonical, linkable catalog that proves the doctrine: it lists real tools found by applying the method, each with the standard sections. Tasks 4 and 5 link to and re-verify this catalog.

> **Domain rule:** each separation is an *application* of the existing method to a well-known recurring case. The plan does not invent mechanism — it identifies a repeated pattern (auth, user schema, logging, payments, notifications), applies the probe, names the hidden tool, and names the open layer + money gate. If applying the method to a case genuinely requires new doctrine, that case is left as a stub row in `00-index.md` flagged "needs founder" — do NOT invent.

- [ ] **Step 1: Write the ledger index**

Create `separations/00-index.md` with this exact structure:

```
# The Separations Ledger

Proof by example. Each entry below is a real tool found by applying the Separation
Law to a case we keep repeating. Reading these shows the method working — it is
not the theory, it is the theory applied.

## How to read an entry

Every separation answers the same four questions:

1. **The repeated pattern** — what performance keeps recurring, across actors.
2. **The hidden tool** — the reusable thing fused inside that performance
   (probe: remove it → degrades; add it → evolves).
3. **The open layer** — the separated tool as its own open, shared layer.
4. **The money gate** — what remains as the paid performance, the doing.

Apply this to your own work. When you find a tool, propose it via the
[separation template](../.github/ISSUE_TEMPLATE/separation.yml) and we add it here.

## The entries

| # | Hidden tool | Open layer | Money gate (performance) | Entry |
|---|-------------|------------|--------------------------|-------|
| 1 | Auth sub-system embedded in every app | Open auth layer (attach/detach) | The app's own job done for the user | [01-auth.md](01-auth.md) |
| 2 | User-management schema baked into each app's DB | Open ready user-schema layer | The business built on the data | [02-user-schema.md](02-user-schema.md) |
| 3 | Logging/observability code wired into every service | Open logging layer | The service's own output | [03-logging.md](03-logging.md) |
| 4 | Payment handling fused into each product | Open payment/checkout layer | The product or service sold | [04-payments.md](04-payments.md) |
| 5 | Notification/email plumbing repeated in every app | Open notification layer | The product your users actually use | [05-notifications.md](05-notifications.md) |

## What to do with a tool you find

Separate it. Open it (a license makes it durable — see `../framework/08-license-enforcement.md`).
Keep the remaining performance as the money gate. Then propose it here.
```

- [ ] **Step 2: Verify the index table and links are coherent**

Run: `rg -n '^\| [0-9] \|' separations/00-index.md` and `test -f separations/01-auth.md` (the entry files are created in Steps 3–7; confirm the index numbers and filenames match the table exactly).
Expected: rows 1–5 with the exact filenames listed; no orphan link.

- [ ] **Step 3: Write entry 1 — Auth**

Create `separations/01-auth.md`:

```
# Separation 1 — Auth as an open layer

## The repeated pattern

Every application fuses an auth sub-system into itself — sign-up, login, sessions,
password reset, roles, permissions. The same integration keeps recurring across
every product and every team.

## The hidden tool

Apply the probe: remove auth from an app → the app degrades (no one can get in).
Add auth → the app evolves (users can be onboarded). Auth is therefore a *tool*
fused into the performance — see the fused-concern method
(`../framework/09-fused-concerns.md`).

Because the *same* auth integration repeats across every app, the integration
pattern is the hidden tool, not the app itself.

## The open layer

Extract auth as an open layer that applications attach and detach on demand: a
shared auth service with the user free not to know what happens inside
(`../framework/10-glossary.md` — Tool). Open it with a permissive license so no
one can re-close it (`../framework/08-license-enforcement.md`).

## The money gate

The app stays sellable. Users pay for what the app *does* for them — the product,
the service, the specific job the performance does — not for the shared auth
plumbing. Auth (tool) is free; the app (performance) is the money gate.
```

- [ ] **Step 4: Write entry 2 — User schema**

Create `separations/02-user-schema.md` (use the MySQL/schema claim as the anchor — raw "The Layer Model": "the schema of the database" is the next tool):

```
# Separation 2 — The ready user-management schema

## The repeated pattern

Every app that holds users needs the same schema — users, roles, sessions,
password resets. The schema pattern repeats across every database and every
product (raw "The Layer Model": the next tool in the database problem is the
schema).

## The hidden tool

Probe: remove the user schema → the app degrades (it cannot hold its users).
Add a good user schema → the app evolves. The schema is a tool, currently baked
inside each app instead of standing alone.

## The open layer

Release the user-management schema pattern as an open, reusable schema layer that
attaches to any database on demand. "Making schemas open source makes the tools
another layer to become open source" (raw "The Layer Model").

## The money gate

The business built on the data — what the app does with its users — is the paid
performance. The schema (tool) is free for everyone.
```

- [ ] **Step 5: Write entry 3 — Logging**

Create `separations/03-logging.md`:

```
# Separation 3 — Logging as an open layer

## The repeated pattern

Every service wires in logging/observability — capture events, errors, metrics.
The same plumbing repeats across every application.

## The hidden tool

Probe: remove logging → the service degrades (you cannot see what it does).
Add logging → the service evolves (it becomes operable). Logging is a tool fused
into the performance.

## The open layer

Extract logging as an open layer applications attach on demand — a shared
logging/observability tool, open so anyone can build on it.

## The money gate

The service's own output — the product, the data processed, the job done for the
user — is what is sold. Logging (tool) stays open and free.
```

- [ ] **Step 6: Write entry 4 — Payments**

Create `separations/04-payments.md`:

```
# Separation 4 — Payment handling as an open layer

## The repeated pattern

Every product that sells must handle payment — checkout, cards, receipts,
invoicing. The integration repeats across every seller.

## The hidden tool

Probe: remove payment handling → the product degrades (it cannot transact). Add
it → the product evolves (it can earn). Payment is a tool fused into the
performance.

## The open layer

Extract payment/checkout as an open layer products attach on demand, open so any
seller can build on it and compete on the performance.

## The money gate

The product or service sold — the thing the customer actually buys and uses — is
the performance. Payment plumbing (tool) is free.
```

- [ ] **Step 7: Write entry 5 — Notifications**

Create `separations/05-notifications.md`:

```
# Separation 5 — Notification delivery as an open layer

## The repeated pattern

Every application needs to notify its users — email, push, in-app. The delivery
plumbing repeats across every product.

## The hidden tool

Probe: remove notification delivery → the app degrades (users are not informed).
Add it → the app evolves (it can engage users). Notification delivery is a tool
fused into the performance.

## The open layer

Extract notification delivery as an open layer applications attach on demand,
open so anyone can build on it.

## The money gate

The product your users actually use — what the app does for them — is the paid
performance. Notification plumbing (tool) is free.
```

- [ ] **Step 8: Run the method fidelity check**

Run: `rg -n "probe|remove|degrades|evolves|open layer|money gate" separations/*.md`
Expected: every entry contains the probe language ("remove … degrades; add … evolves"), an "open layer", and a "money gate". This proves each entry applies the *existing* Separation Law and fused-concern method — not new doctrine.

- [ ] **Step 9: Wire the ledger into the coverage map and index**

In `framework/00-coverage-map.md`, append after the audit log block:

```
## Demonstration layer (2026-09-02)

The `separations/` ledger applies the Separation Law (sections 8, 11) and the
fused-concern method (section 8) to real recurring cases — proof the method works,
not new doctrine. See `separations/00-index.md`.
```

In `index.md`, add to the "Read" list (after the plain-language link area):

```
- [The Separations Ledger](separations/00-index.md) — real tools found by applying the Separation Law, proof the method works.
```

- [ ] **Step 10: Re-verify and commit**

Re-run Task 3 Step 8's grep and confirm every ledger link in `index.md` resolves (`test -f separations/00-index.md`). Then:

```bash
git add separations/ framework/00-coverage-map.md index.md
git commit -m "docs: add the separations ledger, concrete proof of the method in action"
```

---

### Task 4: Give people a first-class surface to act (CONTRIBUTING + action wiring)

**Files:**
- Create: `CONTRIBUTING.md`
- Modify: `README.md` (add a "Contribute / Act" section pointing at the pledge, the separation template, and the ledger)
- Read-only (reference): `PLEDGE.md`, `.github/ISSUE_TEMPLATE/pledge.yml`, `.github/ISSUE_TEMPLATE/separation.yml`, `separations/00-index.md`, `docs/plain-language.md`

**Interfaces:**
- Consumes: Task 3's ledger (`separations/00-index.md`), the existing pledge template, the existing separation template.
- Produces: `CONTRIBUTING.md` — the concrete path a reader takes to act on the doctrine (take the pledge, propose a separation). Task 5 re-verifies these surfaces resolve.

- [ ] **Step 1: Write `CONTRIBUTING.md`**

Create `CONTRIBUTING.md`:

```
# Contributing — how to act on the doctrine

This is a doctrine, not a codebase. The best contribution is to *apply* it: find a
tool, open it, and keep the performance as the money gate. Three ways to act:

## 1. Take the Pledge

Open an issue using the [pledge template](.github/ISSUE_TEMPLATE/pledge.yml):

> **"The tools I make stay open. I charge only for performance."**

The pledge is public and dated on purpose — it lets others build on your tools
without fear they will be closed. See [PLEDGE.md](PLEDGE.md).

## 2. Propose a separation

Found a tool hidden inside a performance? Open an issue using the
[separation template](.github/ISSUE_TEMPLATE/separation.yml) and we add it to
the [Separations Ledger](separations/00-index.md). Every good separation is
proof the method works.

Each proposal answers:
- The repeated pattern
- The hidden tool (probe: remove it → degrades; add it → evolves)
- The proposed open layer
- The money gate (the paid performance)

## 3. Improve the representation

Found something in the doctrine that reads as unclear or misleading?
Open a PR against the docs. The raw source of truth
([raw/VERBATIM-RAW.md](raw/VERBATIM-RAW.md)) is immutable — edit the *derived
presentations* (MANIFESTO, IDEA, framework/), never the raw.

## Ground rules

- Terms follow the [glossary](framework/10-glossary.md): "tool" and "performance"
  keep their exact meanings; no redefinition.
- The founder decides the doctrine's hard intellectual questions; contributors
  shape naming, structure, channels, and representation.
```

- [ ] **Step 2: Verify the contribution paths resolve**

Run: `test -f .github/ISSUE_TEMPLATE/pledge.yml`, `test -f .github/ISSUE_TEMPLATE/separation.yml`, `test -f separations/00-index.md`, `test -f docs/plain-language.md`
Expected: all resolve. The reader's three action paths in `CONTRIBUTING.md` match real files.

- [ ] **Step 3: Add the action section to `README.md`**

Append to `README.md`, directly under the existing "Act" section content or as a new subsection:

```
### Contribute / Act

Three ways to act on the doctrine — take the pledge, propose a separation, or
improve the representation. See [`CONTRIBUTING.md`](CONTRIBUTING.md).
```

- [ ] **Step 4: Re-read and commit**

Re-read `CONTRIBUTING.md` top to bottom. Confirm it contains no command or path that does not exist in the repo. Then:

```bash
git add CONTRIBUTING.md README.md
git commit -m "docs: add contributing surface so readers can act on the doctrine"
```

---

### Task 5: Final consistency + coverage + live gate (verification)

**Files:**
- Modify: `framework/00-coverage-map.md` (audit log line)
- Modify: `PLAN.md` (reflect the new distribution/demonstration/action layer)
- Read-only (reference): every `framework/0X-*.md`, `separations/*.md`, `MANIFESTO.md`, `IDEA.md`, `docs/plain-language.md`, `README.md`, `index.md`, `.github/ISSUE_TEMPLATE/`, `raw/VERBATIM-RAW.md`

**Interfaces:**
- Consumes: all artifacts from Tasks 1–4 plus the pre-existing hardened representation.
- Produces: a completed, verified state and an updated `PLAN.md` recording it. Nothing later depends on this except reviewers trusting the representation.

- [ ] **Step 1: Re-run the definition-consistency check**

For each term in `framework/10-glossary.md`, `grep -rn "<term>" framework/ MANIFESTO.md IDEA.md docs/ separations/ 2>/dev/null` and spot-check that no doc contradicts the glossary definition. Pay special attention to the new `separations/*.md` — they must use "tool" and "performance" exactly per the glossary.
Expected: zero contradictions. The ledger uses "tool" = reusable enabler, "performance" = the doing. Record any contradiction found and fix it before proceeding.

- [ ] **Step 2: Run the link-resolution check**

For every relative link `](path)` and inline-code path `` `path` `` in `index.md`, `README.md`, `CONTRIBUTING.md`, `MANIFESTO.md`, and `separations/*.md`, confirm the target exists: `test -f <resolved path>`.
Expected: every link resolves. Fix any broken link found.

- [ ] **Step 3: Confirm the front-door story is unbroken**

Read `docs/plain-language.md`, then `MANIFESTO.md`, then `separations/00-index.md`.
Expected: the plain page, the manifesto, and the ledger tell one consistent story — same core claim, same money-gate idea, same term definitions. No contradiction between them.

- [ ] **Step 4: Update `PLAN.md` to the verified state**

Add to `PLAN.md` (in the Status section, after the existing entries):

```
- `separations/00-index.md` — the ledger: real tools found by applying the Separation Law (proof, not theory).
- `CONTRIBUTING.md` — the surface readers use to act (pledge, propose a separation, improve the representation).
```

And append or update an audit block:

```
## Audit (2026-09-02, second pass)

- Published: hardened representation merged to master; live site links resolve.
- Demonstration: Separations Ledger applies the Separation Law to 5 recurring cases
  (auth, user schema, logging, payments, notifications) — no new doctrine.
- Definition consistency: passed — including the new ledger (tool/performance used
  per the glossary).
- Front-door consistency: passed — plain page, manifesto, and ledger agree.
- Founder-time cost: the founder's only inputs remain the four open intellectual
  questions (naming, scope, fused-concern correctness, pledge launch) that the
  doctrine reserves exclusively for them.
```

- [ ] **Step 5: Verify and commit**

Run `git status --short`; confirm only Task-5 files modified. Re-read `PLAN.md` top to bottom. Then:

```bash
git add framework/00-coverage-map.md PLAN.md
git commit -m "docs: run the distribution+demonstration+action gate; record audit in PLAN"
```

---

## Execution Handoff

After the plan is saved, offer execution choice:

**"Plan complete and saved to `docs/superpowers/plans/2026-09-02-distribute-demonstrate-act.md`. Two execution options:**

**1. Subagent-Driven (recommended)** — I dispatch a fresh subagent per task, review between tasks, fast iteration.

**2. Inline Execution** — I execute tasks in this session using executing-plans, batch execution with checkpoints.

**Which approach?"**
