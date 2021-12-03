# Open Source MLOps

This is the [Fuzzy Labs](https://fuzzylabs.ai) guide to the universe of free and open source MLOps tools.

## Contents

* [What is MLOps, anyway?](#what-is-mlops)
* [Data versioning](#data-versioning)
* [Experiment tracking](#experiment-tracking)
* [Model training](#model-training)
* [Model deployment and serving](#model-deployment-and-serving)
* [Model monitoring](#model-monitoring)
* [Full stacks](#full-stacks)
* [More resources](#more-resources)

# What is MLOps anyway?

MLOps (machine learning operations) is a discipline that helps people to train, deploy and run machine learning models successfully in production environments. Because this is a new and rapidly-evolving field, there are a lot of tools out there, and new ones appear all the time. If we've missed any, then please do raise a pull request!

# Data version control

Just like code, data grows and evolves over time. Data versioning tools help you to keep track of these changes.

You might wonder why you can't just store data in Git (or equivalent). There are a few reasons this doesn't work, but the main one is size: Git is designed for small text files, and typical datasets used in machine learning are just too big. Some tools, like DVC, store the data externally, but also integrate with Git so that data versions can be linked to code versions.

* [DVC](https://dvc.org) - one of the most popular general-purpose data versioning tools.
* [Delta Lake](https://delta.io) - data versioning for data warehouses.
* [LakeFS](https://lakefs.io) - Transform your object storage into a Git-like repository.
* [Git LFS](https://www.atlassian.com/git/tutorials/git-lfs) - while this doesn't specialise in machine learning use-cases, it's another popular way to version datasets.

# Experiment tracking

Machine learning involves a lot of experimentation. We end up training a lot of models, most of which are never intended to go into production, but represent progressive steps towards having something production-worthy. Experiment tracking tools are there to help us keep track of each experiment. What exactly do we need to track? typically this includes the code version, data version, input parameters, training performance metrics, as well as the final model assets.

* [Sacred](https://github.com/IDSIA/sacred).
* [Tensorboard](https://www.tensorflow.org/tensorboard).
* [Guild.AI](https://guild.ai).
* [MLFlow](https://mlflow.org).

# Model training

* [MLFlow](https://mlflow.org).
* [Kubeflow](https://www.kubeflow.org).
* [Metaflow](https://metaflow.org).

# Feature stores

* [Feast](https://feast.dev)

# Model deployment and serving

Model serving is the process of taking a trained model and presenting it behind a REST API, and this enables other software components to interact with a model. To make deployment of these model servers as simple as possible, it's commonplace to run them inside Docker containers and deploy them to a container orchestration system such as Kubernetes.

* [BentoML](https://github.com/bentoml/BentoML)
* [Bodywork](https://www.bodyworkml.com)

# Model monitoring

* [Evidently](https://evidentlyai.com).
* [Boxkite ML](https://github.com/boxkite-ml/boxkite).

# Full stacks

* [https://github.com/datarevenue-berlin/OpenMLOps](Open MLOps).
* [https://github.com/jacopotagliabue/you-dont-need-a-bigger-boat](You Don't Need a Bigger Boat).

# More resources

Here are some more resources for MLOps, both open-source and proprietary.

* [Top 10 Open Source MLOps Tools](https://thechief.io/c/editorial/top-10-open-source-mlops-tools)
* [The Awesome MLOps List](https://github.com/visenger/awesome-mlops) - a mixture of open source and proprietory tools and platforms.
* [Best open source MLOps tools](https://neptune.ai/blog/best-open-source-mlops-tools)
