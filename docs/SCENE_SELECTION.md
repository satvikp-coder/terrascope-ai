# Verified catalog candidates

Retrieved 2026-10-18 with asf_search 14.1.0; crosschecked against NASA CMR. Query: GCOV PROVISIONAL, supplied Majuli WKT, 2026-08-14T00:00:00Z through 2026-08-29T00:00:00Z, maximum 30. Both services returned 3 products. Full public source responses remain outside Git under 01_NASA_Data_Exploration/metadata. Compact inventory: ../metadata/scene_inventory.json.

Selected for further inspection (not yet scientifically approved):

- `NISAR_L2_PR_GCOV_028_040_A_015_4005_DHDH_A_20260815T230527_20260815T230601_P05023_N_F_J_001`
  - UTC: 2026-08-15T23:05:27Z through 2026-08-15T23:06:01Z; HDF5 7,084,179,456 bytes.

- `NISAR_L2_PR_GCOV_029_040_A_015_4005_DHDH_A_20260827T230526_20260827T230601_P05023_N_F_J_001`
  - UTC: 2026-08-27T23:05:26Z through 2026-08-27T23:06:01Z; HDF5 7,289,700,352 bytes.

Both: collection NISAR_L2_GCOV_PROVISIONAL_V1, track 40, frame 15, ascending, main and side HH/HV, bandwidth configuration 40+5, processor R05.02.3, CRID P05023, orbit type MOE. Both catalog footprint polygons fully cover the AOI, verified geometrically using Shapely. This does not establish valid-pixel coverage. Catalog HHHH browse entries suggest channel availability, but actual HDF5 path remains uninspected.

Excluded third result: August 24, descending track 163/frame 75, configuration 20+5 and quad-pol main band. It is not the same repeat geometry.

Outstanding: actual HHHH path, CRS/grid, units, calibration, quality flags, NoData and valid pixel coverage. No raster comparison or flood interpretation is justified yet. CMR's stop time includes fractional seconds whereas ASF's stopTime is second precision; preserve original metadata when exact timing matters.

Actual-resource probes: unauthenticated HEAD redirected to NASA's CloudFront delivery infrastructure and returned 200, but the subsequent Range bytes=0-15 GET returned 401. HEAD success is not proof of read authorization. No imagery body was read. Credentials are required before further GDAL access.

Sources: https://nisar-docs.asf.alaska.edu/asf-search/ ; https://cmr.earthdata.nasa.gov/search/granules.json ; https://nisar-docs.asf.alaska.edu/gcov/
