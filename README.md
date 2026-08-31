# RDM-Website

Onboarding site for Research Data Management (RDM), for anyone getting
started with the topic. Built with [MkDocs](https://www.mkdocs.org/) and
[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/), deployed
automatically to GitHub Pages on every push to `main`.

**Live site:** https://mvoelken-hub.github.io/RDM-Website/

## Local development

```
pip install -r requirements.txt
mkdocs serve
```

Then open http://127.0.0.1:8000/.

## Deployment

The `deploy` workflow (`.github/workflows/deploy.yml`) builds and publishes the
site on every push to `main`. Before the first run can succeed, set
**Settings → Pages → Build and deployment → Source** to **"GitHub Actions"**
in this repository's GitHub settings (defaults to "Deploy from a branch",
which will not work with this workflow).

## Contributing

See the "About & Contributing" page on the live site for how to suggest edits.
Each page also has an edit pencil (top right) linking straight to the GitHub
editor for that file.

## Content status

Module 1 (Foundations of RDM) is fully written. Modules 2–8 are scaffolded
with their planned heading structure but not yet written out — see the
`Recherche/` folder in the Second Brain vault for source material per module.
