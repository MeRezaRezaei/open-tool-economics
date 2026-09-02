# Literature Foundation — where the doctrine stands on the scholarship

This document backs key claims of the doctrine with peer-reviewed and authoritative literature. It does **not** add new doctrine — it maps claims that already exist in `raw/VERBATIM-RAW.md` and the derived docs to the academic work that supports, refines, or contests them. Its purpose is to make the doctrine *standable*: a reader who doubts a claim has somewhere canonical to go, and a defender has a reproducible citation.

Scope note: the doctrine is an economic and philosophical argument, and its strong claims cross several established literatures (open-source incentives and sustainability, growth theory, development economics, public-goods and commons economics, competition theory). Each row below names the doctrine claim, the supporting literature, and the verified identifier (DOI) where one exists. Works without a DOI (reports, books) are marked as such and quoted by publisher/year.

## Claim → literature map

### The open-source license advantage (raw §2; `framework/08-license-enforcement.md`)

The doctrine claims the open license keeps the economic reward at performing, prevents tool monopolies, and is *why* openness wins over closed. The economic case that open source is incentive-compatible and privately beneficial is the core of the influential economics-of-open-source literature:

| Doctrine claim | Supporting literature | Identifier |
|---|---|---|
| Open source is sustained by mixed private/collective incentives, not pure altruism | Lerner, J., & Tirole, J. (2002). *Some Simple Economics of Open Source*. Journal of Industrial Economics, 50(2), 197–234. | `10.1111/1467-6451.00174` |
| Open source fuses private (for-profit) and collective (commons) incentives into a distinct innovation model | von Hippel, E., & von Krogh, G. (2003). *Open Source Software and the "Private-Collective" Innovation Model*. Organization Science, 14(2), 209–223. | `10.1287/orsc.14.2.209.14992` |
| Contributing to open source is individually rational (private benefit), so openness is self-sustaining | Riehle, D. (2007). *The Economic Motivation of Open Source Software: Stakeholder Perspectives*. IEEE Computer, 40(4), 25–32. | `10.1109/mc.2007.147` |
| Open cooperation ("bazaar") at scale outperforms closed, cathedral-style coordination | Raymond, E. S. (1998). *The Cathedral and the Bazaar*. First Monday, 3(3). | `10.5210/fm.v3i2.578` |

### Why open source projects die — and the funding gap (raw §3)

The doctrine's "why projects die" is the taken-for-granted failure the Incentive Model is built to fix. The evidence that open source is systematically underfunded and that individual contributors rarely extract monetary reward is direct:

| Doctrine claim | Supporting literature | Identifier |
|---|---|---|
| Individual open-source contributors are essentially unpaid; donations rarely make anyone rich | Overney, C., et al. (2020). *How to not get rich: An empirical study of donations in open source*. Foundations of Software Engineering (FSE '20), 444–454. | `10.1145/3377811.3380410` |
| The underlying digital infrastructure is maintained by an invisible, under-supported labor force | Eghbal, N. (2016). *Roads and Bridges: The Unseen Labor Behind Our Digital Infrastructure*. Ford Foundation. **Report** (no DOI). | Ford Foundation, 2016 |

### Diminishing returns are a signal, not a wall — growth from solved frictions (raw §20–21; `framework/05-macro-economics.md`)

The doctrine treats endlessly-renewed frictions as a source of further growth rather than a ceiling. This is the contested move of modern growth theory, and it is precisely what the endogenous-growth tradition established against the fixed-capital view:

| Doctrine claim | Supporting literature | Identifier |
|---|---|---|
| Growth can be self-sustaining rather than leveling off, because knowledge is not subject to diminishing returns | Romer, P. M. (1990). *Endogenous Technological Change*. Journal of Political Economy, 98(5), S71–S102. | `10.1086/261725` |
| Solow's cross-check: without ongoing change, an economy converges to a steady state — so *new* problems are what keep growth alive | Solow, R. M. (1956). *A Contribution to the Theory of Economic Growth*. Quarterly Journal of Economics, 70(1), 65–94. | `10.2307/1884513` |
| Growth comes through *creative destruction* — the constant displacement of the old by the new, which is the doctrine's "monopoly collapses when improved" | Aghion, P., & Howitt, P. (1992). *A Model of Growth Through Creative Destruction*. Econometrica, 60(2), 323–351. | `10.2307/2951599` |
| Learning by doing — capability accumulates precisely through use/performance, the micro-foundation of growth and of the "path" the doctrine opens | Arrow, K. J. (1962). *The Economic Implications of Learning by Doing*. Review of Economic Studies, 29(3), 155–173. | `10.2307/2295952` |

### Breaking the poverty trap — the path, not just the tool (raw §15, §22–23; `framework/06-missing-key.md`)

The doctrine's core normative claim is that giving value is about opening the *path to build from a society's own limits*, not transferring finished tools — and that this is what breaks the poverty trap rather than perpetuating it:

| Doctrine claim | Supporting literature | Identifier |
|---|---|---|
| Development outcomes hinge on the *capabilities* people are enabled to build, not on one-time transfers of capital/things | Banerjee, A. V., & Newman, A. F. (1993). *Occupational Choice and the Process of Development*. Journal of Political Economy, 101(2), 274–298. | `10.1086/261876` |
| Poverty traps exist when the means to accumulate are missing — exactly the "missing key / missing path" condition | Azariadis, C., & Stachurski, J. (2005). *Poverty Traps*. In Handbook of Economic Growth, Vol. 1A, ch. 5, 295–384. | `10.1016/s1574-0684(05)01005-1` |
| Aid/transfers alone fail to produce sustained growth unless the receiving environment/institution can *use* them — supports "giving food free fails; open the path" | Burnside, C., & Dollar, D. (2000). *Aid, Policies, and Growth*. American Economic Review, 90(4), 847–868. | `10.1257/aer.90.4.847` |
| Capability is built by doing over time (again): the path is learned, not received | Arrow, K. J. (1962). *The Economic Implications of Learning by Doing*. Review of Economic Studies, 29(3), 155–173. | `10.2307/2295952` (see growth table) |

### The Incentive Model — public goods, free-riding, and the commons (raw §4, §17; `framework/04-game-theory.md`)

The doctrine's "if they don't, someone else will / performers fund the tools" rides on the classic problem that collectively valuable goods are individually under-provided — and Ostrom-type work shows common-pool resources *can* be governed so the commons survives:

| Doctrine claim | Supporting literature | Identifier |
|---|---|---|
| Rival open-access resources are at risk of being depleted/under-maintained — the failure the doctrine is engineered to avoid | Hardin, G. (1968). *The Tragedy of the Commons*. Science, 162(3859), 1243–1248. | `10.1126/science.162.3859.1243` |
| Counter-case: communities can and do sustain shared resources with the right rules — the "self-policing" the doctrine builds on | Ostrom, E. (1990). *Governing the Commons: The Evolution of Institutions for Collective Action*. Cambridge University Press. **Book** (no DOI). | Cambridge University Press, 1990 |
| Motivations for contributing to collective software are heterogeneous and real — effort is not free | Lakhani, K. R., & Wolf, R. G. (2005). *Why Hackers Do What They Do: Understanding Motivation and Effort in Free/Open Source Software Projects*. In Perspectives on Free and Open Source Software, ch. 1. MIT Press. | `10.7551/mitpress/5326.003.0005` |
| Classical statement that large groups under-provide collective goods unless selective incentives exist — the "paying performers" mechanism | Olson, M. (1965). *The Logic of Collective Action*. Harvard University Press. **Book** (no DOI). | Harvard University Press, 1965 |

### Monopoly collapses when it is seen and improved (raw §4–5; `framework/04-game-theory.md`)

The doctrine claims openness makes monopoly fragile: the moment a monopoly is visible, someone else can and will do it. This is the contestable-markets / creative-destruction intuition:

| Doctrine claim | Supporting literature | Identifier |
|---|---|---|
| New value destroys old advantage — monopolists are temporary, not terminal | Aghion, P., & Howitt, P. (1992). *A Model of Growth Through Creative Destruction*. Econometrica, 60(2), 323–351. | `10.2307/2951599` (see growth table) |
| Markets can be contestable: the *threat* of entry disciplines incumbents the way the doctrine claims openness already does | Baumol, W. J., Panzar, J. C., & Willig, R. D. (1982). *Contestable Markets and the Theory of Industry Structure*. Harcourt Brace Jovanovich. **Book** (no DOI). | Harcourt, 1982 |

## Provenance

- **Access date:** 2026-09-02.
- **Databases queried:** Crossref (`api.crossref.org`, `query.bibliographic` + `/works/{doi}`) for DOI verification and authoritative metadata; OpenAlex was trialed first and found unreliable for exact-title retrieval (its keyword `search=` surfaces top-cited noise, not the target paper), so Crossref's bibliographic search became the primary verification path.
- **Verification method:** every DOI row above was confirmed to resolve in Crossref (title, year, and lead author match) before being listed. Reports and books carry no DOI and are quoted by publisher/year instead of being forced into the DOI format.
- **Identifier conversions:** none — all works cited by their native DOI. No PMID/arXiv-ID conversion was needed.
- **Open-access status:** **Not determined.** The open-access layer (Unpaywall DOI lookups) was attempted but a valid API identity was unavailable (Unpaywall rejects placeholder email addresses; no `OPENALEX_API_KEY`, `S2_API_KEY`, or `NCBI_API_KEY` is set in the environment). OA links should be added in a follow-up pass using a real email/API key. Until then, "freely readable" is **not** claimed for any paper.
- **Known limitations / silent-gap honesty:**
  - The bibliography is a *curated foundation*, not a systematic review. It is intended to make the doctrine arguable, not to be an exhaustive survey of each field.
  - Two doctrine claims rest on books (Ostrom; Olson; Baumol et al.) and one on a report (Eghbal) because those are the canonical statements in those subfields and have no stable DOI.
  - The "why open source projects die" and "donations don't pay" evidence is one strong empirical paper (Overney et al. 2020) plus the Eghbal report; a heavier future pass could widen this to the bus-factor / maintenance-burden literature.

## How to read this

Adjacent to `framework/00-coverage-map.md` and `framework/10-glossary.md`, this is a support layer: it tells you *where each economic claim already in the docs stands in the literature*, and gives you the citation to argue with. It does not alter the doctrine's claims and does not add new ones.
