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

## October 18 preparation review and project index

**Repository is PUBLIC following the owner's October 18 instruction.** Five historical personal-author-email commits are retained. No history rewrite or force push occurred.

The [global FAQ](https://www.spaceappschallenge.org/resources/participant-faqs/) now independently confirms the pre-event challenge-work prohibition. Existing project-specific crops, masks and external utilities are frozen for organizer review; eligibility for submission reuse is **not established**. Do not execute the reproduction guides or copy prepared utilities into submission work until the boundary is clarified. Ahmedabad build start is unverified; submission opening does not authorize building.

- Compliance: [rules matrix](docs/COMPETITION_RULES_AND_BOUNDARIES.md), [Ahmedabad draft](docs/AHMEDABAD_CLARIFICATION.md), [challenge requirements](docs/COMPETITION_REQUIREMENTS.md), [timeline](docs/COMPETITION_TIMELINE.md).
- Research: [literature](docs/research/LITERATURE_REVIEW.md), [reference catalog](docs/research/VALIDATION_DATASET_CATALOG.md), [open questions](docs/research/OPEN_SCIENTIFIC_QUESTIONS.md), [user needs](docs/research/USER_NEEDS_AND_EXISTING_SOLUTIONS.md).
- Planning only: [architecture](docs/planning/ARCHITECTURE_OPTIONS.md), [evaluation](docs/planning/SCIENTIFIC_EVALUATION_PLAN.md), [execution](docs/planning/HACKATHON_EXECUTION_PLAN.md), [backlog](docs/planning/PRIORITIZED_BACKLOG.md), [risks](docs/planning/RISK_REGISTER.md), [submission](docs/planning/SUBMISSION_CHECKLIST.md), [cost/performance](docs/planning/COST_AND_PERFORMANCE_PLAN.md).
- People/process: [skills](docs/preparation/TECHNICAL_SKILLS_CHECKLIST.md), [team](docs/team/TEAM_PREPARATION.md), [contributing](CONTRIBUTING.md), [GitHub workflow](docs/GITHUB_WORKFLOW.md), [privacy/publication](docs/GITHUB_PUBLICATION_PLAN.md), [scientific/AI responsibility](docs/SCIENTIFIC_AND_AI_RESPONSIBILITY.md).
- Continuity: [readiness matrix](docs/PREPARATION_READINESS_MATRIX.md), [status](docs/PREPARATION_STATUS.md), [handoff](docs/HANDOFF.md). Earlier detailed future plans are historical drafts; the linked October18 plans govern current preparation decisions, subject to official clarification.

## Superseding owner instruction ? October 18

After the preparation/privacy review, the owner explicitly requested public visibility. Preserve existing history, including the five personal-author-email commits; do not rewrite or force-push. Earlier private-only instructions in this document describe the prior state and are superseded for this publication action. Complete the fresh object scan, push safe documentation, change visibility and verify anonymously. The final verified visibility/commit receipt is recorded in the external handoff directory; never assume success from this plan alone. Competition implementation remains gated and unbuilt.
