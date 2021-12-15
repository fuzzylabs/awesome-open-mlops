# Open Source MLOps

This is the [Fuzzy Labs](https://fuzzylabs.ai) guide to the universe of free and open source MLOps tools.

## Contents

* [What is MLOps, anyway?](#what-is-mlops-anyway)
* [What counts as open source?](#what-counts-as-open-source)
* [Data version control](#data-version-control)
* [Experiment tracking](#experiment-tracking)
* [Model training](#model-training)
* [Feature stores](#feature-stores)
* [Model deployment and serving](#model-deployment-and-serving)
* [Model monitoring](#model-monitoring)
* [Full stacks](#full-stacks)
* [More resources](#more-resources)

# What is MLOps anyway?

MLOps (machine learning operations) is a discipline that helps people to train, deploy and run machine learning models successfully in production environments. Because this is a new and rapidly-evolving field, there are a lot of tools out there, and new ones appear all the time. If we've missed any, then please do raise a pull request! (but please ensure it meets the definitions of open source below).

# What counts as open source?

In deciding what to include in this list we apply 3 criteria.

**Fits the definition**

Rather than invent our own definition, we defer to the Open Source Initiative's [definition of open source](https://opensource.org/osd). The OSI have laid out a set of clear and unambiguous requirements for something to be considered free _and_ open source.

**Open source license**

So it follows that any OSI-approved license is acceptable, with examples including the various Apache, GPL, and BSD licenses. But this also means there are licenses that we don't include, such as the increasingly-popular Server Side Public License; to understand why, see the [OSI's writeup on the subject](https://opensource.org/node/1099).

**Batteries included**

We only list tools that are fully-functional and able to stand on their own. Some vendors offer limited open source versions of their tools, but ultimately those vendors want to guide you towards a SaaS offering. Sometimes there's a genuinely open-source client, but a proprietary server, meaning that the tool is not truly stand-alone. Everything in this collection come complete with _"batteries included"_.

# Data version control

Just like code, data grows and evolves over time. Data versioning tools help you to keep track of these changes.

You might wonder why you can't just store data in Git (or equivalent). There are a few reasons this doesn't work, but the main one is size: Git is designed for small text files, and typical datasets used in machine learning are just too big. Some tools, like DVC, store the data externally, but also integrate with Git so that data versions can be linked to code versions.

| Name                                                       | License    | Description                                                                                 |
|------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------|
| [DVC](https://dvc.org)                                     | Apache 2.0 | One of the most popular general-purpose data versioning tools.                              |
| [Delta Lake](https://delta.io)                             | Apache 2.0 | Data versioning for data warehouses.                                                        |
| [LakeFS](https://lakefs.io)                                | Apache 2.0  | Transform your object storage into a Git-like repository.                                   |
| [Git LFS](https://www.atlassian.com/git/tutorials/git-lfs) | MIT        | Not specialised in machine learning use-cases, but another popular way to version datasets. |

# Experiment tracking

Machine learning involves a lot of experimentation. We end up training a lot of models, most of which are never intended to go into production, but represent progressive steps towards having something production-worthy. Experiment tracking tools are there to help us keep track of each experiment. What exactly do we need to track? typically this includes the code version, data version, input parameters, training performance metrics, as well as the final model assets.

| Name                                                  | License    | Description |
|-------------------------------------------------------|------------|-------------|
| [Sacred](https://github.com/IDSIA/sacred)             | MIT        |             |
| [Tensorboard](https://www.tensorflow.org/tensorboard) | Apache 2.0 |             |
| [Guild.AI](https://guild.ai)                          | Apache 2.0 |             |
| [MLFlow](https://mlflow.org)                          | Apache 2.0 |             |
| [Kedro](https://kedro.readthedocs.io/)                | Apache 2.0 | A Python framework for creating reproducible, maintainable and modular data science code. |

# Model training

| Name                                       | License    | Description                                                                                       |
|--------------------------------------------|------------|---------------------------------------------------------------------------------------------------|
| [MLFlow](https://mlflow.org)               | Apache 2.0 |                                                                                                   |
| [Kubeflow](https://www.kubeflow.org)       | Apache 2.0 |                                                                                                   |
| [Metaflow](https://metaflow.org)           | Apache 2.0 |                                                                                                   |

# Feature stores

| Name                       | License    | Description                           |
|----------------------------|------------|---------------------------------------|
| [Feast](https://feast.dev) | Apache 2.0 | A complete open source feature store. |
| [Hopsworks](https://github.com/logicalclocks/hopsworks) | AGPL-3.0 | A feature store, feature engineering, and more. |

# Model deployment and serving

Model serving is the process of taking a trained model and presenting it behind a REST API, and this enables other software components to interact with a model. To make deployment of these model servers as simple as possible, it's commonplace to run them inside Docker containers and deploy them to a container orchestration system such as Kubernetes.

| Name                                                   | License    | Description |
|--------------------------------------------------------|------------|-------------|
| [BentoML](https://github.com/bentoml/BentoML)          | Apache 2.0 |             |
| [Bodywork](https://www.bodyworkml.com)                 | AGPL-3.0   |             |

# Model monitoring

Monitoring means making sure that each deployed model is both functioning, and producing sensible results. We don't just want to check for errors in the traditional sense, but also for things like drift and signs of bias in the predictions and decisions that come from a model.

| Name                                                                 | License    | Description |
|----------------------------------------------------------------------|------------|-------------|
| [Evidently](https://evidentlyai.com)                                 | Apache 2.0 |             |
| [Boxkite ML](https://github.com/boxkite-ml/boxkite)                  | Apache 2.0 |             |

# Full stacks

| Name                                                                                           | License | Description |
|------------------------------------------------------------------------------------------------|---------|-------------|
| [Open MLOps](https://github.com/datarevenue-berlin/OpenMLOps)                                  | MIT     |             |
| [You Don't Need a Bigger Boat](https://github.com/jacopotagliabue/you-dont-need-a-bigger-boat) | MIT     |             |

# More resources

Here are some more resources for MLOps, both open-source and proprietary.

* [Top 10 Open Source MLOps Tools](https://thechief.io/c/editorial/top-10-open-source-mlops-tools)
* [Awesome MLOps](https://github.com/visenger/awesome-mlops) - a mixture of open source and proprietory tools and platforms.
* [Best open source MLOps tools](https://neptune.ai/blog/best-open-source-mlops-tools)
