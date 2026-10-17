# Future scientific evaluation plan — no analysis executed

## Gates before any claimed result

1. Confirm artifact reuse permission, full challenge fit and build authorization.
2. Preserve source identifiers/checksums, product/processing/maturity, UTC dates, units and exact AOI convention.
3. Assess radiometry/noise/banding, geometry and physical registration. Existing mask-qualified coverage is necessary, not sufficient.
4. Establish the target: radar-change measurement, surface water, or independently supported event inundation. Do not substitute one for another.
5. Acquire appropriately timed independent reference evidence with licensing, resolution and uncertainty documented. Predefine exclusions and reference labeling protocol before tuning a method.

| Future output | Appropriate evaluation | Limits |
|---|---|---|
| Continuous backscatter difference | Units, robust distributions, stable-area consistency, artifact sensitivity, physical registration uncertainty | IoU/F1 are not meaningful without a defined class and reference; a difference is not flood |
| Binary water or event label | TP/FP/FN/TN confusion matrix; precision TP/(TP+FP), recall TP/(TP+FN), F1 2TP/(2TP+FP+FN), IoU TP/(TP+FP+FN) | Undefined denominators must be reported; background-heavy overall accuracy can mislead |
| Reported area | Explicit projected pixel area/exact AOI; probability-sample error/area estimation when defensible; reference uncertainty | Raw classified area is not automatically unbiased flood area or an uncertainty interval |
| Time comparison | Reference-date offsets, stable controls, plausible seasonal context | Two observations do not establish seasonality or causal attribution |

Use spatially separated reference regions; prevent adjacent train/test leakage. If supervised learning is considered, hold out independent labels/locations and keep tuning separate from assessment. For unsupervised methods, do not choose thresholds by maximizing the final test score. Label uncertain/cloud/edge/mixed-reference pixels separately rather than forcing classes. Assess registration sensitivity using predefined positional tolerance and disclose both exact and tolerance-based evaluations; do not use tolerance to hide errors.

No numerical accuracy target is justified yet. Future acceptance requires reproducible outputs, no unaccounted invalid pixels, documented normalization, artifact checks, an independent reference assessment where claims require it, and honest failure/uncertainty reporting. If labels are insufficient, provide exploratory signal evidence and abstain from accuracy/flood-extent claims.

Sensitivity research should cover reference-date mismatch, polygon boundary effects, noise-floor behavior and spatial bands without inventing confidence scores. Compare reference sources for disagreement; HLS and its source optical mission are not independent corroborations. Stratified sampling may need weights; spatial bootstrap/block methods need a defensible design rather than arbitrary pixel resampling.

Presentation disclosures: provisional calibration; metadata errors; joint-mode bands; uncorrected-noise flag; incomplete geometry validation; grid versus physical alignment; reference resolution/time/cloud limitations; no operational warning capability.

Evidence: [Olofsson et al. 2014](https://doi.org/10.1016/j.rse.2014.02.015), [SAR review 2019](https://doi.org/10.3390/rs11070879), [review 2024](https://doi.org/10.3390/rs16040656), [NASA caveats](https://nisar-docs.asf.alaska.edu/provisional-known-issues/). Accessed 2026-10-18; no local experiment or metric value produced.
