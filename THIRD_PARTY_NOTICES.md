# Attribution and license scope

The repository's Apache-2.0 license applies to original TerraScope AI preparation documentation and any future original code explicitly included under that license. It does not relicense referenced satellite datasets, publications, agency marks, installed tools, or third-party material. The repository currently has no competition application and distributes no imagery, third-party source packages or copied product guides.

## NASA and ISRO data provenance

Research uses the joint NASA-ISRO NISAR mission's L-band observations, distributed through NASA's Alaska Satellite Facility DAAC. Collection: **NISAR Provisional Geocoded Polarimetric Covariance Product (Version 1)**, short name `NISAR_L2_GCOV_PROVISIONAL_V1`, DOI [10.5067/NIL2GCOV-P1](https://doi.org/10.5067/NIL2GCOV-P1). The DOI was verified in both source products and NASA CMR collection metadata on October 18, 2026. Full granule identifiers and acquisition times are recorded in metadata/scene_inventory.json and docs/FINAL_DATA_READINESS.md. Imagery is retained outside Git.

Suggested acknowledgement: "This preparation research used NASA-ISRO NISAR L-band GCOV observations provided through NASA ASF DAAC, collection NISAR_L2_GCOV_PROVISIONAL_V1, DOI 10.5067/NIL2GCOV-P1." Preserve the producer's citation and exact versions/granules in any later publication.

[ASF's NISAR citation guidance](https://nisar-docs.asf.alaska.edu/data-use-citation-guidance/) points to [NASA Data Use and Citation Guidance](https://www.earthdata.nasa.gov/engage/open-data-services-software-policies/data-use-guidance). The latter returned HTTP 403 during this audit. NASA CMR's collection record did not include explicit UseConstraints or AccessConstraints fields; absence of those fields is not treated as a separate license grant. No broad claim that all ISRO material is public domain is made. Current publication consists of attributed factual catalog metadata, our own notes, and short identified diagnostics, not redistribution of mission imagery or documents.

NASA/ISRO names identify data sources and do not imply sponsorship, approval or endorsement. Agency logos/insignia are not included or licensed by this repository. See [NASA media/brand guidance](https://www.nasa.gov/nasa-brand-center/images-and-media/).

## Software and publications

- [isce-framework/nisarqa](https://github.com/isce-framework/nisarqa), v17.0.0: Copyright 2024 California Institute of Technology; United States Government Sponsorship acknowledged. Upstream offers Apache-2.0 or BSD-3-Clause. The audit cites upstream checks and stores its local research checkout outside Git; no source code is vendored here.
- NASA GCOV product specification and ASF user guide: cited by title/link in the reports; complete PDF/HTML copies remain outside Git and retain their source terms.
- Python, QGIS, GDAL, NumPy, h5py and asf_search: local tools only, with versions recorded in docs/exploration-packages.txt where applicable. Their binaries and packages are not distributed here, and retain their own licenses. Future redistribution must preserve applicable notices and check linking/package obligations.
- Future Copernicus, USGS, NRSC/ISRO or other validation datasets require their own provenance, license and citation checks before inclusion. No such reference imagery has been uploaded.

One account is recorded as the sole Git/GitHub contributor at this audit. Apache-2.0 was prepared at that owner's request for original contributions; no additional recorded contributor consent is pending. Unrecorded third-party contributions must be reviewed before being added. Nothing in this notice claims ownership of third-party content.
