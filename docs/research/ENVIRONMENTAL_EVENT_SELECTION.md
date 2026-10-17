# AU404 / TerraScope AI — environmental event selection

**Research date:** 2026-10-18 IST. **Starting commit:** 730eb95f4db2cc8ba7f24514dfd4aa8beaaf5536, clean main; repository public. Team name is **AU404**; TerraScope AI is the project. This report adds source/metadata research, not a flood result, final AOI, processing method or application.

## 1. Executive summary

**Provisional recommendation: prioritize Option B — the July 19, 2026 Upper Assam flood in the Sivasagar/Nazira area. Retain Majuli and its original images as a preserved exploratory fallback. Do not finalize a flood-study polygon or describe any pair as fully validated yet.**

The strongest catalog candidate is NISAR **July 10, 23:05:29 UTC → July 22, 23:05:28 UTC**, ascending track 040/frame 015, provisional GCOV, matching catalog HH/HV, joint observation and 40+5 MHz configuration. Both catalog footprints cover both defined Nazira/Sivasagar and Teok/Jorhat search boxes. July 10 precedes the documented July 19 wave; July 22 falls during the active flood period documented by July 22–23 government reports. This is a **pre-event versus active-wave** comparison, not a dry-versus-peak proof or a post-recession pair.

Official daily reports provide materially stronger dated evidence for Nazira and Teok than for an August 15–27 event in Majuli. A Sentinel-1D same-track reference pair on July 10/22 partially overlaps the Nazira box and includes its centre, improving corroboration prospects. It does not cover the full box or establish ground truth. New July NISAR QA summaries still fail the identification group; exact component causes are unverified, and the joint 40 MHz caveat remains.

**No candidate passes every final scientific gate.** Affected boundaries, pixel-level quality, physical registration and radiometric interpretability remain unresolved. The defensible decision now is a research priority, not a certified study-area selection or download authorization. Existing Majuli scientific assessment remains CONDITIONALLY_READY. New July pair status: **CATALOG_MATCHED_NOT_RASTER_VALIDATED**.

## 2. Methodology and verification labels

Read existing README, HANDOFF, PREPARATION_STATUS, FINAL_DATA_READINESS, QA_INVESTIGATION, FUTURE_SCIENTIFIC_VALIDATION, SCIENTIFIC_LIMITATIONS and COMPETITION_REQUIREMENTS. Reused prior grid/mask evidence without repeating raster QA. Confirmed the organizer and ASF messages remain drafts; no sent-message evidence exists in the handoff.

Searched official Assam/ASDMA/NRSC/CWC sources, dated reporting and primary research for Majuli erosion/water changes in the exact August interval and the July Upper Assam flood. Followed the ASDMA official index to its public date-selected DRIMS reports; retrieved seven small government PDFs, parsed them locally with existing software and recorded hashes. Distinguished report *as-of* dates from export dates and news publication dates. Queried documented `asf_search` filters with explicit AOIs/time intervals and finite result limits. Only catalog footprints and lightweight QA/ISO sidecars were examined; no image data or browse thumbnails were requested.

- **VERIFIED:** direct evidence supports the stated, bounded fact (for example catalog coverage or an official administrative flood report).
- **PARTIALLY_VERIFIED:** evidence is relevant but lacks exact boundary, timing, independent validation or measurement detail.
- **UNVERIFIED:** sufficient evidence was not established; not equivalent to evidence of absence.
- **CONTRADICTED:** a specific claim conflicts with reliable evidence; scope of conflict must be stated.

All sources below were accessed 2026-10-18 IST. Compact sanitized queries, exact IDs, footprints, source URLs, QA rows, document hashes and reference catalog records are in [event_selection_metadata.json](event_selection_metadata.json). Raw PDFs/XML/catalog responses remain on E: outside Git. No private website session values, personal contacts from reports or restricted ancillary URLs are published.

## 3. Option A — Majuli, August 15–27

Original AOI: `POLYGON((94.05 26.82,94.42 26.82,94.42 27.13,94.05 27.13,94.05 26.82))`, EPSG:4326. Existing crops are preserved. The bounding rectangle is not a Majuli administrative boundary and can include river/channel and adjoining land; district-wide reports cannot label its pixels.

### A1. Evidence and geographical checks

| Phenomenon / source | What the evidence establishes | Exact interval / AOI status |
|---|---|---|
| District government [profile](https://majuli.assam.gov.in/about-us/district-profile), updated April 29, 2026 | Historical flooding, erosion, sand deposition and ecological change are real regional processes | VERIFIED background; UNVERIFIED August15–27 transformation inside our polygon |
| [PIB June1 release](https://www.pib.gov.in/PressReleasePage.aspx?PRID=2267496&lang=2&reg=48) | A long-term palaeoenvironmental study addresses Majuli fluvial/vegetation history | Millennial record, not this acquisition interval; cannot supply 2026 labels |
| [Xue et al. 2025, DOI 10.3390/rs17060944](https://research.birmingham.ac.uk/en/publications/planform-change-and-its-delayed-response-to-discharge-in-an-activ/) | Landsat-based 1990–2020 planform change and delayed response to discharge | VERIFIED research context; no measured 12-day displacement in August2026; abstract/institutional record reviewed, not a replicated result |
| [August13 erosion article](https://prime24seven.com/news/erosion-in-majuli-brahmaputra-riverbank-erosion-threatens-historic-vaishnavite-satras/) | Search-indexed supplementary report of intensified erosion threatening Satras; direct page timed out | PARTIALLY_VERIFIED report only; predates our first image, lacks a usable event polygon/displacement/time series; not sufficient evidence |
| Official DRIMS flood reports as of August15 and27 | Neither lists Majuli as an affected district; both identify continuing effects in Jorhat/Sivasagar | VERIFIED report contents; UNVERIFIED absence of inundation inside every part of our AOI or on intervening dates |
| Official erosion reports August16 and27 | August16 erosion-area/affected-circle entries are Nil; Majuli infrastructure entries are also Nil. August27 reports other districts, not Majuli | No positive interval-specific Majuli erosion evidence; missing/Nil reports do not prove zero erosion |
| [Mint September4 feature](https://www.livemint.com/mint-lounge/art-and-culture/climate-change-assam-craft-textile-majuli-salmora-pottery-masks-weaving-eri-muga-silk-11788497391640.html) | Explicitly reports Majuli had not experienced flooding that year; discusses long-term livelihood/erosion changes | Supports caution about a major island-wide event; not a hydrological survey of our polygon |
| [July20 ferry report](https://www.nationpress.com/national/assam-floods-cut-off-majuli-island) / [July30 broader commentary](https://www.newslaundry.com/2026/07/30/at-least-75-dead-7-lakh-displaced-the-making-of-assams-annual-unprecedented-flood) | Ferry-ramp/access flooding and broad lists can mention Majuli | Different timing/geographical scope; does not establish a new August15–27 inland flood |

The [August16 Scroll analysis](https://scroll.in/article/1095046/upper-assams-flood-catastrophe-is-a-direct-result-of-river-and-mountain-grabbing) distinguishes embanked interiors from long-inundated riverside areas. Thus claims that Majuli was entirely dry versus broadly affected are not safely resolved by choosing a headline. **A major August15–27 flood inside the exact AOI remains UNVERIFIED**, while treating regional Assam flooding as proof of it is not supported by the sources' limited geographic specificity.

Important false-positive source match: the July23 DRIMS report mentions **No.5 Majuli village under Udalguri**, with longitude about **92.175871**, not Majuli island near 94.05–94.42. That infrastructure incident is outside our AOI and is rejected as evidence for this study. A village name alone is not a geographic match.

### A2. Can two GCOV observations demonstrate another change?

| Candidate phenomenon | Physical plausibility | What is missing |
|---|---|---|
| Bank erosion / channel migration | A large actual bank displacement could affect a resolved water/land boundary | No independently dated displaced bankline or displacement magnitude; changing water stage can mimic bank retreat |
| Sandbar emergence / submerged bars | Water-level and wet-sediment differences could alter radar response | Need contemporaneous stage, exposed-sediment reference and persistence; emergence is not necessarily sediment deposition |
| Seasonal water extent | Potentially suitable for exploratory two-date visualization | No verified local water-transition geometry; seasonal plausibility does not prove a transition |
| Vegetation/crop/moisture changes | L-band may respond to structure and moisture | No dated crop/vegetation reference; signal is non-specific and confounded with water/noise/geometry |
| Other surface transformation | None independently established in this interval | Do not invent an alternative phenomenon to justify already-prepared imagery |

Ten-metre **grid spacing** does not guarantee detection of a ten-metre bank shift. Effective resolution, speckle, point-spread effects, stage, mixed pixels, registration and positional uncertainty matter. Long-term erosion rates cannot be linearly prorated into a defensible 12-day prediction. No radar differences or transformation maps were computed.

### A3. Suitability conclusion

**PROMISING_BUT_UNVERIFIED** for exploratory surface/river-change research; **weak evidence for any specific August15–27 physical event**, and not suitable as a verified flood case now. Advantages: existing intact rasters, identical verified grids and complete prior mask-qualified overlap; no new image transfer for reuse if organizers permit. Disadvantages: no interval-specific causal/reference evidence, potential subtle changes, known banding/noise/geometry issues and difficult attribution. Retain as fallback, not as an assumed winner or claimed result.

## 4. Option B — documented July Upper Assam flood

### B1. Event chronology and independent evidence

The event most strongly established in the searched Assam material is the wave beginning around **July19**, affecting **Sivasagar/Nazira and Jorhat/Teok**, with major inundation reported July20–24. Peak timing differs by locality and is not established for a final polygon. July27 government reporting describes recession in many places, while administrative impacts persist into August; ongoing relief/damage totals are not evidence of standing water at every later date.

Official DRIMS as of July10 lists **Dhemaji only** as affected. This supports choosing July10 as a baseline before the July19 wave in the shortlisted circles, but does not prove every future baseline pixel was dry. July22 reports **126 affected villages in Nazira** and **67 in Teok**; July23 reports **126 and70**, respectively. These are reported administrative counts, not mapped flood area or TerraScope measurements. Use the circle boundaries/affected-village geometry before final AOI selection.

The [July20 Akashvani report](https://newsonair.gov.in/assam-floods-rescue-operations-continue-amid-rising-water-levels/) documents active rescue/inundation in Sivasagar, Charaideo and Jorhat. The [August6 government broadcaster report](https://newsonair.gov.in/union-minister-j-p-nadda-assures-centres-full-support-to-flood-hit-assam/) specifically identifies Nepalikhuti/Nazira and dates the wave to July19. The [July30 central assessment report](https://newsonair.gov.in/inter-ministerial-central-team-assesses-flood-damage-in-assams-worst-affected-districts/) independently supports these district-level impacts. These establish actual inundation, rather than just rain or a warning.

Supplementary [July25/28 Indian Express reporting](https://indianexpress.com/article/explained/explained-climate/assam-floods-2026-causes-explained-10802845/) identifies inundated Nazira/Sivasagar areas and Teok imagery; [ANI/Reuters July21 photo metadata](https://www.reutersconnect.com/item/floodwaters-inundate-houses-in-assams-jorhat-villagers-assess-damage/dGFnOnJldXRlcnMuY29tLDIwMjY6bmV3c21sX01UMUFTTkVXUzIwMjYwNzIxMzkyTA) identifies Teok inundation. Photo rights are restricted; no photograph was downloaded or redistributed. Do not infer the entire district or search box was flooded.

### B2. Breadth of screening

Jorhat, Sivasagar, Charaideo, Dibrugarh, Dhemaji, Lakhimpur and other floodplain districts were screened through dated government reporting/daily-report entries. July20 coverage identifies the wider affected region; July22/23 reports document several circles in Dibrugarh and other districts. Dhemaji was already affected July10, weakening an assumed dry baseline for the proposed pair there. A specific Lakhimpur event polygon/date pair was not established. None of these broad mentions was promoted to a validated candidate without precise evidence.

NDEM/NRSC/Bhuvan were checked for a dated 2026 Assam inundation product. A usable July2026 official GIS/reference map was **not retrieved**. Search results included 2024/2025 maps; they were rejected as this event's reference. Portal current-event headlines are not a historical flood polygon, and some services are intended for authorized users. No restricted service was bypassed or hypothetical map URL constructed.

Expansion outside Assam was unnecessary for this shortlist because two independently documented affected Assam localities have a catalog-matched pair. This is not a nationwide claim of optimality. Outside-India events were not needed to manufacture a winner; if local reference/quality gates fail, widen the documentary search before any imagery request.

## 5. Official source and publication-date catalog

| ID / source URL | Publication / generation date versus event date | Geography / claim status / limits |
|---|---|---|
| G1 [ASDMA index](https://asdma.assam.gov.in/information-services/detail/assam-flood-report) → [DRIMS](https://sdrf.assam.gov.in/dfr/) → [flood date form](https://sdrf.assam.gov.in/dfr/download?type=flood) | Retrieved exports for as-of July10,22,23 and August15,27 | VERIFIED official report contents; aggregated district/circle data, not pixel truth |
| G1a July10 report | As-of July10; generated July10 16:47 | Dhemaji only listed; Nazira/Teok baseline is before later wave, not guaranteed dry |
| G1b July22 report | As-of July22; export footer generated **September28 15:30** | Retrospective export/revision possibility; preserve hash; do not call it contemporaneously published July22 |
| G1c July23 report | As-of July23; export footer generated **August28 18:17** | Same retrospective-export limitation; 8AM CWC bulletin referenced, direct CWC record not independently obtained |
| G1d August15 /27 reports | Generated same dates at19:40 /18:09 | Majuli not listed; other affected circles still listed; snapshot absence is not proof of zero water |
| G2 [erosion date form](https://sdrf.assam.gov.in/dfr/download?type=erosion) | As-of August16 /27; August16 export lacks a generated footer; August27 17:51 | No positive Majuli event in these snapshots; not a complete daily interval census |
| G3 [Akashvani July20](https://newsonair.gov.in/assam-floods-rescue-operations-continue-amid-rising-water-levels/) | Published July20 13:50; active conditions July19–20 | VERIFIED government broadcaster account of affected districts; not a flood polygon |
| G4 [Akashvani July27](https://newsonair.gov.in/assam-flood-situation-improves-as-waters-recede-across-affected-districts/) | Published July27 12:46; recession then, not event end everywhere | VERIFIED reporting, supports using July22 instead of assuming late-August flood peak |
| G5 [Akashvani August6](https://newsonair.gov.in/union-minister-j-p-nadda-assures-centres-full-support-to-flood-hit-assam/) | Published August6 09:02; refers to July19 onset and later visit | VERIFIED specific affected locality Nazira/Nepalikhuti; no georeferenced perimeter |
| G6 [Akashvani July30](https://newsonair.gov.in/inter-ministerial-central-team-assesses-flood-damage-in-assams-worst-affected-districts/) | Published July30 08:40; July29 assessment / July19 trigger | VERIFIED regional impact, no pixel labels |
| G7 [NRSC NDEM](https://ndem.nrsc.gov.in/) / [ASDMA NRSC index](https://asdma.assam.gov.in/resource/inundation-mapping-nrsc) | Portal/index dates are not July2026 map publication dates | Accessed public pages; July reference geometry UNVERIFIED; authorization restrictions respected |
| G8 [CWC service](https://www.cwc.gov.in/en/flood-forecasting-services) | Direct historical bulletin inaccessible in web attempt | UNVERIFIED independent stage series; ASDMA's reported gauge status is indirect evidence |
| M1 [Majuli government profile](https://majuli.assam.gov.in/about-us/district-profile) / [PIB](https://www.pib.gov.in/PressReleasePage.aspx?PRID=2267496&lang=2&reg=48) | April29 /June1; historical processes | VERIFIED background, no interval event |
| M2 [Xue et al. institutional publication](https://research.birmingham.ac.uk/en/publications/planform-change-and-its-delayed-response-to-discharge-in-an-activ/) | Published March7,2025; 1990–2020 observations | VERIFIED bibliographic/abstract evidence; no August2026 event |
| M3 [Mint](https://www.livemint.com/mint-lounge/art-and-culture/climate-change-assam-craft-textile-majuli-salmora-pottery-masks-weaving-eri-muga-silk-11788497391640.html) | September4,2026; broader seasonal statement | Directly accessible article; provides contrary seasonal reporting, not a polygon-specific survey |

For the date-form sources, URLs require choosing a date and submitting the normal form; there is no invented permanent PDF link. Exact seven filenames, byte counts and hashes are in supporting metadata; PDFs stay outside Git. Report timezones are interpreted as local IST based on the government context; the printed footers do not explicitly label a timezone. Neither first-publication dates nor revision history of exported daily reports were independently established.

## 6. ASF acquisition matching and reference availability

### Preferred NISAR pair — authoritative exact identifiers

**Baseline:**

`NISAR_L2_PR_GCOV_025_040_A_015_4005_DHDH_A_20260710T230529_20260710T230603_P05023_N_F_J_001`

UTC start **2026-07-10T23:05:29Z**; IST **July11 04:35:29**. About eight days before the July19 wave. A July10 daily report is earlier than this acquisition, not a coincident dry reference.

**Active-wave candidate:**

`NISAR_L2_PR_GCOV_026_040_A_015_4005_DHDH_A_20260722T230528_20260722T230602_P05023_N_F_J_001`

UTC start **2026-07-22T23:05:28Z**; IST **July23 04:35:28**. Within the independently documented active wave, not necessarily the local maximum. July23's reported 8AM gauge context follows the acquisition by about3h25m; administrative totals are not instantaneous water maps.

Both: NISAR L-SAR, GCOV, collection NISAR_L2_GCOV_PROVISIONAL_V1, ascending track40/frame15, HH/HV A and B, main40MHz /side5MHz, jointObservation=True, full catalog frame, CRID P05023, catalog processor R05.02.3. ISO sidecars independently report **Left** look direction and40,000,000/5,000,000 Hz range bandwidths. Full waveform/PRF and raster grid/resolution/NoData were **not inspected for these July products**. Matching catalog settings are not proof of identical pixel grids or complete acquisition-mode metadata. No July product/specification version is inherited from August without evidence.

Both QA CSVs: open-file, grid-metadata-cubes, calibration-LUT and completion checks PASS; crosstalk LUTs skipped; identification group FAIL; backscatter validity check PASS on **decimated** data. The two exact August identification errors must not be assumed to explain the July failures. AOI masks, pixel validity, full HHHH dataset paths, source-processing flags and physical registration remain unchecked for July. The catalog includes HHHH-associated product metadata, but no layer read was performed.

Source HDF5 sizes in catalog: baseline **7,088,373,760 bytes**, event **7,084,179,456 bytes**. **Neither was downloaded.** Authoritative catalog URLs are recorded, not constructed.

### Query scope and rejected alternatives

The two boxes below are analyst-defined **discovery boxes, not official affected boundaries or final AOIs**:

- B: Nazira/Sivasagar `94.55,26.84,94.83,27.04` (west,south,east,north).
- C: Teok/Jorhat `94.27,26.74,94.46,26.94`.

Queries: dataset=NISAR, processingLevel=GCOV, dataMaturity=PROVISIONAL, July7–27 UTC, maxResults30. B returned7 and C4; neither limit was reached. Results deduplicated to7 unique products. Both track40 catalog footprints cover both entire boxes; this is geometric metadata coverage, not valid-pixel or flood coverage.

Reject for the primary comparison: track62/frame75 July12 quad-pol20+5 versus July24 dual-pol40+5; track163/frame75 July7 quad-pol20+5 versus July19 dual-pol40+5. These pairs have configuration changes, and the July19 observation has ambiguous timing relative to rapid local onset. Track112/frame15 July15 lacks a same-track during-wave mate in this bounded search. Do not pair ascending and descending observations merely because dates are closer.

### Independent reference candidates actually found

ASF Sentinel-1 GRD_HD query for B July20–25 found:

`S1D_IW_GRDH_1SDV_20260722T113958_20260722T114023_003786_006CD7_FA7E`

Baseline July8–12 found:

`S1D_IW_GRDH_1SDV_20260710T113957_20260710T114022_003611_0066E3_AE4E`

Both ascending relative track70/frame1267, VV+VH, with acquisitions about11h25m before corresponding NISAR dates. Each partially overlaps B and covers its box centre; neither fully covers B. The event scene does not intersect C. A separate C July20–25 query returned zero GRD_HD records. This bounded absence does not rule out other Sentinel-1 products, dates or optical sources.

Sentinel-1 C-band VV/VH and NISAR L-band HH/HV require sensor-specific interpretation and normalization. They share radar ambiguities; agreement is corroboration, not independent field truth. Footprints do not prove all affected villages are included. No reference pixels were downloaded or classified.

CMR HLS2.0 query over combined B/C bbox94.27,26.74,94.83,27.04 for July20–25 returned2 L30 records (July23,97–100% tile cloud) and4 S30 records (July21,55/66%; July23,89/95%). All hits fit page_size20. Pixel QA and local cloud-free coverage are unverified; optical references are possible but uncertain. Different timestamps, resolution30m, shadows and mixed pixels limit comparisons with a prospective NISAR grid. Do not count HLS and its source Landsat/Sentinel-2 as independent references.

## 7. Scientific comparison and gates

Known NISAR [provisional limitations](https://nisar-docs.asf.alaska.edu/provisional-known-issues/) still matter: joint40MHz residual bands, RFI/ripples and limited global calibration/validation. The new pair is not shown to be cleaner than the existing pair. July mask/geometry/noise flags remain uninspected. A different event improves event evidence, not necessarily sensor quality.

| Mandatory gate | A: Majuli August | B: Nazira July | C: Teok July |
|---|---|---|---|
| Independent phenomenon at relevant place/time | UNVERIFIED exact interval | VERIFIED revenue-circle/locality flood; final affected polygon UNVERIFIED | VERIFIED revenue-circle/locality flood; final affected polygon UNVERIFIED |
| NISAR affected-area coverage | Existing AOI verified; transformation location unknown | Catalog boxes covered; actual affected boundary/pixels PARTIALLY_VERIFIED | Same limitation |
| Appropriate timing | No established event transition | Pre-wave / active-wave supported; exact local stage not mapped | Pre-wave / active-wave supported; exact local stage not mapped |
| Reasonable comparability | Grid/mode known; science incomplete | Matching catalog+look; waveform/grids/registration/quality incomplete | Same July pair; incomplete |
| Quality limitations documented | Yes; unresolved | Yes, aggregate identification FAIL and bands; exact component issues unknown | Same July pair |
| Final verified study-area decision | **Not passed** | **Not passed** | **Not passed** |

### Transparent feasibility scores

Scores0–5 are qualitative **research-priority judgments**, not measured accuracy, probabilities or gate overrides.0 means absent evidence;5 would require strong local evidence with relevant coverage/feasibility. Enough catalog and administrative evidence exists for provisional prioritization, not a final scientific ranking. Weighted total=sum(weight×score), out of5 (percent shown only as rescaled points).

| Criterion / weight | A | B | C | Evidence-based reason |
|---|---:|---:|---:|---|
| Independent event evidence25% | 1 | 4 | 4 | A has historical process evidence only; B/C dated official active-flood circles, no exact polygons |
| NISAR temporal/spatial coverage20% | 3 | 4 | 4 | A grids proven but event timing absent; B/C catalog pair brackets wave, new pixel coverage unverified |
| Scientific interpretability20% | 1 | 2 | 2 | A unspecified cause; B/C documented flood but bands/noise/vegetation/registration remain |
| Independent references15% | 1 | 3 | 2 | A no interval reference; B partial matched S1 pair plus reports; C reports and cloudy optical, no S1 hit in tested interval |
| Hackathon feasibility10% | 4 | 3 | 3 | A preparation already verified; B/C require new authorized crops/QA/reference work; reuse permission unresolved for all |
| Storage/processing10% | 5 | 3 | 3 | A no new imagery needed if permitted; B/C require two small future remote crops and selected references |
| Weighted score | **2.10/5 (42/100)** | **3.25/5 (65/100)** | **3.10/5 (62/100)** | Scores do not certify science |

B leads C only through currently found partial Sentinel-1 corroboration. This0.15/5 margin is weak: if its reference advantage disappears, they tie. A clear, dated Teok reference could change their order. Neither new locality gets credit for unverified good pixels or promised accuracy. If all final gates fail, select none and narrow the project claim rather than force a winner.

## 8. Ranked shortlist

### 1 — B: Nazira/Sivasagar, July19 wave (preferred research lead)

- Phenomenon: documented flood inundation, with subsequent sediment/damage confounders.
- Timing: onset aroundJuly19; major impacts July20–24; some recession byJuly27, variable later impacts. Exact local peak/end unknown.
- Evidence: DRIMS July22–23 circle entries; government broadcaster July20/August6; dated supplementary Nazira reporting. Sources above.
- NISAR: exact July10/22 track040/frame015 pair above; both box footprints covered, matching catalog configuration/Left look. During-wave stage, not simply after-event.
- References: matched partial Sentinel-1D70/1267 July10/22; official administrative reports; cloudy HLS candidates; no retrieved official GIS flood perimeter.
- Additional data: **two different NISAR AOI HHHH crops eventually required**, plus minimum quality/geometry metadata and selected references. Existing August Majuli rasters cannot substitute.
- Complexity: medium, qualitatively estimated; source-science and independent reference work dominate. Strength: best event/timing/corroboration combination. Weakness: exact affected geometry and radiometric quality unresolved.
- Recommendation: **strongest provisional lead, not verified final study area**. Identify an officially affected open-floodplain subarea within both NISAR and S1 footprints before fixing its boundary; do not choose only a visually dramatic or sediment-buried village.

### 2 — C: Teok/Jorhat, same July19–24 wave

- Phenomenon: flood inundation documented by circle reports and dated Teok journalism/photo metadata.
- NISAR: same July10/22 pair and track/frame; no additional source scenes compared with B, but different future AOI crop/reference coverage.
- References: official circle reports, July21 inundation photo metadata (no reuse rights assumed), high-cloud optical candidates. Separate bounded S1 GRD_HD query returned0. No flood boundary verified.
- Additional data: two new authorized AOI crops plus quality/reference subsets; medium complexity. More precisely geolocated references could make C preferable to B.
- Recommendation: **credible provisional alternative**; currently weaker reference-catalog support. Do not mistake relief-camp locations for inundated land or treat whole Teok as submerged.

### 3 — A: existing Majuli August15–27 surface/river research

- Phenomenon: possible water/bar/bank/vegetation change; no specific transformation established for this interval.
- Existing exact scenes:
  - `NISAR_L2_PR_GCOV_028_040_A_015_4005_DHDH_A_20260815T230527_20260815T230601_P05023_N_F_J_001`
  - `NISAR_L2_PR_GCOV_029_040_A_015_4005_DHDH_A_20260827T230526_20260827T230601_P05023_N_F_J_001`
- Track040/frame015 ascending; both originals already stored, aligned3707×3470,10m spacing,EPSG32646; exact12,611,824 mask-qualified centres. Existing QA evidence retained unchanged.
- References: historical geomorphology and mixed seasonal reporting, not direct interval labels; prior HLS catalog highly cloudy. No new imagery required merely to retain this fallback.
- Complexity: low additional data-access effort but **high attribution/validation difficulty**. It is cheaper to access, not automatically easier to prove scientifically.
- Recommendation: retain preserved exploratory fallback; PROMISING_BUT_UNVERIFIED, no verified flood/erosion conclusion. A longer documented interval might eventually be more defensible for geomorphology, but no replacement dates were invented or downloaded.

## 9. Final recommendation and unanswered questions

1. **Retain or move?** Move the *research priority* to OptionB, Nazira/Sivasagar July flood; preserve Majuli. Final location/polygon remains provisional until affected geometry/reference/quality gates are met.
2. **Strongest actual event?** The July19 Upper Assam flood, with direct official affected-circle evidence for Nazira and Teok aroundJuly22–23. This is stronger than an assumed August Majuli transition.
3. **Best NISAR pair?** July10T23:05:29Z andJuly22T23:05:28Z, track040/frame015, exact IDs above. Catalog comparability is established; pixel/scientific suitability is not.
4. **Do we have images?** No for the recommended dates/area: we have only August Majuli crops. Two new AOI crops would eventually be needed after separate permission and compliance clearance. Do not crop/download now.
5. **Official evidence?** DRIMS dated reports and government broadcaster accounts establish actual flood impacts, not just rainfall; see source catalog and export-date caveats.
6. **Biggest science risk?** Demonstrating that a radar transition at the final AOI is genuinely the documented inundation at acquisition time, rather than bands/noise, geometry, sediment, vegetation/moisture or other effects, with insufficient independent spatial reference.
7. **Next now?** Obtain an authoritative July22–23 affected-village/flood boundary or appropriately dated reference, clarify exact locality and overlap, and resolve metadata/quality questions through the unsent ASF draft if owner approves. No application work is needed to settle these.

## 10. Downloads, provenance and resource decision

**NO_NEW_SATELLITE_IMAGERY — metadata/document research only.** No HDF5 scene, GeoTIFF, browse image, reference image, archive, model or processing environment downloaded/installed. No original imagery modified. No competition algorithm or scientific map produced.

Seven government report PDFs total **5,390,080 bytes**; four NISAR metadata sidecars (two CSV+two ISO XML) total **237,317 bytes**. These are documents/metadata, not satellite measurements. Small catalog JSON/HTML/text receipts additionally reside on E:; exact network/TLS overhead was not measured. PDFs/XML stay outside Git; only own report and sanitized lightweight metadata are committed. Full candidate HDF5 pair totals **14,172,553,216 bytes**, explicitly not requested.

External evidence locations:

- `E:/TerraScope_AI/03_Documentation/event_selection_20261018`: government PDFs/text/hashes and public archive-page receipts.
- `E:/TerraScope_AI/01_NASA_Data_Exploration/metadata/event_selection_20261018`: bounded ASF/CMR catalogs, exact official URLs, QA CSV and ISO XML.

If future authorized science warrants crops, choose the affected subregion first. A20×20km10mFloat32 layer is ~16MB uncompressed/date before masks/metadata; actual grid, compression and range overhead are unknown. This is a planning estimate, not the chosen AOI or a bandwidth guarantee. No download queue is authorized; request approval for expected>1GB and use OptionB remote subsetting only.

## 11. Future checklist and competition boundary

- [ ] Owner review/send Ahmedabad clarification: official start and reuse permission remain unknown; existing artifacts stay isolated from submission.
- [ ] Obtain dated official village/flood geometry and original/report-version context; no generic district polygon as flood truth.
- [ ] Confirm reference-footprint/locality overlap and an appropriate labeling/uncertainty protocol. A matched S1 scene is not ground truth.
- [ ] Ask ASF, only with owner approval, about July identification FAIL causes, mode/PRF completeness, bands/noise and corrected releases; add exact July IDs to a draft if needed.
- [ ] Finalize study area only after independent evidence and suitability gates pass. Preserve Majuli regardless.
- [ ] Review full challenge afterOctober28 and submission guides afterNovember13 when published; no background monitoring promised.
- [ ] Only after verified start, applicable rules and `START TERRASCOPE AI HACKATHON BUILD`: perform permitted source/quality verification, acquire approved small subsets, then implement/evaluate the competition method.

The [global FAQ](https://www.spaceappschallenge.org/resources/participant-faqs/) pre-event challenge-work prohibition remains in force. This session performed research, metadata discovery, source/date verification and future planning only. No flood detection, classification, model, frontend/backend, integrated pipeline or demo was implemented. No organizer/support message was sent, event changed, Git history rewritten or unrelated issue/milestone modified.

## Verification before commit

Checked all56 current repository files and77 relative documentation links; no missing local targets, known Earthdata-value/token findings, oversized files or imagery signatures found. Existing three raster SHA256 values and exact sizes match recorded originals. Candidate scoring arithmetic and source IDs/footprint assertions were crosschecked against supporting metadata. This is a documentation/source audit, not a scientific validation test or universal guarantee against unknown secrets. Final full-history scan and remote commit verification are recorded outside Git after committing.
