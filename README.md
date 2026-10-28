# FAIRification of IBGE BC250 Water-Body Data

**FAIR Data Engineering — Group 22 (2026)**

This repository contains the FAIRification outputs for a subset of the Brazilian Institute of Geography and Statistics (IBGE) BC250 2025 hydrography dataset.

The project focuses on transforming water-body geospatial data into RDF using a custom ontology and established semantic-web vocabularies to improve its findability, accessibility, interoperability and reusability.

## 1. Original Dataset

- **Provider:** Instituto Brasileiro de Geografia e Estatística (IBGE)
- **Source layer:** `CCAR:BC250_2025_hid_massa_dagua_a`
- **Source access:** IBGE GeoServer Web Feature Service (WFS)
- **Formats available:** GML 3.2, CSV and XSD schema
- **Coordinate reference system:** SIRGAS 2000 (EPSG:4674)
- **Extracted records:** 400 water bodies
- **Geographic scope:** Brazil; no bounding-box filter was applied during extraction

The extraction was limited to 400 records by the Python retrieval script. It is not a geographically filtered sample of Minas Gerais.

## 2. FAIRification Process

The FAIRification workflow involved:

1. Retrieving the IBGE water-body records from the WFS.
2. Inspecting the source dataset and its attributes.
3. Creating a custom water-body ontology using Protégé.
4. Mapping selected source columns into RDF using OpenRefine with the RDF Extension.
5. Representing geometries using GeoSPARQL and EPSG:4674.
6. Validating the exported RDF and polygon geometries.
7. Creating DCAT-based metadata for the dataset and its distributions.
8. Publishing the resulting files on GitHub and configuring W3ID redirects.

Five original attributes were mapped: `FID`, `nome`, `tipomassadagua`, `regime`, and `geom`.

## 3. Implementation Results

- **400** water-body RDF resources
- **400** separate geometry resources
- **2,436** RDF triples
- **400** validated polygon geometries
- **36** Portuguese name labels

The RDF uses a custom `WaterBody` ontology alongside RDFS and GeoSPARQL.

## 4. Repository Files

| File | Description |
|---|---|
| `waterbodies_fairified.ttl` | FAIRified water-body RDF data |
| `waterbodies_ontology.ttl` | Custom ontology developed in Protégé |
| `waterbodies_metadata.ttl` | DCAT Dataset, Distribution, agent and provenance metadata |
| `FAIRness_assessment.md` | Qualitative assessment of FAIR improvements and limitations |
| `README.md` | Project overview and implementation documentation |

## 5. Published Identifiers

The following W3ID identifiers have been tested in a web browser and successfully redirect to their corresponding published files:

- **RDF data:** https://w3id.org/FAIR-course-UT/2026/group22/data
- **Ontology:** https://w3id.org/FAIR-course-UT/2026/group22/ont
- **Dataset metadata:** https://w3id.org/FAIR-course-UT/2026/group22/dataset/waterbodies
- **RDF distribution metadata:** https://w3id.org/FAIR-course-UT/2026/group22/distribution/waterbodies-rdf
- **Group metadata:** https://w3id.org/FAIR-course-UT/2026/group22/agent/group22

The redirect configuration was submitted and merged through [Pull Request #64](https://github.com/luizbonino/pid-relay/pull/64).

## 6. Remaining Limitations

- Only 5 of the original 10 source attributes were mapped into RDF.
- Water-body types and regimes remain Portuguese text literals, rather than linked controlled vocabulary concepts.
- The original IBGE data redistribution licence has not yet been verified.
- The original CSV extract has not yet been published in this repository.
- FAIR Data Point installation, metadata-schema configuration and catalog publication remain incomplete.
- Long-term availability and persistence are not guaranteed by the successful browser redirect tests alone.

## 7. FAIRness Assessment

See [FAIRness_assessment.md](FAIRness_assessment.md) for the qualitative before-and-after comparison against the FAIR principles.

This project demonstrates improvements in semantic interoperability, machine-readable metadata and identifier-based access. It does not claim that all FAIR principles have been fully satisfied.
