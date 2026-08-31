---
description: Issues, pull requests, GitHub Pages, Zenodo DOIs, CI/CD, and licensing.
---

# 4. Collaboration with GitHub & GitLab

Module 3 covered Git itself. This module turns to the platforms built around it, GitHub and GitLab, and to the collaboration workflows and licensing decisions that come with sharing a repository with other people.

!!! tip "In this module"
    - GitHub basics: repositories, issues, pull requests, GitHub Pages, and Zenodo integration
    - GitLab basics and how it compares to GitHub
    - Collaboration workflows and licensing code and data

## GitHub Basics

### Accounts and Repository Creation

A free GitHub account is sufficient for public repositories and, to a limited extent, private ones. A new repository can be created empty or from a template that already includes a README, a `.gitignore`, and a license file. For a research project, adding a license file from the start is worth doing rather than deferring it, a point returned to below.

### Issues and Project Boards

Issues record tasks, bugs, or points for discussion related to a repository, before or while work on them begins. Project boards are customizable, Kanban-style tables that link issues and pull requests together to plan and track work, supporting filtering, sorting, custom fields, and automation.

### Pull Requests and Code Review

A pull request (PR) proposes changes to a repository and invites discussion and review before those changes are merged. Code review conducted within pull requests is, according to studies from Google, one of the more effective ways to catch problems early, more so than testing or static analysis performed in isolation. Anyone with read access can comment, and reviewers can approve changes or request adjustments before a merge proceeds.

### GitHub Pages and Project Documentation

GitHub Pages hosts a static website directly from a repository, the same mechanism this site itself is built on. It is well suited to project documentation, README-based websites, or small course sites of this kind.

### Zenodo Integration for DOIs

Zenodo can archive a GitHub repository and assign it a DOI, making it citable. Every new release of the repository triggers a new archived version on Zenodo, complete with its own DOI, with metadata pulled automatically from the repository and the release. The repository must be public, and the integration is enabled through a per-repository toggle in Zenodo's GitHub connection settings.

## GitLab Basics

### GitLab vs. GitHub

Both platforms are built on Git but differ in feature set and hosting model. GitHub remains the default choice for open-source communities and cloud-native setups, partly because of GitHub Actions. GitLab is the stronger choice where self-hosting, integrated security and compliance reporting, or a single all-in-one tool rather than a patchwork of separate tools are the priority.

### Self-Hosted GitLab

GitHub offers self-hosting only on its Enterprise plan, while GitLab provides a free self-hosting option. This matters for organizations or consortia that prioritize control over their own infrastructure and data, for data protection reasons for instance, connecting back to the legal aspects introduced in Module 1.

### CI/CD Pipelines

GitLab has CI/CD integrated deeply into the platform: every project receives a `.gitlab-ci.yml` file describing its build, test, and deployment steps. GitHub achieves the same through GitHub Actions, available since late 2018, event-driven and flexibly configurable. In an RDM context, either can be used to automatically validate metadata or a data schema on every commit, for instance.

### GitLab for RDM

A self-managed GitLab instance allows consistent version control of code, configuration files, and smaller structured datasets within an environment an organization fully controls. Combined with CI/CD, this makes it possible to automate checks such as data schema or metadata validation.

## Collaboration Workflows

### Fork-and-Pull vs. Shared Repositories

In the shared-repository model, contributors receive push access to a common repository and work through branches; this is typical for small teams or internal projects. In the fork-and-pull model, contributors create their own copy, a fork, of the repository, work there, and propose changes back to the original through a pull request. Fork-and-pull lowers the barrier for new or external contributors, avoids an uncontrolled proliferation of branches in the main repository, and restricts write access for security reasons, which is why it is common practice for open-source projects.

### Branching Strategies for Research Projects

The main branch should always hold a working, publishable state. Feature or experiment branches are used for new analyses, evaluations, or, in the case of a site like this one, new sections of content, and are merged back into the main branch only after review. For course material such as this site, a branch per new module, kept open until its content is finished and checked, is a workable pattern.

### Working Jointly on Publications and Code

Clear agreement on roles and responsibilities in advance reduces the coordination overhead of shared work, echoing the team aspects already touched on in Module 1. Combining version control for code and text with the consistent naming and folder conventions from Module 2 prevents duplicated effort and version confusion when several people contribute to the same publication.

### Licensing Code and Data

Software licenses fall broadly into three groups: copyleft licenses, such as the GPL, which require that the same rights be passed on with any redistribution; permissive licenses, such as MIT or Apache, which favor the widest possible distribution, with Apache additionally offering patent protection; and public-domain-equivalent licenses. For research data and other non-software material, Creative Commons licenses, CC0, CC BY, or CC BY-SA, are the usual choice, and the DEAL consortium recommends CC BY for open-access publications specifically. Without an explicit license, reuse by third parties is only permitted with express permission. The absence of a license notice does not mean the material is free to use.

## Worked Example

Suppose the analysis script from Module 3 is now shared with a colleague through a GitHub repository. The repository is created with an MIT license from the start, since the code is meant to be reused freely by other groups working with similar catalyst systems. The colleague does not have push access to the main repository. They fork it instead, add a function to also parse ICP-OES results, and open a pull request. A reviewer comments that the new function should handle missing values the same way the existing BET and XRD functions already do. The colleague adjusts the pull request accordingly, and it is merged once the review is resolved. When the resulting analysis is later published, the repository is tagged as a release, and its Zenodo integration mints a DOI for that exact version of the code, which is then cited in the resulting paper.

## Step-by-Step Guide: Creating a First GitHub Repository with a License

1. Sign in to GitHub and select "New repository".
2. Choose a short, descriptive repository name and decide whether it should be public or private.
3. Initialize the repository with a README file.
4. Select a license during creation, MIT for code intended for broad reuse for instance, or add a `LICENSE` file afterward if the platform does not offer this step directly.
5. Add a `.gitignore` appropriate to the project, following the guidance from Module 3.
6. Clone the repository locally with `git clone`, add the project files, and push the first commit.
7. If the project should mint a DOI on release, connect the repository to Zenodo before creating the first release.

## Self-Check

??? question "1. What is a pull request, and why is code review within one considered effective?"
    A pull request proposes changes to a repository and invites discussion and review before merging. Studies from Google have found review conducted within pull requests to be one of the more effective ways to catch problems early, more so than testing or static analysis performed in isolation.

??? question "2. How does the fork-and-pull model differ from a shared-repository model?"
    In a shared-repository model, contributors have push access to a common repository and work through branches. In fork-and-pull, contributors work in their own copy of the repository and propose changes back through a pull request, which lowers the barrier for new contributors and restricts write access to the original repository.

??? question "3. What happens if a repository has no explicit license?"
    Reuse by third parties is only permitted with express permission. The absence of a license notice does not mean the material is free to use.

??? question "4. How does the Zenodo-GitHub integration work?"
    Once enabled for a public repository, every new release triggers a new archived version on Zenodo with its own DOI, with metadata pulled automatically from the repository and the release.

## Next Steps

- Continue to [Module 5: Data Standards & Interoperability](../05-data-standards/index.md), which turns from collaboration to the formats and vocabularies that make shared data interoperable.
- Further reading: [GitHub Docs on collaborative development models](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/about-collaborative-development-models), [Zenodo's GitHub integration guide](https://help.zenodo.org/docs/github/).
