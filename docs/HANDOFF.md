# Handoff

Read PREPARATION_STATUS.md, FINAL_DATA_READINESS.md and PUBLICATION_AUDIT.md first. Main workspace E:/TerraScope_AI, repository 05_GitHub_Repository/terrascope-ai. Final verified local/remote commit is recorded in 00_Project_Management/handoff/last_verified_commit.txt outside Git.

Scientific status CONDITIONALLY_READY. Both original HHHH crops are intact, 3707 x 3470 Float32 linear gamma0, 10 m EPSG:32646. Complete mask and exception layers now inspected: all validity 1, all exception 0; looks finite/positive throughout. Shared mask-qualified exact AOI 12,611,824 pixels, 100%; not a guarantee against noise, banding, terrain or registration errors. Exact center-membership mask confirms 251,466 pixels outside original WGS84 rectangle. New masks, stats, source URLs and hashes live in 01_NASA_Data_Exploration/quality_audit; logs in logs. Reuse these completed masks and existing HHHH files; do not download full HDF5 products or duplicate originals.

Identification ERRORs: LSAR versus QA L-SAR/S-SAR naming and placeholder observation modes. Official isce3 issue #202 supports upstream convention problems but does not resolve these products. Known P05023 joint-mode 40 MHz banding is relevant. Noise/shadow/valid-subsample correction flags False; RTC True. Future geometry/noise/coregistration/reference checks remain. ASF_SUPPORT_QUESTION.md is only a draft, not sent.

Private Earthdata credentials/cookies stay in standard user-profile locations; never print them or copy them into E:/project/Git. Existing QGIS OSGeo4W GDAL 3.13.3 environment and isolated tools suffice. Generic audit tools stay outside Git, with bounded sequential remote reads. Ask before expected >1 GB or unexpectedly large transfers.

Publication: user wants repo public but then explicitly required complete audit and fresh final confirmation. Keep PRIVATE until that confirmation. No secrets/imagery found in complete historical object audit. Five original commits retain a personal email; do not rewrite history without permission. New commits use GitHub noreply. Apache-2.0 covers original material; third-party/data/agency rights remain separate. No additional contributors were recorded. See PUBLICATION_AUDIT.md and THIRD_PARTY_NOTICES.md.

Competition solution is NOT STARTED. No change classifier, flood method, model or application was built. Registered local event/start/timezone still unknown; verify official event permission and wait for exact user text START TERRASCOPE AI HACKATHON BUILD before competition implementation. Publication approval does not authorize a hackathon build.
