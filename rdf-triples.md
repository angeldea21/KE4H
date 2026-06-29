---
layout: default
title: RDF Triple Generation
---

## Navigation

- 🏠 [Home](index.md)
- 📖 [Topic](topic.md)
- ⚙️ [Methodology](method.md)
- 💻 [SPARQL Queries](sparql.md)
- 🔍 [Knowledge Gap](knowledge-gap.md)
- 🧩 **RDF Triple Generation**
- 🤖 [LLM Comparison](llm-comparison.md)
- ⚠️ [Challenges](challenges.md)
- ✅ [Conclusion](conclusion.md)

# RDF Triple Generation

After identifying the semantic gaps through SPARQL queries and validating them using official historical sources, we used Large Language Models to generate RDF triples that could enrich the ArCo Knowledge Graph.

The purpose of this phase was not to automatically accept the generated triples, but to evaluate whether an LLM could correctly reuse the ArCo ontology and produce meaningful RDF statements.

## Gap 1 – Missing current use: Outdoor Cinema

The first identified gap concerns the current usage of the Rocca Sforzesca of Imola.

While ArCo already models the monument as a museum and an outdoor theatre, the official website of the Municipality of Imola also identifies the Rocca as the venue of the annual **Arena Cinema**, a current use that is completely absent from the knowledge graph.

### Prompt:

Following the great success of the Zero-Shot technique used in the LLMs interrogations, we opted to create another Zero-Shot prompt for this task. Doing so is possible as the a-cd:hasUse is used inside ArCo's ontologies and represents only the different functions the cultural property had over time.

```
Hey, could you help me in building an RDF triple?

The context is the Rocca Sforzesca of Imola.

The entity already exists in the ArCo Knowledge Graph:

https://w3id.org/arco/resource/ArchitecturalOrLandscapeHeritage/0800242914

According to the official website of the Municipality of Imola, the Rocca is also currently used as an outdoor cinema ("Arena Cinema"), but this information is missing in ArCo.

Please identify the most appropriate ArCo property to represent this information.

Then generate:

1. The RDF triple in Turtle syntax (using the correct prefixes).
2. A SPARQL CONSTRUCT query that creates this triple.

Reuse existing ArCo classes and properties whenever possible. Do not invent new predicates unless strictly necessary.
```

### Generated RDF:

#### **ChatGPT**

![RDF ChatGPT 1](assets/images/rdf-chatgpt-1.png)

_The prompt answer_

![RDF ChatGPT 1](assets/images/rdf-sparql-chatgpt-1.png)

_Results obtained executing the query on SPARQL_

#### **Gemini**

![RDF Gemini 1](assets/images/rdf-gemini-1.png)
Gemini
_The prompt answer_

![RDF Gemini 1](assets/images/rdf-sparql-gemini-1.png)

_Results obtained executing the query on SPARQL_

### Evaluation

The generated RDF was analysed to verify whether:

- existing ArCo classes were correctly reused;
- existing ArCo properties (such as `a-cd:hasUse` and `a-cd:useFunction`) were correctly employed;
- unnecessary ontology extensions were introduced.
