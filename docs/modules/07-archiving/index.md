---
description: Backup strategy, choosing a repository, Repo4Cat, and data citation.
---

# 7. Data Archiving & Publication

With data organized, documented, and described using standard vocabularies, as covered in the preceding modules, the remaining question is how to keep it safe and how to eventually share it beyond the immediate research group. This module covers backup strategy, choosing and using a data repository, and the practicalities of publishing and citing a dataset.

!!! tip "In this module"
    - Backup strategy and the 3-2-1 rule
    - Choosing and uploading to a data repository, including Repo4Cat
    - Publishing and citing research data

## Data Storage and Backup

### The 3-2-1 Rule

The 3-2-1 rule recommends keeping at least three copies of data, on two different types of storage medium, with at least one copy kept offsite, physically separate from the others. External storage media should be replaced roughly every five years, and the integrity of backups should be checked at least once a year.

### Institutional vs. Private Storage

Free consumer cloud services such as Google Drive, Dropbox, or OneDrive are best avoided for research data, since GDPR compliance is generally not guaranteed for them. Institutional, GDPR-compliant alternatives, such as sciebo or a university's own storage systems, should be used instead. Many universities also operate a dedicated institutional repository, TU Dortmund's TUDOdata among them, as an alternative to private cloud services.

### Cloud Storage

Cloud storage has a legitimate place within a 3-2-1 strategy, as the offsite copy for instance, but should not be the only copy of a dataset. The relevant selection criteria are GDPR compliance and the physical location of the servers, ideally within the EU or Germany.

### Long-Term Archiving

Long-term archiving is the practice of keeping research data available and interpretable for an indefinite period, typically understood as more than ten years after a project ends. It requires open, standardized, and, where possible, losslessly convertible file formats, covered in Module 5, since software capable of reading a proprietary format cannot be assumed to remain available over that time horizon.

## Data Repositories

### Types of Repositories

Discipline-specific repositories are tailored to a single field, Repo4Cat for catalysis research being one example. Institutional repositories are operated by a university or research organization, TUDOdata again being one example. Generic, discipline-independent repositories accept data regardless of field, Zenodo being the most prominent example.

### Choosing a Repository

re3data.org is a registry for finding a repository suited to a given field. Relevant quality criteria when choosing between repositories include persistent identifiers for both datasets and authors, comprehensive metadata and documentation, version control, clear download options, well-defined licenses and access rules, and CoreTrustSeal certification as a mark of trustworthiness.

### Zenodo, Figshare, Repo4Cat

Zenodo is a discipline-independent, European repository operated by CERN, with a close GitHub integration for minting DOIs, covered in Module 4. Figshare is particularly suited to visual and graphical datasets. EUDAT/B2Share is a European, program-funded repository. Repo4Cat is the catalysis-specific counterpart: NFDI4Cat's central repository, offering both private and public areas, FAIR-compliant storage with persistent identifiers, and hosting on servers within Germany.

### Upload Process and Metadata

Uploading to a repository typically requires filling in a set of mandatory metadata fields: title, authors, description, and license, a direct application of the metadata standards introduced in Module 2. The more complete this metadata is at the point of upload, the more findable the resulting dataset becomes later, the Findable principle from Module 1 in practice.

## Data Publication

### Data Papers

A data paper is a peer-reviewed publication that primarily describes a dataset itself: the circumstances of its collection, its structure, how to access it, and its potential for reuse, rather than discussing a hypothesis or a result. The dataset itself resides in a repository, with the data paper and the dataset cross-linked. Journals dedicated exclusively to data papers are a small minority of those that accept them; most accepting journals are open access.

### Citing Research Data

The standard citation format is: creator (publication year), title, version, publication agent, identifier. The required elements are the creator, with "et al." used from five names onward, the year of publication, the title and version, a DOI or PID link, and the publication agent, typically the institution or data center responsible.

### Embargoes and Access Restrictions

Repositories commonly allow a time-limited access restriction, an embargo, until an associated publication has appeared for instance. The dataset should still be deposited with complete metadata during an embargo. Doing so keeps it findable, in line with the Findable principle from Module 1, even while the data access itself remains delayed. Only that access is restricted: the Accessible principle from Module 1 allows access to remain restricted without a dataset ceasing to be FAIR.

### Measuring the Impact of Data Publications

The Data Citation Index is a commercial service that indexes datasets, data publications, and their citations in the literature. Altmetrics capture attention and usage beyond traditional citations, such as social media mentions, downloads, and discussion. Altmetrics services currently cover only a limited number of repositories, so disciplinary benchmarking for research data remains correspondingly limited.

## Worked Example

The nickel-catalyst dataset from Module 1, by now organized following Module 2, version-controlled where it consists of analysis code following Module 3, and annotated with Voc4Cat terms following Module 5, is ready for deposit. Repo4Cat is the natural choice of repository, since it is built specifically for catalysis data and issues persistent identifiers integrated with PID4Cat, introduced in Module 6. During upload, the mandatory metadata fields, title, authors, description, and license, are filled in following DCAT-AP+, and the dataset receives a DOI. Citing it afterward follows the standard format: for instance, "Author, A. (2026). Nickel-alumina hydrogenation dataset. Version 1. Repo4Cat. https://doi.org/[identifier]."

## Step-by-Step Guide: Choosing and Uploading to a Repository

1. Search re3data.org for repositories relevant to the dataset's field, or use a catalysis-specific repository such as Repo4Cat directly if the data fits that scope.
2. Check the shortlisted repositories against the quality criteria above: persistent identifiers, metadata completeness, version control, licensing clarity, and CoreTrustSeal certification.
3. Prepare the dataset following the organization and documentation conventions from Module 2 before starting the upload.
4. Fill in the required metadata fields completely, following the relevant metadata standard rather than leaving fields as generic free text.
5. Set an embargo period if the data should remain restricted until an associated publication appears, while still submitting full metadata now.
6. After the DOI is issued, record the resulting citation in the project's own documentation so it can be reused consistently in future publications.

## Self-Check

??? question "1. What does the 3-2-1 backup rule require?"
    At least three copies of the data, on two different types of storage medium, with at least one copy kept offsite, physically separate from the others.

??? question "2. Why are free consumer cloud services such as Google Drive or Dropbox generally discouraged for research data?"
    GDPR compliance is generally not guaranteed for them, so institutional, GDPR-compliant alternatives should be used instead.

??? question "3. What is the difference between a data paper and simply depositing a dataset in a repository?"
    A data paper is a separate, peer-reviewed publication that describes the dataset itself, its collection, structure, access, and reuse potential, and is cross-linked with the dataset, which continues to reside in the repository.

??? question "4. Why can a dataset under embargo still be considered FAIR?"
    It is deposited with complete metadata during the embargo, which keeps it findable. Only the data access itself is delayed, and FAIR allows access to remain restricted without a dataset ceasing to be FAIR.

## Next Steps

- Continue to [Module 8: Further Topics & Integration](../08-further-topics/index.md), which covers reproducible workflows and further resources for continued learning.
- Further reading: [re3data.org](https://www.re3data.org/), [TIB-Blog on data papers](https://blog.tib.eu/2022/02/15/data-papers-eine-ode-an-die-daten/).
- Catalysis-specific tools: Repo4Cat, used throughout the worked example above, is the repository to check first for any catalysis dataset.
