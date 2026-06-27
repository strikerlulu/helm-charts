# Helm Charts

Helm chart repository for publishing charts on GitHub Pages.

## Getting started

[Helm](https://helm.sh) must be installed to use the charts in this repository.

Refer to Helm's [documentation](https://helm.sh/docs/) to get started.

## Installation

```sh
helm repo add strikerlulu https://strikerlulu.github.io/helm-charts
```

You can then run `helm search repo strikerlulu` to search the charts.

## Repository Structure

```text
charts/                  # Helm charts (one chart per directory)
charts/homepage/         # Homepage chart source
docs/                    # GitHub Pages landing content
.github/workflows/       # Lint, release, and pages sync pipelines
```

## Publishing on GitHub Pages

- This repo uses `helm/chart-releaser-action` to package charts and update `gh-pages/index.yaml` on pushes to `main`.
- Enable GitHub Pages for the repository with source set to `gh-pages` branch, root (`/`).
- Use `secrets.GITHUB_TOKEN` provided by Actions; no personal token required.
- Landing content is synced from `docs/` to the `gh-pages` branch by `.github/workflows/pages-content.yaml`.
- Do not commit packaged `.tgz` to `main`; they are generated in releases.

## License

This project is licensed under the terms of the Apache 2.0 License license.
