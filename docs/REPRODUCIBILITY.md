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
