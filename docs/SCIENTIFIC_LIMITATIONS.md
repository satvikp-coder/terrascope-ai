# Scientific limitations

Backscatter change is not proof of flooding. Geometry, incidence angle, vegetation, soil moisture, wind-driven water roughness, noise, layover and shadow can alter the signal. Flooded vegetation can brighten while open water can darken. No flood area, confidence, accuracy or ground truth has been measured.

Future work must inspect radiometric conventions and units, calibration/quality flags, valid-data masks, co-registration and grid consistency. Preserve source measurements; keep derived visualization separate. Provisional maturity may affect results.

Potential future validation sources to investigate: temporally matched Sentinel-1 observations, cloud-free optical water evidence, official flood bulletins/maps and river gauge records. Availability, dates, resolution, licensing and independence must be verified before use. No reference observations have been acquired or validated here.

## Verified product-specific limitations

Both scenes are CONDITIONALLY_READY, not fully QA-passed. QA v17.0.0 rejects the LSAR spelling (expects L-SAR/S-SAR) and the NOT SPECIFIED observation-mode placeholder. The latter leaves detailed acquisition metadata incomplete. No raster-invalidity conclusion follows solely from these errors; do not silently repair source metadata.

Actual flags: noiseCorrectionApplied=False, shadowMaskingApplied=False, validSamplesSubSwathMaskingApplied=False, RTC=True. Finite positive HHHH values therefore require independent quality screening. Mask 0 is invalid/partially focused; 1–5 are fully focused subswaths, 255 fill. Exception mask 0 means no documented anomaly; code 2 is sample slip. Sparse sampled quality results cannot establish whole-AOI validity. Number of looks is not confidence and has no chosen universal cutoff here. Shadow/layover, noise-floor effects and physical coregistration remain unvalidated.

The exact projected AOI lies inside the crops, but 251,466 crop pixel centres lie outside the requested polygon. Use polygon membership before future AOI area statistics. Identical native grids do not prove physical registration or flood attribution. See QA_INVESTIGATION.md for evidence and source references.

## Full-AOI audit supersedes sparse coverage limitation

Complete validity and exception masks now cover both entire crops: all valid subswath 1, zero exceptions, no fill/unknown values. Complete numberOfLooks layers are finite/positive, with minima near 0.092 and maxima near 8.519; no universal quality threshold was imposed. This removes the uncertainty about unsampled validity/exception codes, but not shadow/layover, residual noise, RFI, radiometric banding, physical co-registration or event attribution. The directly relevant P05023 joint-mode 40 MHz banding caveat remains. Pixel-center AOI coverage is independently verified, and originals remain unchanged. See FINAL_DATA_READINESS.md and FUTURE_SCIENTIFIC_VALIDATION.md.
