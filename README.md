# Open Source MLOps

This is the [Fuzzy Labs](https://fuzzylabs.ai) guide to the universe of free and open source MLOps tools.

## Contents

- [What is MLOps, anyway?](#what-is-mlops-anyway)
- [What counts as open source?](#what-counts-as-open-source)
- [Data annotation](#data-annotation)
- [Data validation](#data-validation)
- [Data version control](#data-version-control)
- [Experiment tracking](#experiment-tracking)
- [Model training](#model-training)
- [Model registries](#model-registries)
- [Feature stores](#feature-stores)
- [Feature engineering](#feature-engineering)
- [Model deployment and serving](#model-deployment-and-serving)
- [Model monitoring](#model-monitoring)
- [Full stacks](#full-stacks)
- [More resources](#more-resources)

# What is MLOps anyway?

MLOps (machine learning operations) is a discipline that helps people to train, deploy and run machine learning models successfully in production environments. Because this is a new and rapidly-evolving field, there are a lot of tools out there, and new ones appear all the time. If we've missed any, then please do raise a pull request! (but please ensure it meets the definitions of open source below).

# What counts as open source?

In deciding what to include in this list we apply 3 criteria.

**👮‍ Fits the definition**

Rather than invent our own definition, we defer to the Open Source Initiative's [definition of open source](https://opensource.org/osd). The OSI have laid out a set of clear and unambiguous requirements for something to be considered free _and_ open source.

**⚖ Open source license**

So it follows that any OSI-approved license is acceptable, with examples including the various Apache, GPL, and BSD licenses. But this also means there are licenses that we don't include, such as the increasingly-popular Server Side Public License; to understand why, see the [OSI's writeup on the subject](https://opensource.org/node/1099).

**🔋 Batteries included**

We only list tools that are fully-functional and able to stand on their own. Some vendors offer limited open source versions of their tools, but ultimately those vendors want to guide you towards a SaaS offering. Sometimes there's a genuinely open-source client, but a proprietary server, meaning that the tool is not truly stand-alone. Everything in this collection comes complete with _"batteries included"_.

# Data annotation

Data annotation (or labelling) tools help us create labelled training data for use in supervised learning. This is one of the most labour-intensive processes in machine learning, and one where good tooling can save a great deal of effort. Because data comes in a huge variety of types and formats, there are also a huge variety of different tools which specialise in certain types of data.

| Supported Data Types | Name                                                                              | License    | Description                                                                                                                                                                                |
| -------------------- | ---------------------------------------                                           | ---------- | -----------                                                                                                                                                                                |
| Multiple             | [Label Studio](https://github.com/heartexlabs/label-studio)                       | Apache 2.0 | A Swiss army knife of data labelling.                                                                                                                                                      |
| Text                 | [doccano](https://github.com/doccano/doccano)                                     | MIT        | A popular tool for text annotation to build datasets for NLP tasks such as sentiment analysis and named entity recognition. Easy to setup and support most languages.                      |
| Image                | [labelme](https://github.com/wkentaro/labelme)                                    | GPL-3      | A graphical image annotation tool for object detection, segmentation, and classification. Supports polygon, circle, line, and point annotations.                                           |
| Video                | [Computer Vision Annotation Tool (CVAT)](https://github.com/openvinotoolkit/cvat) | MIT        | One of the most popular video and image annotation tools used by professional data annotation teams. It can be used online so you can start labelling your data without any installations. |
| Audio                | [Praat](https://github.com/praat/praat)                                           | GPL-3      | A speech analysis tool used for doing phonetics by computer. Some of its most prominent features are speech labelling and speech analysis.                                                 |

For a more in-depth list of data annotation tools, check out [Open Source Data Annotation & Labeling Tools](https://github.com/zenml-io/awesome-open-data-annotation) by ZenML.

# Data validation
The golden rule of machine learning is that a model is only as good as the data used to train it. Data validation is the process of verifying that data is accurate and consistent. As errors in data can severely impact the performance of your model, it is crucial to spot data errors early.

Sometimes your model might achieve good accuracy during training , but performs poorly on real-world data. This could be an indication that there are errors in your data which were not spotted during validation. Even a tiny mismatch in the format of the data provided to your machine learning model can significantly impact its performance.

| Name                                                                                                      | License    | Description                                                                                                                                                                                                                       |
| ----                                                                                                      | -------    | -----------                                                                                                                                                                                                                       |
| [Great Expectations](https://github.com/great-expectations/great_expectations)                            | Apache 2.0 | An easy-to-use tool with over 280 assertions for validating, documenting, and profiling your data to maintain quality. Great Expectations works with a variety of data sources, including SQL databases, and various file formats |
| [Data Validation Tool (DVT)](https://github.com/GoogleCloudPlatform/professional-services-data-validator) | Apache 2.0 | A Python tool that allows you to build custom query validation, schema validation and much more. It also supports a wide range of databases such as MySql, Snowflake and BigQuery, just to name a few.                            |
| [data-diff](https://github.com/datafold/data-diff)                                                        | MIT        | An open-source command-line tool to compare rows across two different databases. An ideal tool to use for data migration.                                                                                                         |
| [Cerberus](https://github.com/pyeve/cerberus)                                                             | ISC        | A powerful yet simple data validation library for Python. Lightweight data validation functionality out-of-the-box and is designed to be easily extensible, allowing for custom validation.                                       |
| [deequ](https://github.com/awslabs/deequ)                                                                 | Apache 2.0 | A library built on top of Apache Spark for defining "unit tests for data" in large datasets.                                                                                                                                      |

# Data version control

Just like code, data grows and evolves over time. Data versioning tools help you to keep track of these changes.

You might wonder why you can't just store data in Git (or equivalent). There are a few reasons this doesn't work, but the main one is size: Git is designed for small text files, and typical datasets used in machine learning are just too big. Some tools, like DVC, store the data externally, but also integrate with Git so that data versions can be linked to code versions.

| Name                                                       | License    | Description                                                                                 |
| ---------------------------------------------------------- | ---------- | ------------------------------------------------------------------------------------------- |
| [DVC](https://dvc.org)                                     | Apache 2.0 | One of the most popular general-purpose data versioning tools.                              |
| [Delta Lake](https://delta.io)                             | Apache 2.0 | Data versioning for data warehouses.                                                        |
| [LakeFS](https://lakefs.io)                                | Apache 2.0 | Transform your object storage into a Git-like repository.                                   |
| [Git LFS](https://www.atlassian.com/git/tutorials/git-lfs) | MIT        | Not specialised in machine learning use-cases, but another popular way to version datasets. |

# Experiment tracking

Machine learning involves a lot of experimentation. We end up training a lot of models, most of which are never intended to go into production, but represent progressive steps towards having something production-worthy. Experiment tracking tools are there to help us keep track of each experiment. What exactly do we need to track? typically this includes the code version, data version, input parameters, training performance metrics, as well as the final model assets.

| Name                                                  | License    | Description                                                                               |
| ----------------------------------------------------- | ---------- | ----------------------------------------------------------------------------------------- |
| [Sacred](https://github.com/IDSIA/sacred)             | MIT        |                                                                                           |
| [Tensorboard](https://www.tensorflow.org/tensorboard) | Apache 2.0 |                                                                                           |
| [Guild.AI](https://guild.ai)                          | Apache 2.0 |                                                                                           |
| [MLFlow](https://mlflow.org)                          | Apache 2.0 |                                                                                           |
| [Kedro](https://kedro.readthedocs.io/)                | Apache 2.0 | A Python framework for creating reproducible, maintainable and modular data science code. |

# Model training

| Name                                        | License    | Description                                                                                       |
| ------------------------------------------  | ---------- | ------------------------------------------------------------------------------------------------- |
| [MLFlow](https://mlflow.org)                | Apache 2.0 |                                                                                                   |
| [Kubeflow](https://www.kubeflow.org)        | Apache 2.0 | The machine learning toolkit for kubernetes                                                       |
| [Metaflow](https://metaflow.org)            | Apache 2.0 |                                                                                                   |
| [envd](https://github.com/tensorchord/envd) | Apache 2.0 | The machine learning development environment for data science and AI/ML engineering teams.        |

# Model registries

Model registries are used to track the lifecycle of trained machine learning models.

| Name                                                   | License    | Description                                                                                                                                                          |
| ------------------------------------------             | ---------- | -------------------------------------------------------------------------------------------------                                                                    |
| [MLFlow](https://mlflow.org)                           | Apache 2.0 | The ML Flow [model registry](https://mlflow.org/docs/latest/model-registry.html) allows you to store, annotate, discover, and manage models in a central repository. |
| [modelstore](https://github.com/operatorai/modelstore) | Apache 2.0 | A Python library for versioning, storing, and tracking ML model artefacts across several different types of storage.                                                 |

# Workflows

| Name                                    | License    | Description |
|-----------------------------------------|------------|-------------|
| [CML](https://github.com/iterative/cml) | Apache 2.0 |             |

# Feature stores

| Name                                                    | License    | Description                                     |
| ------------------------------------------------------- | ---------- | ----------------------------------------------- |
| [Feast](https://feast.dev)                              | Apache 2.0 | A complete open source feature store.           |
| [Hopsworks](https://github.com/logicalclocks/hopsworks) | AGPL-3.0   | A feature store, feature engineering, and more. |

# Feature Engineering

| Name                                                    | License    | Description                                     |
| ------------------------------------------------------- | ---------- | ----------------------------------------------- |
| [Hamilton](https://github.com/stitchfix/hamilton)       | BSD-3 CC   | A way to organize, curate, and scale your feature transform code.   |

# Model deployment and serving

Model serving is the process of taking a trained model and presenting it behind a REST API, and this enables other software components to interact with a model. To make deployment of these model servers as simple as possible, it's commonplace to run them inside Docker containers and deploy them to a container orchestration system such as Kubernetes.

| Name                                                   | License    | Description                                              |
| ------------------------------------------------------ | ---------- | -------------------------------------------------------- |
| [Seldon Core](https://github.com/SeldonIO/seldon-core) | Apache 2.0 | Turn your models into microservices to run on Kubernetes |
| [BentoML](https://github.com/bentoml/BentoML)          | Apache 2.0 |                                                          |
| [Bodywork](https://www.bodyworkml.com)                 | AGPL-3.0   |                                                          |
| KServe                                                 | Apache 2.0 |                                                          |

# Model monitoring

Monitoring means making sure that each deployed model is both functioning, and producing sensible results. We don't just want to check for errors in the traditional sense, but also for things like drift and signs of bias in the predictions and decisions that come from a model.

| Name                                                                 | License    | Description                                                                                                                               |
| -------------------------------------------------------------------- | ---------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| [Evidently](https://evidentlyai.com)                                 | Apache 2.0 |                                                                                                                                           |
| [Boxkite ML](https://github.com/boxkite-ml/boxkite)                  | Apache 2.0 |                                                                                                                                           |
| [Alibi Detect](https://github.com/SeldonIO/alibi-detect) (by Seldon) | Apache 2.0 |                                                                                                                                           |
| [whylogs](https://github.com/whylabs/whylogs)                        | Apache 2.0 | whylogs allows users to generate data profiles, statistical summaries of data, that can be used as logs for an AI observability platform. |
| [RecList](https://reclist.io/)                        | MIT | RecList is an open source library providing behavioral testing for recommender systems, to be used either offline or online for a better understanding of model "true" generalization abilities. RecList comes with a [WWW paper](https://arxiv.org/abs/2111.09963), and several [tutorials](https://www.youtube.com/watch?v=cAlJYxFYA04). |

# Data Catalogues 

Tools for data discovery and data access control. Can be very important to workout and manage what data can be trained on or tested on, and how these rules vary from client to client. Great summary at https://atlan.com/open-source-data-governance-tools/. This space is pretty young with no real convergence on an expected set of features. They vary in focus from data discovery to data accesss management.

| Name                                                                                           | License       | Description |
| ---------------------------------------------------------------------------------------------- | ------------- | ----------- |
| [Magda](https://magda.io/)                                                                     | Apache 2.0    |             |
| [Amundsen](https://www.amundsen.io/)                                                           | Apache 2.0    |             |
| [Apache Atlas](https://atlas.apache.org/)                                                      | Apache 2.0    |             |

# Full stacks

| Name                                                                                           | License    | Description                                                                                       |
| ---------------------------------------------------------------------------------------------- | -------    | -----------                                                                                       |
| [Open MLOps](https://github.com/datarevenue-berlin/OpenMLOps)                                  | MIT        |                                                                                                   |
| [You Don't Need a Bigger Boat](https://github.com/jacopotagliabue/you-dont-need-a-bigger-boat) | MIT        | An end-to-end open project, from real-world data to an endpoint serving Transformer-based predictions, supported by [videos](https://www.youtube.com/watch?v=Ndxpo4PeEms), [scholarly references](https://arxiv.org/abs/2107.07346) and a [TDS blog series](https://towardsdatascience.com/tagged/mlops-without-much-ops) on "Reasonable Scale" ML                                                                                                  |
| [Recommendations at "Reasonable Scale"](https://github.com/jacopotagliabue/recs-at-resonable-scale) | MIT        | An end-to-end recommendation project leveraging NVIDIA Merlin library to train a deep learning model on top of the Modern Data Stack; the related NVIDIA [keynote talk](https://youtu.be/9rouLchcC0k?t=147) is also publicly available. |
| [ZenML](https://github.com/zenml-io/zenml)                                                     | Apache 2.0 | An extensible, open-source MLOps framework to create production-ready machine learning pipelines. |
# Governance

| Name                                   | License    | Description                                                                                                       |
| -------------------------------------- | ---------- | ----------------------------------------------------------------------------------------------------------------- |
| [Bailo](https://github.com/gchq/Bailo) | Apache 2.0 | Managing the lifecycle of machine learning to support scalability, impact, collaboration, compliance and sharing. |

# More resources

Here are some more resources for MLOps, both open-source and proprietary

- [Top 10 Open Source MLOps Tools](https://thechief.io/c/editorial/top-10-open-source-mlops-tools)
- [Awesome MLOps](https://github.com/visenger/awesome-mlops) - a mixture of open source and proprietory tools and platforms.
- [Best open source MLOps tools](https://neptune.ai/blog/best-open-source-mlops-tools)
