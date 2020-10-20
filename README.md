# Ocean Protein Portal Ontology

## COMPETENCY QUESTIONS

__1. What cruises are there data for?__

```
SELECT DISTINCT ?cruise WHERE { ?cruise a opp:Cruise }
```

__2. What cruises collected samples from Dataset 'X'?__

```
SELECT DISTINCT ?cruise 
WHERE { 
  ?cruise a opp:Cruise . 
  ?sampler sosa:hasDeployment ?cruise . 
  ?sample sosa:isResultOf [ sosa:madeBySampler ?sampler ] .
  ?sample opp:describedInDataset <Dataset X> .
}
```

__3. What datasets used a 0.2-3.0 filter?__

```
SELECT DISTINCT ?dataset
WHERE {
  ?sampler opp:usesSamplerFilter <0.2-3.0FilterSize> .
  ?sample sosa:isResultOf [ sosa:madeBySampler ?sampler ] .
  ?sample opp:describedInDataset ?dataset .
}
```

__4. What datasets measure Total Spectral Counts?__
```
SELECT DISTINCT ?dataset
WHERE { ?dataset opp:datasetType opp:DatasetType_TotalSpectralCounts }
```

__5. What is the minimum & maximum depth in Dataset 'X'? All datasets?__
```
SELECT MIN(?depth) MAX (?depth) WHERE {
  ?sample opp:describedInDataset <Dataset X> .
  ?sample opp:sampleDepth [ schema:value ?depth ] .
}
```
```
SELECT MIN(?depth) MAX (?depth) WHERE {
  ?sample opp:sampleDepth [ schema:value ?depth ] .
}
```

__6. What datasets measured Total Spectral Counts in the Pacific Ocean?__
```
SELECT DISTINCT ?dataset
WHERE {
  ?dataset opp:datasetType opp:DatasetType_TotalSpectralCounts .
  ?sample opp:describedInDataset ?dataset .
  ?sample sosa:isResultOf [ sosa:hasFeatureOfInterest ?foi ] .
  ?foi opp:atLocation ?sample_location .
  FILTER geo:within(<PacificOcean>, ?sample)
}
```

__7. What datasets did Nunn submit?__
```
SELECT DISTINCT ?dataset 
WHERE { 
  ?dataset opp:hasAgentRole ?role  .
  ?role opp:actedAs opp:Role_Author .
  ?role opp:performedBy <Nunn> .
}
```


