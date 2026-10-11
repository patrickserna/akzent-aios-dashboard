# AIOS Dashboard — Repository Instructions

## Permanent LEAD Template (Aptar Querétaro reference)

Established 2026-10-10 at the user's request. This standard governs future work in this repository when these instructions are loaded. It does not apply outside this repository.

### Approved reference

- **Repository:** `/Users/patriciojacobsernagarza/Documents/GitHub/akzent-aios-dashboard`
- **Dashboard file:** `index.html`, the multi-account dashboard at the repository root.
- **Approved reference commit:** `230fdf80b1a3acdbdf90945450de84f98690ea42`, "Aptar Querétaro — exported file keeps the network filter selection", committed 2026-10-11 00:06 −06:00 with the user's approval.
  - It equals the original approved version `6b556fc` (2026-10-10) plus one line in the network script, which reads the saved filter selection when an exported file opens. There is no visual or data change.
  - When this was recorded, the commit existed locally and was **not yet pushed**. Pushes from Claude sessions fail, so the user pushes manually.
  - Read the reference with `git show 230fdf8:index.html`.
- **Locating Aptar inside `index.html`.** Line numbers drift, so search for these markers instead:
  - **Scoped CSS:** the block starting `/* Aptar Querétaro — Account Brief 2.0 (#view-aptar only).`, which ends right before `/* BRAHM Precision Products Corporation Mexico — scoped view components`. Every rule is prefixed `#view-aptar` and uses `.ap2-` classes.
  - **View markup:** from `<!-- ══ APTAR QUERÉTARO VIEW` to the next `<!-- ══ FÁBRICA DE MERMELADAS VIEW ══ -->`. The root element is `<div id="view-aptar" class="view" data-ap2-mode="seller">`.
  - **Sections:** `#ap2-s1` The network at a glance (interactive network, `#ap2-net`), `#ap2-s2` Inbound and outbound profile, `#ap2-s3` Core corridors, `#ap2-s4` What changed, `#ap2-s5` Customs footprint, `#ap2-s6` Where coordination matters, `#ap2-s7` Seller desk (internal).
  - **Lead / Client view:** the `[data-ap2-mode-toggle]` button switches `data-ap2-mode` between `seller` and `prospect`.
    - In `prospect` mode, `.ap2-internal` is hidden: relationship status, wallets, Arcatek/Akzent capture, profit and revenue, discovery guide, data quality and the Account Matrix.
    - Every "PJ" mention reads "Trade Records" via `.ap2-pj` / `.ap2-tr`.
  - **Other surfaces:** home account card (`<!-- Aptar Querétaro · AIOS Seller Report`), portfolio table row, `ACCOUNTS` entry (`id:'view-aptar'`) and `D2_FACTS["view-aptar"]`.

### 1. Mandatory template for LEADs

For every future account **explicitly designated as LEAD**:

- Work in the existing multi-account `index.html`.
- Use the approved Aptar implementation as the structural and visual template.
- Preserve section order, hierarchy, component types, layouts, tables, charts, cards and expandable details.
- Preserve typography, styling, navigation, responsive behavior and print behavior.
- Update only the target account, preserving unrelated accounts and shared functionality.
- Replace an existing target account's obsolete content rather than appending a duplicate.
- Do not create a standalone dashboard unless explicitly requested.

The account's intelligence changes; the approved structure remains consistent.

Do not redesign, reorder sections, replace visualizations with narrative or add duplicate content without explicit user approval.

### 2. Network structure and interactivity

Preserve the approved five-column network:

**Origin Countries → Entry Gateways → Account → Exit Gateways → Destination Countries**

Maintain:

- Previous-full-calendar-year and current-YTD period filters.
- An explicit current-YTD cutoff based on supplied intelligence.
- Import / Export / Both selection.
- Transport-mode filtering.
- Independent country and gateway selections for Imports and Exports.
- Linked counts and percentages based on actual cross-tab relationships.
- Clearly identified directional denominators.
- Reset behavior.
- Access to every supported country and gateway.

Use the previous calendar year and current year applicable to each analysis. Do not hard-code 2025 and 2026 into the permanent template.

Do not add a comparable-prior-YTD view, historical comparison panel or other functionality unless requested.

Never present Full Year versus YTD as a like-for-like growth rate or annualize YTD.

### 3. Account-specific data integrity

Use only the target account's AIOS-authorized intelligence.

Never carry over any of these Aptar-specific items:

- Numerical values.
- Countries, gateways or routes.
- Conclusions or commercial recommendations.
- Relationship statuses or classifications.
- Reporting periods or source limitations.

Use AIOS-supplied country × gateway × mode × direction × period cross-tabs for linked filtering.

Deterministic filtering, summation and display-percentage calculations are permitted when supported by the supplied data and defined denominators.

Do not infer missing relationships, estimate unsupported figures, generate account classifications or create new business interpretations.

Maintain separate Import and Export populations. Do not imply linkage between Import origins and Export destinations.

Preserve composite country values and source limitations according to AIOS instructions. Do not silently split, merge, deduplicate or normalize source values.

Preserve the AIOS source distinctions:

- PJ Facts
- Arcatek Facts
- Akzent Facts
- AIOS Calculations
- AIOS Interpretations
- AIOS-Enriched Data
- Discovery Validation

Use "Shipments" consistently. English is the default business-facing language for all LEAD dashboards, following the approved Aptar template. Use Spanish only when the user explicitly requests it. Do not ask the user to choose a language for each LEAD.

### 4. Missing or unsupported intelligence

If required intelligence is missing:

- Identify the exact missing dataset or relationship.
- Preserve the approved structure.
- Clearly mark or disable the affected unsupported functionality.
- Complete independent work supported by available intelligence.
- Report the unresolved gap.

Do not invent data, silently remove components or represent unsupported functionality as complete.

Confirmed zero activity and unavailable data must remain distinguishable.

### 5. LEAD and CLIENT separation

Apply this standard only to accounts explicitly designated as LEAD.

Do not reclassify CLIENT accounts. CLIENT accounts follow the separate **Permanent CLIENT Template** below (Doga México Componentes reference), which shares this visual architecture.

Account classification, commercial relationship and service relationship remain distinct concepts. Missing internal data does not establish zero captured business.

### 6. Exceptional improvement proposals

The approved Aptar template remains the default.

You may recommend an exceptional design or interaction improvement only when it offers a substantial, concrete benefit to at least one of:

- Commercial understanding.
- Analytical clarity.
- Usability.
- Decision-making.

Cosmetic preference, novelty or a different aesthetic alone does not justify a proposal.

Complete the requested work using the approved template first. Present optional improvement proposals at the end; do not interrupt or delay the requested implementation.

Each proposal must briefly state:

- The specific change.
- The concrete benefit compared with the approved template.
- The affected components.
- Any meaningful tradeoff.

Provide a small mockup or preview when practical. Keep it separate from the working `index.html`.

Do not implement the proposed deviation before explicit user approval.

Approval for one account applies only to that account. Do not extend it to all LEADs or change the permanent template unless the user explicitly approves that broader scope.

If no substantial improvement is identified, omit proposals entirely.

### 7. Final verification for every LEAD

Compare the completed target account against the approved Aptar reference. Verify:

- Structural and visual consistency.
- Correct target-account intelligence.
- Correct periods and YTD cutoff.
- Working filters and accurate directional denominators.
- Access to all supported countries and gateways.
- Visible material source limitations.
- No inherited Aptar-specific intelligence.
- No duplicate target account or analytical content.
- Unrelated accounts and shared functionality preserved.

Actually test implemented controls before claiming they work.

Report unresolved failures clearly. Do not claim implementation is complete while required checks remain unresolved.

### 8. Instruction precedence

Explicit user instructions may override this standard for a specified task.

A task-specific exception does not permanently change the standard unless the user explicitly requests that change.

## Permanent CLIENT Template (Doga México Componentes reference)

Established 2026-10-11 at the user's request. It governs accounts **explicitly designated as CLIENT** in this repository. LEAD accounts keep the Aptar template above. Both templates share one visual architecture; the CLIENT template adds a commercial layer that appears only in Seller View.

### Approved reference

- **Approved reference commit:** `04bd7267e15d80c432342babdcda05be9f35b491`, "DOGA CLIENT reference — wallet hierarchy, Matrix fields, $ only, provenance; view-aware export", committed 2026-10-11 00:01 −06:00.
  - When this was recorded, the commit existed locally and was **not yet pushed**: `origin/main` was at `4c146e3`. The user pushes manually.
  - Read the reference with `git show 04bd726:index.html`.
- **Audit status when recorded:** passed.
  - Lead / Client View leak audit on the exported file (text, attributes and scripts): no commercial values, fields, internal blocks or "PJ".
  - Protected 2025 record byte-identical.
  - Unrelated accounts and the Aptar reference byte-identical.
  - Export tested standalone for Doga (both views), Aptar (both views) and BRAHM (no view selector).
  - No console errors; 375 px and print checked.
- **Locating Doga inside `index.html`:**
  - **Scoped CSS:** the block starting `/* DOGA MEXICO COMPONENTES — Account Brief 2.0 (#view-doga only).`. It is a re-scoped copy of the Aptar CSS (`#view-doga`, `.ap2-` classes) plus the CLIENT chart rules, and ends right before `/* DOGA MEXICO COMPONENTES — legacy dga- components`. The legacy block is kept only for the preserved 2025 card.
  - **View markup:** from `<!-- ══ DOGA MEXICO COMPONENTES VIEW · Account Brief 2.0` to the next `<!-- ══ SERVICIOS AGREGADOS DE ENERGÍA VIEW ══ -->`. The root element is `<div id="view-doga" class="view" data-ap2-mode="seller">`.
  - **IDs:** element IDs use the account prefix `dg2-` (`#dg2-net`, `#dg2-s1` … `#dg2-s8`). Aptar's view uses `ap2-` IDs in the same document, so every CLIENT built on this template needs its own unique ID prefix; classes stay `ap2-`.
  - **Sections:**
    - Shared: `#dg2-s1` Network, `#dg2-s2` Profile, `#dg2-s3` Core corridors, `#dg2-s4` What changed, `#dg2-s5` Customs footprint, `#dg2-s6` Where coordination matters.
    - Seller View only: `#dg2-s7` Captured business, `#dg2-s8` Seller desk.
  - **Other surfaces:** home account card (`<!-- DOGA Mexico Componentes SA de CV -->`), portfolio table row, `ACCOUNTS` entry (`id:'view-doga'`), `D2_FACTS["view-doga"]` and the `ARCATEK_REGISTRY` wallet entry.

### 1. Mandatory template for CLIENTs

For every future account **explicitly designated as CLIENT**:

- Apply the same work rules as LEAD section 1: existing `index.html`, target account only, replace obsolete content rather than duplicating it, no standalone dashboard unless requested.
- Use the Doga implementation as the structural and visual template: the Aptar sections 01–06 and their components, the network and its filters, typography, responsive and print behavior.
- LEAD sections 2, 3, 4, 6 and 8 apply unchanged.
  - Read "Aptar-specific items" in section 3 as "Doga-specific items" as well.
  - The network keeps period, direction, mode, country and gateway filters for the previous full calendar year and the current YTD, with separate directional denominators.

**Store architecture and rules, never values.** Doga's figures, dates, periods, wallets, relationship statuses and its currency presentation are Doga intelligence, not defaults for other CLIENTs.

### 2. Two presentation views

- **Lead / Client View** (`data-ap2-mode="prospect"`) keeps the complete operating intelligence: network, countries, gateways, modes, Trading Partners and facilities, complete Core Routes, HS with AIOS-authorized descriptions, observed patents and regimes, historical intelligence and Exact-Route Persistence, operational AIOS Interpretations, and the material source limitations in each section's footnotes.
  - It shows no "PJ": the label is "Trade Records" (or "TR" where space is tight).
- **Seller View** adds the commercial layer, and only Seller View shows it:
  - service relationships;
  - Captured Business, Shipments and reported Profit;
  - monthly and cumulative performance;
  - supported historical comparisons;
  - Logistics and Customs Wallets per service, and their whitespace;
  - commercial hypotheses, the Seller Discovery Guide and the Account Matrix.
- Every commercial element sits inside `.ap2-internal`: cards, tables, charts, tooltips (`<title>`), expandable details, lane clauses and navigation links. Nothing commercial may sit in shared markup, attributes or scripts.
- The views are presentation, not access control.
- Doga remains a CLIENT in both views; the views never change classification.

### 3. CLIENT commercial layer (placement)

- **First Seller block, under the hero:**
  - an 8-card status band: relationship, each service, classification, Captured Business, Profit, Logistics Wallet, Customs Wallet;
  - a same-window comparison of captured Shipments and Profit against the prior year;
  - the cumulative current-year Profit against the prior-year total, as a context line, not a growth rate;
  - monthly reported Profit;
  - monthly captured Shipments as a line over a shaded area of PJ visible records.
- **Short amber "Internal" notes** inside the shared sections where a commercial fact belongs next to the operating fact.
- **Section 07 Captured business:** windows, modality, internal code lanes, the wallet references, Logistics and Customs whitespace kept separate, and the preserved prior-year record.
- **Section 08 Seller desk:** commercial direction, Discovery Guide, guardrails, source scope, unsupported modules and the Account Matrix.
- Each commercial figure has one primary home. The hero band summarizes and links to it.

### 4. Protected history

- Existing prior-year information, both PJ and AKZENT, stays exactly as it is: records, figures, metrics, descriptions and presentation. Doga's 2025 card is carried byte-for-byte and asserted by the build.
- Add the current year alongside it. Replace a current-year value only when AIOS explicitly supersedes it.
- A preserved total may serve as a contextual reference line. Say so plainly, together with the fact that the record was not recalculated or modified.
- State the provenance of every comparison: which AIOS package and date supplied it.

### 5. Wallets, figures and currency

- Show finalized AIOS values. Percentages are rounded once from the supplied numerator and denominator (44 / 87 → 50.57%), never re-rounded from a value AIOS already rounded.
- Keep wallet definitions explicit and separate:
  - A primary Logistics Wallet must name its scope and period; at Doga that is Imports January–August, 37 / 41.
  - Any aggregate reference must state its own periods and units; at Doga that is 38 internal operations January–September / 87 PJ records with August cutoffs.
  - The Customs Shared Wallet is a separate measure.
- Label Provisional wallets as Provisional. Flag source-count references above 100%; never cap them. Show no point where the denominator is unavailable.
- Currency presentation follows what the user confirms for each account (Doga: "$", confirmed 2026-10-10, written without "USD"). Remove contradictory currency states.
- Service relationships follow the latest authorized source.
  - Patent 3468 / 1930 visible ⇒ Arcatek Customs Confirmed Client, per the Akzent rule of 2026-09-19.
  - Correct the Account Matrix fields themselves; "superseded" notes are not enough.

### 6. Shareable export (both templates)

- "Export This Account" exports the account and the view on screen, and carries the active network filters and the open country tab.
- From Lead / Client View the file is generated without any `.ap2-internal` content, "PJ" label or view toggle, with the suffix `_Lead-Client-View.html`.
- Before handing a shareable file over, audit it: text, attributes and scripts must hold no commercial values or fields.
- Both reference scripts (Aptar `230fdf8`, Doga `04bd726`) restore the saved network selection. Every new account built on either template must keep that line in its network script.

### 7. Final verification for every CLIENT

Before reporting completion, verify:

- **Consistency:** header, status band, charts, tables, notes and Account Matrix all agree.
- **Two views:** Lead / Client View and the exported shareable file contain no commercial information, including tooltips, details and print.
- **Filters:** periods and directional denominators are correct.
- **History:** the preserved prior-year record is unchanged.
- **Scope:** unrelated accounts and shared functionality are preserved; export works for at least one other account with and without a view selector.
- **Prototype first:** substantial changes to the standard go to a prototype or preview outside production first, with user approval before production and before this file changes.
