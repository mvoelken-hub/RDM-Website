---
description: Folder structures, naming conventions, metadata standards, and electronic lab notebooks.
---

# 2. Data Organization & Documentation

Once a research question and a plan for its resulting data are in place, as introduced in Module 1, the next requirement is a way to keep that data organized as it accumulates. This module covers how to structure folders and name files consistently, what metadata is and which standards apply to catalysis research data, and how to document data and the workflows that produce it so that both the origin and the meaning of a dataset remain traceable.

!!! tip "In this module"
    - Folder structures and naming conventions for research projects
    - What metadata is, and the standards used to describe it
    - Documenting research data and the workflows that produce it

## File Organization and Naming Conventions

### Folder Structures for Research Projects

A research project benefits from a hierarchically organized directory structure, with clearly nested parent and child folders rather than a flat collection of files in a single location. Raw data should be kept in its own, clearly separated folder and never overwritten once recorded, so that the original measurement remains available even after processing. Work that is still ongoing and work that has been completed are best kept in physically separate locations rather than mixed together. The folder structure used locally should also match the structure on any server or external storage medium the data is later copied to, so the same layout can be navigated regardless of where the data is accessed.

### Naming Conventions for Files and Folders

Placing a date in the YYYY-MM-DD format at the start of a filename allows files to sort chronologically without any additional effort. Beyond the date, a descriptive, content-based name is preferable to a cryptic abbreviation, since the filename alone should already give a reasonable indication of what it contains. A small number of further constraints keep filenames portable across systems: no more than 255 characters in total, umlauts resolved to their two-letter equivalents, underscores and hyphens as the only special characters, and no spaces or periods within the name itself.

### Versioning Files Without Git

Where a full version control system, covered in Module 3, is not in use, version numbers should be incremented consistently, such as v01, v02, up to v10, rather than appended with labels like "_new" or "_final", which do not indicate an order and multiply quickly once several rounds of revision have taken place. Older versions are best moved into an archive folder rather than duplicated in place or deleted outright. A representative filename combining both conventions above would be "2026-05-17_Project_Catalyst_v02".

### README Best Practices

A short README file at the top level of a project folder should document the folder structure and naming convention in use, together with a glossary of any abbreviations. This allows a third party, or the same researcher returning to the data after several years, to reconstruct how the structure is organized. Beyond structure, the README is the natural place for context that metadata alone does not cover: a project overview, the people to contact, and the license under which the data is shared.

## Metadata

### What Metadata Is and Why It Matters

Metadata is commonly described as additional information recorded alongside a dataset, data about data in short. It is what makes a dataset understandable, findable, and reusable well after the context in which it was produced has been forgotten. This matters in particular for large or complex datasets and for anything intended for long-term archiving, discussed further in Module 7.

### Types of Metadata

Metadata is typically grouped into five categories. Bibliographic metadata covers title, authors, and keywords. Administrative metadata covers the creation date, licenses, and access rights. Structural metadata covers the file format, field names, and the relations between parts of a dataset. Technical metadata covers file size and the hardware or software used to produce it. Contextual metadata covers the project, methodology, and the work steps that led to the data.

### Metadata Standards

A number of generic, cross-disciplinary metadata standards are widely used, including Dublin Core, the DataCite Schema, MARC21, and RADAR. It is worth distinguishing two related but different terms here. A metadata **standard** is a broadly adopted specification for which fields to record and what they mean, agreed on by a community. A **schema**, by contrast, is a concrete, machine-readable structural definition, such as a JSON Schema or a LinkML schema, that implements a standard so software can validate or process records against it. [DCAT-AP+](https://nfdi4cat.org/Services/DCAT_AP_-p-78.html) illustrates this relationship for catalysis research: a metadata standard developed by NFDI4Cat and NFDI4Chem as an extension of DCAT-AP, the EU's own profile of DCAT. It captures the more complex contextual relationships found in catalysis data, and its accompanying schema supports both JSON Schema validation and conversion to RDF.

### Creating Metadata in Practice

Metadata documentation ideally begins at the point data is created, rather than being reconstructed afterward, just before publication, when much of the original context has typically already been lost. Adopting a shared standard rather than an ad hoc, self-invented scheme is what allows data to be exchanged consistently between different research groups and disciplines, a point Module 1 already introduced under Interoperable in the FAIR principles.

## Documenting Research Data

### Codebooks and Data Dictionaries

A codebook, or data dictionary, records detailed information about the variables used in a dataset: their designation, the values they can take, permissible ranges, and the codes used to mark missing values. It can be produced as a table, a CSV file for instance, or as a plain text or PDF document. Codebooks are particularly relevant for tabular, structured measurement data, a format catalysis research produces frequently.

### Lab Notebooks and Electronic Lab Notebooks (ELNs)

An electronic lab notebook (ELN) is a digital lab journal used to document the planning, execution, and evaluation of an experiment. In disciplines with an established tradition of paper lab notebooks, chemistry and the life sciences among them, an ELN often functions as a direct digital replacement. Tools such as Chemotion are already in use for this purpose in catalysis research.

### Documenting Analysis Workflows

Documentation should cover every phase of the data lifecycle introduced in Module 1, not only the point of data collection. It works best as a living document that grows alongside the project from the outset, rather than one reconstructed retroactively once a result is ready for publication.

### Reproducible Research

Good documentation establishes a consistent, shared basis for handling data across everyone involved in a project. It improves findability, reduces the risk of losing data, and enables collaborative work by keeping knowledge accessible rather than confined to one person's memory. This connects directly to Module 8: computational notebooks, containers, and workflow tools are, in the end, also a form of documentation.

## Worked Example

Continuing the nickel-on-alumina catalyst example from Module 1, consider how its files might be organized on disk. A project folder separates raw instrument output from processed results, for instance `raw/` and `processed/` subfolders beneath a top-level `Ni-Al2O3-hydrogenation/` folder, mirrored identically on the group's server. Within `raw/`, a BET measurement recorded on 17 May 2026 might be named `2026-05-17_Ni-Al2O3_BET-surface-area_v01.xlsx`, immediately conveying its date, sample, and measurement type without needing to open the file. A short `README.md` at the top level explains the folder structure, lists the abbreviations used for each characterization technique, and names the person responsible for the dataset. Alongside the files themselves, a small metadata record, following DCAT-AP+ where the dataset is destined for [Repo4Cat](https://nfdi4cat.org/Services/Repo4Cat.html), captures the catalyst type, support material, and reaction type as structured, standardized fields rather than as free text buried in a filename.

## Step-by-Step Guide: Writing a Folder README

1. Create a plain text or Markdown file named `README` at the top level of the project folder.
2. State the purpose of the folder in one or two sentences: what the data is, and which project or investigation it belongs to.
3. Describe the folder structure, listing each subfolder and what it contains.
4. Document the naming convention in use, with one concrete example filename.
5. Add a glossary for any abbreviations used in folder or file names, such as characterization technique codes.
6. Name a contact person and, where one has already been decided, the license under which the data is shared.
7. Update the README whenever the folder structure changes, rather than letting it drift out of sync with the actual contents.

## Self-Check

??? question "1. Why should raw data be kept separate from processed data and never overwritten?"
    So that the original measurement remains available even after processing or analysis, allowing results to be recalculated or checked against the source at any point.

??? question "2. What is the difference between a metadata standard and a schema?"
    A metadata standard is a broadly adopted specification for which fields to record and what they mean. A schema is a concrete, machine-readable structural definition that implements a standard so software can validate or process records against it.

??? question "3. Name the five common categories of metadata."
    Bibliographic, administrative, structural, technical, and contextual metadata.

??? question "4. Why is an ELN often described as a direct replacement for a paper lab notebook?"
    In disciplines such as chemistry, which already have an established tradition of recording experiments in a paper notebook, an ELN digitizes the same planning, execution, and evaluation records rather than introducing an entirely new practice.

## Next Steps

- Continue to [Module 3: Version Control with Git](../03-version-control/index.md), which introduces a more powerful alternative to the manual versioning covered here.
- Further reading: [FDMatStudium.nrw](https://landesinitiativefdmnrw.github.io/FDMatStudium/thk/), learning units 5 through 7.
- Catalysis-specific tools: DCAT-AP+, referenced above, is covered further in Module 5, and Repo4Cat, the repository referenced in the worked example, in Module 7.
