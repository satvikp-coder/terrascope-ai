# Architecture options — planning only

2026-10-18. These are trade-off notes, not a completed design or implemented component. Full challenge and organizer clarification may change every choice. No endpoints, component files, data loaders, algorithm code or UI screens were created.

| Problem | Candidates / license direction | Benefits | Limits / complexity / hardware / performance | Recommendation and risk |
|---|---|---|---|---|
| Raster science | Existing GDAL; NumPy; optional Rasterio (permissive licenses, verify selected releases) | Reuse proven local tools, explicit units/CRS | Native library compatibility; bounded arrays on 16 GB RAM; medium scientific effort | Local single-process workflow during event; preserve scientific source and provenance |
| User interface | Plain HTML/JS versus React+TS+Vite (MIT) | Plain is small; React useful for experienced team state management | Framework setup costs time; browser cannot absorb arbitrary full raster arrays | Smallest stack team can maintain; no framework commitment now |
| Map | Leaflet (BSD-2-Clause) versus MapLibre GL JS (BSD-3-Clause) | Leaflet simple regional overlays; MapLibre vector/WebGL flexibility | Reprojection/rendered overlays and tile services introduce complexity | Leaflet candidate for one regional demo; independently label preview versus measurements |
| API | No service versus FastAPI (MIT) | Static local results simpler; API supports dynamic queries | Service adds error/security/concurrency work | Add only if required by actual interaction; no endpoints prepared now |
| Data persistence | Local files + small JSON manifest versus SQLite/PostGIS | Files minimize setup and preserve checksums | File consistency versus DB operational/license overhead | No database for two-date AOI MVP |
| Image delivery | Small derived preview versus on-demand tiles/COG access | Preview easiest offline; tiling scales larger data | Browser memory, CRS transformation, access/auth leakage | Keep credentials server/local only; no source signed URLs in browser |
| Analysis | Interpretable statistical baseline versus supervised ML | Baseline explainable without training infrastructure | Either needs physical QA and reference assessment; ML needs labels/time | Select after evidence review during event; no algorithm implemented |
| Visualization | Native map labels/basic chart versus Plotly (MIT) | Simple views lower complexity | Plotly increases bundle/interaction work | Quantitative tables first; chart only if explanatory |
| Explanation/report | Deterministic evidence notes versus optional LLM | Templates can cite exact provenance; LLM may improve language | Hallucination, privacy, API cost and latency | Human-reviewed factual explanation; LLM unnecessary for MVP |
| Reliability | Local files and manual reproducibility checklist versus deployment | Offline demo avoids network/cloud risk | Offline collaboration and install compatibility need planning | Local demonstration first; deployment only after authorized build and review |

Each license is a planning-level identification, not a dependency-lock audit. Before distribution verify exact release LICENSE files and transitive assets; see [third-party notices](../../THIRD_PARTY_NOTICES.md). No package was installed from this comparison. Candidate source repositories: [React](https://github.com/facebook/react), [Vite](https://github.com/vitejs/vite), [FastAPI](https://github.com/fastapi/fastapi), [Rasterio](https://github.com/rasterio/rasterio), [Leaflet](https://github.com/Leaflet/Leaflet), [MapLibre](https://github.com/maplibre/maplibre-gl-js).

Future conceptual flow: permitted source inputs → explicit provenance/quality checks → authorized analysis → independent evaluation → derived display/report. All executable stages remain deferred. A failure to validate the intended flood interpretation should reduce the claim, not trigger fabricated features or measurements.
