---
description: What research data is, why Research Data Management matters, and the FAIR principles.
---

# 1. Foundations of Research Data Management

Every result produced in catalysis research rests on research data: reaction records, spectroscopic measurements, simulation output, and the scripts used to analyze them. Before this data can be organized, shared, or reused, it helps to establish a common understanding of what research data actually is and why managing it deliberately is worth the effort. This module introduces research data and its lifecycle, sets out the legal and funding-related reasons Research Data Management (RDM) has become a project requirement rather than a personal preference, and closes with the FAIR principles, the framework referenced throughout the remaining modules of this site.

!!! tip "In this module"
    - What research data is, and the forms it takes in catalysis research
    - The research data lifecycle
    - Why RDM matters, including legal and funding-related requirements
    - The FAIR principles and how to assess FAIRness

## Introduction to Research Data

### What Is Research Data

Research data is commonly defined as digital data collected, generated, or analyzed within a scientific investigation, whether through digitization, source research, experiments, or measurement. It forms the basis for testing hypotheses, developing knowledge, and validating scientific claims across disciplines. The term is deliberately broad: it covers everything from raw measurement values to analysis code and draft manuscripts. For catalysis research specifically, this includes reaction data, measurement series produced by laboratory instruments, and simulation results, alongside the more general categories described below.

### Data Types and File Formats

Research data can be distinguished along several dimensions. By medium, it spans text, audio, image, and video data, as well as sensor or measurement data and geodata. By processing state, a distinction is made between raw data and processed or aggregated data. By origin, primary data, collected directly, is distinguished from secondary data, derived from existing primary data. At a more technical level, individual values are typed as integers, floating-point numbers, strings, or booleans. Typical file formats encountered in practice include CSV, XLSX, PDF, JPG, PNG, WAV, MP3, GeoJSON, XML, and source code such as Python scripts. Module 5 returns to file formats in more detail, with particular attention to which formats are suited to long-term preservation.

### The Research Data Lifecycle

The research data lifecycle is commonly described in five phases: planning, data collection, management and organization, data processing, and preservation and provision. During the planning phase, the design of the investigation is defined together with licensing, file formats, and storage locations, typically formalized in a Data Management Plan (DMP). The management and organization phase covers consistent storage, folder structure, backups following the 3-2-1 rule introduced in Module 7, and the recording of metadata. Data processing includes digitization, conversion, validation, cleaning, analysis, and interpretation. In the final phase, preservation and provision, data is deposited in a repository, ideally in a non-proprietary format, with access rights defined through a license. As a general recommendation, raw data should remain available for at least ten years after a project ends.

### Why Data Management Matters

The growing volume and diversity of research data call for deliberate organization, protection, and reuse rather than ad hoc handling. Good scientific practice requires that the context in which data was created remains clearly documented and traceable, and funding bodies and publishers increasingly treat compliance with RDM requirements as a condition for funding or publication. Without structured data management, projects risk losing data outright, duplicating work already done elsewhere in the team, and leaving data unusable once a project or a doctoral thesis has concluded.

## Research Data Management

### What Is RDM

Research Data Management encompasses all stages of the research process, from data collection and documentation through processing to storage, publication, or archiving. Its goal is a well-organized structure and long-term accessibility for research data. RDM is not purely a technical concern: it is equally an organizational matter, involving defined roles, processes, and responsibilities, and it is anchored in legal requirements, discussed next.

### Legal Aspects: GDPR, Copyright, and Research Ethics

Several legal and ethical frameworks are directly relevant to handling research data within the EU. The General Data Protection Regulation (GDPR) defines personal data, in Article 4, as any information relating to an identified or identifiable natural person. Its collection is permitted only on a demonstrable legal basis, such as explicit consent. Article 5 sets out seven principles that govern the processing of personal data: lawfulness, fairness and transparency; purpose limitation; data minimisation; accuracy; storage limitation; integrity and confidentiality; and accountability. Where personal data cannot be avoided, for instance in participant records, a distinction is drawn between anonymization and pseudonymization. Anonymization removes any link to a person permanently. Pseudonymization instead replaces identifying features with a substitute, such as a code number. Re-identification of the original person then remains possible, but only under controlled conditions.

Copyright protection arises automatically when a work is created. Under German law, this follows from Section 11 of the Urheberrechtsgesetz (UrhG), the German copyright act. Protection expires seventy years after the death of the author, matching the term harmonized across the EU. Plain facts and measurement results are not covered by copyright. A structured collection of such facts can still be protected in its own right, as a database work. Readers based outside Germany should confirm the corresponding rules in their own jurisdiction, since specific terms and the scope of database protection vary between countries even where the underlying principles are similar.

Good scientific practice adds a further, non-legal layer of obligation on top of these regulations. The DFG's guidelines for safeguarding good research practice call for compliance with both legal and ethical standards. Most institutions additionally maintain their own internal policies, which apply regardless of a project's funding source.

### Funding Requirements and Institutional Support

An increasing number of funders and publishers require compliance with RDM policies as a condition for funding or publication. The DFG, the FWF, the SNF, Horizon Europe, and the Volkswagen Foundation all require a DMP as part of a funding application, discussed further below. Institutional support is typically available alongside these external requirements. At TU Dortmund, for example, the Forschungsdatenservice, a joint service of the Research Funding department, the university library, and the IT center (ITMC), advises on drafting a DMP, structuring data, collaboration, publication, and archiving, and operates TUDOdata, an institutional repository that issues DOIs. Readers based at other institutions should expect a comparable service, usually attached to the library or a central research support office, and are encouraged to identify their own institution's equivalent early in a project rather than at the point of publication.

### Data Management Plans

A Data Management Plan (DMP) is a systematic description of how the data created or collected within a project will be stored, recorded, maintained, processed, retained, and published. It should be drafted as early as possible in the research process and treated as a living document, revisited and extended as the project develops rather than written once and archived. Templates ease the process considerably: examples include the DMP template provided by Freie Universität Berlin, which follows the DFG's checklist, and DMPTool, a browser-based tool for drafting and managing plans. Since several major funders, including the DFG, the FWF, the SNF, Horizon Europe, and the Volkswagen Foundation, require DMP information as part of a funding application, drafting one is in most cases not optional but a prerequisite for the funding itself.

## The FAIR Principles

The FAIR principles, Findable, Accessible, Interoperable, and Reusable, provide the framework referenced throughout the rest of this site whenever a module discusses how data should be structured, described, or shared.

### Findable, Accessible, Interoperable, and Reusable

**Findable.** Data is findable when it carries a persistent identifier (PID) and sufficiently rich metadata, supported by structured storage with consistent, meaningful naming.

**Accessible.** Accessibility is governed by clear access rules and, where appropriate, open licenses that allow controlled reuse. FAIR does not automatically mean open access. The guiding principle is better expressed as data being as open as possible and as closed as necessary. Accordingly, sensitive or personal data can remain FAIR even when access to it is restricted.

**Interoperable.** Interoperability rests on standardized metadata and on formal, broadly applicable languages, such as controlled vocabularies and ontologies, that make data understandable to both people and machines. This is also what allows data to be combined across disciplinary boundaries, a topic Module 6 returns to in the context of ontologies.

**Reusable.** Reusability follows from a thorough description of data and its metadata according to discipline-specific standards, together with a clear, accessible data usage license that leaves no doubt about the terms under which third parties may reuse the data.

### Putting FAIR into Practice

Turning these principles into practice involves several concrete steps. A persistent identifier, typically a DOI issued through a repository, should be assigned to a dataset. Metadata should be extensive and standardized rather than left as free text, following discipline-specific metadata standards instead of an ad hoc, self-invented scheme. A data usage license should be defined explicitly from the outset of a project, not deferred until publication.

### Assessment Tools

Several tools support the practical assessment of FAIRness. F-UJI, developed within the FAIRsFAIR project, is an automated web service that evaluates a dataset against sixteen metrics, taking a PID or URL as input. FAIR-Checker is a free online tool that scans a dataset's landing page, again via its PID or URL, and reports on FAIR compliance. FAIR-Aware takes a different approach: rather than assessing a finished dataset, it is a quiz-style self-assessment tool that helps researchers gauge their own familiarity with FAIR before they upload data to a repository.

## Worked Example

Consider a research group synthesizing a nickel-based catalyst supported on alumina and testing it in a hydrogenation reaction. Over the course of the project, this generates several distinct types of research data: synthesis parameters recorded during preparation, characterization measurements such as BET surface area and XRD patterns, and reaction data from the catalytic tests themselves, including conversion and selectivity over time.

Applying the data lifecycle to this example, the planning phase would fix the file formats for instrument output, decide where raw measurement files are stored, and sketch a first DMP before any measurement is taken. During data collection, instrument software typically writes proprietary or instrument-specific files, which are then organized into a consistent folder structure, following the conventions introduced in Module 2, as part of the management and organization phase. In the processing phase, raw spectra are converted into analyzed peak positions or particle sizes, ideally with the conversion steps documented rather than performed silently in a spreadsheet. Finally, in the preservation and provision phase, the resulting dataset, both raw and processed files together with its metadata, is deposited in a repository such as Repo4Cat, described further in Module 7, where it receives a persistent identifier and becomes citable.

The same example illustrates why FAIR matters in a concrete case. A dataset described only as "Ni catalyst data.xlsx" on a personal laptop is not findable by anyone outside the group, and it becomes inaccessible once its author leaves the project. Annotating the same file with structured metadata, depositing it in Repo4Cat, and describing its fields using the shared terms defined in Voc4Cat instead turns it into a dataset that colleagues, and eventually the wider catalysis research community, can locate, understand, and build on.

## Step-by-Step Guide: Starting a Data Management Plan

1. Check the requirements of the relevant funder or institution first. The DFG, Horizon Europe, and most other major funders publish a checklist or template of the sections a DMP must cover.
2. Start from an existing template rather than a blank page, such as the FU Berlin template referenced above or the browser-based DMPTool.
3. Describe, for each type of data the project will produce, the file formats used, the expected volume, and where it will be stored during the active phase of the project.
4. Define responsibilities: who is accountable for backups, for metadata, and for the eventual deposit of the data in a repository.
5. Set a provisional repository and license for the final dataset, even if the final choice is only confirmed later. Module 7 covers repository selection in more detail.
6. Revisit the plan at fixed points during the project, since a DMP is only useful as a living document that reflects how the project actually develops.

## Self-Check

??? question "1. What are the five phases of the research data lifecycle?"
    Planning, data collection, management and organization, data processing, and preservation and provision.

??? question "2. Does FAIR require that all research data be made openly accessible?"
    No. FAIR requires that access conditions are clearly defined and that metadata remains findable regardless of access restrictions. The guiding principle is to keep data as open as possible and as closed as necessary, so sensitive or personal data can be FAIR while still being access-restricted.

??? question "3. What is the difference between anonymization and pseudonymization?"
    Anonymization removes any link to a person permanently. Pseudonymization replaces identifying features with a substitute, such as a code number, so that re-identification remains possible under controlled conditions.

??? question "4. Why should a Data Management Plan be drafted at the start of a project rather than at the end?"
    Because a DMP is meant to guide decisions about formats, storage, and responsibilities throughout the project, and because most funders that require one, including the DFG and Horizon Europe, require it as part of the funding application itself, before the project begins.

## Next Steps

- Continue to [Module 2: Data Organization & Documentation](../02-data-organization/index.md), which builds directly on the FAIR principles introduced here.
- Further reading: [FDMatStudium.nrw](https://landesinitiativefdmnrw.github.io/FDMatStudium/thk/), learning units 1 through 4 and 10.
- Catalysis-specific tools: Repo4Cat and Voc4Cat, both referenced in the worked example above, are covered in detail in Modules 5 and 7.
