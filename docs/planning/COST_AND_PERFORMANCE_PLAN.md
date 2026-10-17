# Cost and performance plan

Windows hardware audited 2026-10-18: Intel Core i7-1355U, 10 cores/12 logical processors; 16,849,256,448 RAM bytes. E: USB Hitachi HDD, NTFS, volume 500,105,736,192 bytes; free 499,667,353,600 at audit. This is the connected ~500 GB drive, not the originally expected 1 TB. No large benchmark or disk modification performed; actual throughput unmeasured.

Two 3707×3470 Float32 arrays require 102,906,320 uncompressed bytes combined (~98.1 MiB); one byte mask ~12.3 MiB. Several intermediate arrays and Python/GDAL caches increase this, but two-date AOI processing should fit 16 GB with bounded operations. This is arithmetic planning, not an application benchmark. Avoid unbounded array copies, worker pools and full-frame products; one process with controlled caches is the starting candidate.

Reuse 38,712,699 + 38,414,270 bytes of original compressed crops on E:. Keep scientific originals unchanged, temporary outputs bounded and derived display separate. HDD seek costs favor sequential/bounded reads; SSD is not required merely for a two-date demo. Consider lossless tiled/DEFLATE/COG only for new authorized derived outputs when access patterns justify it; no recompression/copy is performed now.

Recommended lowest complexity: local processing with existing tools, file manifests, small regional display and offline fallback. No database, paid API, cloud server or LLM is necessary. An API/framework is optional based on team skills and actual challenge needs. Static hosting or a local service can be considered after authorized implementation; no deployment now. Free service limits and tile-provider policies must be checked then; free does not mean unlimited redistribution or tile downloads.

No paid infrastructure, heavyweight packages, imagery transfer or application deployment was created in this preparation. Reference research used small public metadata. Future remote requests must justify new information, estimate transfer including range overhead, keep logs off Git if sensitive, and obtain approval above expected 1 GB. Complete HDF5 downloads remain disallowed.
