# TerraScope AI — NASA Space Apps 2026 preparation

**Research and preparation only. No completed competition solution or flood-detection application exists.**

TerraScope AI is a proposed satellite-based Earth surface-change intelligence project for NASA Space Apps Challenge 2026, *Dancing with the SARs*. The exploratory focus is Majuli and the Brahmaputra floodplain, Assam, India. This repository records data-access experiments, scientific QA findings, provenance, environment notes and future plans. It claims no detected floods, model accuracy or validated environmental result.

Current dataset assessment: **CONDITIONALLY_READY**. Two genuine NISAR provisional GCOV observations (August 15 and 27, 2026) have matching 10 m grids. Complete validity/exception checks pass over the exact AOI; metadata warnings, radiometric/geometry limitations and independent event validation remain. See [final readiness](docs/FINAL_DATA_READINESS.md), [scientific limitations](docs/SCIENTIFIC_LIMITATIONS.md), [status](docs/PREPARATION_STATUS.md), and [handoff](docs/HANDOFF.md).

## Preparation boundary

The event is scheduled for November 14–15, 2026. Verify the actual local event start and current rules. Competition development requires both official permission and explicit user authorization. Research notes and learning experiments must not be represented as a completed submission or copied into submission work where prohibited. See [timeline](docs/COMPETITION_TIMELINE.md) and [future validation plan](docs/FUTURE_SCIENTIFIC_VALIDATION.md).

## Data access and reproduction

Use [NASA data access](docs/NASA_DATA_ACCESS.md), [scene selection](docs/SCENE_SELECTION.md), [QA investigation](docs/QA_INVESTIGATION.md), and [reproducibility checklist](docs/REPRODUCIBILITY.md). The documented Windows environment reuses QGIS GDAL 3.13.3 and an isolated asf_search Python environment. Source IDs/URLs and lightweight audit metadata are included; imagery, external learning utilities, virtual environments, caches and private Earthdata credentials are excluded. Local audit outputs remain on the designated external E: drive. No complete HDF5 scenes were downloaded.

## Attribution and licensing

Original project material is under [Apache-2.0](LICENSE); see [NOTICE](NOTICE) and [third-party/data attribution](THIRD_PARTY_NOTICES.md). The license does not relicense NASA/ISRO datasets, publications, software dependencies or agency marks. Data source: joint NASA-ISRO NISAR mission, distributed through NASA ASF DAAC, collection NISAR_L2_GCOV_PROVISIONAL_V1, DOI [10.5067/NIL2GCOV-P1](https://doi.org/10.5067/NIL2GCOV-P1). No NASA or ISRO endorsement is claimed.

Official starting points: [Space Apps 2026](https://www.spaceappschallenge.org/2026/), [challenge](https://www.spaceappschallenge.org/2026/challenges/dancing-with-the-sars/), [legal terms](https://www.spaceappschallenge.org/legal/), [ASF Search](https://nisar-docs.asf.alaska.edu/asf-search/), [GDAL](https://nisar-docs.asf.alaska.edu/gdal/), [NISAR access](https://nisar-docs.asf.alaska.edu/access-overview/), [GCOV](https://nisar-docs.asf.alaska.edu/gcov/), [known issues](https://nisar-docs.asf.alaska.edu/provisional-known-issues/).

[Publication audit](docs/PUBLICATION_AUDIT.md) records security checks and pending visibility approval. No credentials, raw imagery, large rasters or personal contact details belong in repository files.
