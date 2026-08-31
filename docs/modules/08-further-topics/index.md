---
description: Reproducible workflows, containerization, case studies, and further reading.
---

# 8. Further Topics & Integration

The preceding seven modules covered the core of Research Data Management, from foundational concepts through to archiving and publication. This closing module gathers a set of related topics that extend RDM into everyday research practice: automating and documenting analysis workflows, seeing how the pieces come together in practice, and pointing toward further resources for continued learning.

!!! tip "In this module"
    - Reproducible workflows, containerization, and computational notebooks
    - Applying RDM in practice, including common pitfalls
    - Organizations and resources for further learning

## Workflows and Automation

### Reproducible Workflows

Workflow engines such as Snakemake and Nextflow support efficient, reproducible execution of complex, multi-step analyses. Snakemake is Python-based and inspired by the classic Make language: rules describe individual work steps, and dependencies between them are inferred automatically from their input and output files. Nextflow uses a Groovy-based domain-specific language and is likewise designed for portable, scalable, reproducible pipelines, first described in a 2017 Nature Biotechnology publication.

### Containerization

A container packages code, its runtime environment, system tools and libraries, and configuration into a single, lightweight, self-contained unit. Docker is the more widely used option in industry, with a larger feature set and more integrations, but traditionally requires root privileges, which is often impractical on shared HPC clusters. Singularity, now also known as Apptainer, needs no root access to run and has become the standard on HPC clusters as a result, and it can open or convert Docker containers directly. For research, the benefit is a reproducible software environment that behaves the same way across different systems, independent of whatever happens to be installed locally.

### Computational Notebooks

Jupyter Notebook, from the Python community, combines text and executable code in cells, with results shown directly beneath the code that produced them, in a web-based client-server model. RMarkdown is the equivalent for R, with header arguments controlling how code and its results are displayed. Notebooks are increasingly treated as a research output in their own right, published as "executable papers" in open repositories, sometimes hosted through services such as Binder.

### Workflow Documentation

Automated workflows still need documentation: which steps ran, which software and package versions were used, and which parameters were set. This is best kept directly alongside the workflow code itself, as comments or a README next to the pipeline definition, rather than in a separate document that easily falls out of date, connecting back to the documentation practices introduced in Module 2.

## Research Data in Practice

### Case Studies

Seeing the modules of this site applied to an actual catalysis dataset, a metadata extraction workflow or a Repo4Cat deposit for instance, is more instructive than the abstract principles on their own, since it shows how the individual modules connect in a single, concrete project.

### Common Challenges and Solutions

Typical obstacles include inconsistent file naming that needs to be reconciled after the fact, metadata that was never recorded and must be reconstructed later, and proprietary instrument formats that need converting before they can be shared. The underlying solution in each case is the same as in Modules 2 and 5: start early, adopt existing standards, and avoid leaving these tasks until the end of a project.

### Community Standards and Best Practices

Community-developed standards, such as Voc4Cat, DCAT-AP+, and Reac4Cat, tend to be more practical than purely generic standards, since domain experts help develop them directly. Many of these tools are developed openly and welcome contributions and feedback from the community that uses them, rather than being maintained as closed, one-way specifications.

### FAIR-ifying Existing Datasets

Making an existing, unstructured dataset FAIR after the fact takes more effort than working FAIR from the start, but it is possible. This is exactly the kind of task that large language model-assisted extraction workflows are increasingly applied to: converting heterogeneous legacy datasets into structured, schema-conformant metadata.

## Resources and Further Education

### Key Organizations

The Research Data Alliance (RDA) is a global, community-driven organization, founded in 2013 by the European Commission together with the US NSF and NIST and the Australian government, working to build social and technical bridges for open data exchange. FORCE11 is the community that coined the term FAIR in 2016 and hosts, among other groups, the FAIR4RS working group on FAIR principles for research software specifically. GO FAIR is an initiative focused on the practical implementation of the FAIR principles, alongside RDA and FORCE11 as part of the broader FAIR infrastructure.

### Online Resources and Communities

forschungsdaten.info is a German-language portal with foundational articles covering nearly every topic this site addresses. FDMatStudium.nrw, a blended-learning RDM course from TH Köln and partners, referenced throughout this site, is an openly licensed course worth exploring directly for a different angle on the same material.

### Institutional Support Services

Most universities offer some form of dedicated research data support, typically attached to the library or a central research office. TU Dortmund's Forschungsdatenservice, introduced in Module 1, is one example, offering low-barrier advice on Data Management Plans, data structuring, collaboration, publication, and archiving, alongside TUDOdata as its own repository. Identifying the equivalent service at one's own institution is a practical starting point for turning the material on this site into practice.

## Worked Example

Extending the nickel-catalyst workflow from earlier modules with automation, the BET and XRD analysis scripts from Module 3 could be wrapped in a small Snakemake workflow, with one rule per characterization technique and the dependencies between raw files and processed results inferred automatically rather than run by hand each time. Packaging the required Python environment as a Singularity container ensures the same workflow produces identical results whether run on a lab workstation or on a shared HPC cluster. A short README next to the Snakemake file documents which package versions the container pins, closing the loop back to the documentation practices from Module 2.

## Self-Check

??? question "1. What is the main advantage of a workflow engine such as Snakemake over running analysis scripts by hand?"
    Dependencies between work steps are inferred automatically from their input and output files, and the workflow can be re-run reproducibly, rather than relying on a researcher to remember and repeat the correct manual sequence of steps.

??? question "2. Why is Singularity, rather than Docker, typically the standard on HPC clusters?"
    Singularity does not require root access to run, which is often impractical to grant on a shared HPC cluster, while Docker traditionally does require it.

??? question "3. Where should the documentation for an automated workflow ideally live?"
    Directly alongside the workflow code itself, as comments or a README next to the pipeline definition, rather than in a separate document that can fall out of sync with the actual workflow.

??? question "4. Name the organization that coined the term FAIR."
    FORCE11, in 2016.

## Next Steps

- This is the final module. Consider revisiting [Module 1: Foundations of RDM](../01-foundations/index.md) with the practical detail of the following modules in mind, or jump directly to whichever module is most relevant to a current project.
- Further reading: [Research Data Alliance](https://en.wikipedia.org/wiki/Research_Data_Alliance), [FORCE11](https://en.wikipedia.org/wiki/FORCE11), [forschungsdaten.info](https://forschungsdaten.info/).
- Catalysis-specific tools: Voc4Cat, DCAT-AP+, Repo4Cat, PID4Cat, and Reac4Cat, introduced throughout this site, are the practical entry points for applying RDM to catalysis research specifically.
