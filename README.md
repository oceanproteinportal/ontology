# Ocean Protein Portal Ontology

## WebVOWL Visualization

http://www.visualdataweb.de/webvowl/#iri=https://raw.githubusercontent.com/oceanproteinportal/ontology/main/opp.owl

## Conceptual Model

https://lucid.app/lucidchart/invitations/accept/4b8cb8d5-4beb-458f-acef-8b63de0f6768

## WIDOCO - Ontology documentation generation

`widoco -ontFile v2/opp.owl -outFolder ./widoco -confFile widoco.cfg -htaccess -webVowl -includeAnnotationProperties -uniteSections`

1. Edit the widoco/doc/index-en.html
  a. replace `index-en.html` with `index.html`
  b. insert all sections from `/v2/_sections`
  c. rename the file to `index.html`

2. Copy from /widoco/doc to /v2:
  a. index.html
  b. all ontology.* files (`cp ontology.* ../../v2/.`)
  c. resources/ , provenance/ and webvowl/ directories.
    - `cp -R resources ../../v2/.`
    - `cp -R provenance ../../v2/.`
    - `cp -R webvowl ../../v2/.`


