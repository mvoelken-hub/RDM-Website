---
description: RDF, OWL, SKOS, linked data, persistent identifiers, and Reac4Cat.
---

# 6. Ontologies & Semantic Technologies

Module 5 introduced controlled vocabularies and taxonomies as ways to standardize terminology and its hierarchy. An ontology goes a step further, formally defining not just terms but the relationships between them, which allows a machine to draw conclusions a plain vocabulary cannot support. This module introduces ontologies, the languages and tools used to build them, and linked data, the broader idea of connecting data across the web through persistent identifiers.

!!! tip "In this module"
    - What an ontology is, and how it differs from a taxonomy
    - Ontology languages and tools: RDF, OWL, SKOS, and Protégé
    - Linked data, persistent identifiers, and knowledge graphs

## Foundations of Ontologies

### What Is an Ontology?

An ontology is a formal representation of the knowledge within a field, including the relationships between its concepts. It defines both the vocabulary of a domain and the structure of the information within it, going beyond a plain list of terms such as the controlled vocabularies introduced in Module 5.

### Taxonomies vs. Ontologies

A taxonomy captures only hierarchical is-a relationships between broader and narrower terms. An ontology goes further: it allows arbitrary, formally defined relationship types between concepts, supports logical axioms, and enables a machine to draw conclusions through reasoning, none of which a taxonomy alone provides.

### Classes, Properties, Instances

A class is a category or concept within a domain, such as "catalyst" or "reaction". A property is a relation that connects classes or instances to each other or to values, such as "has temperature" or "was performed with". An instance is a single, concrete occurrence of a class, one specific experiment carried out on a specific date for instance.

### Use Cases in Research

Reac4Cat is an ontology developed for NFDI4Cat that describes and reasons over chemical reactions with a particular focus on catalysis. It applies ontological description logic within graph databases to represent complex data relationships and draw logical conclusions from them, and has been published in Datenbank-Spektrum.

## Ontology Languages and Tools

RDF, the Resource Description Framework, is the basic format of the semantic web: knowledge is represented as triples of subject, predicate, and object, with the subject and predicate expressed as URIs so statements can be referenced unambiguously anywhere. OWL, the Web Ontology Language, extends RDF and RDFS with considerably more expressive ways to describe classes and properties, such as disjoint classes, logical combinations, and reflexivity of relations. An OWL ontology consists of axioms, statements about classes and properties, and facts, statements about concrete individuals. SKOS, the Simple Knowledge Organization System, is lighter weight than OWL and intended for simpler hierarchical structures such as taxonomies and thesauri. It can be used on its own or combined with OWL, the approach Voc4Cat, itself SKOS-based, follows. Protégé is a free, open-source ontology editor from Stanford University supporting the full OWL 2.0 standard, covering the entire ontology lifecycle from modeling through reasoning to querying and collaboration, available both as a desktop application and, as WebProtégé, a browser-based, collaborative version with sharing, comments, and version history.

## Linked Data

### Linked Open Data Principles

The underlying idea of linked data is to avoid publishing data in isolation. Instead, data is made uniquely identifiable through URIs and connected to other data sources. Together with the FAIR principles from Module 1, this forms the conceptual foundation for machine-readable, networked research data.

### URIs and Persistent Identifiers

A persistent identifier (PID) is a durable, externally maintained link that, unlike an ordinary URL, remains stable over the long term. A DOI identifies an object, an article or a dataset for instance, while an ORCID identifies a person, a researcher, across an entire career. PID4Cat is a catalysis-specific example: a Handle-based PID system developed by NFDI4Cat for samples, instruments, and similar entities, with its own API and a LinkML-based data model, integrated with Repo4Cat.

### SPARQL Queries

SPARQL is a query language specifically for graph data represented in RDF, comparable to SQL for relational databases. It allows a knowledge graph to be queried directly, for every reaction that used a particular catalyst for instance.

### SHACL Shapes

SHACL, the Shapes Constraint Language, is a W3C standard for validating an RDF graph against a defined set of conditions, called shapes. A shape consists of a target selection, which nodes are checked, and constraints, the conditions those nodes must satisfy. Combined with SPARQL, it allows data quality within a knowledge graph to be enforced without writing custom validation code.

### Knowledge Graphs in Research

A knowledge graph connects entities, datasets, people, and publications for instance, through typed relations into a single, searchable network. Extracting such a graph from unstructured data is an active area of application in catalysis research, converting legacy datasets into a structured, queryable form.

## Worked Example

Recording the nickel-catalyst example from earlier modules as a set of RDF triples, rather than as a spreadsheet row, might look like the following, in simplified Turtle syntax:

```turtle
Ni-Al2O3-sample-042  hasSupport        Alumina .
Ni-Al2O3-sample-042  hasMetalLoading   "5.0"^^xsd:float .
Ni-Al2O3-sample-042  wasTestedIn       hydrogenation-run-017 .
```

Each subject and predicate resolves to a URI. The statement "this sample has alumina as its support" is therefore unambiguous regardless of which language or spreadsheet column header was originally used to record it, the same interoperability goal Voc4Cat CURIEs serve in Module 5, expressed here as a graph rather than as annotated table columns.

## Self-Check

??? question "1. What can an ontology express that a taxonomy cannot?"
    An ontology allows arbitrary, formally defined relationship types between concepts and supports logical axioms, enabling a machine to draw conclusions through reasoning. A taxonomy only captures hierarchical broader-term and narrower-term relationships.

??? question "2. What are the three parts of an RDF triple?"
    Subject, predicate, and object.

??? question "3. What is the difference between a DOI and an ORCID?"
    A DOI identifies an object, an article or a dataset for instance. An ORCID identifies a person, a researcher, across an entire career.

??? question "4. What does SHACL add on top of RDF?"
    A way to validate an RDF graph against a defined set of conditions, called shapes, each consisting of a target selection of which nodes are checked and constraints specifying the conditions those nodes must satisfy.

## Next Steps

- Continue to [Module 7: Data Archiving & Publication](../07-archiving/index.md), which turns to storing and sharing the data described here for the long term.
- Further reading: [W3C SKOS Reference](https://www.w3.org/TR/skos-reference/), [W3C SHACL specification](https://www.w3.org/TR/shacl/), [Protégé](https://protege.stanford.edu/).
- Catalysis-specific tools: Reac4Cat and PID4Cat, both referenced above, are worth exploring further once the concepts in this module feel familiar.
