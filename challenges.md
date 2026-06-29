---
layout: default
title: Challenges
---

## Navigation

- 🏠 [Home](index.md)
- 📖 [Topic](topic.md)
- ⚙️ [Methodology](method.md)
- 💻 [SPARQL Queries](sparql.md)
- 🔍 [Knowledge Gap](knowledge-gap.md)
- 🤖 [LLM Comparison](llm-comparison.md)
- 🔗 [RDF Triple Generation](rdf-triples.md)
- ⚠️ **Challenges**
- ✅ [Conclusion](conclusion.md)

# Challenges

Throughout the project we encountered several technical and semantic challenges while exploring the ArCo Knowledge Graph and designing meaningful enrichments.

Rather than being isolated problems, these challenges often influenced one another and required multiple iterations of SPARQL exploration, ontology analysis and LLM-assisted reasoning.

## Finding the correct cultural property

The first challenge was identifying the correct entity corresponding to the **Rocca Sforzesca of Imola**.

Simple keyword searches such as _"Rocca di Imola"_ did not immediately return the expected resource because ArCo adopts official cataloguing labels rather than common names.

We therefore refined our SPARQL queries by combining multiple `FILTER` and `REGEX` clauses until the correct ArchitecturalOrLandscapeHeritage entity was identified.

## Understanding the ArCo ontology

Once the Rocca entity had been found, understanding its RDF description proved considerably more difficult than expected.

ArCo is composed of several interconnected ontologies, including:

- Context Description
- Cultural Event
- Denotative Description
- Location
- Construction Description
- Catalogue

Consequently, identifying the correct property to query often required exploring the ontology documentation before writing the final SPARQL queries.

## Distinguishing missing data from modelling choices

One of the most challenging aspects of the project was determining whether an apparent "gap" actually corresponded to missing information or was simply the result of ArCo's modelling decisions.

For example, the Rocca is currently described as a museum and an outdoor theatre, but its documented use as an outdoor cinema during the **Arena Cinema** festival is absent.

Similarly, the graph associates Danesio Maineri with the Rocca but contains no explicit reference to Caterina Sforza.

These observations required consulting external historical sources before concluding that genuine semantic gaps existed.

## Generating RDF with existing ontologies

The RDF generation phase highlighted another important challenge.

For the outdoor cinema use case, existing ArCo classes and properties were sufficient to describe the missing knowledge.

However, representing the historical role of Caterina Sforza proved much more complex.

No existing property adequately distinguishes:

- the original construction of the fortress;
- later architectural interventions;
- historical patrons or commissioners.

As a consequence, generating correct RDF required proposing an ontology extension instead of simply creating additional triples.

## Evaluating LLM-generated knowledge

Large Language Models produced coherent RDF suggestions, but their outputs could not be accepted without verification.

Each generated triple had to be manually compared against:

- the ArCo ontology;
- the existing knowledge graph;
- official historical documentation.

This validation phase was essential to avoid introducing historically incorrect or semantically inconsistent knowledge into the graph.

## Lessons learned

This project demonstrated that enriching a cultural heritage knowledge graph involves much more than generating RDF triples.

A successful enrichment requires:

- understanding the ontology;
- exploring the existing graph through SPARQL;
- validating historical information using authoritative sources;
- critically evaluating the output of Large Language Models.

The combination of these activities ultimately allowed us to identify meaningful semantic gaps and propose realistic enrichments for the ArCo Knowledge Graph.

<span style="display:block; width:100%; text-align:center; margin-top:50px; font-size:25px;">➡️ **Next:** [Conclusion](conclusion.md)</span>
