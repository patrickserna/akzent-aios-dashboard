# AIOS Dashboard — Repository Instructions

## Permanent LEAD Template (Aptar Querétaro reference)

Established 2026-10-10 at the user's request. This standard governs future work in this repository when these instructions are loaded. It does not apply outside this repository.

### Approved reference

- **Repository:** `/Users/patriciojacobsernagarza/Documents/GitHub/akzent-aios-dashboard`
- **Dashboard file:** `index.html`, the multi-account dashboard at the repository root.
- **Approved reference commit:** `6b556fc6a0b64fae6e7ab30f5c0a6c844fd67bbc`, "Aptar Querétaro — period button label "2026 YTD"", committed 2026-10-10 19:53 −06:00.
  - The working tree matched this commit exactly when it was recorded.
  - When this was recorded, the commit existed locally and was **not yet pushed**: `origin/main` was at `f0b683b`. Pushes from Claude sessions fail, so the user pushes manually.
  - Read the reference with `git show 6b556fc:index.html`.
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

Do not reclassify CLIENT accounts or apply this template to them automatically. A separate CLIENT template will be approved later.

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
