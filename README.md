# Open Source MLOps

Fuzzy Labs' guide to the universe of open source MLOps tools.

## Contents

* [What is MLOps, anyway?](#what-is-mlops)
* [Data versioning](#data-versioning)
* [Experiment tracking](#experiment-tracking)
* [Model training](#model-training)
* [Model deployment](#model-deployment)
* [Model registries / storage](#model-registries-storage)
* [Model deployment and serving](#model-deployment-and-serving)
* [Model monitoring](#model-monitoring)
* [Full stacks](#full-stacks)
* [More resources](#more-resources)

# What is MLOps anyway?

MLOps is a new discipline that helps people do train, deploy and run machine learning models successfully in production environments.

# Data versioning

Just like code, data grows and evolves over time. Data versioning tools help you to keep track of these changes.

You might wonder why you can't just store data in Git (or equivalent). There are a few reasons this doesn't work, but the main one is size: Git is designed for small text files, and typical datasets used in machine learning are just too big. Some tools, like DVC, store the data externally, but also integrate with Git so that data versions can be linked to code versions.

Read more in our [guide to data versioning](https://medium.com/p/5c93d6a58823).

* [DVC](https://dvc.org) - [example notebook](data-versioning/dvc.ipynb)
* Delta Lake
* Dolt
* LakeFS
* [Git LFS](https://git-lfs.github.com)
* [Pachyderm community edition](https://www.pachyderm.com/products/#community-edition)

# Experiment tracking

* Sacred
* MLFlow
* Tensorboard
* DVC
* ClearML
* Guild.AI

# Model training

* MLFlow
* Kubeflow
* Metaflow

# Model registries / storage

* MLFlow

# Feature stores

* [Feast](https://feast.dev)

# Model deployment and serving

* [BentoML](https://github.com/bentoml/BentoML)

# Model monitoring

* [Evidently](https://evidentlyai.com)

# Full stacks

* https://github.com/datarevenue-berlin/OpenMLOps

# More resources

Here are some more resources for MLOps, both open-source and proprietary.

* [Top 10 Open Source MLOps Tools](https://thechief.io/c/editorial/top-10-open-source-mlops-tools)
* [The Awesome MLOps List](https://github.com/visenger/awesome-mlops) - a mixture of open source and proprietory tools and platforms.

