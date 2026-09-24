---
description: Open versus proprietary formats, controlled vocabularies, and Voc4Cat.
---

# 5. Data Standards & Interoperability

Once data is well organized and documented, as covered in Module 2, the next question is how well it can be understood and combined with data from other groups. This module covers file formats and the tradeoffs between open and proprietary choices, controlled vocabularies as a way to standardize terminology, and taxonomies as a way to structure that terminology hierarchically.

!!! tip "In this module"
    - Open versus proprietary file formats, and which formats suit long-term preservation
    - Controlled vocabularies, including Voc4Cat
    - Taxonomies and how they differ from folksonomies

## Standardized Data Formats

### Open vs. Proprietary Formats

An open format has a specification that is freely available, so any software can read or write it without restriction. A proprietary format keeps its specification undisclosed or only partially accessible. Proprietary formats complicate later reuse through licensing restrictions, poor documentation, and dependence on a single software vendor, carrying the risk that a format becomes unreadable within a decade or two once that vendor's software is no longer maintained or available.

### Key Formats

CSV suits large, uniformly structured tabular datasets well. It is simple, but carries no type information and cannot represent nested structures. JSON is a simple format that is read automatically by almost any programming language and suits nested or structured data well. XML is widely used for data exchange and can both structure data and document it further, through an accompanying schema for instance. For long-term archiving specifically, open, losslessly convertible formats are recommended: PDF/A, CSV, TIFF, and WAV among them.

### Discipline-Specific Standards

Beyond these generic formats, discipline-specific data standards exist as well, such as EnzymeML for enzyme kinetics data. For catalysis research, [DCAT-AP+](https://nfdi4cat.org/Services/DCAT_AP_-p-78.html) and its associated subschemas, introduced in Module 2, serve the same purpose, alongside [Voc4Cat](https://nfdi4cat.org/Services/Voc4Cat.html) and the other NFDI4Cat tools discussed below and throughout this site.

### Format Conversion and Preservation

Converting between formats is not always lossless. Converting a spreadsheet from XLS to CSV, for example, retains the plain numeric values but loses formatting, formulas, and any embedded figures. Before converting a file, it is worth checking which of that information actually matters for future reuse, and keeping the original alongside the converted version where anything might be lost.

## Controlled Vocabularies

### What Controlled Vocabularies Are

A controlled vocabulary is a system of terms with definitions, a hierarchical structure, and cross-references, used to index and search a dataset or database. The underlying task, terminological control, is to establish clear relationships between concepts and their labels: merging synonyms together and resolving ambiguity between terms that might otherwise be used inconsistently.

### Thesauri and Classification Systems

Hierarchically structured controlled vocabularies include taxonomies, classification systems, and thesauri. A thesaurus extends a pure hierarchy with associative relationships between terms, beyond the strict broader-term and narrower-term relationships a hierarchy alone provides.

### Examples: Voc4Cat

Established examples include LCSH, the Library of Congress Subject Headings, in use since 1909 as a widely recognized standard for subject cataloging in libraries; MeSH, the Medical Subject Headings maintained by the US National Library of Medicine for indexing the life sciences literature; and AGROVOC, a multilingual thesaurus maintained by the FAO for agriculture, food, fisheries, forestry, and the environment. Voc4Cat is the catalysis-specific counterpart to these: a SKOS-based, community-curated controlled vocabulary maintained by NFDI4Cat, linking tools and services together through unique URIs, with contributions accepted through Excel or GitHub.

### Application in Your Own Research

A controlled vocabulary such as Voc4Cat resolves the problem of inconsistent free-text terminology, several different spellings for the same reactor type for instance, and makes metadata comparable in a machine-readable way. This is the same underlying idea behind the CURIE-based annotation approach that CoreMeta4Cat, referenced throughout this site's design, uses for its own spreadsheet templates.

## Introduction to Taxonomies

### Definition and Purpose

In information practice, a taxonomy generally refers to a hierarchically structured controlled vocabulary. A formal taxonomy rests on generic classification: every narrower term shares all the characteristics of its broader term and adds at least one further, more specific characteristic.

### Hierarchical Structures

Taxonomies use a predetermined classification system, usually developed by domain experts, applied top-down. This gives a taxonomy the advantage of being organized, hierarchical, and clearly connected, at the cost of being comparatively difficult to design, maintain, and revise once established.

### Developing a Simple Taxonomy

A taxonomy is typically built by first collecting the central concepts of a field, then organizing them step by step into broader and narrower terms. Building a small taxonomy, for file types or reactor types for instance, is a useful exercise for applying this process directly.

### Taxonomies vs. Folksonomies

A folksonomy is a non-hierarchical classification system built from user-generated, freely chosen tags, applied bottom-up rather than following any predetermined structure. A taxonomy, by contrast, follows a predetermined system, usually developed by experts, applied top-down. Folksonomies are collaborative and flexible but potentially more ambiguous and less consistent than a taxonomy.

## Worked Example

Returning to the nickel-catalyst example from earlier modules, its reaction type could be recorded simply as free text: "hydrogenation", "Hydrierung", or "H2 addition" depending on who entered it, three different strings for the same underlying concept. Annotating the corresponding spreadsheet column instead with the Voc4Cat term for hydrogenation, referenced by its CURIE, resolves this ambiguity. Any dataset using that same CURIE is now comparable to this one, regardless of which word or language was used in the original spreadsheet. This is exactly the annotation pattern CoreMeta4Cat's own reference workbook is built around, adding a CURIE such as `voc4cat:0007010` alongside a human-readable column header rather than replacing the header outright.

## Self-Check

??? question "1. Why do proprietary file formats pose a risk for long-term archiving?"
    Their specification is undisclosed or only partially accessible, which creates dependence on a single software vendor and risks the format becoming unreadable if that vendor's software is no longer maintained or available.

??? question "2. What does a controlled vocabulary solve that free-text entry does not?"
    It merges synonyms and resolves ambiguity between terms that might otherwise be used inconsistently, such as several different spellings or names for the same concept, making data comparable in a machine-readable way.

??? question "3. What is the key difference between a taxonomy and a folksonomy?"
    A taxonomy follows a predetermined, usually expert-developed system applied top-down. A folksonomy is built bottom-up from freely chosen, user-generated tags with no predetermined structure.

??? question "4. What additional feature does a thesaurus add on top of a plain hierarchy?"
    Associative relationships between terms, beyond the strict broader-term and narrower-term relationships a hierarchy alone provides.

## Next Steps

- Continue to [Module 6: Ontologies & Semantic Technologies](../06-ontologies/index.md), which builds on controlled vocabularies to introduce formally defined relationships between concepts.
- Further reading: [NFDI4Chem Knowledge Base on data format standards](https://knowledgebase.nfdi4chem.de/knowledge_base/de/docs/format_standards/?userLocale=true), [Library of Congress on controlled vocabularies](https://www.loc.gov/librarians/controlled-vocabularies/).
- Catalysis-specific tools: Voc4Cat, referenced throughout this module, is introduced further in the [Getting Started guide of CoreMeta4Cat](https://nfdi4cat.github.io/CoreMeta4Cat/latest/getting-started/).
