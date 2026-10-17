# Draft technical question for ASF — not sent

Subject: P05023 provisional GCOV identification QA errors and joint-mode 40 MHz interpretation

We are researching the following NISAR_L2_GCOV_PROVISIONAL_V1 granules for an exploratory Majuli, Assam AOI:

- NISAR_L2_PR_GCOV_028_040_A_015_4005_DHDH_A_20260815T230527_20260815T230601_P05023_N_F_J_001
- NISAR_L2_PR_GCOV_029_040_A_015_4005_DHDH_A_20260827T230526_20260827T230601_P05023_N_F_J_001

Their QA summaries fail the identification group. Reusing the v17.0.0 identification check reproduces two ERRORs in both: instrumentName is LSAR rather than the validator's L-SAR/S-SAR values, and listOfObservationModes is ['(NOT SPECIFIED)']. Product version 1.0.11, specification 1.5.0, CRID P05023; catalog pgeVersion R05.02.3. Both report ascending/left-looking, dithered joint observations, 40+5 MHz, HH/HV.

1. Is LSAR a known producer convention inherited from upstream products, and is the placeholder observation-mode field a known P05023 metadata defect? Is there an authoritative source for the actual waveform/pulse/PRF-sequence details for these granules, or a corrected release?
2. Do these identification errors affect GCOV radiometric/geolocation interpretation, or only metadata conformance? We found related historical metadata discrepancies in isce3 issue #202, but no resolution specific to these two granules.
3. Which diagnostics or ancillary layers are recommended to assess the documented joint-mode 40 MHz radiometric banding, residual noise, and shadow/layover for quantitative repeat-observation analysis? Their noiseCorrectionApplied, shadowMaskingApplied and validSamplesSubSwathMaskingApplied flags are False. Across our exact AOI, subswath masks are all 1 and exception masks all 0 on both dates; these mask checks alone do not address those effects.

We have not altered source metadata or claimed flooding. We accessed only AOI subsets remotely. Any recommended documentation or corrected-product identifiers would be appreciated.

Intended recipient: ASF User Services, uso@asf.alaska.edu, listed in the [official guide](https://nisar-docs.asf.alaska.edu/provisional-known-issues/). This is a user-sendable draft only; no message has been sent.
