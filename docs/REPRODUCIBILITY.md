# Preparation checklist

- Record OS/tool/package versions and storage root.
- Preserve query AOI/date filters, retrieval UTC and full catalog metadata.
- Record exact granule IDs, URLs, collection/version/maturity and acquisition times.
- Before raster reads: authenticate privately, verify drivers/CRS support and bounded network plan.
- For every future crop: record command, source subdataset, bounds/grid, units, NoData, file bytes and SHA256.
- Verify usable finite pixels, spatial overlap, grid agreement and required quality masks.
- Keep scientific outputs separate from previews, preserve original values.
- Audit staged files for secrets, imagery and oversized artifacts before every push.
- Never assert successful extraction or detection without measured evidence.

## October 18 review — no new raster work

Existing scientific evidence is retained; assessment remains CONDITIONALLY_READY. Official provisional issues and isce3 issue 202 were reviewed without identifying a granule-specific resolution. Full-AOI mask coverage is not radiometric/flood validation. See [open questions](research/OPEN_SCIENTIFIC_QUESTIONS.md) and [evaluation plan](planning/SCIENTIFIC_EVALUATION_PLAN.md).

Global FAQ now independently confirms the early challenge-work restriction. Existing project-specific crops, masks and external utilities are frozen pending organizer clarification of reuse. This document preserves historical work; its reproduction steps do not authorize running additional project-specific preparation or reusing it in a submission. See [rules](COMPETITION_RULES_AND_BOUNDARIES.md).
