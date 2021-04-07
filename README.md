# Ocean Protein Portal Ontology

[![DOI](https://zenodo.org/badge/305539938.svg)](https://zenodo.org/badge/latestdoi/305539938)

The Ocean Protein Portal Ontology is an application ontology used to formalize shared conceptualizations of ocean proteomics data. These shared conceptualizations exists between the portal's researchers and the software systems that describe, ingest, search and visualize the data. Their main purpose is to minimize the amount of technical debt of the underlying software used to operate the portal. Mappings to more formal ontologies such as the Protein Ontology and the Mass Spectrometer Ontology are required and should be made to enable better data sharing with other initiatives.


## WebVOWL Visualization

http://www.visualdataweb.de/webvowl/#iri=https://raw.githubusercontent.com/oceanproteinportal/ontology/main/opp.owl

## Conceptual Model

https://lucid.app/lucidchart/invitations/accept/4b8cb8d5-4beb-458f-acef-8b63de0f6768

## WIDOCO - Ontology documentation generation

`widoco -ontFile v2/opp.owl -outFolder ./widoco -confFile widoco.cfg -htaccess -webVowl -includeAnnotationProperties -uniteSections`

1. Edit the widoco/doc/index-en.html
  a. rename the `indexx-en.html` to `index.html`
  b. insert all sections from `/v2/_sections`
  c. remove the line `<div style="float:right">language <a href="index-en.html"><b>en</b></a> </div>`


2. Copy from /widoco/doc to /v2:
  a. index.html
  b. all ontology.* files (`cp ontology.* ../../v2/.`)
  c. resources/ , provenance/ and webvowl/ directories.
    - `cp -R resources ../../v2/.`
    - `cp -R provenance ../../v2/.`
    - `cp -R webvowl ../../v2/.`


