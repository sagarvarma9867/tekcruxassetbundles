# Databricks Asset Bundles – Environment-Based Deployment

## Overview

Implemented a Git-based deployment framework for Databricks using **Databricks Asset Bundles, Databricks CLI, and GitHub**. The project manages notebooks, workflow jobs, and declarative pipelines as code and supports deployment across multiple environments.

## Technologies

**Databricks | Asset Bundles | Databricks CLI | GitHub | Git | Python | Databricks Workflows | Declarative Pipelines**

## Key Features

* Implemented **Databricks Asset Bundles** to manage Databricks resources as code.
* Integrated **GitHub** with Databricks Git folders and feature-branch development.
* Configured **DEV and PROD deployment targets** using `databricks.yml`.
* Implemented **dynamic environment-specific catalog configuration** using Asset Bundle variables instead of hardcoded values.
* Managed **Databricks Workflow Jobs and Declarative Pipelines** through YAML configuration.
* Used **relative resource paths** to make deployments environment-independent.
* Configured deployment **presets, workspace paths, and permissions** for target environments.
* Implemented bundle **validation, summary, and deployment** using Databricks CLI.
* Demonstrated **incremental synchronization** of changed and newly added bundle files.

## Deployment

### DEV

```bash
databricks bundle validate --target dev
databricks bundle deploy --target dev
```

### PROD

```bash
databricks bundle validate --target prod
databricks bundle deploy --target prod --var="catalog_name=assetbundles_prod"
```

## Project Structure

```text
dabproject/
├── databricks.yml
├── resources/
│   ├── jobs/
│   ├── pipelines/
│   └── variables/
└── src/
    ├── notebooks/
    └── pipelines/
```

## Outcome

Created a reusable **environment-independent Databricks deployment structure** where the same codebase can be promoted across environments while environment-specific configuration is supplied dynamically at deployment time.
