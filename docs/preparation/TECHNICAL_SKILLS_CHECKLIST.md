# Technical skills and environment checklist

Audit 2026-10-18. Installed software is not evidence of a person's proficiency. No teammate skill survey or interviews were conducted; no person is marked already familiar without confirmation.

| Skill | Preparation status | Evidence / next learning task |
|---|---|---|
| Python / NumPy arrays, NaN and memory | Need revision | Existing Python 3.13 exploration environment works; teammate proficiency unknown |
| GDAL subdatasets/range access | Need revision | Prior verified GDAL 3.13.3 reads; study official driver/auth documentation, no new project pipeline |
| CRS / affine transform / alignment | Need revision | Existing audits demonstrate dataset facts, not individual competence; explain grid versus physical registration |
| Rasterio | Need learning | Candidate ergonomic raster I/O; installation not required for current documentation |
| QGIS inspection | Need revision | Existing QGIS 4.2.2 and 3.44.12; learn layer CRS/NoData/metadata concepts |
| Scientific validation and metrics | Need learning | Reference quality/spatial leakage/uncertainty are critical; read evaluation plan |
| Git / review / safe credentials | Need revision | Git 2.53, gh 2.97 authenticated; use noreply identity and targeted staging |
| Basic web mapping | Need learning | Leaflet is a candidate; study docs, no TerraScope component or finished screen |
| React / TypeScript / Vite | Optional | Node/npm are present; choose only if team competence saves event time |
| FastAPI | Optional | Needed only if dynamic local service materially benefits MVP |
| SciPy / Plotly | Optional | Avoid dependencies until a measured analysis/visualization need exists |
| ML frameworks / geospatial database / cloud | Not required for MVP | No training infrastructure or database justified |

Minimum future knowledge: raster interpretation, explicit masks/CRS, NumPy memory handling, evidence-based metrics, simple map rendering and Git collaboration. Generic unrelated tutorials may be considered after rule clarification; this session used conceptual documentation only and created no executable competition exercise.

Primary learning sources: [GDAL](https://gdal.org/en/stable/), [Rasterio](https://rasterio.readthedocs.io/en/stable/), [NumPy](https://numpy.org/doc/), [QGIS](https://docs.qgis.org/), [Leaflet](https://leafletjs.com/reference.html), [FastAPI](https://fastapi.tiangolo.com/), [React](https://react.dev/learn), [Git](https://git-scm.com/docs). These are study references; no claim that every tutorial was completed.

Fresh version checks: Python 3.13.5; GDAL 3.13.3; asf_search 14.1.0; h5py 3.16.0; NumPy 2.5.4; Git 2.53.0.windows.2; GitHub CLI 2.97.0; Node v24.12.0; npm 11.6.2. No installs performed.
