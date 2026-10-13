# AIOS Dashboard — Repository Instructions

## Permanent LEAD Template (Aptar Querétaro reference)

Established 2026-10-10 at the user's request. This standard governs future work in this repository when these instructions are loaded. It does not apply outside this repository.

### Approved reference

- **Repository:** `/Users/patriciojacobsernagarza/Documents/GitHub/akzent-aios-dashboard`
- **Dashboard file:** `index.html`, the multi-account dashboard at the repository root.
- **Approved reference commit:** `230fdf80b1a3acdbdf90945450de84f98690ea42`, "Aptar Querétaro — exported file keeps the network filter selection", committed 2026-10-11 00:06 −06:00 with the user's approval.
  - It equals the original approved version `6b556fc` (2026-10-10) plus one line in the network script, which reads the saved filter selection when an exported file opens. There is no visual or data change. Verified 2026-10-11: the Aptar CSS is byte-identical to `6b556fc`, and the Aptar view differs from it by exactly that line.
  - Pushed: `origin/main` contained it at `5ddb2c3` (verified 2026-10-11). Pushes from Claude sessions fail, so the user pushes manually.
  - Read the reference with `git show 230fdf8:index.html`.
  - Use this reference until the user explicitly replaces it.
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

Deterministic filtering, summation and display-percentage calculations are permitted when supported by the supplied data and defined denominators. Keep them narrowly scoped to the network filters and display formatting; do not extend them into new business analysis.

AIOS supplies the finalized business values, interpretations, classifications and individual HS descriptions. Claude implements presentation and functionality only.

Do not infer missing relationships, estimate unsupported figures, generate account classifications or create new business interpretations.

Keep narrative, charts, tables, source notes, embedded datasets and the Account Matrix consistent with one another. When a value changes, correct the canonical field everywhere: the view, the Account Matrix, `D2_FACTS`, the home card, the portfolio row and the `ACCOUNTS` entry. Never leave a stale value with an override footnote.

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

Use "Shipments" consistently. English is the default business-facing language for all LEAD and CLIENT dashboards and reports, following the approved Aptar and Doga templates. Use Spanish only when the user explicitly requests it. Do not ask the user to choose a language for each account. Write future Claude implementation prompts in English.

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

The approved Aptar template remains the default for LEADs, and the Doga template for CLIENTs.

Flag immediately, with location and consequence:

- Evident data contradictions.
- Misleading presentation.
- Missing intelligence.
- Functional defects.

Routine fixes within the authorized scope may proceed. Materially changing the permanent architecture or analytical scope requires approval first.

You may recommend an exceptional design or interaction improvement only when it offers a substantial, concrete benefit to at least one of:

- Commercial understanding.
- Analytical clarity.
- Usability.
- Decision-making.

Cosmetic preference, novelty or a different aesthetic alone does not justify a proposal.

Complete the requested work using the approved template first. Present optional improvement proposals at the end; do not interrupt or delay the requested implementation.

Each proposal must briefly state:

- The specific change, kept to the smallest necessary.
- The concrete benefit compared with the approved template.
- The affected components.
- The data it requires.
- Any meaningful tradeoff.

Provide a small mockup or preview when practical. Keep it separate from the working `index.html`.

Do not implement the proposed deviation before explicit user approval.

Approval for one account applies only to that account. Do not extend it to all LEADs or CLIENTs, or change a permanent template, unless the user explicitly approves that broader scope. After an approval, state which parts are reusable standard changes and which are account-specific adaptations.

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

Report unresolved failures clearly. Do not claim implementation is complete while required checks remain unresolved. Distinguish executed checks from unverified claims. Never record an unapproved or unaudited candidate as a permanent reference.

### 8. Instruction precedence

Explicit user instructions may override this standard for a specified task.

A task-specific exception does not permanently change the standard unless the user explicitly requests that change.

## Permanent CLIENT Template (Doga México Componentes reference)

Established 2026-10-11 at the user's request. It governs accounts **explicitly designated as CLIENT** in this repository. LEAD accounts keep the Aptar template above. Both templates share one visual architecture; the CLIENT template adds a commercial layer that appears only in Seller View.

### Approved reference

- **Approved reference commit:** `04bd7267e15d80c432342babdcda05be9f35b491`, "DOGA CLIENT reference — wallet hierarchy, Matrix fields, $ only, provenance; view-aware export", committed 2026-10-11 00:01 −06:00.
  - Approved by the user on 2026-10-11 after review of the full-dashboard preview.
  - Pushed: `origin/main` contained it at `5ddb2c3` (verified 2026-10-11). The Doga view, its scoped CSS and the shared export function in `index.html` were byte-identical to `04bd726` at that point. The only later change, `230fdf8`, touched Aptar.
  - Read the reference with `git show 04bd726:index.html`.
  - Use this reference until the user explicitly replaces it. Earlier Doga production versions (`674fd14`, `9853cdb` through `4c146e3`) and the preview files are not references.
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
- Use the Doga implementation as the structural and visual template. Preserve its section order, navigation, typography, components, network visualization, filters, progressive disclosure (expandable details), responsive behavior and print behavior.
- Adapt to the target account's supported information. Never copy reference-account facts, and never omit required AIOS intelligence.
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
- The separation also holds in print and in exports.
- The views are presentation, not access control.
- Doga remains a CLIENT in both views; the views never change classification.

### 3. CLIENT commercial layer (placement)

- **First Seller block, under the hero:**
  - an 8-card status band: relationship, each service, classification, Captured Business, Profit, Logistics Wallet, Customs Wallet;
  - a same-window comparison of captured Shipments and Profit against the prior year, always headlined by the full current-YTD values (see **Template v2 design standard** below);
  - the cumulative current-year Profit chart against the prior-year total line, with no caption narrative;
  - monthly reported Profit;
  - monthly captured Shipments as a line over a shaded area of PJ visible records, with the cumulative directional wallet.
- **Only what AIOS supplies.** Include monthly and cumulative Shipments, Profit, directional wallets and equivalent-period comparisons only when AIOS supplies them.
  - Keep their source cutoffs, denominators, Provisional statuses, missing-data gaps and above-100% warnings.
  - If a component's data is missing, follow LEAD section 4. Never derive a series or show a placeholder.
- **Short amber "Internal" notes** inside the shared sections where a commercial fact belongs next to the operating fact.
- **Section 07 Captured business:** windows, modality, internal code lanes, the wallet references, Logistics and Customs whitespace kept separate, and the preserved prior-year record.
- **Section 08 Seller desk:** commercial direction, Discovery Guide, guardrails, source scope, unsupported modules and the Account Matrix.
- Each commercial figure has one primary home. The hero band summarizes and links to it.

### 4. Protected history

- Existing prior-year information, both PJ and AKZENT, stays exactly as it is: records, figures, metrics, descriptions and presentation. Doga's 2025 card is carried byte-for-byte and asserted by the build.
- Add authorized new-year intelligence separately, alongside it. Replace an existing value only when the latest AIOS package explicitly supersedes it and the user's preservation instructions permit it.
- Growth comparisons require equivalent periods. A previous full-year total may serve as a clearly labelled contextual benchmark, never as the base of a growth rate against an incomplete YTD.
- When a preserved total is used that way, the chart label names it ("2025 full year"); no explanatory paragraph is added.
- Record the provenance of every comparison (AIOS package and date, or the PJ calculation) in the commit and the build notes. On the page, a one-line source tag appears only for values not supplied by AIOS. Provenance paragraphs were removed at the user's request on 2026-10-12.

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

- "Export This Account" exports only the active account in the selected view. It carries the active network filters and the open country tab, and the file must work standalone.
- From Lead / Client View, the file physically excludes every `.ap2-internal` element, the "PJ" labels and the Seller View switch from its markup, attributes and scripts. The filename gets the suffix `_Lead-Client-View.html`.
- From Seller View, the file retains the authorized Seller content.
- Before handing a shareable file over, audit it: text, attributes and scripts must hold no commercial values or fields.
- Any change to the shared export code requires regression checks: Aptar in both views, plus at least one account without a view selector (for example BRAHM).
- Both reference scripts (Aptar `230fdf8`, Doga `04bd726`) restore the saved network selection. Every new account built on either template must keep that line in its network script.

### 7. Final verification for every CLIENT

Before reporting completion, verify:

- **Values:** source values, periods, cutoffs and denominators match the AIOS package.
- **Consistency:** header, status band, charts, tables, notes, datasets and Account Matrix all agree.
- **Two views:** Lead / Client View and the exported shareable file contain no commercial information, including tooltips, details and print.
- **Interface:** filters and directional denominators are correct; navigation, responsive behavior and print work.
- **Export:** the file opens standalone and keeps the selection.
- **History:** the preserved prior-year record is unchanged.
- **Scope:** unrelated accounts and shared functionality are preserved; export works for at least one other account with and without a view selector.
- **Reporting:** state which checks were executed and which remain unverified. Never record an unapproved or unaudited candidate as the reference.
- **Prototype first:** substantial changes to the standard go to a prototype or preview outside production first, with user approval before production and before this file changes.

## Template v2 Design Standard (all LEAD and CLIENT accounts)

Approved by the user on 2026-10-12 ("every dashboard must always carry this"). It applies to every future LEAD and CLIENT account built on either template, and to existing accounts when they are rebuilt or refreshed. Where it conflicts with the Aptar or Doga reference, this section wins.

### Design reference

- **Reference:** the "Doga 2 (New)" view in `index.html` at commit `8d1341d` (`#view-doga2`, IDs `dg3-`). Read it with `git show 8d1341d:index.html`.
- The Doga 2 CSS is the block starting `/* ══ DOGA 2 (NEW) — design-comparison copy`, at the end of the main `<style>`.
- The original `#view-doga` remains the 04bd726 version until the user approves replacing it. The change log is `prototypes/client-template-v2-CHANGES.md`, which is local and git-excluded.

### Structure and design rules

1. **No narrative paragraphs** under charts or comparison cards. Keep one Observed Operational Signal + AIOS Interpretation line where AIOS supplies it.
2. **Captured-business comparison card (CLIENT, Seller View):**
   - It always headlines the **full current-YTD** values: Shipments by modality, Profit final, Profit per Shipment.
   - The prior-year side must use the same cutoff, supplied by AIOS.
   - If that side is missing, show "<prior year> same window · pending AIOS", grey, with no rate.
   - Never show a current-year Profit with an older cutoff in the same section, and never repeat a headline value as a bar row.
3. **Core corridors (section 03):**
   - Coverage tiles, then the collapsible frequency tables only: `details.ap2-more` with `table.ap2-t.routes`. No route-card lists.
   - Current-YTD tables are open by default; prior-year tables are collapsed.
4. **Customs footprint (section 05):**
   - **Seller-only summary band** (`.ap2-cxsum.ap2-internal`) between the section header and the charts, with three cards:
     - Customs Shared Wallet, current YTD (n / N, by direction);
     - comparable same-window change in pp (prior-year % → current %, own-patent Shipments n → n with % change, by direction);
     - Other-Patent Shipments, current YTD, with the AIOS overlap value.
   - **Patent charts** (`.ap2-cx`): one stacked bar of patent totals, a legend with count and %, and one stacked bar per gateway.
     - Generate them from the gateway × patent cross-tab and assert that the column sums equal the supplied totals.
     - Lead / Client View uses neutral navy shades.
     - Seller View shows own patents (3468 / 1930, class `ar`) in teal `#0e7490` and other patents in grey, plus an `.ap2-internal` "Arcatek" legend chip and an "Arcatek 3468 · n / N · %" header pill per direction.
   - **Comparable customs change:** if AIOS does not supply it, compute it from the account's PJ files with own patents {3468, 1930} and the current per-direction cutoffs, applied to both years.
     - Do this only after the same method reproduces AIOS's current-YTD and prior-full-year wallet values exactly.
     - Label it "Calculated from PJ records · pending AIOS confirmation".
     - Captured Profit comparisons cannot be computed from PJ: they stay pending AIOS.
5. **Where coordination matters (section 06):** one corridor board (`.ap2-board`), grouped Imports / Exports, with one collapsible row per corridor.
   - **Row columns:**
     - Volume;
     - Corridor (mode + key gateway or partner);
     - Patent chips (own patents in teal in Seller View only);
     - Akzent today (Seller only, amber, no Profit; Profit's home is section 07);
     - Validate-with-the-client chips (Seller-only questions in amber).
   - **Expanded row:** the AIOS paragraphs verbatim.
   - **No repetition:** Discovery Validation appears once, as chips, and source tags appear only inside the expanded row.

### Commercial-layer gating (all accounts)

- If the user supplies **no Akzent internal data** and the package shows **no Arcatek evidence** (no own patent 3468 / 1930 visible, no Arcatek registry entry), the account carries **no CLIENT or commercial layer**. That means no:
  - CLIENT or relationship labels;
  - status band;
  - Captured Business or Profit;
  - Logistics or Customs Wallets;
  - section 07, Arcatek pills or highlights, or the customs summary band;
  - "Akzent today" column.
- Build it on the operational sections only.
- Each commercial element appears only when its own source exists:
  - Akzent internal data → logistics capture, Profit and the Logistics Wallet;
  - Arcatek / own-patent evidence → the customs wallet and the own-patent highlights.
- Missing data still never means zero captured business, and the relationship-governance rule (own patent visible ⇒ Arcatek Customs Confirmed Client) still applies.

### Data to request from AIOS

When a package lacks any of these, ask the user to add the standard request block to the AIOS prompt:

- the captured-business same-window comparison;
- the Customs Shared Wallet same-window comparison;
- the gateway × patent cross-tab for both periods;
- structured corridor records (short Discovery items, a one-sentence interpretation);
- the monthly series.

The block was given to the user on 2026-10-12.

## Visible Panjiva Volume (TEU) standard (all accounts)

Established 2026-10-13 at the user's request. It applies to every Arcatek account, every future LEAD and CLIENT, and every refresh. TEU is mandatory in **both** the individual account view and the Arcatek Dashboard.

### Source and calculation

- **Field:** sum the original Panjiva column `Volume (TEU)` over retained source rows. Never derive TEU from Shipments, weight, customs entries, freight value, quantity, container counts, modal percentages, narrative text or another account.
- **Precision:** a blank cell is missing, never zero. Keep full source precision and round to 2 decimals only for display.
- **Universe:** the retained universe must equal the current AIOS universe for that account.
  - Verify it by reproducing the AIOS Shipment counts per direction and period.
  - Apply an account-specific exclusion only when it reproduces the AIOS counts (2026-10-13: Siete Leguas Exports drop the 20 Brp Queretaro shipper rows; BRAHM keeps only BRAHM-as-consignee/shipper rows).
  - Report every exclusion.
  - Never merge affiliates or name variants.
  - Never add an older file version to a newer one.
- **Direction:** take it from the file itself (`Mexico Imports Shipments` / `Mexico Exports Shipments`).
- **Periods:** use `Shipment Date`, never the file-generation date.
  - Compute FY (previous calendar year), current YTD (per-direction cutoff = latest Shipment Date), a comparable prior-year YTD (same day-month as each direction's cutoff), and the complete universe (methodology only).
  - Never annualize. Never compare FY with YTD as growth.
- **Modes:** keep the original `Transport Method`, then normalize.
  - Mapping: Maritime/Ocean → Maritime; Air → Air; Truck/Road → Truck; Rail → Rail; Double Stack Rail → Double Stack Rail; blank/Unknown → Unknown; anything else → Other.
  - Land = Truck + Rail + Double Stack Rail, with the sub-breakdown kept.
  - Unknown and Other are never redistributed.
  - A mode whose rows are all blank reads "No TEU data", not 0.00.
- **Reconciliation:** at full precision, check four things:
  - each direction's modes equal its total;
  - Imports + Exports equal the account sum;
  - the combined modes equal the account sum;
  - Land equals Truck + Rail + Double Stack Rail.
  - FY + YTD must equal the universe.

### Status (per direction, headline = current YTD)

- **Available:** both directions supplied, 100% of rows populated.
- **Available · partial coverage:** some rows are blank. Show the populated / total rows and disclose the missing count.
- **Insufficient coverage to total:** coverage is below 50%.
  - Show the value only as "Visible TEU in populated rows".
  - Show no account total.
- **Directional source not supplied:** no file for that direction. It is never zero, and there is no account total.

### Review flags

The visible text is "⚑ Double-click and review", and each flag states the issue, scope, period, source and whether the value stays usable.

Raise a flag for any of these:

- **Coverage:** below 95%, or a direction not supplied.
- **Cutoff gap:** the Import and Export YTD cutoffs differ by more than 7 days.
- **Unknown / Other share:** 20% or more of YTD TEU.
- **Entity scope:** 10% or more of a direction's rows name the account only as the counterparty.
- **Mirrored pairs:** Import and Export rows share the same date and identical TEU, and they make up 5% or more of YTD TEU.
- **Concentration:** a single record is 25% or more of a direction-period, or 100 TEU or more.
- **Source versions:** newer and older source versions exist.
- **Reconciliation:** any reconciliation failure.
- **Relationship:** the Arcatek relationship is not Confirmed. The dashboard derives this flag live from the registry.

Missing data uses the pending statuses, never a flag.

### Architecture

- **Record:** one TEU record per account, schema `aios-teu/1`, embedded in the account view as `<script type="application/json" class="ateu-record" data-view="view-…">`.
  - It is the single TEU source.
  - It travels with exports.
  - In ap2 views it sits inside `.ap2-internal`.
- **View blocks:** four blocks are generated from the record and inserted between chapters.
  - `#ateu-<id>-sum` sits after the Executive chapter, `-modes` after Network, `-hist` after Historical, `-src` after Historical (BRAHM: after Data Quality).
  - Their figures carry `data-ateu` paths. `AIOS_TEU.verify()` checks every displayed figure against the record on load and logs `console.error` on any mismatch.
- **Dashboard:** the Arcatek Dashboard reads `AIOS_TEU.record(view)`, which provides the detail panel, the TEU overview tiles and `AIOS_TEU.portfolio()`.
  - `portfolio()` produces the additive current-YTD total.
  - It includes only account-directions that are supplied, have 95% or more coverage, reconcile, carry no entity-scope / mirrored-pair / source-version flag, and have a cutoff within 7 days before the most common cutoff.
  - It lists every excluded account-direction with its reason.
- **Styling:** the shared CSS (`.ateu-*`) sits at the end of the first `<style>`, so single-account exports carry it.
- **Pending accounts:** an account without a record shows the reference preview (no figures), "Pending", and the activation requirement.
- **Language:** English labels, per the language rule above.

The 2026-10-13 build scripts (engine, block generator, splice) were kept in that session's scratchpad. Reproduce them from this specification when adding a new account.
