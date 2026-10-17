# Final pre-hackathon data readiness: CONDITIONALLY_READY

Audit updated 2026-10-17T20:46:51.919178+00:00; starting repository commit 6395fe2. The pair is a suitable candidate for a future, validated surface-change demonstration. This is **not a completed competition solution or a validated flood result**. No flood detector, change-classification algorithm, model or application has been developed.

## Verified source observations

Collection NISAR_L2_GCOV_PROVISIONAL_V1, DOI [10.5067/NIL2GCOV-P1](https://doi.org/10.5067/NIL2GCOV-P1), L-band frequency-A HHHH:

- `NISAR_L2_PR_GCOV_028_040_A_015_4005_DHDH_A_20260815T230527_20260815T230601_P05023_N_F_J_001`
  - UTC start: 2026-08-15T23:05:27Z; authoritative URLs in metadata/scene_inventory.json. Full source size 7,084,179,456 bytes, **not downloaded**.
- `NISAR_L2_PR_GCOV_029_040_A_015_4005_DHDH_A_20260827T230526_20260827T230601_P05023_N_F_J_001`
  - UTC start: 2026-08-27T23:05:26Z; authoritative URLs in metadata/scene_inventory.json. Full source size 7,289,700,352 bytes, **not downloaded**.

Both: track 40/frame 15, ascending, left-looking, dithered, joint observations, frequency A/B HH/HV, 40+5 MHz, CRID P05023, product version 1.0.11, specification 1.5.0. Catalog processor R05.02.3 and PDF softwareVersion 0.25.16 are distinct recorded version fields. Both cropped originals remain SHA256-identical to the previous audit: 38,712,699 and 38,414,270 bytes. Their Float32 linear gamma0 values, units 1 and NaN NoData were not changed. Common CRS EPSG:32646, dimensions 3707 x 3470, affine `(604050,10,0,3001630,0,-10)`, bounds `(604050,2966930,641120,3001630)`.

## Complete region quality-mask assessment

GDAL 3.13.3 read only the complete cropped frequency-A mask, inputDataExceptionMask and numberOfLooks layers via authenticated `/vsicurl/`. Source mask values are unchanged, separately stored under E:/TerraScope_AI/01_NASA_Data_Exploration/quality_audit. Looks statistics were computed in memory; no duplicate looks raster or HHHH raster was created. Operations ran sequentially with a 256 MiB observed range-request budget/date and bounded caches/timeouts.

Official validity mask semantics: 0 invalid/partially focused; 1–5 fully focused valid subswaths; 255 fill outside acquisition; other values unknown. Exception code 0 means no documented anomaly; code 2 indicates LSAR qFSP-H1 sample slip. Valid dithered acquisitions use subswath 1. These meanings do not include every possible scientific error.

| Region/date | Denominator | Valid count (%) | Invalid count (%) | Fill count (%) | Unknown count (%) | Nonzero exception count (%) |
|---|---:|---:|---:|---:|---:|---:|
| Full crop, Aug 15 | 12,863,290 | 12,863,290 (100%) | 0 (0%) | 0 (0%) | 0 (0%) | 0 (0%) |
| Full crop, Aug 27 | 12,863,290 | 12,863,290 (100%) | 0 (0%) | 0 (0%) | 0 (0%) | 0 (0%) |
| Exact AOI, Aug 15 | 12,611,824 | 12,611,824 (100%) | 0 (0%) | 0 (0%) | 0 (0%) | 0 (0%) |
| Exact AOI, Aug 27 | 12,611,824 | 12,611,824 (100%) | 0 (0%) | 0 (0%) | 0 (0%) | 0 (0%) |

Shared coverage under the inspected criteria is **12,611,824 exact-AOI pixels (100%)**, or 1261.1824 km² of selected native pixel area. The enclosing-crop shared count is 12,863,290 (100%). Criteria: valid subswath and zero exception code on both dates; all HHHH and looks pixels separately verified finite/positive. This is mask-qualified coverage, not a declaration that every pixel is suitable for every scientific analysis. No flood area has been calculated.

| Exact AOI numberOfLooks | Minimum | Median | 99th percentile | Maximum | Nonfinite/nonpositive |
|---|---:|---:|---:|---:|---:|
| 20260815 | 0.092062 | 4.532132 | 5.328417 | 8.518903 | 0 / 0 |
| 20260827 | 0.092333 | 4.532285 | 5.328550 | 8.518965 | 0 / 0 |

Fractional/low looks describe variable averaging and measurement variance; no undocumented rejection threshold is imposed. Prior sparse gamma-to-sigma checks were finite/positive, but the complete factor layer was not reread because this audit does not convert normalization conventions. There were no unknown mask codes or nonzero exception codes to investigate further. Full-row/source alignment and reopened mask values were verified.

## Exact AOI geometry

The original WKT is `POLYGON((94.05 26.82,94.42 26.82,94.42 27.13,94.05 27.13,94.05 26.82))`, EPSG:4326. A separate Byte mask inverse-projects **every** native pixel center to WGS84 and tests rectangle membership, avoiding projected-boundary interpolation. Values: 1 inside, 0 outside, reserved NoData 255. Reopened values, dimensions, affine and CRS match both HHHH rasters.

Inside: 12,611,824 centers; outside: 251,466; total: 12,863,290. This independently confirms the prior densified-polygon result. Continuous projected polygon area is approximately 1261.181622 km²; center-selected pixel area is 1261.1824 km². They are different estimators, not conflicting flood measurements. Original imagery is untouched; use the polygon mask for any future AOI area reporting.

## Metadata investigation and official caveats

The previously reproduced QA v17.0.0 identification ERRORs remain: instrumentName `LSAR` versus the validator's `L-SAR`/`S-SAR` spellings; listOfObservationModes `['(NOT SPECIFIED)']` instead of meaningful mode information. No source field was edited to make QA pass.

[Official isce3 issue #202](https://github.com/isce-framework/isce3/issues/202), opened January 15, 2026 and still open at audit, documents the **same LSAR spelling mismatch** in upstream RSLC metadata and discusses missing observation-mode metadata. Its author suggests some fields may be copied from L0B. This supports a product-generation/convention explanation for the name mismatch, but does not prove the exact lineage or resolve these two August GCOV granules. The placeholder remains incomplete metadata, not a verified waveform description. The specification describes instrumentName as a string without resolving the validator's stricter spelling choice. A precise [ASF question](ASF_SUPPORT_QUESTION.md) is prepared, **not sent**.

The [P05023 provisional known-issues page](https://nisar-docs.asf.alaska.edu/provisional-known-issues/), updated July 30, 2026, is directly relevant: joint-mode 40 MHz products may have enhanced residual radiometric bands; residual RFI/ripples and incomplete upstream data can affect interpretation. The reported polarimetric phase correction leaves HHHH unaffected. Frequency-B calibration has larger residuals; this audit uses frequency A. Do not apply BETA-specific mask warnings automatically to these PROVISIONAL products. Published release notes do not certify these individual scenes or resolve their placeholder fields. The [availability page](https://nisar-docs.asf.alaska.edu/availability-overview/) describes future validated reprocessing; that schedule alone is not evidence that a replacement granule is available.

Direct source processing flags remain RTC=True, noiseCorrectionApplied=False, shadowMaskingApplied=False and validSamplesSubSwathMaskingApplied=False. Valid samples can still contain terrain/geometry effects, noise-floor bias, RFI/banding or physical misregistration. No complete layover/shadow analysis, physical co-registration test or independent event validation has been performed.

## Candidate suitability and next checks

**CONDITIONALLY_READY** remains appropriate. Strengths: genuine same-configuration repeat observations, identical grids, intact originals, complete mask-qualified overlap and reproducible provenance. Limitations: unresolved metadata convention/placeholder, known joint-mode banding risk, unapplied noise/shadow masking, variable looks, no independent evidence of a flood transition. There is no evidence requiring automatic replacement solely from these QA errors.

Alternative observations may be needed if authoritative mode details cannot be clarified, independent references do not show a meaningful event transition at these dates, artifacts/noise dominate the intended measurement, or physical registration/geometry is unacceptable. Do not treat two monsoon acquisitions as a guaranteed before/after flood pair. Do not automatically enlarge the AOI or queue alternatives.

See [future scientific validation](FUTURE_SCIENTIFIC_VALIDATION.md) for a prioritized event checklist, metrics and independent reference candidates. Additional geometry/noise metadata and temporally matched references are still needed. A Float32 AOI layer is 51,453,160 bytes uncompressed per date; reference packages might require roughly 100–500 MB, and optional extra same-track dates roughly 77–155 MB for 2–4 compressed HHHH crops comparable to current outputs. These are estimates, not authorized download queues. Inspect metadata first and ask before expected >1 GB or unexpectedly large transfers.

## Local artifacts and transfer audit

| File under 01_NASA_Data_Exploration/quality_audit | Exact bytes |
|---|---:|
| exact_aoi_coverage.tif | 26810 |
| inputDataExceptionMask_20260815.tif | 20550 |
| inputDataExceptionMask_20260827.tif | 20550 |
| mask_20260815.tif | 23930 |
| mask_20260827.tif | 23930 |

New raster outputs total 115,770 bytes. Full quality operations requested 247,463,936 observed byte ranges (20260815 and 20260827); this excludes HTTP/TLS/redirect overhead and is not total wire accounting. No full source HDF5 or HHHH redownload occurred. Exact source names, layer URLs, masks, statistics, SHA256 values and sanitized logs are saved on E: outside Git.

Reproduction utilities remain outside Git: create_exact_aoi_mask.py, full_quality_audit.py, guard_full_quality.py and summarize_full_quality.py. Cached completed masks are reused; current scientific originals must not be overwritten. No additional heavy environment was installed. All Git changes are documentation/license materials only.

Sources: [GCOV specification Rev F, version 1.5.0](https://cumulus.asf.earthdatacloud.nasa.gov/PUBLIC/DATA/NISAR/NISAR_D-102274_RevF_NASA_SDS_Product_Specification_L2_GCOV_w-esigs.pdf), section 4.3.3 and dataset tables; [GDAL access guide](https://nisar-docs.asf.alaska.edu/gdal/); [QA v17.0.0 source](https://github.com/isce-framework/nisarqa/blob/v17.0.0/src/nisarqa/validate/sanity_checks.py). Research preparation only: official local event start plus explicit build authorization remain required.

## October 18 review — no new raster work

Existing scientific evidence is retained; assessment remains CONDITIONALLY_READY. Official provisional issues and isce3 issue 202 were reviewed without identifying a granule-specific resolution. Full-AOI mask coverage is not radiometric/flood validation. See [open questions](research/OPEN_SCIENTIFIC_QUESTIONS.md) and [evaluation plan](planning/SCIENTIFIC_EVALUATION_PLAN.md).

Global FAQ now independently confirms the early challenge-work restriction. Existing project-specific crops, masks and external utilities are frozen pending organizer clarification of reuse. This document preserves historical work; its reproduction steps do not authorize running additional project-specific preparation or reusing it in a submission. See [rules](COMPETITION_RULES_AND_BOUNDARIES.md).
