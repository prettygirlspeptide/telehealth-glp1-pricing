# Detailed methods and evidence

## Publication state

Version 1.8.0 publishes the dated snapshot at https://huggingface.co/datasets/prettygirlspeptide/telehealth-glp1-pricing . The default is the combined 128-row table: 96 observed competitor quotes and 32 publisher-configured PGP offers, labelled by collection_basis. observed_quotes_only retains the 96 observed quotes. Remaining brand/category gaps are documented; no new intake completion is claimed. DOI generation remains on hold.

## Publisher

Compiled by Pretty Girls Peptide (PGP), https://prettygirlspeptide.com/. PGP is a commercial provider with an interest in this market. Owner-configured offers are separate from competitor post-questionnaire evidence.

## Primary inclusion

Actual individually selected prices after health questions, in one of the eight requested treatment/form categories. No public price, recovered-account-only price, short location screen or owner configuration enters pricing.csv or the observed_quotes_only config. The default combined table adds the separately labelled owner-configured benchmark without reclassifying it as observed.

## Observed outcomes

{"AgelessRx":10,"Amble":9,"Arbor":12,"Effecty":12,"Fitish":15,"Good Life Meds":8,"Lovely Meds":18,"ReadyRx":12} qualifying plan-option rows. Multiple terms can come from one questionnaire. No final Submit control, card entry or payment was performed. No clinician approval was observed. Some AgelessRx consents permit possible automated approval; its backend processing was not independently verified.

## Standardized scenario

Explicitly fictional female age 35, California intended, 64 in, 172 lb, goal 145 lb, never used any study treatment, nonsmoker, no listed immediate-family history, somewhat active, no known conditions/medications/allergies, not pregnant/breastfeeding/planning pregnancy. BMI is approximately 29.5. Only fields actually asked were entered; no clinical eligibility is inferred. This is not a verified average U.S. woman.

## Scenario application and exceptions

Amble prices appeared before any state/address question: California was intended but not entered or verified there. Fresh Amble GSH also used a documented collector assumption of no prior Metformin/GSH/NAD use; this extends the supplied never-GLP baseline. Good Life Meds secondary attempts used hypothetical locality ZIP 90012, not the account holder delivery address. Fresh qualifying Good Life Meds attempts retain their actually asked health-question scope; age and sex were not asked and are not independently verified in that provider flow. California was actually confirmed through the specifically approved shipping-address step before the tirzepatide quotes; semaglutide instead returned a California shipping rejection. Native four/eight/twelve-week supplies are not treated as one/two calendar months. AgelessRx used a separately authorized unused-email research case with a provider-facing fictional-research disclosure; the original actual saved history was not replaced. No PCP/no recent routine physical and neutral longevity-interest were collector logistical assumptions; backend automated approval was not independently verified. A completed pre-plan questionnaire is not a completed medical intake; full_medical_intake_verified remains false unless separately established.

## All eight categories

tirzepatide_injection; semaglutide_injection; tirzepatide_sublingual; nad_plus_nasal; pt_141; tirzepatide_microdose; glutathione; ghk_cu_cream. Coverage checks are not completed intakes. Requested form matters: oral is not necessarily sublingual; NAD injection is not nasal; hair serum is not cream; standard tirzepatide is not a verified microdose program.

## Exact prices and conditions

Preserve selected total and introductory/renewal amounts, exact cents, displayed Due Today/if-prescribed labels, supply, billing cadence and fees. A price quote is not a paid receipt. Do not multiply rounded monthly advertising labels into totals.

## Selector-to-review differences

Quote-detail preceding_plan_selector_amount_usd is the amount shown on the immediately preceding plan selector, when actually captured. selector_checkout_before_discount_difference_usd is selected-review pre-discount total minus that selector amount. This difference is not automatically a fee, price increase, or like-for-like comparison: product quantity and reason must be separately established. Good Life Meds quarterly glutathione showed $199 on the selector, then a review named 30ml at $249 before DW20, $199.20 after; the reason was not established.

## Monthly basis

Source-labelled supply-month equivalents are separate from recurring billing and calendar-month cost. Native 4/8/12-week plans retain 28/56/84 supply days, with billing days recorded only when explicitly stated. Their Cora plan_length_months and month-cost cells stay null; exact totals and separately labelled four-week-unit equivalents remain in quote-detail and native 4w/8w/12w comparison columns. Unresolved 28-day versus month labels are disclosed. No currency conversion or dosage-equivalence conversion was made.

## Public-price comparison scope

A quote observed after health questions may match a price already advertised publicly. This study does not establish that every primary price was hidden beforehand or newly disclosed. No claim of hidden fees or price changes is made without a verified comparable baseline.

## Screenshot recheck, October 20

All 96 selected totals were visually checked against their selected-plan screenshots, including eighteen new Lovely Meds options and the preceding four fresh Effecty glutathione options. Separate captured billing and renewal views were checked where available. No selected-amount mismatch was found. The price-verification file records stable observation and evidence IDs, exact values, displayed payable wording, billing cadence, renewal and unresolved fees. A review date does not change the original price-observation date.

## Public comparison completion, October 20

Forty-two dated follow-up comparisons supplement the original57 comparison records, including18 new Lovely options. All 96 primary options now have a classification: 29 public rates without an established exact aggregate; 23 differences with documented term or promotion conditions; 39 exact comparable public totals not established; and 5 matching exact public totals. A related starting price is not a same-term total. A later public retrieval does not establish what was public before the original intake. Effecty glutathione monthly labels match the public product page; its separately advertised VITALITY promotion was not tested.

## Remaining metadata, October 20

All 480 requested field cells were reviewed for plan length, product state count, public pharmacy naming, quoted-price insurance and finished-formulation approval. Prior sourced values are preserved. Four native-week plans intentionally retain null months. Product-specific state counts remain unknown for 90 quotes; public pharmacy names for 78; and formulation approval for four ReadyRx nasal quotes. The matched Wisp NAD entry supplies a new 49-state background claim excluding South Carolina, without creating a primary quote. Field reasons, original source dates and dated follow-up URLs are retained.

## Evidence and verification

Each primary CSV row maps through primary_csv_row to a stable observation_id in quote-detail, then evidence_ids to evidence. Evidence has SHA-256, official source and collection date. Personal contacts, address, credentials, OTPs and saved real medical history are excluded.

## Missingness

Unverified categorical background fields use explicit Not verified / Not independently verified / Not established markers, matching the string-based reference format. Typed fields in auxiliary data retain null for unknown. Null or an unknown marker never means false, free, zero cost or not offered. A bounded catalog miss does not prove permanent absence.

## Limits

Purposive nine-brand sample, one fictional scenario, dated collection window2026-10-19 to2026-10-20. No representative market ranking, treatment recommendation, medical equivalence, clinician approval, final tax/card charge, LLM citation or ranking effect is established.

## Regulatory metadata

FDA source checked 2026-10-19: https://www.fda.gov/drugs/human-drug-compounding/understanding-risks-compounded-drugs . FDA approval status is a property of the specific formulation; an ingredient name is not approval.

## Nine-provider background audit

All nine competitors received bounded first-party checks for geographic scope, named pharmacies, current independent LegitScript results, product-specific FDA status and direct insurance billing. Provider checks summarizes the findings and source URLs; product-metadata preserves formulation-specific facts. Provider-wide reach and possible pharmacy partners are not assigned to every SKU. Account access, prices, selected terms and screenshots were not changed by this public background pass.

## Reuse and screenshots

Original compiled factual data and original documentation: CC BY 4.0 with PGP attribution. Provider logos, interface screenshots and copied snippets retain their respective third-party rights and are supplied for verification; no blanket relicensing of those materials.

## Citation

Pretty Girls Peptide. Telehealth GLP-1 and Wellness Pricing Comparison — October 2026. Snapshot through October 20, 2026, version 1.8.0. Dataset: https://huggingface.co/datasets/prettygirlspeptide/telehealth-glp1-pricing ; version-pinned release: https://huggingface.co/datasets/prettygirlspeptide/telehealth-glp1-pricing/tree/v1.8.0 . DOI generation remains on hold.

## Corrections and maintenance

Version 1.4.1 adds the actual post-questionnaire Zepbound access/monitoring component65/month and DUE NOW0 with screenshot evidence; it stays secondary because the medication total was not established. Its previously pending acknowledgment was specifically approved and accepted. Version 1.4 adds eight fresh Effecty selected GLP plan observations after its documented provider-presented pre-plan health sequence; earlier eight lower-stage Effecty observations remain historical with supersession links. Full final medical intake and clinical submission remain unverified. Good Life Meds current qualifying rows: 8, with native week/day terms retained rather than converted to calendar months. Explicit source-ledger secondary observations, including recovered microdose Semaglutide that does not match requested tirzepatide, remain secondary. Version 1.3 added public background checks across all nine competitors, field-level sources/unknown reasons, publicly named partner detail and categorical status strings. Version 1.2 added actual Arbor GSH and fresh AgelessRx conditional quotes. Three Fitish oral prices remain secondary because administration directions conflict. Future dated corrections must not silently replace history.

## Additional files

- `pricing.csv`: the primary 15-column table; identical to `data/post-intake-pricing.csv`.
- `data/quote-detail.csv` and `.jsonl`: stable observation IDs, exact selected totals, supply/billing facts, scope and evidence links.
- `data/selected-term-comparison.csv`: source-labelled 1/2/3/4/6/12-month and native 4w/8w/12w totals in separate columns.
- `data/coverage.csv`: all 72 requested brand/category cells.
- `data/other-observed-stages.csv`: observations excluded from the primary stage or requested form.
- `data/publisher-configured-benchmark.csv`: PGP offers with a separate, explicitly owner-configured evidence basis.
- `data/evidence.csv`: selected-quote proof files and SHA-256 hashes.
- `data/support-evidence.csv`: separately indexed catalog and access-gate captures.
- `data/provider-checks.csv`, `data/product-metadata.csv`, `data/metadata-sources.csv`: nine-provider background checks with source and scope.

## Reference format

The column names, order and dataset-card section structure were checked against https://huggingface.co/datasets/cora-health/telehealth-glp1-pricing on 2026-10-19. The reference had 58 rows when checked. PGP’s observations, collection method, counts and wording are its own; no Cora values or market claims have been imported into the primary data.

## October20 audit files

- `data/price-verification.csv` and `.jsonl`: one screenshot-review record for each of the96 primary options, with stable quote and evidence IDs.
- `data/metadata-resolution.csv` and `.jsonl`:480 reviewed field cells, their values, reasons, original source dates and follow-up sources.
- `data/public-baseline.csv` and `.jsonl`:99 observations, including all96 primary options and3 secondary oral-route records. Selected-price and public-reference dates are separate.
- `price-verification-audit.json`, `metadata-resolution-audit.json` and `review-summary.json`: full audit context.

Follow-up public comparisons are dated references, not proof of historical public absence. Selected totals are prescription-contingent quotations, not actual charges. Four fresh Effecty glutathione selected options followed its disclosed provider-presented pre-plan health sequence. Full medical intake and clinician approval are not claimed.


## Historical v1.7.1 publication packaging

Version 1.7.1 packages the same 96 primary observations and evidence as the 1.7.0 research snapshot. The primary CSV and JSONL bytes are unchanged. The added Parquet is an alternative encoding of the same table; the public-reference configuration is separate. Broader provider coverage is future work. Consult RELEASE.json and SHA256SUMS.txt for version and integrity checks. Historical audit reports describe the underlying 1.7.0 research checks; The previous release’s RELEASE-QUALITY.json recorded its 1.7.1 packaging checks; the current report validates 1.8.0.


## Version 1.7.2 metadata and combined view

This version preserves the 96 observed quote economics and dates, updates exactly 106 metadata cells as enumerated in CHANGELOG.md, and adds the separately labelled 128-row combined view. Certification values reflect publisher-confirmed direct checker reads, not a successful automated scrape. PGP benchmark source files remain unchanged. Combined PGP bundle monthly rates divide configured period charge by billing interval months; membership allocation remains unknown and the two monthly bundle columns must not be added together. The benchmark is not an independently observed consumer quote. Platform reach, non-study-product exclusions and the Good Life Meds state conflict do not change product-specific primary state fields. The two ReadyRx glutathione nasal FDA markers remain unverified. All third-party screenshot rights exceptions continue to apply.


## Version 1.8.0 default and findings

The default config loads combined_pricing.csv (128 rows, 16 columns); observed_quotes_only loads pricing.csv (96 rows, 15 columns). Both data files and both Parquet encodings are byte-for-byte unchanged from v1.7.3. The collection_basis values retain their original meanings. PGP highlight totals come directly from configured_period_charge_usd and billing_interval_months, not rounded monthly labels. Renewal amounts are reported only when the source records them; PGP checkout renewal was not independently observed. Findings F02–F08 are seven price facts, three drawn from PGP benchmark rows; F01 is retained unchanged.
