# Changelog — v1.8.0

## v1.8.0 — October 20, 2026

Default-view and price-findings release. Previous release v1.7.3 is preserved. `primary_changed_cells: 0`; no observed price, plan term, collection date, source URL or observation ID changed.

### Every release change

1. README.md YAML: default now points to combined_pricing.csv (128 rows, 16 columns), with default: true. Added observed_quotes_only pointing to pricing.csv (96 rows, 15 columns). The five other configs retain their data files; combined_all_providers remains the explicit combined-table alias and primary_parquet remains CSV-backed.
2. README.md summary and loading instructions: identify the combined table as the default, document loading with no config argument and the observed-only selection, preserve the two-evidence-class warning, and distinguish direct file downloads. Updated the main-file description, schema explanations and current combined-view references.
3. README.md dated findings and findings.json: preserved F01 exactly; replaced F02–F05 and F08 and updated F07 with source-backed price facts; retained F06’s price sentence. The eight findings now contain seven concrete price facts, including three PGP facts and no additional methodology statistic. Added structured provider/product/term/total, renewal status, collection basis, source URL and original record date to price facts. The dated fact list is below.
4. README.md Comparison highlights: added four PGP benchmark rows (listed below), each marked publisher-configured with renewal not independently observed. Updated table headings and the explanatory paragraph to cover observed and configured totals without implying equivalent supply or an observed checkout.
5. CITATION.cff: version is 1.8.0; date-released remains 2026-10-20. README.md and METHODS.md active citations point to v1.8.0; historical release labels remain unchanged.
6. RELEASE.json: version/release_tag/previous_release become 1.8.0/v1.8.0/1.7.3; config mapping matches YAML; added default config/file/row/column/provider fields and observed_quotes_config; updated the combined-view scope. Current primary_changed_cells and primary_row_changes_from_source are 0; inherited v1.7.2 counts are no longer reported as current-release changes. Data-file hashes are unchanged.
7. research-status.json: active version and previous release updated; current primary_metadata_cells_changed is 0; added default config/file/row count and observed-only config. All source collection dates and coverage records remain unchanged.
8. schema.json: active release version updated; added default_view and observed_quotes_only declarations. Existing observed columns and combined evidence-class definitions are unchanged.
9. METHODS.md: replaced stale unpublished status, distinguished the observed-only inclusion rule from the combined default, updated the current QA version and citation, and documented v1.8.0 findings and benchmark-total handling.
10. RELEASE-QUALITY.json: replaced the previous-release audit report with v1.8.0 validation results, including the seven official-loader configs and default loading without a config argument. SHA256SUMS.txt regenerated.

### Dated findings (source records remain dated as originally collected)

| ID | Finding | Source observation ID |
|---|---|---|
|F02|Pretty Girls Peptide’s publisher-configured Semaglutide Plan (injection) records a $175 total for the one-month billing interval; checkout renewal was not independently observed.|`B-pgp-config-plan3357-variant20308-20261019`|
|F03|Pretty Girls Peptide’s publisher-configured Tirzepatide Plan (injection) records a $597 total for the quarterly (three-month) billing interval; checkout renewal was not independently observed.|`B-pgp-config-plan3372-variant20335-20261019`|
|F04|Pretty Girls Peptide’s publisher-configured NAD+ Nasal Spray 300 mg/mL plan records a $525 total for the quarterly (three-month) billing interval; checkout renewal was not independently observed.|`B-pgp-config-plan3804-variant22314-20261019`|
|F05|Good Life Meds’ selected one-month-labelled NAD+ nasal spray quote showed a $111.20 total after DW20, compared with $139 before the code; the promotion’s renewal amount was not established.|`goodlife-nad-nasal-monthly-new-research-20261019`|
|F06|AgelessRx’s selected monthly compounded tirzepatide quote showed $279 initially with the displayed CTG70 promotion and $349 on monthly renewal.|`ageless-compounded-tirzepatide-monthly-post-questionnaire-20261019`|
|F07|Lovely Meds’ selected three-month-labelled tirzepatide injection plan showed a $537 initial total after NEW60, compared with $597 before the code; an exact future renewal total was not itemized.|`lovely-tirzepatide-injection-3m-research-20261020`|
|F08|AgelessRx’s selected four-month-labelled Personalized Compounded Semaglutide + Glycine injection plan showed an $856 initial total after TSEMA100 and $956 on four-month renewal.|`ageless-compounded-semaglutide-4m-post-questionnaire-20261020`|

### PGP comparison additions

| Benchmark observation ID | Product | Configured billing interval | Configured total |
|---|---|---|---:|
|`B-pgp-config-plan3357-variant20308-20261019`|Semaglutide Plan|1 month(s)|$175.00|
|`B-pgp-config-plan3372-variant20334-20261019`|Tirzepatide Plan|1 month(s)|$225.00|
|`B-pgp-config-plan3372-variant20335-20261019`|Tirzepatide Plan|3 month(s)|$597.00|
|`B-pgp-config-plan3804-variant22314-20261019`|NAD+ Nasal Spray 300mg/mL|3 month(s)|$525.00|

### Verification

- pricing.csv: 96 rows; publisher benchmark: 32 rows; combined_pricing.csv: 128 rows. Both Parquet tables are byte-for-byte unchanged.
- Every CSV, JSONL, evidence and support-evidence file is byte-for-byte unchanged from v1.7.3. No data row was rewritten.
- All 128 collection_basis values remain exactly as before: 96 post_questionnaire_selected_quote and 32 owner_verified_configured_benchmark.
- All seven configs passed the official datasets loader locally. Omitting the config selects the 128-row default.
- Every displayed price fact and PGP comparison addition reconciles to its original source row; unknown renewal totals remain unknown.
- CC BY 4.0, third-party evidence rights and DOI hold remain unchanged.


## v1.7.3 — October 20, 2026

Typography only — no data, price, term, or wording changes; `primary_changed_cells: 0`.

All CSV, JSONL, benchmark, combined-table, Parquet and screenshot bytes are unchanged from v1.7.2. Counts remain pricing 96, benchmark 32 and combined 128. Active version references and checksums are updated. v1.7.2 remains preserved.

### Every spacing correction

Line numbers below refer to v1.7.2. Original spellings are retained only as inline-code audit examples. Legitimate promotion codes, observation IDs, source IDs, URLs, YAML tokens and historical version numbers are preserved.

| File | v1.7.2 line | Before | After |
|---|---:|---|---|
|CHANGELOG.md|124|`Added18`|`Added 18`|
|CHANGELOG.md|124|`October20,2026`|`October 20, 2026`|
|CHANGELOG.md|124|`nasal15mL300mg/mL`|`nasal 15 mL 300 mg/mL`|
|CHANGELOG.md|124|`with1/3/6/12`|`with 1/3/6/12`|
|README.md|153|`30ml`|`30 ml`|
|README.md|154|`200mg/ml`|`200 mg/ml`|
|README.md|158|`30ml`|`30 ml`|
|README.md|166|`All78 prior quotes`|`All 78 prior quotes`|
|README.md|166|`contains96 primary options,480 scoped metadata reviews and99 public comparison records`|`contains 96 primary options, 480 scoped metadata reviews and 99 public comparison records`|
|README.md|166|`for1/3-month-labelled`|`for 1/3-month-labelled`|
|README.md|168|`All74 preceding quote economics`|`All 74 preceding quote economics`|
|README.md|168|`All78 primary options`|`All 78 primary options`|
|README.md|168|`a49-state background claim`|`a 49-state background claim`|
|README.md|168|`added20 previously missing comparisons`|`added 20 previously missing comparisons`|
|README.md|168|`all78 current selected totals`|`all 78 current selected totals`|
|README.md|168|`reviewed390 requested metadata cells`|`reviewed 390 requested metadata cells`|

### v1.7.3 verification

- Prose changes insert spaces only; no existing non-whitespace wording changed.
- Letter-digit and digit-letter pattern searches found no remaining unintended prose fusions.
- Pricing CSV: 96 rows; publisher benchmark: 32 rows; combined CSV: 128 rows.
- Every CSV, JSONL and Parquet file is byte-for-byte identical to v1.7.2.
- Both Parquet tables retain the same contents and row counts.
- The dataset-card YAML, six configurations, licensing and citation release date are unchanged.
- SHA256SUMS.txt is regenerated; DOI generation remains on hold.

## v1.7.2

Date: October 20, 2026. Previous release v1.7.1 is preserved. This release changes 106 cells in pricing.csv and its equivalent primary encodings; no observed economic value changed. CSV row numbers include the header.

The combined view adds 32 PGP benchmark mappings and one collection_basis column; it does not turn the benchmark into post-questionnaire observations. PGP monthly bundle rates are configured period charge / billing interval months. Membership allocation, states and pharmacy names remain unverified. Source references remain byte-for-byte the benchmark references.

## Every changed primary cell

| CSV row | Observation ID | Field | Before | After | Source ID |
|---:|---|---|---|---|---|
|2|ageless-ghk-cream-05-monthly-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-agelessrx.com|
|3|ageless-gsh-injection-1m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-agelessrx.com|
|4|ageless-gsh-injection-3m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-agelessrx.com|
|5|ageless-nad-nasal-monthly-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-agelessrx.com|
|6|ageless-pt141-monthly-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-agelessrx.com|
|7|ageless-compounded-semaglutide-1m-post-questionnaire-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-agelessrx.com|
|8|ageless-compounded-semaglutide-2m-post-questionnaire-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-agelessrx.com|
|9|ageless-compounded-semaglutide-4m-post-questionnaire-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-agelessrx.com|
|10|ageless-compounded-tirzepatide-monthly-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-agelessrx.com|
|11|ageless-tirz-micro-trial-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-agelessrx.com|
|12|amble-glutathione-new-research-1m-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-joinamble.com|
|13|amble-glutathione-new-research-3m-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-joinamble.com|
|14|amble-glutathione-new-research-6m-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-joinamble.com|
|15|amble-semaglutide-new-research-1m-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-joinamble.com|
|16|amble-semaglutide-new-research-3m-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-joinamble.com|
|17|amble-semaglutide-new-research-6m-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-joinamble.com|
|18|amble-tirzepatide-new-research-1m-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-joinamble.com|
|19|amble-tirzepatide-new-research-3m-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-joinamble.com|
|20|amble-tirzepatide-new-research-6m-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-joinamble.com|
|21|arbor-glutathione-resumed-1m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|22|arbor-glutathione-resumed-3m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|23|arbor-glutathione-resumed-6m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|24|arbor-glutathione-resumed-12m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|25|arbor-semaglutide-1-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|26|arbor-semaglutide-3-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|27|arbor-semaglutide-6-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|28|arbor-semaglutide-12-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|29|arbor-tirzepatide-injection-1-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|30|arbor-tirzepatide-3-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|31|arbor-tirzepatide-6-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|32|arbor-tirzepatide-12-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-startarbor.com|
|33|effecty-glutathione-1m-fresh-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|34|effecty-glutathione-3m-fresh-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|35|effecty-glutathione-6m-fresh-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|36|effecty-glutathione-12m-fresh-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|37|effecty-round2-semaglutide-1m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|38|effecty-round2-semaglutide-3m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|39|effecty-round2-semaglutide-6m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|40|effecty-round2-semaglutide-12m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|41|effecty-round2-tirzepatide-1m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|42|effecty-round2-tirzepatide-3m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|43|effecty-round2-tirzepatide-6m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|44|effecty-round2-tirzepatide-12m-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-effecty.com|
|45|Q-fitish-wellness-ghk-1m|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|46|Q-fitish-wellness-ghk-3m|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|47|Q-fitish-wellness-ghk-6m|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|48|Q-fitish-wellness-nad-1m|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|49|Q-fitish-wellness-nad-3m|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|50|Q-fitish-wellness-nad-6m|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|51|Q-fitish-followup-004|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|52|Q-fitish-followup-005|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|53|Q-fitish-followup-006|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|54|Q-fitish-followup-001|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|55|Q-fitish-followup-002|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|56|Q-fitish-followup-003|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|57|Q-fitish-microdose-followup-001|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|58|Q-fitish-microdose-followup-002|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|59|Q-fitish-microdose-followup-003|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-fitish.com|
|60|goodlife-glutathione-monthly-new-research-20261019|pharmacy_named_publicly|Not established in reviewed sources|Yes (GoGo Meds d/b/a Jungle Jims; Pharmacy Hub — named in the provider's Terms as its fulfillment pharmacies; assignment to an individual prescription unverified).|V172-GOODLIFE-TERMS-PHARMACY|
|60|goodlife-glutathione-monthly-new-research-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-goodlifemeds.com|
|61|goodlife-glutathione-one-time-new-research-20261019|pharmacy_named_publicly|Not established in reviewed sources|Yes (GoGo Meds d/b/a Jungle Jims; Pharmacy Hub — named in the provider's Terms as its fulfillment pharmacies; assignment to an individual prescription unverified).|V172-GOODLIFE-TERMS-PHARMACY|
|61|goodlife-glutathione-one-time-new-research-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-goodlifemeds.com|
|62|goodlife-glutathione-quarterly-new-research-20261019|pharmacy_named_publicly|Not established in reviewed sources|Yes (GoGo Meds d/b/a Jungle Jims; Pharmacy Hub — named in the provider's Terms as its fulfillment pharmacies; assignment to an individual prescription unverified).|V172-GOODLIFE-TERMS-PHARMACY|
|62|goodlife-glutathione-quarterly-new-research-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-goodlifemeds.com|
|63|goodlife-nad-nasal-monthly-new-research-20261019|pharmacy_named_publicly|Not established in reviewed sources|Yes (GoGo Meds d/b/a Jungle Jims; Pharmacy Hub — named in the provider's Terms as its fulfillment pharmacies; assignment to an individual prescription unverified).|V172-GOODLIFE-TERMS-PHARMACY|
|63|goodlife-nad-nasal-monthly-new-research-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-goodlifemeds.com|
|64|goodlife-tirzepatide-new-research-4w-20261019|pharmacy_named_publicly|Not established in reviewed sources|Yes (GoGo Meds d/b/a Jungle Jims; Pharmacy Hub — named in the provider's Terms as its fulfillment pharmacies; assignment to an individual prescription unverified).|V172-GOODLIFE-TERMS-PHARMACY|
|64|goodlife-tirzepatide-new-research-4w-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-goodlifemeds.com|
|65|goodlife-tirzepatide-new-research-8w-20261019|pharmacy_named_publicly|Not established in reviewed sources|Yes (GoGo Meds d/b/a Jungle Jims; Pharmacy Hub — named in the provider's Terms as its fulfillment pharmacies; assignment to an individual prescription unverified).|V172-GOODLIFE-TERMS-PHARMACY|
|65|goodlife-tirzepatide-new-research-8w-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-goodlifemeds.com|
|66|goodlife-tirzepatide-microdose-4w-new-research-20261019|pharmacy_named_publicly|Not established in reviewed sources|Yes (GoGo Meds d/b/a Jungle Jims; Pharmacy Hub — named in the provider's Terms as its fulfillment pharmacies; assignment to an individual prescription unverified).|V172-GOODLIFE-TERMS-PHARMACY|
|66|goodlife-tirzepatide-microdose-4w-new-research-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-goodlifemeds.com|
|67|goodlife-tirzepatide-microdose-12w-new-research-20261019|pharmacy_named_publicly|Not established in reviewed sources|Yes (GoGo Meds d/b/a Jungle Jims; Pharmacy Hub — named in the provider's Terms as its fulfillment pharmacies; assignment to an individual prescription unverified).|V172-GOODLIFE-TERMS-PHARMACY|
|67|goodlife-tirzepatide-microdose-12w-new-research-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-goodlifemeds.com|
|68|lovely-glutathione-injection-1m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|69|lovely-glutathione-injection-3m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|70|lovely-glutathione-injection-6m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|71|lovely-glutathione-injection-12m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|72|lovely-nad-nasal-15ml-1m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|73|lovely-nad-nasal-15ml-3m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|74|lovely-nad-nasal-15ml-6m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|75|lovely-nad-nasal-15ml-12m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|76|lovely-semaglutide-injection-1m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|77|lovely-semaglutide-injection-3m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|78|lovely-semaglutide-injection-6m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|79|lovely-semaglutide-injection-12m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|80|lovely-tirzepatide-injection-1m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|81|lovely-tirzepatide-injection-3m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|82|lovely-tirzepatide-injection-6m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|83|lovely-tirzepatide-injection-12m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|84|lovely-tirzepatide-sublingual-drops-1m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|85|lovely-tirzepatide-sublingual-drops-3m-research-20261020|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-lovelymeds.com|
|86|readyrx-glutathione-injection-1-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|87|readyrx-glutathione-nasal-1-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|88|readyrx-glutathione-injection-3-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|89|readyrx-glutathione-nasal-3-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|90|readyrx-nad-nasal-1-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|90|readyrx-nad-nasal-1-month-post-questionnaire-20261019|fda_approved_medication|Not verified|No|V172-READYRX-NAD-NASAL-FAQ|
|91|readyrx-nad-nasal-3-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|91|readyrx-nad-nasal-3-month-post-questionnaire-20261019|fda_approved_medication|Not verified|No|V172-READYRX-NAD-NASAL-FAQ|
|92|readyrx-semaglutide-1-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|93|readyrx-semaglutide-3-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|94|readyrx-semaglutide-6-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|95|readyrx-tirzepatide-1-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|96|readyrx-tirzepatide-3-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|
|97|readyrx-tirzepatide-6-month-post-questionnaire-20261019|legitscript_certified|Not independently verified|Yes|V172-LEGITSCRIPT-readyrx.com|

## Other release changes

- Added combined_pricing.csv (128 rows, 16 columns), combined_pricing.parquet and combined_all_providers config. Regenerated pricing.parquet (96 rows, 15 columns).
- Updated current metadata and source provenance, including publisher-confirmed LegitScript reads and the Good Life Meds state-claim conflict. Sources are dated 2026-10-20.
- Preserved PGP benchmark source files and all original screenshot evidence unchanged.
- Updated README findings context, certification section, active version references, CITATION.cff, schema, release status and checksums. Historical changelog entries retain their original version labels.
- Corrected Added 18, nasal 15 mL 300 mg/mL, with 1/3/6/12 and October 20, 2026 spacing in the card.
- CC BY 4.0 continues to cover PGP original data and writing; third-party evidence retains its rights exception. DOI generation remains on hold.

- Release-candidate loader correction: retained primary_parquet as a CSV-backed alias so all six named configurations load with the shared CSV builder. Actual pricing.parquet and combined_pricing.parquet are retained as independently verified alternate encodings. No table cell changed in this loader correction.
