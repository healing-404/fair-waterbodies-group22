
# FAIRness Assessment — IBGE BC250 Water Bodies

## 1. Dataset Overview

- Source: IBGE BC250 2025 hydrography — Water Bodies
- Dataset layer: CCAR:BC250_2025_hid_massa_dagua_a
- Extracted records: 400
- Geographic scope: Brazilian water-body layer; no spatial bounding-box filter applied
- Original formats: GML 3.2, XSD schema and CSV
- FAIRified format: RDF/Turtle
- Coordinate reference system: SIRGAS 2000 (EPSG:4674)

## 2. FAIRness Comparison

| FAIR Principle | Original Dataset | FAIRified Version | Assessment |
|---|---|---|---|
| F1 — Persistent identifiers | Original WFS feature identifiers | W3ID-based resource URIs created; data, ontology and selected metadata redirects tested | Improved; long-term persistence not established |
| F2 — Rich metadata | IBGE metadata and XSD schema | Additional DCAT Dataset and Distribution metadata publicly published | Improved; some metadata fields remain incomplete |
| F3 — Metadata identifies data | Original source metadata | Dataset linked to CSV and RDF distributions | Partially achieved |
| F4 — Searchable registration | IBGE online service | No independent searchable registration | Not yet achieved |
| A1 — Retrievable by identifier | Original WFS access | RDF, ontology and metadata publicly hosted; selected W3ID redirects verified | Improved for published resources |
| A2 — Persistent metadata access | Source metadata maintained by IBGE | Independent metadata persistence not established | Not demonstrated |
| I1 — Formal representation | GML, CSV and XML schema | RDF/Turtle using an ontology | Improved |
| I2 — Shared vocabularies | Existing geographic standards | RDFS, GeoSPARQL, DCAT and DCTERMS | Improved |
| I3 — Qualified references | Original relationships not fully evaluated | Water bodies linked to geometry resources | Partially achieved |
| R1 — Rich descriptions | Source attributes and metadata | Selected semantic attributes and metadata | Improved for mapped fields |
| R1.1 — Licence | Original licence not confirmed | No verified licence statement | Unresolved |
| R1.2 — Provenance | Source and extraction information | Transformation history documented | Improved |
| R1.3 — Domain standards | Geographic standards including GML | GeoSPARQL with EPSG:4674 | Improved semantic representation |

## 3. Implementation Evidence

- 400 water-body RDF resources.
- 400 separate geometry resources.
- 2,436 RDF triples in the validated Turtle export.
- 400 GeoSPARQL polygon geometries validated.
- 36 Portuguese name labels; 364 records without names.
- Custom WaterBody ontology developed in Protégé.
- RDF transformation configured in OpenRefine.
- DCAT metadata created for one dataset and two distributions.
- Two malformed property IRIs were identified and corrected during validation.
- W3ID pull request #64 was merged and five redirect identifiers were browser-tested.

## 4. Limitations

- Only 5 of the 10 original CSV columns were mapped into RDF.
- Water-body types and regimes remain Portuguese text literals rather than linked controlled vocabulary concepts.
- The 400-record extraction was limited by the Python script and was not restricted to Minas Gerais.
- The original IBGE dataset's redistribution licence requires verification.
- FAIRified RDF, ontology and metadata are publicly hosted on GitHub, and selected W3ID redirects have been verified. Original CSV publication and FAIR Data Point deployment remain incomplete.
- No formal automated FAIRness score was calculated.

## 5. Conclusion

The FAIRification improved the semantic interoperability and machine-readable description of a 400-record extract from the IBGE BC250 2025 water-body layer.

The strongest demonstrated results are the RDF representation, reuse of established semantic and geospatial vocabularies, and the creation of descriptive DCAT metadata.

Public GitHub hosting and working W3ID redirects have improved the findability and accessibility of the published resources. However, complete FAIRness has not yet been demonstrated: original CSV publication, verified licensing information, and FAIR Data Point deployment remain incomplete.

This is a qualitative assessment of the implemented work, not a claim that the dataset is fully FAIR.
