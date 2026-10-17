# Ranked open scientific questions

Reviewed 2026-10-18 against [official provisional issues](https://nisar-docs.asf.alaska.edu/provisional-known-issues/), [GCOV](https://nisar-docs.asf.alaska.edu/gcov/), [nisarqa](https://github.com/isce-framework/nisarqa) and [isce3 issue 202](https://github.com/isce-framework/isce3/issues/202). Existing QA/readiness reports were reused. No expensive revalidation or remote raster read was performed.

| Priority | Unresolved issue | Evidence / effect | Required future action |
|---|---|---|---|
| P0 | Eligibility of prepared inputs/utilities | Global FAQ prohibits early challenge work; prior project-specific preprocessing may be restricted | Organizer ruling before reuse; preserve artifacts and history |
| P1 | Are these dates a verified flood event? | No contemporaneous ground truth or event established; water change is not necessarily flood | Find dated official evidence/reference or restrict claims to surface-change hypotheses |
| P1 | Joint-mode 40 MHz bands | Both P05023 products match documented affected configuration; all-valid masks do not detect radiometric artifacts | Review spatial radiometry and non-event controls during authorized work; reject pair if artifacts dominate interpretable signal |
| P1 | Noise / calibration comparability | noiseCorrectionApplied=False; minimum looks ~0.092 is not calibrated confidence | Obtain noise/uncertainty guidance; no arbitrary cutoff or subtraction |
| P1 | Geometry and physical registration | Identical grid is established; shadow/layover and feature registration are not | Independent stable-feature/geometry assessment; exclude or disclose unreliable areas |
| P2 | Metadata errors | Actual LSAR versus expected L-SAR; NOT SPECIFIED mode in both scenes | Obtain ASF clarification; never edit metadata to pass QA |
| P2 | Version suitability | Current archive pair product 1.0.11 / spec 1.5.0 / CRID P05023 | Check authoritative same-acquisition reprocessing metadata before event; a higher ID alone does not prove superior science |
| P2 | Temporal confounders | Moisture, vegetation/crops, channel changes, wind and incidence may alter return | Research reference conditions and no-event areas; disclose unresolved causes |

The known-issues page still shows July 30, 2026 and does not identify a correction resolving our exact granules. Issue 202 remains open; it discusses upstream missing observation modes and the same instrument spelling in RSLC. That supports a plausible upstream convention issue, not a confirmed resolution of the GCOV placeholder. No newer corrected product for these exact acquisitions was independently established in this review. Do not assert none exists.

Full crop validity/exception/looks coverage already passed; repeating it has little marginal value. No additional project-specific QA execution is justified before organizer clarification. HHHH is not affected by the listed off-diagonal phase rotation, but still has radiometric/geometry limitations. The precise [ASF support draft](../ASF_SUPPORT_QUESTION.md) remains unsent.

Alternative scenes become justified if official corrections supersede this pair, artifacts/registration prevent interpretation, independent evidence cannot support the intended event, footprints/quality fail a later required criterion, or the full challenge requires a different scope. Do not replace dates merely to obtain a visually dramatic difference.
