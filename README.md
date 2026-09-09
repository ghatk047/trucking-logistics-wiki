# Trucking & Logistics Process Wiki

End-to-end business process reference for North American trucking and logistics, modelled on
**J.B. Hunt Transport Services, Inc.** (NASDAQ: JBHT) across all five segments — JBI Intermodal,
DCS Dedicated Contract Services, ICS brokerage on the J.B. Hunt 360 platform, FMS Final Mile
Services and JBT Truckload — with **Schneider National** as a secondary reference point for
things J.B. Hunt's model doesn't cover well (company driving academies, Power Only brokerage,
battery-electric Class 8 deployment).

**Live site → [ghatk047.github.io/trucking-logistics-wiki](https://ghatk047.github.io/trucking-logistics-wiki/)**

> ⚠️ **This site is public.** GitHub Pages on a personal account serves from a `*.github.io`
> URL that anyone with the link can read. A private repository does **not** make the site
> private — only GitHub Enterprise Cloud offers access-controlled Pages. This repo is
> deliberately public so the two facts agree. See [Decision 1](#decision-1--repo-visibility).

---

## Table of contents

- [Live links](#live-links)
- [Current status](#current-status)
- [Taxonomy](#taxonomy)
- [Architecture — and the one that failed](#architecture--and-the-one-that-failed)
- [Phase 0: measure before you generate](#phase-0-measure-before-you-generate)
- [The registries](#the-registries)
- [Defect catalogue — every mistake, and the fix](#defect-catalogue--every-mistake-and-the-fix)
- [What the registry actually catches](#what-the-registry-actually-catches)
- [Runbook](#runbook)
- [Known open items](#known-open-items)
- [If you are building the next wiki, read this first](#if-you-are-building-the-next-wiki-read-this-first)

---

## Live links

### Entry points

| Page | URL |
|---|---|
| Home | https://ghatk047.github.io/trucking-logistics-wiki/ |
| Search | https://ghatk047.github.io/trucking-logistics-wiki/search.html?q=intermodal |
| Enterprise Architecture index | https://ghatk047.github.io/trucking-logistics-wiki/ea-diagrams/index.html |
| EA-01 — Trucking Enterprise System Landscape | https://ghatk047.github.io/trucking-logistics-wiki/ea-diagrams/ea-01/index.html |

### Generated processes (21 of 360 live)

All of **Network & Load Planning** except `TL-NP-FC-06`.

**Network Design & Capacity Planning**

| PID | Process | Link |
|---|---|---|
| TL-NP-ND-01 | Lane Network Design and Freight Flow Balancing | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/network-design/tl-np-nd-01/index.html) |
| TL-NP-ND-02 | Terminal and Domicile Footprint Planning | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/network-design/tl-np-nd-02/index.html) |
| TL-NP-ND-03 | Headhaul and Backhaul Pairing Analysis | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/network-design/tl-np-nd-03/index.html) |
| TL-NP-ND-04 | Dedicated versus Network Capacity Allocation Decision | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/network-design/tl-np-nd-04/index.html) |
| TL-NP-ND-05 | Seasonal Peak Capacity Planning and Surge Preparation | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/network-design/tl-np-nd-05/index.html) |
| TL-NP-ND-06 | Fleet Size and Mix Modelling for Tractors and Trailers | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/network-design/tl-np-nd-06/index.html) |
| TL-NP-ND-07 | Drop-and-Hook Trailer Pool Sizing at Customer Sites | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/network-design/tl-np-nd-07/index.html) |
| TL-NP-ND-08 | Network Profitability Review and Lane Exit Decisions | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/network-design/tl-np-nd-08/index.html) |

**Load Planning & Tender Management**

| PID | Process | Link |
|---|---|---|
| TL-NP-LT-01 | Inbound EDI 204 Load Tender Receipt and Validation | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/load-planning-tender/tl-np-lt-01/index.html) |
| TL-NP-LT-02 | Tender Acceptance and Rejection Decision Logic | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/load-planning-tender/tl-np-lt-02/index.html) |
| TL-NP-LT-03 | Load Building and Multi-Stop Consolidation | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/load-planning-tender/tl-np-lt-03/index.html) |
| TL-NP-LT-04 ⚠️ | Pre-Planning and Forward Load Assignment to Available Capacity | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/load-planning-tender/tl-np-lt-04/index.html) |
| TL-NP-LT-05 | Appointment Scheduling and Delivery Window Negotiation | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/load-planning-tender/tl-np-lt-05/index.html) |
| TL-NP-LT-06 | Weight and Cargo Securement Planning under 49 CFR 393 Subpart I | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/load-planning-tender/tl-np-lt-06/index.html) |
| TL-NP-LT-07 ⚠️ | Hazmat Load Planning and Routing under 49 CFR Part 397 | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/load-planning-tender/tl-np-lt-07/index.html) |
| TL-NP-LT-08 | Load Cancellation, Reconsignment and Diversion Handling | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/load-planning-tender/tl-np-lt-08/index.html) |

**Volume Forecasting & Demand Planning**

| PID | Process | Link |
|---|---|---|
| TL-NP-FC-01 | Customer Volume Forecast Collection and Reconciliation | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/volume-forecasting/tl-np-fc-01/index.html) |
| TL-NP-FC-02 | Statistical Demand Forecasting by Lane and Equipment Type | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/volume-forecasting/tl-np-fc-02/index.html) |
| TL-NP-FC-03 | Capacity Commitment Planning against Routing Guide Awards | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/volume-forecasting/tl-np-fc-03/index.html) |
| TL-NP-FC-04 | Market Rate and Tender Rejection Index Monitoring | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/volume-forecasting/tl-np-fc-04/index.html) |
| TL-NP-FC-05 | Produce Season and Regional Surge Forecasting | [open](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/volume-forecasting/tl-np-fc-05/index.html) |

⚠️ = carries a known defect, see [Known open items](#known-open-items).

### Domain indexes

Every L1 index is live and navigable even where its processes are not yet generated.
Ungenerated PIDs 404 by design — the sidebar carries all 360 links from day one so the
information architecture is reviewable before the content exists.

| Domain | Index |
|---|---|
| Network & Load Planning | [network-planning](https://ghatk047.github.io/trucking-logistics-wiki/network-planning/index.html) |
| Dispatch & Driver Operations | [dispatch-driver-ops](https://ghatk047.github.io/trucking-logistics-wiki/dispatch-driver-ops/index.html) |
| Terminal & Yard Operations | [terminal-yard](https://ghatk047.github.io/trucking-logistics-wiki/terminal-yard/index.html) |
| Intermodal Operations | [intermodal](https://ghatk047.github.io/trucking-logistics-wiki/intermodal/index.html) |
| Brokerage & Freight Matching | [brokerage](https://ghatk047.github.io/trucking-logistics-wiki/brokerage/index.html) |
| Dedicated Contract Services | [dedicated-contract](https://ghatk047.github.io/trucking-logistics-wiki/dedicated-contract/index.html) |
| Warehousing & Fulfillment | [warehousing-fulfillment](https://ghatk047.github.io/trucking-logistics-wiki/warehousing-fulfillment/index.html) |
| Final Mile Delivery | [final-mile](https://ghatk047.github.io/trucking-logistics-wiki/final-mile/index.html) |
| Fleet Maintenance & Asset Management | [fleet-maintenance](https://ghatk047.github.io/trucking-logistics-wiki/fleet-maintenance/index.html) |
| Safety & DOT Compliance | [safety-dot-compliance](https://ghatk047.github.io/trucking-logistics-wiki/safety-dot-compliance/index.html) |
| Driver Recruiting, Training & Retention | [driver-workforce](https://ghatk047.github.io/trucking-logistics-wiki/driver-workforce/index.html) |
| Customer Service & Account Management | [customer-account](https://ghatk047.github.io/trucking-logistics-wiki/customer-account/index.html) |
| Revenue Management & Pricing | [revenue-pricing](https://ghatk047.github.io/trucking-logistics-wiki/revenue-pricing/index.html) |
| Finance & Settlement | [finance-settlement](https://ghatk047.github.io/trucking-logistics-wiki/finance-settlement/index.html) |
| Technology & Telematics | [technology-telematics](https://ghatk047.github.io/trucking-logistics-wiki/technology-telematics/index.html) |
| Procurement, Fuel & Sustainability | [procurement-fuel-sustainability](https://ghatk047.github.io/trucking-logistics-wiki/procurement-fuel-sustainability/index.html) |

---

## Current status

| | |
|---|---|
| Processes live | **21 / 360** |
| EA diagrams live | **1 / 10** |
| Domains complete | Network & Load Planning (21/22) |
| Template version | `1.0.0` |
| Registries | 92 systems · 63 regulations · 78 roles · 67 KPIs · 24 market facts |
| Generator | 2,436 lines (`generate_trucking_wiki.py`) + 378 (`generate_trucking_ea.py`) |
| Sanitiser self-test | 15/15 passing |

---

## Taxonomy

**16 L1 domains · 48 L2 groups · 360 processes · 10 EA diagrams.**

PID format: `TL-{L1}-{L2}-{NN}` → `TL-NP-ND-01`
Path: `{domain-slug}/{l2-slug}/{pid-lower}/index.html` (depth 3)
EA path: `ea-diagrams/{ea-id}/index.html` (depth 2)

| Code | Domain | Slug | L2 | Processes | Done |
|---|---|---|---|---|---|
| NP | Network & Load Planning | `network-planning` | 3 | 22 | 21 |
| DO | Dispatch & Driver Operations | `dispatch-driver-ops` | 4 | **32** | 0 |
| TY | Terminal & Yard Operations | `terminal-yard` | 2 | 12 | 0 |
| IM | Intermodal Operations | `intermodal` | 3 | 24 | 0 |
| BK | Brokerage & Freight Matching | `brokerage` | 3 | 24 | 0 |
| DC | Dedicated Contract Services | `dedicated-contract` | 3 | 22 | 0 |
| WH | Warehousing & Fulfillment | `warehousing-fulfillment` | 3 | 22 | 0 |
| FM | Final Mile Delivery | `final-mile` | 2 | 14 | 0 |
| MX | Fleet Maintenance & Asset Management | `fleet-maintenance` | 4 | **32** | 0 |
| SC | Safety & DOT Compliance | `safety-dot-compliance` | 4 | **32** | 0 |
| DR | Driver Recruiting, Training & Retention | `driver-workforce` | 3 | 24 | 0 |
| CS | Customer Service & Account Management | `customer-account` | 3 | 18 | 0 |
| RM | Revenue Management & Pricing | `revenue-pricing` | 2 | 14 | 0 |
| FN | Finance & Settlement | `finance-settlement` | 3 | 22 | 0 |
| TE | Technology & Telematics | `technology-telematics` | 3 | 24 | 0 |
| PF | Procurement, Fuel & Sustainability | `procurement-fuel-sustainability` | 3 | 22 | 0 |

Weighting is deliberate: dispatch/driver operations, fleet maintenance and safety/DOT compliance
carry 32 each because they are where a trucking company actually lives. Peripheral corporate
domains carry 12–18.

### ⚠️ Taxonomy arithmetic — a real mistake worth repeating out loud

The taxonomy was first presented for approval as "16 L1 / 45 L2 / 360 processes". It was
actually **48 L2 / 384 processes** — the per-domain counts in the proposal table were summed
by hand and one of the sixteen rows was dropped. Nobody caught it in review; the
`assert len(PROCESSES) == 360` in the generator caught it at import time.

Two lessons:

1. **Put the assertion in before the taxonomy, not after.** `assert len(PROCESSES) == N` and
   `assert len(TAXONOMY) == M` cost nothing and are the only thing standing between you and
   scaffolding 384 folders you didn't mean to.
2. **Don't hand-sum a table you're asking someone to approve.** Generate the totals from the
   same data structure the code uses.

The fix trimmed the last two L3 processes from 12 mid-weight/peripheral L2 groups — never from
DO, MX, SC, IM or BK, which carry the weighting story. Casualties included *Win-Loss Analysis*,
*Budgeting & Variance Analysis* and *Terminal Security & Cargo Theft Prevention*.

---

## Architecture — and the one that failed

```
registries/*.json  ──┐
                     ├──> Ollama call 1 (JSON: steps, roles, systems, KPIs, risks)
taxonomy (Python) ───┤         │
                     │         ├──> registry validation (systems / roles / citations)
                     │         │
                     └──> Ollama call 2 (raw Mermaid, given the steps from call 1)
                               │
                               ├──> sanitise_mermaid()        ← 7 ordered transforms
                               ├──> diagram_richness()        ← scored vs Phase 0 floors
                               ├──> mmdc render → SVG
                               ├──> finalize_svg()            ← strips the max-width cap
                               └──> GitHub Contents API (SHA-before-PUT, backoff)
                                          │
                                          └──> .deploy pushed LAST → Pages rebuild
```

**Local-only, never pushed** (`.gitignore`): `data/` (tracker + Excel), `diagrams/` (`.mmd`
sources), `scripts/` (generators). The published repo is HTML, CSS, JS, SVG/PNG and the
registries.

### The architecture that did NOT work

A sibling project (`ghatk047/rail-wiki`) was built as **raw Markdown with YAML frontmatter that
never got templated into HTML**, with **Mermaid source printed as literal text** instead of
rendered. It also used a flat, inconsistent directory layout.

Symptoms to recognise if you inherit something like it:

- Pages show `---\ntitle: ...\n---` frontmatter as visible body text
- Diagrams appear as `flowchart LR\n A --> B` in a code block, not as a picture
- EA pages sit at a different depth from process pages, so relative asset paths break

The working pattern is: **Python generator → real HTML with a baked-in sidebar → mmdc renders
Mermaid to SVG → GitHub Contents API push.** Both `shipping-wiki` and `airline-process-wiki`
use it; this repo ports it directly rather than reinventing.

### Why two model calls, never one

Call 1 returns content JSON and its system prompt **explicitly forbids Mermaid or diagram
syntax**. Call 2 returns raw Mermaid only, and is the only prompt that recites Mermaid rules.

This is not stylistic:

- A multi-line Mermaid node label inside a JSON string needs escaped `\n`. A 14B model gets
  this wrong often enough that labels silently flatten to one line.
- Reusing one prompt for both calls makes the model inject a diagram into the JSON response,
  which breaks extraction. **Separate system prompts are load-bearing.**

---

## Phase 0: measure before you generate

Before writing a line of generator code, both reference repos were cloned and their `.mmd`
files measured. These are **measured floors, not invented ones** — the single most useful
thing done in this build.

**Airline reference, n = 149 process diagrams:**

| Metric | Mean | Range |
|---|---|---|
| Lines | 52.1 | 39–82 |
| Unique nodes | 30.6 | 23–44 |
| Decision diamonds | 6.2 | 4–13 |
| Labelled branches | 12.4 | — |
| Subgraphs | 5.4 | — |
| style/classDef lines | 8.5 | — |

**Shipping reference, n = 16 process diagrams:**

| Metric | Mean | Range |
|---|---|---|
| Lines | 54.9 | 42–66 |
| Unique nodes | 27.3 | 17–33 |
| Decision diamonds | 7.2 | 5–11 |
| Labelled branches | 14.4 | 10–22 |
| Subgraphs | 5.7 | 4–6 |
| style lines | 11.1 | 7–16 |

Derived floors, enforced in code:

```python
PID_FLOOR = {"nodes": 22, "decisions": 5, "branches": 10,
             "subgraphs": 5, "styles": 7, "lines": 42}
EA_FLOOR  = {"nodes": 22, "labelled": 12, "subgraphs": 6,
             "classdefs": 5, "lines": 60}
```

Up to 3 drafts are generated and the best-scoring is kept. A diagram below the floor is still
published, but the run log names the PID so it can be re-run with `--force`.

### Aspect ratio is not a defect

Process diagrams (`flowchart LR`, 5–6 phase subgraphs) render as very wide ribbons —
**7.1× to 10.7×** width:height, up to 8100px wide. This looked alarming until measured against
the reference, whose own LR diagrams run **7.7× to 18.3×**. This is normal for the format.
The lightbox zoom is the intended reading mechanism. **No upper bound was added to the scorer**
— an earlier plan to add one was wrong.

---

## The registries

Five JSON files of real, verifiable entities. Generated content is validated against them
**after generation** — instructing the prompt and hoping is not sufficient.

| File | Count | Contents |
|---|---|---|
| `systems.json` | 92 | Real TMS (McLeod, Oracle OTM, Trimble TMW, MercuryGate), ELD/telematics (Samsara, Motive, Omnitracs, PeopleNet, Geotab), load boards (DAT One, Truckstop.com), fuel/settlement (Comdata, EFS/WEX, TriumphPay), maintenance (Decisiv, Fleetio, Trimble TMT), visibility (project44, FourKites, MacroPoint), rail (BNSF, NS, CSX, UP, Railinc), regulatory systems (FMCSA Clearinghouse, SAFER/SMS, PSP), plus J.B. Hunt 360 |
| `regulations.json` | 63 | Real citations with titles: 49 CFR Parts 40, 382, 383, 385, 387, 390–399, the ELD mandate at 395.8, HOS at 395.3, DQ files at 391.51, DVIR at 396.11, annual inspection at 396.17, broker rules at Part 371, Carmack at 49 USC 14706, plus IFTA, IRP, UCR, CSA/SMS, CARB, OSHA, EPA SmartWay, ASC 606/842, NMFC, AAR, UIIA |
| `roles.json` | 78 | Real job titles by domain — Driver Manager, Load Planner, Ramp Operations Manager, Carrier Sales Representative, Designated Employer Representative, Medical Review Officer, Shop Foreman, Settlement Clerk |
| `kpis.json` | 67 | Standard metrics with representative industry target ranges — operating ratio, revenue per loaded mile, empty mile %, driver turnover, CSA BASIC percentile, PM compliance, box turns/year, detention hours/load |
| `facts.json` | 24 facts | J.B. Hunt segment structure, Schneider reference notes, and hard regulatory numbers (80,000 lb GVW, 11-hour drive, 14-hour window, 34-hour restart, $750k liability minimum, $75k broker bond) |

Each entry carries `category` and often a `note` explaining what it actually is. The `category`
field is what makes domain-scoped prompting possible — see [Defect 9](#defect-9--prompt-anchoring-the-big-one).

⚠️ `regulations.json` carries a caveat on **CARB Advanced Clean Fleets**: the waiver request was
withdrawn in January 2025. Verify current status before relying on it. Regulatory registries go
stale — date them and re-check.

---

## Defect catalogue — every mistake, and the fix

Nine defects were found and fixed during this build. Six were found **only by running real
generation** — the synthetic unit tests written first passed the whole time. That is the
headline lesson.

### Defect 1 — Sanitiser mangles regulatory citations

**Class:** pre-existing, inherited from the reference (already fixed there)
**Symptom:** a regex rewriting digit-leading Mermaid node IDs (`1.1` → `S1_1`) also rewrites
`49 CFR 395.8` → `49 CFR S395_8`. In a domain this citation-dense it corrupts most diagrams.
**Fix:** stash all label text (`[...]`, `{...}`, `|"..."|`) into placeholders *before* the
digit rewrite, restore *after*.

```python
mmd = re.sub(r'\[[^\]]*\]|\{[^}]*\}|\|"[^"]*"\|', _hold, mmd)
mmd = re.sub(r'\b(\d+)\.(\d+)\b', r'S\1_\2', mmd)
mmd = re.sub(r'\x00(\d+)\x00', lambda m: stash[int(m.group(1))], mmd)
```

**Regression test:** `sanitise("... 49 CFR 395.8 ...")` must still contain `49 CFR 395.8`, and
`1.1[Node]` must still become `S1_1[Node]`. Run `--self-test`.

---

### Defect 2 — `style` directives carrying node shapes

**Class:** model output, found by running
**Symptom:** mmdc parse error `Expecting 'SPACE', ... got 'STADIUMSTART'`. The model emits
`style B([End]) fill:#232f3e` — repeating the node's shape. Mermaid's `style` and `class`
directives take a **bare node ID only**.
**Cost if unfixed:** one full ~5-minute regeneration round-trip per occurrence. Across 360
processes that is hours.
**Fix:** strip any shape suffix following an identifier on a `style`/`class` line, handling
`[...]`, `{...}`, `([...])`, `((...))` and comma-lists (`class D([End]),E[Box] name`).
Must run *after* label cleaning, *before* the init-block normalisation.

```
style B([End]) fill:#111   →   style B fill:#111
class D([End]),E[Box] term →   class D,E term
```

The real node definition `B([End])` elsewhere in the file must be left untouched.

---

### Defect 3 — Render-retry silently downgrades quality

**Class:** logic bug, inherited from the reference
**Symptom:** the draft loop scores 3 candidates and keeps the best. The *render-retry* loop
then replaces that candidate with a fresh generation **without scoring it**. A retry could
publish a thinner diagram than the one it displaced, invisibly.
**Fix:** score every replacement. If it is weaker, still use it (the better one won't render)
but say so explicitly in the log.

This one never actually bit — it was found by reading the code path while tracing Defect 2.
Worth stating: *some* review still beats none, even in a pipeline validated by output checks.

---

### Defect 4 — SVG `max-width` cap blurs zoomed diagrams

**Class:** pre-existing, inherited from the reference (already fixed there)
**Symptom:** mmdc emits the root `<svg>` with `width="100%"` and an inline
`style="max-width: Npx"`. That cap forces the browser to rasterise at that ceiling and scale
the bitmap up — a vector file that looks exactly like a blurry PNG.
**Fix:** after every render, rewrite `width="100%"` to the real pixel width from the `viewBox`
and strip the `max-width` rule.

**Proof:** `grep -c 'max-width' output.svg` must return `0`. Verified 0/21 across the domain.

---

### Defect 5 — Lightbox zoom blurs or drifts

**Class:** pre-existing, inherited from the reference (already fixed there)
**Symptom:** zooming with `transform: scale()` magnifies a cached raster. `will-change:
transform` forces the same. Flex-centring the overlay makes the image drift sideways as its
width grows.
**Fix (in `assets/js/wiki.js` + `wiki.css`):**

- Zoom by changing the image's **layout `width`**, so the browser re-rasterises the SVG at the
  new size
- `transform` is used for **pan only** (`translate`, never `scale`)
- No `will-change`
- `position: absolute` on the image, not flex-centring
- Pan offset centred explicitly once in `resetView()`

**Proof (run in the live page console):**

```js
usesLayoutWidthZoom: true      // width 1177.6px → 2944px
usesTransformScale:  false     // transform is translate() only
willChange:          "auto"
position:            "absolute"
```

---

### Defect 6 — Validator flags legitimate generic descriptors

**Class:** validator precision, found by running
**Symptom:** `"Email System"` flagged as an unlisted system. The allow-list check was
exact-match only, so the allow-listed token `email` never matched `email system`.
**Fix:** strip filler words (`system`, `platform`, `software`, `tool`, `solution`, `the`, …)
then match the allow list **as a whole**.

**The trap:** substring-matching the allow list looks like the obvious fix and is wrong — a
fabricated `FakeTMS Pro 9000` would pass on the strength of the allowed token `tms`. Whole-match
after filler-stripping is the correct shape. Also handles parenthesised acronyms:
`Customer Relationship Management (CRM) System` → generic `crm`.

---

### Defect 7 — Citation validator, four separate bugs

**Class:** validator precision, found by running — **each bug surfaced only when real content
hit it, and the synthetic tests passed throughout.**

| # | Bug | Example that exposed it |
|---|---|---|
| 7a | Registry stored `49 CFR Part 393`; content said `49 CFR 393`. Same citation, different surface form. | `TL-NP-LT-06` |
| 7b | Extraction regex `[\w§.\-]+` consumed the word `Part` before the optional part-clause could match, yielding a numberless `49 CFR Part`. | `TL-NP-ND-04` |
| 7c | Plural `49 CFR Parts` not handled. | `TL-NP-FC-02` |
| 7d | `_norm_cite` stripped singular `part ` but not `parts `, so ranges never reached the range resolver. | found by the 7c fix's own test |

**Final shape:**

```python
_CITE_RE = r"\b49\s+(?:CFR|U\.?S\.?C\.?)\s+(?:Parts?\s+)?\d[\w§.\-]*"
# normalise: drop "part"/"parts", collapse whitespace, usc variants
# resolve:   exact → section-within-part → range span (Parts 390-399)
```

All ten cases pass, including rejecting fabricated `49 CFR Part 999` and `49 CFR 8675.309`.

---

### Defect 8 — Regulations and documents filed as *systems*

**Class:** model content error, found by running — **the dominant defect mode**
**Symptom:** the `system` field of an L4 step contained `49 CFR Part 395`,
`ELD mandate (49 CFR 395.8)`, `Driver vehicle inspection report (DVIR)`, `Bill of Lading`.
These render on the page as **software tags**, which is simply wrong.
**Fix, two parts:**

1. **Prompt rule:** *"A 'system' is a SOFTWARE PRODUCT or platform. Never put a regulation, a
   CFR part, a document or a job title in the system field. 49 CFR 395 is a regulation, not a
   system; the system that enforces it is the ELD platform."*
2. **Detection:** a dedicated `regulations_as_systems` finding bucket, using `re.search`
   (not `re.match`) so embedded cites like `ELD mandate (49 CFR 395.8)` are caught.

---

### Defect 9 — Prompt anchoring (the big one)

**Class:** content quality, found by measuring output distribution
**Symptom:** across the first 11 generated processes, **Samsara appeared 38 times and Lytx
DriveCam 9 times — in network-planning processes.** Those are ELD and dashcam platforms; they
have nothing to do with lane design or tender acceptance. Only 19 distinct systems appeared,
with three names taking 187 of ~237 mentions.

**Root cause — entirely self-inflicted:**

1. The system prompt injected `SYSTEM_NAMES[:44]` — the first 44 registry entries **in file
   order** — into *every* domain's prompt.
2. The `JSON_SHAPE` example literally read `"systems": ["McLeod LoadMaster", "Samsara", "J.B. Hunt 360"]`.

The model did exactly what it was shown.

**Fix:** domain-scoped prompting driven by the registry's `category` field.

- `DOMAIN_CATS` maps each L1 domain to relevant categories, **in priority order**
- `domain_systems(l1)` returns only category-relevant systems
- `json_shape_for(l1)` builds the shape example from **domain-specific** categories, not the
  shared core — otherwise the example collapses back to the same TMS trio
- Picks honour the **declared category order**, not registry file order — filtering by
  membership alone put telematics ahead of maintenance for MX and visibility ahead of WMS for WH

**Measured result across the regenerated 21-process domain:**

| | Before | After |
|---|---|---|
| Telematics/dashcam mentions in a planning domain | 47 | **0** |
| Routing engines (PC\*MILER, Rand McNally) | 2 | **124** |
| Distinct systems | 19 / 11 procs | 22 / 21 procs |

Resulting shape examples, one per domain — this is what "correct" looks like:

```
NP: PC*MILER, Rand McNally IntelliRoute      IM: BNSF Ramp Systems, NS AccessNS
DO: Samsara, Motive                          BK: McLeod PowerBroker, DAT One
MX: Fleetio, Trimble TMT                     SC: FMCSA Clearinghouse, SAFER/SMS
DR: Tenstreet, DriverReach                   FN: Comdata, EFS / WEX Fleet
WH: Manhattan Associates WMS, Blue Yonder    TY: Zebra YMS, 4SIGHT YMS
```

---

## What the registry actually catches

**This is the most transferable finding in the project.**

The registry was built to catch **hallucinated vendors** — a TMS or an ELD product that doesn't
exist. Across 21 generated processes, **zero fabricated products appeared.**

What it actually caught, repeatedly, was **category errors** — the model conflating three
different kinds of thing into one field:

| Caught | Actual type | Times |
|---|---|---|
| `49 CFR Part 395`, `49 CFR 396`, `ELD mandate (49 CFR 395.8)` | regulation | 4 |
| `Driver vehicle inspection report (DVIR)`, `Bill of Lading` | document | 4 |
| `Schneider National Academy` | a business unit, not software | 1 |
| `Network Design Specialist`, `Network Designer` | job titles missing from the roles registry | 2 |
| `Microsoft Teams`, `Email System`, `SMS Gateway` | real/generic tools missing from a domain-specific registry | 3 |

**Implication for the next wiki:** budget your validator for *type confusion*, not invention.
A 14B model asked for "the system used at this step" will happily answer with the regulation
that governs the step, the document produced by it, or the team that performs it. Validate the
**kind** of thing, not just its existence.

Corollary: a registry-miss is not automatically a hallucination. Of the flags above, the correct
response was to *extend the registry* five times (roles ×6, business tools ×6, TriumphPay naming)
and to *fix the content* only for regulations and documents.

---

## Runbook

### Prerequisites

```bash
# Ollama with a 14B-class model
curl -s http://localhost:11434/api/tags | grep -o 'qwen[^"]*' | sort -u

# mermaid-cli
mmdc --version           # 11.12.0 used here

# Token — from the environment ONLY, never written to a file
export GITHUB_TOKEN="$(gh auth token)"
```

**mmdc + Chrome:** if mmdc cannot find Chrome, run
`npx puppeteer browsers install chrome` from inside the mermaid-cli install directory. If it
still cannot resolve the binary, export `PUPPETEER_EXECUTABLE_PATH` to the resolved path and
persist it to the shell profile. This failure has now happened on this machine twice across
two projects — it is persisted at `~/.zshrc`.

### Commands

```bash
# regression tests — run this after ANY sanitiser or validator edit
python3 scripts/generate_trucking_wiki.py --self-test

# push shell only (assets, home, all indexes, search) — do this before enabling Pages
python3 scripts/generate_trucking_wiki.py --bootstrap

# one process
python3 scripts/generate_trucking_wiki.py --pid TL-NP-ND-01

# next N incomplete, verifying and committing every 5
python3 scripts/generate_trucking_wiki.py --count 20 --verify-every 5

# regenerate something the tracker marks Complete
python3 scripts/generate_trucking_wiki.py --pid TL-NP-LT-04 --force

# resume from a PID / everything remaining
python3 scripts/generate_trucking_wiki.py --start TL-DO-DP-01
python3 scripts/generate_trucking_wiki.py --full

# indexes + search index only, no model calls
python3 scripts/generate_trucking_wiki.py --rebuild-nav

# EA diagrams
python3 scripts/generate_trucking_ea.py --id ea-01
```

### Order of operations for a fresh repo

Pages **cannot** be enabled until at least one commit exists on `main`.

1. `gh repo create <name> --public`
2. Scaffold locally, commit and push the shell (`.nojekyll`, CSS, JS, placeholder home)
3. Enable Pages: `gh api -X POST repos/OWNER/REPO/pages -f "source[branch]=main" -f "source[path]=/"`
4. `--bootstrap` to push real indexes
5. Generate content

### Throughput

~5–6 minutes per process (two Ollama calls on a 14B model). 21 processes ≈ 1h55m.
The full 360 is roughly **35 hours** of generation. Use `--count N` and `--verify-every 5`
so an interruption costs at most 4 processes of work.

### Verification commands that actually prove something

```bash
# SVG size cap removed — MUST return 0
grep -c 'max-width' assets/img/<id>.svg

# rendered vector, not raw Mermaid text — expect 100+ <g>, 0 'flowchart'
grep -o '<g ' x.svg | wc -l ; grep -c 'flowchart' x.svg

# citations intact, no mangled forms
grep -oE '49 CFR [0-9]+(\.[0-9]+)?' page.html | sort -u
grep -c 'S49_' x.svg        # MUST be 0

# no token anywhere in the repo — MUST return no match
grep -rn "ghp_[A-Za-z0-9]\{20,\}" . ; grep -rn "gho_[A-Za-z0-9]\{20,\}" .

# local-only artefacts not published — MUST be 0
gh api "repos/OWNER/REPO/git/trees/main?recursive=1" --jq '.tree[].path' \
  | grep -cE '^(data|scripts|diagrams)/'
```

---

## Known open items

| Item | Detail |
|---|---|
| `TL-NP-LT-04` | `49 CFR 396`, `49 CFR Part 382`, `49 CFR Part 395` tagged as systems. Generated before Defect 8 detection existed. Clear with `--pid TL-NP-LT-04 --force`. |
| `TL-NP-LT-07` | `Driver vehicle inspection report (DVIR)`, `ELD mandate (49 CFR 395.8)` tagged as systems. Same fix. |
| `TL-NP-FC-06` | Never generated — the batch was 21, the domain has 22. |
| EA-02 … EA-10 | Not yet generated. |
| Label-stash protection | **Not yet exercised live.** No generated diagram has placed a *decimal* citation (`395.8`) inside a Mermaid node label. Covered by 5 synthetic self-test cases and 0 mangled forms across all diagrams, but the real-world hit is still pending. It will come in the **Safety & DOT Compliance** domain, which cites `382.301`, `395.8` and `396.11` constantly — verify it explicitly there rather than assuming synthetic coverage carries. |
| `J.B. Hunt 360` frequency | 215 of ~430 system mentions in the NP domain. Defensible for the flagship platform in a J.B. Hunt-modelled wiki, but worth re-checking once a domain where it is *less* central (e.g. MX, SC) has been generated. |

---

## If you are building the next wiki, read this first

Ten things, ordered by how much time they save.

1. **Measure the reference before you generate anything.** Clone the working sibling repos and
   compute real `.mmd` statistics — line count, node count, diamond count, labelled branches,
   subgraphs, style lines. Those numbers become your scoring floor. A floor you invented is a
   floor you will rationalise away.

2. **Assert your taxonomy size at import time.** `assert len(PROCESSES) == N`. The one mistake
   that survived human review in this build was hand-summed arithmetic in a proposal table.

3. **Two model calls, two system prompts. Never one.** Mermaid must never travel inside JSON,
   and the JSON prompt must explicitly forbid diagram syntax.

4. **Scope every prompt to its domain.** Feeding the same file-ordered entity list to all
   domains guarantees anchoring. Give the model only what belongs in that domain, order the
   categories by relevance, and make the shape example domain-specific — the example is
   imitated more strongly than the instructions.

5. **Validate the *kind* of entity, not just its existence.** You will catch far more category
   errors (regulation-as-system, document-as-system, job-title-as-system) than invented
   products. Give each its own finding bucket.

6. **Run one real domain before trusting any validator.** Six of nine defects here surfaced
   only against real generated content. The citation validator needed four iterations; its
   synthetic tests passed the entire time.

7. **A registry-miss is not automatically a hallucination.** Decide case by case whether to
   extend the registry or fix the content. This build extended it five times and fixed content
   twice.

8. **Fix the pipeline mid-run, restart deliberately.** A running Python process holds its own
   imported module, so editing the generator during a run is safe and changes nothing until the
   next invocation. When a content-quality fix lands, stop and regenerate rather than letting
   an hour of known-flawed output accumulate.

9. **Prove every claim with a command.** `grep -c 'max-width'` returning 0. `<g>` count > 100.
   Token scan returning no match. Tree listing showing 0 paths under `data|scripts|diagrams`.
   "It looks fine" is not verification, and a page returning HTTP 200 says nothing about
   whether the diagram inside it rendered.

10. **Check your own check.** During final verification a shell loop reported "no pages
    affected" when two pages were in fact affected — the bug was in the loop, not the pages.
    A verification script that reports success is itself an untested claim.

---

## Repository layout

```
trucking-logistics-wiki/
├── assets/
│   ├── css/wiki.css          # published — sidebar, cards, lightbox (no will-change)
│   ├── js/wiki.js            # published — accordion nav, width-based lightbox zoom, search
│   └── img/*.svg *.png       # published — rendered diagrams
├── registries/*.json         # published — the 5 sourced registries
├── ea-diagrams/{id}/         # published — EA pages
├── {domain}/{l2}/{pid}/      # published — process pages
├── search.html
├── search-index.json
├── .nojekyll                 # required: stops Jekyll eating underscore paths
├── .deploy                   # pushed LAST in every batch to trigger the Pages rebuild
├── data/                     # LOCAL ONLY — tracker + Excel workbook
├── diagrams/                 # LOCAL ONLY — .mmd sources
└── scripts/                  # LOCAL ONLY — generators
```

### Decision 1 — repo visibility

The build was originally specified as **private repo + public Pages**. Two facts changed that:

1. GitHub Pages from a private repo on a personal account is still **publicly reachable** at the
   `*.github.io` URL. Private repo ≠ private site.
2. **GitHub Free personal accounts cannot enable Pages on a private repo at all** — it requires
   Pro. This would have failed at the Pages-enable step, after everything else was built.

Decision taken: **public repo, public Pages**, matching both sibling projects, so the repository's
visibility and the site's visibility tell the same story.

### Decision 2 — token handling

`GITHUB_TOKEN` is read from the environment only and is **never written to any file**. It is
minted at run time with `export GITHUB_TOKEN="$(gh auth token)"`. Verified with a repo-wide scan
for `ghp_`/`gho_` patterns returning no match.

---

## Credits

Pattern ported from [`ghatk047/shipping-wiki`](https://github.com/ghatk047/shipping-wiki) and
[`ghatk047/airline-process-wiki`](https://github.com/ghatk047/airline-process-wiki), whose
generators already encode the sanitiser, SVG and lightbox fixes documented above. Do not
reinvent them.

Content is generated by a local 14B model against sourced registries. It is a **reference
model of how trucking operations work**, not a description of any specific carrier's internal
procedures. Regulatory citations are real and traceable to the eCFR, but this is not legal or
compliance advice — verify against the current eCFR before relying on any citation.
