# Remote access and reproducibility

Existing Windows tools: Python 3.13; QGIS 4.2.2 GDAL 3.13.3 and QGIS 3.44.12 GDAL 3.13.1. Use the QGIS OSGeo4W environment (bin/o4w_env.bat) so GDAL_DATA, PROJ and driver paths are configured. Direct executable calls emitted a missing GDAL_DATA warning: fix the process environment before raster work. No software reinstallation needed.

Isolated ASF environment: E:/TerraScope_AI/tools/asf-env. Generic catalog experiment: E:/TerraScope_AI/tools/search_metadata.py, intentionally outside Git. It accepts --wkt, --start, --end and --output; searches NISAR GCOV PROVISIONAL, caps results at 30, deduplicates, saves metadata and get_urls() results, and never downloads imagery. For empty output inspect service availability and filters; do not invent granules. On rate limits honor Retry-After; on network/parameter failures consult official docs and retry only after correction. No unbounded retry or automatic query expansion.

Private authentication: standard user-profile .netrc with machine urs.earthdata.nasa.gov and the user's login/password. Never paste credentials into chat, code, logs, external folders or Git. It was absent at initial audit. Protect its Windows ACL. GDAL_HTTP_NETRC=YES; cookie files must stay in protected user temporary storage, outside Git. Keep TLS verification enabled.

Remote sequence, not yet completed: obtain authoritative URL; inspect gdalinfo /vsicurl/ metadata; select the actual HHHH subdataset; test a tiny in-footprint crop; validate dimensions, CRS, bounds, type, NoData and finite valid pixels; then crop only two verified scenes. GDAL >=3.13 supports NISAR HDF5 georeferencing; earlier versions require NETCDF prefix. Use documented -projwin/-projwin_srs or supported WKT cutline options, preserve native grid/values, avoid arbitrary scaling and default reprojection. Record any resampling.

Use bounded cache, one process, timeouts, and monitor bytes. HDF5 range reads can greatly exceed crop size. Stop on unexpected excessive reads; ask before operations expected to exceed 1 GB or take substantial time. Never fallback to a full HDF5 download without permission.

Official guides: https://nisar-docs.asf.alaska.edu/asf-search/ ; https://docs.asf.alaska.edu/asf_search/searching/ ; https://nisar-docs.asf.alaska.edu/gdal/ ; https://nisar-docs.asf.alaska.edu/access-overview/
