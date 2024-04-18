# RTDIP Integration with OpenSTEF

OpenSTEF offers a comprehensive software solution for predicting electricity grid load for the next 48 hours. RTDIP has developed a [Database connector](../../../code-reference/integrations/openstef/database.md) that enables the execution of OpenSTEF pipelines on data that has been ingested using RTDIP.

## Prerequisites

Ensure that you have followed the installation instructions as specified in the [Getting Started](../../../../getting-started/installation.md) section and follow the steps which highlight the installation requirements for using Integrations. In particular:

* [RTDIP SDK Installation](../../../../getting-started/installation.md#installing-the-rtdip-sdk)

!!! note "RTDIP SDK installation"
    Ensure you have installed the RTDIP SDK, as a minimum, as follows:
    ```
    pip install "rtdip-sdk[integrations]"
    ```

    For all installation options please see the RTDIP SDK installation [instructions.](../../../../getting-started/installation.md#installing-the-rtdip-sdk)

## Overview
OpenSTEF employs a fully automated machine learning pipeline to generate future load forecasts, utilizing both historical grid data and external predictors like weather and market prices, aiding in anticipating load congestion and maximizing asset utilization. 

OpenSTEF tasks can be called to perform training, forecasting, and evaluation. These tasks handle fetching prediction job configuration and feature data from a database, handling task exceptions, and writing data back to a database. These tasks are driven by the corresponding pipelines, which have the ability to select the necessary features for the tasks, based on the requirements of a prediction job. Machine learning is a key component of these pipelines, enabling them to perform training, forecasting, and evaluation. The models generated from these processes are stored and managed using MLflow. Current model types that are supported include 'xgb', 'xgb_quantile', 'lgb', 'linear' and 'linear_quantile'.

RTDIP has simplified the usage of OpenSTEF tasks and pipelines with data ingested through RTDIP by introducing a [Database connector](../../../code-reference/integrations/openstef/database.md). This connector serves as an interface for feature and configuration data stored in Databricks, adhering to our data models.

## Conclusion
Find out more about OpenSTEF [here](https://openstef.github.io/openstef/index.html). For examples of how to use the [Database connector](../../../code-reference/integrations/openstef/database.md), click on the following links:

* [Train Models](../../../examples/integrations/openstef/train-model.md)
* [Create Forecasts](../../../examples/integrations/openstef/create-forecast.md)