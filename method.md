---
layout: default
title: Topic
---

## Navigation

- 🏠 [Home](index.md)
- 📖 [Topic](topic.md)
- ⚙️ **Methodology**
- 💻 [SPARQL Queries](sparql.md)
- 🔍 [Knowledge Gap](knowledge-gap.md)
- 🤖 [LLM Comparison](llm-comparison.md)
- ⚠️ [Challenges](challenges.md)
- ✅ [Conclusion](conclusion.md)

# Semantic Methodology

The objective of this project is to identify semantic information that is missing from the ArCo Knowledge Graph regarding the **Rocca Sforzesca of Imola**.

The adopted methodology combines Semantic Web technologies, SPARQL querying, authoritative cultural heritage sources and Large Language Models (LLMs) in order to analyse the existing knowledge graph and identify possible semantic enrichments.

## Workflow

The project followed the workflow illustrated below.

```text
Selection of the cultural heritage asset
                │
                ▼
Exploration of the ArCo Knowledge Graph
                │
                ▼
SPARQL Queries
                │
                ▼
Analysis of available RDF triples
                │
                ▼
Comparison with official sources
                │
                ▼
Knowledge Gap Identification
                │
                ▼
Proposal of semantic enrichment
```

### Step 1 - Selection of the Case Study

The Rocca Sforzesca of Imola was selected because it is represented within the ArCo Knowledge Graph and is extensively documented by authoritative cultural heritage institutions.

This allows a direct comparison between the information represented in the knowledge graph and the information available from official sources.

### Step 2 - Exploration of the Knowledge Graph

The ArCo SPARQL Endpoint was explored to understand how the Rocca is represented.

The analysis focused on:

- available RDF properties;
- relationships with other entities;
- historical information;
- current and historical uses;
- associated agents.

Several SPARQL queries were executed to inspect both direct and indirect relationships.

### Step 3 - External Knowledge Collection

The information contained in ArCo was compared with authoritative external sources, including:

- Italian Ministry of Culture;
- Imola Musei;
- Comune di Imola;
- other institutional cultural heritage websites.

Only official sources were considered in order to guarantee the reliability of the proposed knowledge enrichment.

### Step 4 - Knowledge Gap Identification

The comparison between ArCo and the external documentation allowed the identification of missing semantic information.

Each candidate gap was verified by:

- analysing RDF triples;
- executing dedicated SPARQL queries;
- checking whether the information was already represented through indirect relationships.

Only information completely absent from the Knowledge Graph was considered a valid knowledge gap.

### Step 5 - Large Language Models

Large Language Models were used as supporting tools during the project.

Different LLMs were employed to:

- assist in SPARQL query formulation;
- explore the ontology;
- suggest possible semantic relationships;
- verify candidate knowledge gaps;
- compare alternative modelling strategies.

However, every generated result was manually verified through SPARQL queries and official documentation before being included in the project.

### Step 6 - RDF Translation and Triple Modelling

We converted the newly acquired insights into formal RDF triples, ensuring strict adherence to ArCo’s established vocabularies and structural guidelines.

After that, we refined the proposed RDF triples so that they seamlessly integrate with ArCo’s underlying ontological framework.

### Step 7 - Website development and publication with a licence under CC0

Developed the website using GitHub Pages to clearly present our work using .MD files and published under the Creative Commons Zero v1.0 Universal licence to be publicly avaible.

<span style="display:block; width:100%; text-align:center; margin-top:50px; font-size:25px;">➡️ **Next:** [SPARQL Queries](sparql.md)</span>
