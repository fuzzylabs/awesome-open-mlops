# Open Source MLOps

Fuzzy Labs' guide to the universe of open source MLOps tools.

## Contents

* [What is MLOps, anyway?](#what-is-mlops)
* [Open source MLOps tools](#open-source-mlops-tools)
  * [Data versioning](#data-versioning)
  * [Experiment tracking](#experiment-tracking)
  * [Model training](#model-training)
  * [Model registries](#model-registries)
  * [Monitoring](#monitoring)
* [More resources](#more-resources)

# What is MLOps anyway?

MLOps is a new discipline that helps people do train, deploy and run machine learning models successfully in production environments.

# Open source MLOps tools

## Data versioning

Just like code, data grows and evolves over time. Data versioning tools help you to keep track of these changes.

You might wonder why you can't just store data in Git (or equivalent). There are a few reasons this doesn't work, but the main one is size: Git is designed for small text files, and typical datasets used in machine learning are just too big. Some tools, like DVC, store the data externally, but also integrate with Git so that data versions can be linked to code versions.

Some criteria for choosing a data versioning tool include:

* Integration with source control tools such as Git.
* Data storage options.
* Data format support.

| Tool                                  | License    | Example notebook                 | Comments                      |
|---------------------------------------|------------|----------------------------------|-------------------------------|
| [DVC](https://dvc.org)                | Apache 2.0 | [DVC](data-versioning/dvc.ipynb) | A good general-purpose option |
| Delta Lake                            | Apache 2.0 |                                  |                               |
| Dolt                                  | Apache 2.0 |                                  |                               |
| LakeFS                                | Apache 2.0 |                                  |                               |
| [Git LFS](https://git-lfs.github.com) | MIT        |                                  |                               |

## Experiment tracking

| Tool | License | Example notebook | Comments |
|------|---------|------------------|----------|
|      |         |                  |          |

## Model training

...

## Model registries

...

## Monitoring

...

# More resources

Here are some more resources for MLOps, both open-source and proprietary.

* https://madewithml.com/#mlops
* https://github.com/visenger/awesome-mlops
* https://mlops.toys
