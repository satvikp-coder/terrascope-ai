# Future architecture — planning only

Smallest candidate MVP: two validated AOI rasters, a documented interpretable change statistic, a map showing dates/source provenance, and a limitation-aware report. Validate scientific usefulness before adding AI.

React/TypeScript/Vite suits a small interactive interface; Leaflet is simpler for basic overlays, MapLibre offers richer styling with more setup. FastAPI is reasonable only if dynamic processing is required; precomputed local results may suffice. GDAL/NumPy offer a minimal analysis foundation; Rasterio improves Python raster ergonomics but must share a compatible native stack. A geospatial database and heavy ML frameworks are unnecessary for the initial two-scene demonstration. No application dependencies installed.

Future evidence-grounded summaries should describe measured results and uncertainty, with provenance. Do not fabricate explanations or scores. Confirm challenge requirements after official resource publication before selecting architecture.

## October 18 planning update

Retained as a historical draft. Current trade-offs and gated schedule are in [architecture options](planning/ARCHITECTURE_OPTIONS.md) and [execution plan](planning/HACKATHON_EXECUTION_PLAN.md). Ahmedabad start remains unverified; do not assume 48 build hours or equate submission opening with permission. Global FAQ prohibits early challenge work; no implementation or reuse of ambiguous prepared artifacts is authorized.
