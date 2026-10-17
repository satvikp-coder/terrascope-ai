# QA investigation: CONDITIONALLY_READY

Checked 2026-10-17T20:22:47.340782+00:00, continuing from verified commit 7f483c7. The pair is suitable for future method development **subject to the conditions below**, not approved for flood claims or unmasked quantitative analysis. Both original AOI raster SHA256 values were rechecked unchanged; no new imagery files or full HDF5 scenes were downloaded.

## Identification FAIL explained

Both existing official QA summaries contain one failed aggregate row, `Passes all identification group checks?`; the other recorded summary rows pass. The PDF reports identify QA software 17.0.0 and product specification 1.5.0. Existing extraction logs show successful finished crops and a separately documented/discarded timeout artifact. Extraction success does not override scientific QA.

To identify the component failures, only the original `identification_sanity_checks` and its helper definitions were executed from official `nisarqa` tag v17.0.0, commit `1caca75a4b76ef8ab9c967a1770b32428e1a4733`, against actual remote HDF5 identification groups. Logging/summary sinks and fixed mission constants were supplied locally; no full QA workflow, isce3 installation, model, or raster classifier was run. Fixed-byte dtypes, shapes and values were checked by the original helpers. Each group contains 35 fields. Each produced **exactly two ERROR messages**, reproducing the aggregate FAIL:

| Official check and field under `/science/LSAR/identification/` | Actual value in both scenes | Exact diagnostic, excluding repeated path | Severity and interpretation |
|---|---|---|---|
| `identification_sanity_checks` / `_verify_data_is_in_list`, `instrumentName` | `LSAR` | `Dataset value is 'LSAR', must be one of ('L-SAR', 'S-SAR').` | ERROR: name convention mismatch with the QA validator. The Rev F specification describes an instrument-name string without enumerating these two spellings. This alone does not establish wrong sensor data or invalid radiometry. |
| `identification_sanity_checks` / `_is_valid_observation_mode`, `listOfObservationModes` | `['(NOT SPECIFIED)']` | `Dataset contains value (NOT SPECIFIED), which does not match a pattern like e.g. L:SCI:DH:40M+05N:FS:B4:D02.` | ERROR: field exists but contains placeholder acquisition-mode information; exact pulse/PRF sequence details are not recoverable from this placeholder. |

The exact path-bearing diagnostics and all field dtypes/values are saved outside Git in `01_NASA_Data_Exploration/metadata/qa_investigation/identification_YYYYMMDD.json`. No additional ERROR was emitted by that function for either scene. The historical production QA LOG was not provided in the catalog; these are reproducible component errors from the same released check version, not a claim to have obtained that historical log. Full product XML/schema validation was not rerun.

Non-failing WARNINGs state that granuleId, boundingPolygon, plannedDatatakeId, plannedObservationId and staticLayersDataAccess are populated but not automatically verified, and that hasInputDataException is not covered by that function. Do not turn these warnings into fabricated FAILs. Both flags actually read `hasInputDataException=0`.

## Available quality layers and their meaning

Rev F / product specification 1.5.0, section 4.3.3 (printed page 25, PDF page 34) defines frequency-A/B `mask` values:

- `0`: averaging ensemble includes invalid or partially focused samples.
- `1–5`: fully focused valid samples; value identifies the predominant source subswath. Dithered PRF products use one subswath, so valid areas are expected to be `1`.
- `255`: fill outside radar image bounds.

`inputDataExceptionMask` is a bitwise OR: documented code `0` means no anomaly, bit/code `2` indicates the LSAR qFSP-H1 sample-slip exception. Do not interpret unknown codes as valid. `numberOfLooks` is the adaptive multi-looking sample count, not a flood-confidence score; no universal acceptance threshold is established here. `rtcGammaToSigmaFactor` converts the backscatter normalization convention from gamma0 to sigma0; no conversion was applied. Number-of-looks and gamma-to-sigma layers have NaN fill and valid_min 0; mask fill is 255. An integer zero has different meanings in the two masks.

The four frequency-A datasets sampled here share the same 10 m EPSG:32646 grids in both products. GDAL 3.13.3 accesses only selected remote HDF5 chunks through `/vsicurl/`. Nine non-overlapping 32 x 32 patches at 10%, 50%, 90% positions across the enclosing crop were inspected in memory per layer. This is 9,216 pixels (0.9216 km² of native pixel area) per layer/date, about 0.072% of the crop; it cannot rule out small or unsampled bad regions. No quality GeoTIFF, full mask, or duplicate HHHH crop was created.

| Date | mask counts | input exception counts | numberOfLooks min–max | gamma-to-sigma min–max |
|---|---|---|---|---|
| 20260815 | {'1': 9216} | {'0': 9216} | 2.083149–5.978511 | 0.593223–0.957986 |
| 20260827 | {'1': 9216} | {'0': 9216} | 2.083359–5.978609 | 0.593152–0.959593 |

All successfully sampled floating-point layers were finite and positive. A valid subswath sample does not certify absence of shadow, layover, radio-frequency interference or noise bias. Sparse sample statistics are not whole-AOI quality percentages.

The August 27 GDAL attempts temporarily failed with DNS/timeout diagnostics before any observed range reads. An independent DNS check initially failed for the NASA product host, while an authenticated 16-byte request subsequently returned HTTP 206; this is a transport failure, not evidence of missing raster data. A NETCDF-driver alternative encountered the same DNS failure. After the independent request demonstrated restored access, the HDF5-driver retry succeeded for all four layers. Final GDAL operation logs show 14,942,208 observed requested-range bytes for August 15 and 14,811,136 for August 27 (70.48 and 84.61 seconds). Exact total wire traffic including failed DNS attempts, redirects and HTTP/TLS overhead is not measured. The successful August 27 diagnostics include nonfatal timeout/404 probes, but final GDAL return code is zero and all requested arrays validated. No network settings or TLS verification were changed.

## Dataset and calibration verification

Both unchanged local AOI rasters: 3707 x 3470, Float32, EPSG:32646, affine `(604050,10,0,3001630,0,-10)`, bounds `(604050,2966930,641120,3001630)`. Each has 12,863,290 finite positive pixels. Both grids/CRS/bounds are identical; the previously extracted tiny sample matches corresponding August 15 crop pixels exactly. Grid identity does not independently validate physical co-registration.

Actual HDF5 fields confirm linear-power gamma0 output, beta0 input normalization, radiometricTerrainCorrectionApplied=True, shadowMaskingApplied=False, validSamplesSubSwathMaskingApplied=False and noiseCorrectionApplied=False in **both** scenes. Units are dimensionless `1`, HHHH fill NaN and valid_min 0. Original values were not changed. Calibration-LUT checks passed in the saved QA summaries, with crosstalk LUTs skipped; this is not independent radiometric validation.

Both acquisitions: track 40/frame 15, ascending, left-looking, dithered, full frame, unmixed, joint observation; frequency A/B HH and HV polarizations with HHHH/HVHV terms. Catalog bandwidth 40+5, composite release P05023, catalog pgeVersion R05.02.3, QA PDF softwareVersion 0.25.16, productVersion 1.0.11 and specificationVersion 1.5.0 agree. These version fields are distinct identifiers, not contradictions. Absolute orbits differ (5502 and 5675), as expected for repeat observations. Exact UTC start times are 2026-08-15T23:05:27.000000000 and 2026-08-27T23:05:26.000000000; exact stop times end 23:06:01.999342105 on each date. Catalog stop timestamps are rounded/truncated to seconds.

## Exact AOI versus enclosing crop

The WGS84 rectangle was densified (101 segments per edge), projected to UTM and tested against the crop. The entire polygon is inside the crop, with zero projected polygon area outside. Projected polygon area is 1261.181622 km² versus 1286.329000 km² for the crop. Pixel-center rasterization in memory counts 12,611,824 centres inside the polygon and 251,466 outside it. These exterior pixels must be excluded before future AOI area statistics; polygon area and pixel-center counting are different estimators. No AOI mask was saved or applied to originals.

## Conditions before future analysis

1. Treat the instrument-name discrepancy as a reproduced QA convention mismatch; obtain official clarification before describing the products as fully QA-passed. Recover/confirm meaningful observation-mode details from authoritative source metadata or ASF support; never invent a replacement or edit source metadata.
2. Perform complete AOI quality screening using documented mask semantics when justified, including independent geometry/static-layer information for shadow/layover where available. Sparse samples are only a preparation check.
3. Assess noise-floor effects because noise correction was not applied. Evaluate calibration comparability, incidence/terrain, vegetation/moisture and physical co-registration before interpreting radar differences. Do not apply arbitrary looks/noise thresholds.
4. Use the exact AOI polygon for area reporting. Preserve NaN/fill handling and linear-power units; keep any later derived products separate.
5. Validate future surface-change interpretations with independent contemporaneous evidence and document uncertainty. No flood detection, change statistic, classification, model or application was implemented here.

## Reproduction, storage and sources

Local generic learning utilities in `E:/TerraScope_AI/tools`: investigate_identification.py (bounded 64 KiB range reader, 64 MiB metadata budget/date; isolated official checks), sample_quality_gdal.py / run_quality_sample.py (sparse GDAL samples, 128 MiB observed range budget and 180-second limit/date), check_aoi_coverage.py (read-only originals, in-memory geometry). Only h5py 3.16.0 was added to the existing isolated environment (3.2 MB wheel); the full nisarqa environment was not installed. The official source was shallow-cloned for research under 03_Documentation/reference_nisarqa, and the 1,976,684-byte specification PDF stored under 03_Documentation/nasa_guides. These resources and the utilities are outside the Git repository.

- [Official QA v17.0.0 identification checks](https://github.com/isce-framework/nisarqa/blob/v17.0.0/src/nisarqa/validate/sanity_checks.py), especially lines 257–265, 280–305, 478–482 and 549–692.
- [Official v17.0.0 string/boolean/time helpers](https://github.com/isce-framework/nisarqa/blob/v17.0.0/src/nisarqa/utils/input_verification.py).
- [Official v17.0.0 GCOV 1.5.0 XML specification](https://github.com/isce-framework/nisarqa/blob/v17.0.0/src/nisarqa/product_specs/1.5.0/nisar_L2_GCOV.xml).
- [NASA GCOV Rev F specification, July 8 2026, version 1.5.0](https://cumulus.asf.earthdatacloud.nasa.gov/PUBLIC/DATA/NISAR/NISAR_D-102274_RevF_NASA_SDS_Product_Specification_L2_GCOV_w-esigs.pdf), sections 4.3.2–4.3.3 and identification/grid/processing parameter tables.
- [ASF GCOV guide](https://nisar-docs.asf.alaska.edu/gcov/) and [remote GDAL guide](https://nisar-docs.asf.alaska.edu/gdal/).

No imagery, credentials, cookies, signed URLs or sensitive configuration is included in this Git update. Official event start plus explicit START TERRASCOPE AI HACKATHON BUILD authorization remain mandatory before competition development.

## Final full-AOI audit update

The later full-AOI audit supersedes sparse-only coverage statements above. Both complete crop masks are all 1; exceptions all 0; numberOfLooks all finite/positive. Exact AOI shared mask-qualified coverage is 12,611,824 pixels (100%). Independent pixel-center AOI raster confirms 251,466 exterior crop pixels. The full factor layer was not reread; no normalization conversion was needed. See FINAL_DATA_READINESS.md for counts, storage and remaining scientific limits.

Official isce3 issue #202 documents the same upstream LSAR naming mismatch and missing observation-mode metadata. It supports a producer/convention explanation but remains open and does not resolve the exact August granules or their placeholder mode. The P05023 joint-mode 40 MHz radiometric-banding caveat applies to this acquisition configuration. Dataset status remains CONDITIONALLY_READY; no source metadata was corrected. A support question is drafted, not sent.
