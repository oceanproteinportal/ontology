# Ocean Protein Portal Ontology

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.4687996.svg)](https://doi.org/10.5281/zenodo.4687996)

The Ocean Protein Portal Ontology is an application ontology used to formalize shared conceptualizations of ocean proteomics data. These shared conceptualizations exists between the portal's researchers and the software systems that describe, ingest, search and visualize the data. Their main purpose is to minimize the amount of technical debt of the underlying software used to operate the portal. Mappings to more formal ontologies such as the Protein Ontology and the Mass Spectrometer Ontology are required and should be made to enable better data sharing with other initiatives.


## WebVOWL Visualization

http://www.visualdataweb.de/webvowl/#iri=https://raw.githubusercontent.com/oceanproteinportal/ontology/main/opp.owl

## Conceptual Model

https://lucid.app/lucidchart/invitations/accept/4b8cb8d5-4beb-458f-acef-8b63de0f6768

## WIDOCO - Ontology documentation generation

`widoco -ontFile v2/opp.owl -outFolder ./widoco -confFile widoco.cfg -htaccess -webVowl -includeAnnotationProperties -uniteSections`

1. Edit the widoco/doc/index-en.html
  a. rename the `index-en.html` to `index.html`
  b. insert all sections from `/_sections`

2. Fix the WebVOWL author order
  a. edit widoco/doc/webvowl/data/ontology.json with `_sections/webvowl`
3. Sync from /widoco/doc to /v2: `rsync -av widoco/doc/ v2`
