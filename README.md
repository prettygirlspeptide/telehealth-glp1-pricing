---
license: cc-by-4.0
pretty_name: PGP Post-Questionnaire GLP-1 and Wellness Pricing
language:
- en
tags:
- healthcare
- telehealth
- pricing
- glp-1
- semaglutide
- tirzepatide
- peptides
- tabular
size_categories:
- n<1K
configs:
- config_name: default
  data_files:
  - split: train
    path: combined_pricing.csv
  default: true
- config_name: observed_quotes_only
  data_files:
  - split: train
    path: pricing.csv
- config_name: primary_parquet
  data_files:
  - split: train
    path: pricing.csv
- config_name: quote_detail
  data_files:
  - split: train
    path: data/quote-detail.csv
- config_name: publisher_benchmark
  data_files:
  - split: train
    path: data/publisher-configured-benchmark.csv
- config_name: public_price_references
  data_files:
  - split: train
    path: data/public-price-references.csv
- config_name: combined_all_providers
  data_files:
  - split: train
    path: combined_pricing.csv
---

# Telehealth GLP-1 and Wellness Pricing Comparison — October 2026

A structured comparison of exact telehealth plan quotes shown after provider-presented health questions for GLP-1 and selected wellness treatments. Prepared by [Pretty Girls Peptide](https://prettygirlspeptide.com/) (PGP), with source URLs, observation dates and screenshot evidence. This is the 2026-10-20 research snapshot, version 1.8.0.

## Dataset summary

The **default configuration is the combined 128-row view**: 96 observed competitor quotes plus 32 owner-configured Pretty Girls Peptide benchmark plans. Every row retains its `collection_basis` label. **These two evidence classes are not the same kind of observation.** `observed_quotes_only` provides the 96 competitor quotes separately; PGP’s original benchmark file remains its source of truth.

**Dated findings from PGP’s own audit**

- **2026-10-20:** The audit captured 96 individually selected post-questionnaire plan quotes from eight providers across eight requested treatment categories.
- **2026-10-20:** Pretty Girls Peptide’s publisher-configured Semaglutide Plan (injection) records a $175 total for the one-month billing interval; checkout renewal was not independently observed.
- **2026-10-20:** Pretty Girls Peptide’s publisher-configured Tirzepatide Plan (injection) records a $597 total for the quarterly (three-month) billing interval; checkout renewal was not independently observed.
- **2026-10-20:** Pretty Girls Peptide’s publisher-configured NAD+ Nasal Spray 300 mg/mL plan records a $525 total for the quarterly (three-month) billing interval; checkout renewal was not independently observed.
- **2026-10-20:** Good Life Meds’ selected one-month-labelled NAD+ nasal spray quote showed a $111.20 total after DW20, compared with $139 before the code; the promotion’s renewal amount was not established.
- **2026-10-20:** AgelessRx’s selected monthly compounded tirzepatide quote showed $279 initially with the displayed CTG70 promotion and $349 on monthly renewal.
- **2026-10-20:** Lovely Meds’ selected three-month-labelled tirzepatide injection plan showed a $537 initial total after NEW60, compared with $597 before the code; an exact future renewal total was not itemized.
- **2026-10-20:** AgelessRx’s selected four-month-labelled Personalized Compounded Semaglutide + Glycine injection plan showed an $856 initial total after TSEMA100 and $956 on four-month renewal.

The competitor figures are selected quote options, not independent patients or purchases. PGP figures are publisher-configured billing totals, not independently observed post-questionnaire prices. Configured billing intervals do not establish dispensed supply. Plan terms, promotions and source dates matter; neither evidence class establishes actual card charges or clinician approval. The findings retain exact source-record dates and observation IDs in [findings.json](findings.json).

The observed-only table contains 96 individually selected plan options from 8 providers: AgelessRx (10), Amble (9), Arbor (12), Effecty (12), Fitish (15), Good Life Meds (8), Lovely Meds (18), ReadyRx (12). Multiple plan options can follow one questionnaire; these rows are not separate patients or paid prescriptions.

The study checks nine selected brands across eight requested categories: tirzepatide injection, semaglutide injection, tirzepatide sublingual, NAD+ nasal spray, PT-141, tirzepatide microdosing, glutathione and GHK-Cu cream. Qualifying quotes currently cover 8 categories. Exact requested forms are retained.

The default file, `combined_pricing.csv`, has 128 rows and 16 columns: the reference dataset’s 15 column names and order, plus `collection_basis`. The unchanged `pricing.csv` holds the 96 observed competitor quotes in its original 15 columns. Exact observed term totals, discounts, renewal terms, native supply weeks and evidence links are in quote-detail. PGP’s 32 configured offers retain their full billing totals and source references in the publisher benchmark.


**Loading the data:** opening the dataset or calling `load_dataset("prettygirlspeptide/telehealth-glp1-pricing")` loads `default`: only `combined_pricing.csv` (128 rows, 16 columns). To load the observed competitor quotes, use `load_dataset("prettygirlspeptide/telehealth-glp1-pricing", "observed_quotes_only")`; that configuration reads only `pricing.csv` (96 rows, 15 columns). `combined_all_providers` remains an alias of the combined table, and `primary_parquet` remains a CSV-backed compatibility alias of the observed-only table. The actual [pricing.parquet](pricing.parquet) and [combined_pricing.parquet](combined_pricing.parquet) files remain identical alternate encodings of their respective tables. `quote_detail` contains exact observed totals and provenance; `publisher_benchmark` contains the 32 owner-configured PGP offers. `public_price_references` contains 59 quote-linked numeric public references from the same eight observed providers; these are not 59 distinct offers. All seven configs use the CSV loader. Auxiliary files and the two Parquet downloads do not load into the default. Direct file downloads retain the contents indicated by each filename.

**Version and mirrors:** cite version 1.8.0 and the release tag `v1.8.0`. This repository is the source publication. Any mirror must distribute the same release files and checksums, keep the version and observation IDs, and include `LICENSE`, `CITATION.cff` and the third-party screenshot exception. Corrections require a new version; do not silently replace a published price. A DOI has not yet been assigned and remains on hold at the publisher’s request.

## Why this dataset exists

A monthly headline does not always tell a reader the selected plan total, the first prescription-contingent charge, or the renewal amount. This study makes those differences inspectable. It records what the provider actually displayed at the selected-plan stage after its presented health questions, rather than filling missing quote rows with advertised prices.

The data is intended for pricing-transparency research, reporting, comparison tools and retrieval systems. Each observation can be traced to the provider, product form, selected term, collection date and supporting evidence. A quote observed after a questionnaire may still match a publicly advertised price; collection stage alone does not establish that a price was hidden beforehand.

## Schema

| Column | Type | Description |
|---|---|---|
|`provider`|string|Provider whose observed quote or owner-configured plan is recorded.|
|`plan_name`|string|Selected plan term, with important introductory or native-week qualifications.|
|`medication_type`|string|Compounded or Brand; null when the formulation class was not established.|
|`medication_name`|string|Named medication or formulation. Different forms are not assumed equivalent.|
|`membership_fee_monthly_usd`|number|Separately required monthly membership, when established. Null means unknown; zero means a separate required membership fee was verified absent.|
|`medication_cost_monthly_usd`|number|Selected medication-plan bundle divided by the provider-labelled plan months. Bundled services may be included. Native-week plans remain null.|
|`total_effective_monthly_usd`|number|Known bundle plus required membership on the same labelled-month basis, or an explicit whole-program monthly quote. Unknown components remain null; final tax and card charge are unverified.|
|`plan_length_months`|integer|Provider-labelled selected plan months for observed quotes, or configured billing-interval months for PGP. Billing intervals do not establish dispensed supply. Native weeks are not converted to calendar months.|
|`states_served`|string|Matched product-specific state-count claim, or an explicit unverified marker. A provider-wide claim does not establish product availability.|
|`pharmacy_named_publicly`|string|Publicly named pharmacy partners where established. Network disclosure does not establish the pharmacy assigned to a selected prescription.|
|`legitscript_certified`|string|Yes for the eight observed providers, based on the publisher’s direct checker confirmation dated October 20, 2026. Automated retrieval was bot-gated; method and source are labelled in metadata-sources.|
|`fda_approved_medication`|string|Approval status of the specific finished formulation: Yes, No, or Not verified. Compounded formulations are No.|
|`insurance_accepted`|string|Whether insurance applies toward the listed cash quote. HSA/FSA eligibility and outside reimbursement are separate.|
|`source_url`|string|Official session-free provider flow for observed quotes, or the exact benchmark evidence reference for PGP. A login may be required for provider flows.|
|`date_collected`|date|Original quote-observation or benchmark-record date, in YYYY-MM-DD form.|
|`collection_basis`|string|Unchanged row-level evidence class: `post_questionnaire_selected_quote` or `owner_verified_configured_benchmark`. Present in the default combined table; absent from the original 15-column observed-only file.|

Numeric fields are nullable. Unknown values are not zero, false or evidence that a product is unavailable. The three monthly amount fields stay null for native-week plans; quote-detail preserves their exact selected totals.

## Important pharmacological and regulatory context

FDA approval refers to a specific finished formulation, not simply its ingredient name or the status of a pharmacy. Compounded drugs are not FDA-approved. This dataset does not assume equivalent dosing, supply, clinical effects or eligibility between products or routes. FDA source: https://www.fda.gov/drugs/human-drug-compounding/understanding-risks-compounded-drugs .

Provider interface wording is recorded as evidence of an offer, not independently adopted as a clinical claim. No treatment outcome or prescription approval is established by these quotes.

## Methodology

The study uses one explicitly fictional case: a 35-year-old woman in California, 5 ft 4 in, 172 lb, goal 145 lb, somewhat active, with no known conditions, medications or allergies, no prior use of any study treatment, and not pregnant or breastfeeding. BMI is approximately 29.5. This is a designed research scenario, not a verified average U.S. woman.

Only fields actually presented were answered. The recorded scope differs by provider; a disclosed case description does not prove that every demographic or health field was separately checked. Each primary observation follows actual provider-presented health questions and individual plan selection. No final clinical submission, card entry or payment was completed by the collector, and full medical-intake completion is not claimed.

Separate rows preserve the terms actually selected. The exact selected total is retained before any division by provider-labelled months. Native 4-, 8- and 12-week plans retain their weeks, days and explicit billing cadence; their calendar-month columns stay null. Introductory discounts, conditional charge labels and renewal amounts remain separate.

The source_url field points to the official flow without private session identifiers. Join the row through primary_csv_row in quote-detail to observation_id and evidence_ids, then to the evidence index and screenshots. Personal contact details, credentials and private session tokens are excluded. Detailed application exceptions and field definitions are in METHODS.md.

## Coverage limitations

This is a purposive nine-brand study using one fictional scenario and one dated collection snapshot. It is not a market-wide ranking or a representative patient sample. 38 brand/category cells still lack a qualifying quote; this does not mean each missing product is permanently unavailable. Wisp has no qualifying primary rows. Lovely Meds has 18 selected options in five categories; its microdose-specific selection remains unresolved. Current product-specific gates are recorded in coverage and access-barriers.json.

Quotes are not receipts, guaranteed card charges or evidence of clinical eligibility. Final taxes, future promotions, dose escalation and dispensing quantities are unknown where not displayed. Billing cadence, supply duration and calendar months must not be treated as interchangeable. Three Fitish oral observations remain secondary because the official route instructions conflict; they are not counted as confirmed tirzepatide sublingual quotes.

A separate paid-consultation, account, consent or clinical-review gate may remain after an observed quote. Some AgelessRx consent language permits possible automated approval; backend processing was not independently verified. Amble’s quote stage did not establish California availability. Good Life Meds did not separately ask all scenario demographics and its semaglutide flow rejected the California shipping case. Recovered-account and other lower-stage prices remain outside the primary table.

PGP is a commercial provider and the study compiler. Its own configured offers have a different evidence basis: they remain separate in the benchmark config and are explicitly labelled in the default combined view.

## LegitScript verification status

All 96 observed rows record `Yes`: the publisher confirmed the LegitScript checker records for AgelessRx, Amble, Arbor, Effecty, Fitish, Good Life Meds, Lovely Meds and ReadyRx on October 20, 2026. PGP’s 32 rows in the default combined view also record `Yes` from the publisher-confirmed PGP checker record. The provenance is **publisher-confirmed direct checker reading**; automated retrieval was bot-gated and is not presented as a successful automated scrape. Per-provider checker URLs, dates and method labels are recorded in metadata-sources and provider-checks. Certification does not establish FDA approval, product availability in every state or an individual prescription’s dispensing pharmacy.

Good Life Meds’ Terms name GoGo Meds d/b/a Jungle Jims and Pharmacy Hub as fulfillment pharmacies; prescription assignment remains unverified. Its Terms exclude seven states and DC (43 states), conflicting with its Help Center’s all-50-states platform claim. Both claims are retained in the metadata; product-specific primary state fields are unchanged. Other providers’ platform-wide reach and exclusions for outside-study products are likewise not transferred onto study rows.

In the combined view, PGP’s medication-plan and total monthly-rate columns both show configured period charge divided by configured billing-interval months. They represent the same bundle, not additive components. The separate membership allocation remains null, and PGP state counts, dispensing-pharmacy names, final fees and dispensed supply remain unverified. PGP source references are preserved exactly from the benchmark, including their evidence-file references.

## Comparison highlights (October 2026 snapshot)

These examples link to stable observation IDs in quote-detail or the publisher benchmark. PGP rows are explicitly marked **publisher-configured**; competitor rows are observed selected quotes. The table does not establish medically equivalent dosing or supply. Good Life Meds examples include the displayed DW20 promotion; continued availability and renewal eligibility were not established. PGP configured totals are not verified final checkout or renewal charges.

All 96 primary selected totals were visually rechecked against saved screenshots on October 20, 2026. The public comparisons contain 5 matching exact public totals, 29 public-rate-only references, 23 differences under documented term or promotion conditions, and 39 exact comparable public totals not established. The last category is an evidence limit, not proof of hidden pricing. Public reference dates remain separate from quote dates.

| Provider | Treatment | Term / billing interval | Selected or configured total | Evidence / condition | Stated renewal | Observation ID |
|---|---|---|---:|---|---|---|
|AgelessRx|Compounded Tirzepatide + Glycine|1 labelled month|$279.00|Displayed CTG70 promotion|$349.00|`ageless-compounded-tirzepatide-monthly-post-questionnaire-20261019`|
|AgelessRx|Personalized Compounded Semaglutide + Glycine|1 labelled month|$279.00|Selected conditional quote|$279.00|`ageless-compounded-semaglutide-1m-post-questionnaire-20261020`|
|AgelessRx|Personalized Compounded Semaglutide + Glycine|2 labelled months|$518.00|Selected conditional quote|$518.00|`ageless-compounded-semaglutide-2m-post-questionnaire-20261020`|
|AgelessRx|Personalized Compounded Semaglutide + Glycine|4 labelled months|$856.00|Displayed TSEMA100 promotion|$956.00|`ageless-compounded-semaglutide-4m-post-questionnaire-20261020`|
|Pretty Girls Peptide|Semaglutide Plan (injection)|1-month configured billing|$175.00|publisher-configured|Not independently observed|`B-pgp-config-plan3357-variant20308-20261019`|
|Pretty Girls Peptide|Tirzepatide Plan (injection)|1-month configured billing|$225.00|publisher-configured|Not independently observed|`B-pgp-config-plan3372-variant20334-20261019`|
|Pretty Girls Peptide|Tirzepatide Plan (injection)|3-month configured billing|$597.00|publisher-configured|Not independently observed|`B-pgp-config-plan3372-variant20335-20261019`|
|Pretty Girls Peptide|NAD+ Nasal Spray 300 mg/mL|3-month configured billing|$525.00|publisher-configured|Not independently observed|`B-pgp-config-plan3804-variant22314-20261019`|
|Good Life Meds|NAD+ Nasal Spray (Monthly)|1 labelled month|$111.20|Displayed DW20 promotion|Not established for this promotion|`goodlife-nad-nasal-monthly-new-research-20261019`|
|Good Life Meds|Glutathione - Monthly|1 labelled month|$79.20|Displayed DW20 promotion|Not established for this promotion|`goodlife-glutathione-monthly-new-research-20261019`|
|Good Life Meds|Glutathione Quarterly - 30 ml|3 labelled months|$199.20|Displayed DW20 promotion|Not established for this promotion|`goodlife-glutathione-quarterly-new-research-20261019`|
|Good Life Meds|Glutathione 200 mg/ml - (one-time purchase)|1 labelled month|$143.20|Displayed DW20 promotion|Not established for this promotion|`goodlife-glutathione-one-time-new-research-20261019`|
|Good Life Meds|Compounded Tirzepatide Microdose|4 weeks|$119.20|Displayed DW20 promotion|Not established for this promotion|`goodlife-tirzepatide-microdose-4w-new-research-20261019`|
|Good Life Meds|Compounded Tirzepatide Microdose|12 weeks|$279.20|Displayed DW20 promotion|Not established for this promotion|`goodlife-tirzepatide-microdose-12w-new-research-20261019`|

For example, the observed Good Life Meds quarterly glutathione selector showed $199 for three months; the selected review named 30 ml and showed $249 before DW20, $199.20 after. The reason and product-quantity equivalence were not established. It is recorded as a screen-to-screen difference, not an inferred fee.

## Changelog

2026-10-20 — **1.8.0**: Made the unchanged 128-row combined table the default; added `observed_quotes_only` for the unchanged 96 competitor quotes. Preserved both `collection_basis` values. Added four publisher-configured PGP comparison examples and replaced methodology-heavy findings with seven sourced price facts, including three PGP facts, while retaining F01. No observed price, plan term, collection date, source URL or observation ID changed. Full changes and release checks are in [CHANGELOG.md](CHANGELOG.md).

2026-10-20 — **1.7.3**: Typography only — no data, price, term, or wording changes; `primary_changed_cells: 0`. Corrected prose spacing, including historical entries, and updated active version references. Every spacing correction is listed in [CHANGELOG.md](CHANGELOG.md). All CSV and Parquet files are byte-for-byte identical to v1.7.2; counts remain 96 observed, 32 benchmark and 128 combined rows.

2026-10-20 — **1.7.2**: Updated exactly **106 primary cells**: 96 publisher-confirmed LegitScript results, eight Good Life Meds publicly named fulfillment-pharmacy values and two ReadyRx NAD nasal FDA-approval values. No observed price, plan term, collection date, source URL or observation ID changed. The two ReadyRx glutathione nasal rows remain Not verified for FDA status. Added an explicitly labelled 128-row combined view and matching Parquet while preserving the 32-row benchmark source unchanged. Platform-state conflicts and outside-study exclusions are documented without changing primary state values. Every changed primary cell, with before/after values and stable observation ID, is listed in [CHANGELOG.md](CHANGELOG.md). Release QA also corrected the inherited mixed-format loading issue: the retained `primary_parquet` config is a documented CSV-backed compatibility alias; both actual Parquet files remain downloadable.

2026-10-20 — 1.7.1: Publication packaging release. All 96 primary rows, prices, dates, nulls, observation IDs and source evidence from the 1.7.0 research snapshot are unchanged. Added eight dated findings, an identical primary Parquet encoding, an explicitly separate public-reference configuration, citation metadata and checksum-based mirror controls. Broader provider coverage and remaining questionnaire checks are not claimed complete.

2026-10-20 — 1.7.0-research-in-progress: Added 18 actual Lovely Meds selected conditional options across tirzepatide injection, semaglutide injection, NAD nasal 15 mL, 300 mg/mL and glutathione injection with 1/3/6/12-month-labelled terms, plus two tirzepatide sublingual-drop quotes for 1/3-month-labelled options. Each has a selected-plan image and separate visible total screenshot after its provider-presented health questions. GLP NEW60 was actually applied. Annual glutathione GLUT100 returned Coupon not found, so no saving is attributed to it. Matched public annual semaglutide pricing differs from the selected annual pre-code review; cause and exact cohort equivalence are unverified. All 78 prior quotes are preserved. The package now contains 96 primary options, 480 scoped metadata reviews and 99 public comparison records. Lovely oral selected quotes captured after specifically approved precaution; Effecty personal-account login remains pending. Microdose marketing leads to a shared standard flow without a separately selected microdose SKU, so no duplicate microdose price is claimed.

2026-10-20 — 1.6.0-research-in-progress: Added four fresh Effecty glutathione selected quotes after its disclosed research-case pre-plan questions: $129 for one month, $330 for three months, $600 for six months and $1,068 for twelve months, conditional on prescribing. No promotion was applied; the matched public page advertises the same monthly rates and a separate untested VITALITY offer. All 74 preceding quote economics are retained. Visually verified all 78 current selected totals, reviewed 390 requested metadata cells, added 20 previously missing comparisons and four new-quote comparisons. All 78 primary options now have public comparison classifications. A matched Wisp NAD entry supplies a 49-state background claim, excluding South Carolina; it creates no primary quote. Source-specific unknowns remain explicit, and four native-week plans retain null month fields. The new price-verification and metadata-resolution files expose each check.

The preceding edition added three AgelessRx compounded semaglutide quotes observed on October 20, 2026: $279 monthly, $518 for two months, and $856 initially / $956 on renewal for four months. The four-month initial total is $214 per source-labelled plan month; its $139 first-month headline is a different quantity. Original price dates and background source dates are preserved. Earlier corrections retain unresolved oral-route evidence, distinguish monitoring fees from medication totals, and keep recovered-account observations secondary. Further medication checks can be added as dated observations. No past price is silently replaced.

## License

PGP’s original compiled factual data and original documentation are offered under CC BY 4.0 with attribution to Pretty Girls Peptide. Provider screenshots, logos and copied source material retain their respective third-party rights and are included for verification; they are not blanket relicensed. License: https://creativecommons.org/licenses/by/4.0/ .

Suggested citation: Pretty Girls Peptide (2026). Telehealth GLP-1 and Wellness Pricing Comparison — October 2026. Snapshot 2026-10-20, version 1.8.0. Dataset: https://huggingface.co/datasets/prettygirlspeptide/telehealth-glp1-pricing ; release: https://huggingface.co/datasets/prettygirlspeptide/telehealth-glp1-pricing/tree/v1.8.0 . DOI not yet assigned. For an individual finding, also identify the provider, medication/form, selected term, exact total, collection date and observation ID.

## Maintenance

This is a dated snapshot. Recheck the row’s date_collected and the provider before using a price as current. Future checks should add dated observations or explicit corrections with evidence. No scheduled refresh or continuing monitoring is represented as active.

## Publisher

Pretty Girls Peptide (PGP) compiled this dataset. PGP has a commercial interest in the treatment market. Its publisher-configured benchmark is included for transparency, with its evidence basis and limitations stated separately. Website: [Pretty Girls Peptide](https://prettygirlspeptide.com/).
