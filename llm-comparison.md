---
layout: default
title: LLM Comparison
---

## Navigation

- 🏠 [Home](index.md)
- 📖 [Topic](topic.md)
- ⚙️ [Methodology](method.md)
- 💻 [SPARQL Queries](sparql.md)
- 🔍 [Knowledge Gap](knowledge-gap.md)
- 🤖 **LLM Comparison**
- ⚠️ [Challenges](challenges.md)
- ✅ [Conclusion](conclusion.md)

# LLM-assisted Knowledge Generation

After identifying the semantic gaps through SPARQL queries, Large Language Models were used to generate additional knowledge that could potentially enrich the ArCo Knowledge Graph.

Rather than accepting the first answer produced by the model, we experimented with different prompting techniques in order to improve the quality, precision and reliability of the generated information.

For both ChatGPT and Gemini we tested the three prompting techniques required by the project:

- Zero-shot prompting
- Few-shot prompting
- Chain-of-Thought prompting

Each answer was then manually compared with official historical sources and the ArCo ontology.

## The first gap - Missing information of the Rocca's usage

### ❓ Zero-Shot Prompting

We find that the response might as well be a yes or no, with little to no detail so we opted for a zero shot prompt, a technique that gives out quick answers without the need of examples.

The property a-cd:hasUse is associated with only the current cultural and historical usage of the building, so a LLM should have an easy task if the prompt is correctly written in terms of language and easy to understand in terms of tasks.

The prompt we went with is:

> Can the Rocca Sforzesca of Imola be considered an outdoor cinema?

#### ChatGPT:

![ChatGPT p1](assets/images/cgpt-1.png)

#### Gemini:

![Gemini p1](assets/images/gmn-1.png)

Both LLMs gave a short but detailed response in which we can actually se why the hasUse property might not be complete with a "cinema" or "outdoor cinema" option.
While Gemini was more straight forward, we found that it also described how locals might feel about the Rocca, as not only a historical place but more of cultural and gathering place.
We can find official resources about the problem in the ["Comune di Imola" official website - (https://www.culturaimola.it/festivals/rocca-cinema-imola-il-cinema-sotto-le-stelle)](https://www.culturaimola.it/festivals/rocca-cinema-imola-il-cinema-sotto-le-stelle)

## The second gap - Incorrect information about the authors and patrons

### ❓ Few Shots Technique

We prefer the Few-shot Technique over the zero-shot prompt in this case because we define the question we want an answer to very misleading. We want to guide the LLM into a richer response by feeding it some guided examples. Before actually asking something about the Rocca of Imola, we went through some similiar subjects like:

> Who is the author of the colosseum?

> Is Arnolfo di Cambio the author of the Palazzo Vecchio in Florence?

> Can Luigi Vanvitelli be considered the author of the Royal Palace of Caserta?

and only then ask the final question about our subject.

#### ChatGPT:

![ChatGPT p2](assets/images/cgpt-2.png)

#### Gemini:

![Gemini p2](assets/images/gmn-2.png)

Both LLMs did not give out a satisfying answer to the question, further strengthening the problematics a property hasAuthor (and "pico:author") might have for complex buildings or objects of historical value. ChatGPT made expecially clear that Danesio Maineri could be considered both the "engineer reponsible for the first Sforza reconstruction" and "...the designer of the Sforza phase of the fortress".

The obtained results did not meet expectations, so we tried the last approach of prompting techniques.

### ❓ Chain-of-Thought Technique

Chain-of-Thought (CoT) prompting encourages the model to explicitly articulate its intermediate reasoning steps before producing a final response. This approach has been shown to improve performance on tasks that require complex, multi-step reasoning by enabling the model to decompose problems into smaller, more manageable components. Consequently, it is particularly effective for addressing intricate or historically rich queries, such as those involving commissions with multiple participants or interconnected events.

#### ChatGPT:

![ChatGPT p3](assets/images/cgpt-3.png)

#### Gemini:

![Gemini p3](assets/images/gmn-3.png)

At last, to better highlight the critical issues of the hasAuthor property we can see that ChatGPT failed to mention Danesio Maineri while Gemini went and gave a positive response even after considering the great [Leonardo da Vinci](https://it.wikipedia.org/wiki/Leonardo_da_Vinci) as a possible author. We can consider Gemini for both the Chain of thought and few shots techniques to have a better understanding and answering fr complex, guided answers.

What we can deduce, is that we can certantly say who the author is, but more likely the one who commissioned the renovations and the author of the renovations itself, being Danesio Maineri for the first time.
