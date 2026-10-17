# Verified remote preparation

Earthdata authentication verified with a 16-byte HTTP 206 response and HDF5 signature. The user-profile .netrc had standalone colon separators after login/password; these were removed without changing credential values. The file remains restricted and outside Git and external project storage. No credentials or cookies are included in these artifacts.

Initial GDAL attempts could not recognize the remote file. Adding the documented GDAL cookie file/jar configuration allowed access. Cookies remain in the user's local temporary directory, never Git. GDAL 3.13.3 is used with existing QGIS driver/data/PROJ paths, TLS verification enabled, one worker and bounded caches/timeouts.

Both products expose 46 raster subdatasets, including frequency-A HHHH, frequency-B HHHH, quality masks, numberOfLooks and rtcGammaToSigmaFactor. Frequency-A HHHH in both is Float32, 34704 x 34128, EPSG:32646, origin (415440,3128400), 10 m spacing, dimensionless units 1, NaN fill, valid_min 0. The official GCOV guide identifies these as calibrated RTC gamma-0 power, not decibels. No dB conversion, normalization, smoothing or classification was applied.

Tiny sample: EPSG:4326 window west 94.23, north 27.01, east 94.24, south 27.00. AOI window: west 94.05, north 27.13, east 94.42, south 26.82. gdal_translate -projwin_srs EPSG:4326 -projwin WEST NORTH EAST SOUTH -of GTiff -co COMPRESS=DEFLATE -co TILED=YES uses the exact HDF5 subdataset name discovered from metadata. No output resolution/CRS change is requested; native pixels are selected with default nearest window handling. These are UTM grid-aligned enclosing windows, not exact WGS84 polygon masks. Small exterior strips are possible; future area analysis must use the actual AOI polygon.

Local inspection reads every output pixel to calculate finite/nonnegative counts, crop statistics, CRS, dimensions, bounds and SHA256. Inherited source metadata max_value/mean_value describe the original product and must not be confused with independently calculated crop statistics in raster_validation.json. Native grid matching establishes raster compatibility, not proof of physical co-registration accuracy or flood attribution.

## Output measurements

| File | Bytes | Dimensions | Finite / total pixels |
|---|---:|---|---|
| HHHH_20260815_aoi.tif | 38712699 | 3707 x 3470 | 12863290 / 12863290 |
| HHHH_20260827_aoi.tif | 38414270 | 3707 x 3470 | 12863290 / 12863290 |
| HHHH_20260815_tiny.tif | 38200 | 102 x 112 | 11424 / 11424 |

Identical AOI grids: True. No full source HDF5 downloaded. Logged successful operations requested 250,314,752 bytes of ranges. This is the sum observable in captured GDAL diagnostics, not exact wire accounting; initial probes/first metadata attempt were not fully instrumented. HTTP/TLS/redirect overhead is additional.

## Product QA caveat

Both official 1,441-byte QA summary CSVs report FAIL for "Passes all identification group checks?". Coordinate-grid metadata and calibration-information LUT checks pass (crosstalk LUTs skipped), as do decimated backscatter validity checks. These passes do not negate the identification failure. Both seven-page QA PDFs were retrieved (August 15: 770,309 bytes; August 27: 788,831 bytes); extracted metadata are saved in qa_report_metadata.json. They report left-looking acquisitions, dithered=True, mixedMode=False, hasInputDataException=0, product version 1.0.11, specification 1.5.0 and softwareVersion 0.25.16. Catalog pgeVersion R05.02.3 is a separate field.

The PDFs list observation modes as NOT SPECIFIED, but they do not state which identification check failed. This is a possible investigation lead, not an established cause. Both products remain flagged pending clarification from official QA/schema documentation or ASF support. They are suitable as verified access/extraction experiments; scientific analysis suitability is conditional. Do not describe the pair as fully quality-approved.

## Failed attempt retained for audit

The initial August 15 AOI attempt used 16 KiB remote chunks and hit its 100-second limit. Its 34,212,854-byte partial raster had zero finite pixels and was explicitly marked FAILED_TIMEOUT. Its size and SHA256 were recorded, then the unusable file was removed to reclaim storage. A single corrected retry used the ASF guide's 2 MiB chunk size, a 180-second limit and a 256 MiB observed range-request budget. No automatic full-scene fallback was used. Failed artifact details are retained in raster_validation.json and the failure log.

## Limits and next work

Pixel finiteness is distinct from quality masking. Quality layer presence is confirmed; per-pixel layover/shadow/input-exception screening remains future scientific work. QA summaries, if retrieved, are product checks and do not validate flood attribution. Compare geometry, incidence conditions, vegetation/moisture and independent reference observations before scientific conclusions. No flood-detection algorithm or competition app was developed.

Reproduction: local generic learning utilities remain E:/TerraScope_AI/tools, outside the repository. inspect_remote.py supports --date 20260815 or 20260827, --layer and --crop tiny/aoi; it refuses to overwrite existing rasters. QGIS OSGeo4W Python runs validate_rasters.py. Do not rerun downloads when valid checksummed outputs already exist. remote_operations.json contains recorded commands when available; earlier operations used the same documented command pattern. Authentication values and signed redirect URLs are never logged.

Sources: https://nisar-docs.asf.alaska.edu/gdal/ ; https://nisar-docs.asf.alaska.edu/gcov/ .
