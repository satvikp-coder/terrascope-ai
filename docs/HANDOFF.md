# Handoff

Read PREPARATION_STATUS.md first, then REMOTE_EXPLORATION.md and metadata/raster_validation.json. Repository: E:/TerraScope_AI/05_GitHub_Repository/terrascope-ai; private GitHub terrascope-ai on main. External last_verified_commit.txt records the verified final hash.

Earthdata auth now works. User-profile .netrc separators were repaired; preserve its restricted ACL. Never display credentials, cookie contents, authorization headers or signed redirect URLs. GDAL requires cookie file/jar in protected user temporary storage plus netrc enabled. Both sources were accessed with existing QGIS GDAL 3.13.3, no full HDF5 downloads. Generic exploration/validation scripts remain outside Git in E:/TerraScope_AI/tools; reuse checksummed outputs rather than repeat transfers.

Two requested track 40/frame 15 ascending PROVISIONAL GCOV observations are catalog-verified and HHHH-inspected. Exact source IDs/URLs are in metadata/scene_inventory.json. Check raster_validation.json for actual finished outputs and validity; do not infer completion solely from file existence. Crops preserve linear dimensionless gamma-0 values and native 10 m EPSG:32646 grids. They enclose the WGS84 AOI and are not exact polygon masks. Crop statistics were computed separately from inherited full-scene metadata statistics. Source quality masks and independent validation still require review before interpretation.

Critical scientific caveat: both official QA summary CSVs fail an identification-group check. Grid and calibration-LUT checks pass. QA PDFs do not identify the exact failing test; NOT SPECIFIED observation modes are an unconfirmed lead only. Resolve this before calling the pair scientifically quality-approved. Small official QA PDFs/text stay outside Git; compact summaries/metadata are committed.

Option B only. Ask before expected >1 GB transfers, unusually large output or significant processing. Large data stay on E:, never Git; no full-scene fallback without approval. Logs and metadata remain E:/TerraScope_AI/01_NASA_Data_Exploration. Keep docs and small public metadata only in Git.

Competition application, model and flood detector remain unstarted. Registered local event/start/timezone unknown; detailed challenge resources need recheck. Require verified event start AND exact user text START TERRASCOPE AI HACKATHON BUILD before competition development. Preparatory utilities must not be copied into submission work where prohibited.
