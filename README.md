# TerraScope AI â€” preparation only

Satellite-Based Earth Surface Change Intelligence: research for NASA Space Apps Challenge 2026, Dancing with the SARs. Proposed focus: flooding and surface-water change around Majuli, Assam. This is an unvalidated research direction. No competition application, flood detector, model, backend, frontend, or dashboard is implemented.

See [preparation status](docs/PREPARATION_STATUS.md), [handoff](docs/HANDOFF.md), [access guide](docs/NASA_DATA_ACCESS.md), and [timeline](docs/COMPETITION_TIMELINE.md).

All imagery and tools are outside this repository on the designated USB E: drive. This repository contains preparation documentation and lightweight public catalog metadata only. Never reuse preparatory code as prebuilt submission work where prohibited.

## Official sources

- https://www.spaceappschallenge.org/2026/
- https://www.spaceappschallenge.org/2026/challenges/dancing-with-the-sars/
- https://www.spaceappschallenge.org/legal/
- https://nisar-docs.asf.alaska.edu/asf-search/
- https://nisar-docs.asf.alaska.edu/gdal/
- https://nisar-docs.asf.alaska.edu/access-overview/
- https://nisar-docs.asf.alaska.edu/gcov/

Research access does not imply NASA endorsement. Preserve granule IDs, collection version, maturity, acquisition times, source URLs, and processing provenance for every future raster.

## Verified remote preparation

Earthdata and remote GDAL access now work. Both requested HHHH layers were inspected; tiny and AOI extraction outcomes, exact file sizes and limitations are recorded in [remote exploration](docs/REMOTE_EXPLORATION.md) and metadata/raster_validation.json. No flood/change analysis has been implemented.
