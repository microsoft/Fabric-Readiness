# Fabric Readiness Hands-on Day - Instructor guide

> This guide is under construction. If you need help while we're writing it, please open an issue and tag @cmaneu ;).

## What is an "Hands-on Day"?

## How to organise an Hands-on Day?

### Content usage guidelines

### Prepare for the delivery

- Download the latest content from the GitHub repository
- Become familiar with the latest product updates [https://blog.fabric.microsoft.com/]
- Choose which labs you'll run in the afternoon
- Create a backup tenant with username/passwords

Please reach out through GitHub issues with any questions.

### Logistics

- Make sure you have good network connectivity
- Ensure you have additional proctors/moderators to support the attendees.

### Preparing tenants for the labs

## How to deliver an Hands-on Day?

### Keynotes


### Labs



### Demo

We recommend to do a demo of Microsoft Fabric at the end of the Afternoon keynote. For now, we don't publish guide for this demo. Here are the things we showcase during this demo.

#### Introduction
- Introduction of Fabric personas and how to switch between the different experiences
- Presentation of workspaces and introduction of Onelake

#### Workspace and Lakehouse Overview
- Opening of a workspace (with Lakehouse and Streaming included)
- Review of the workspace settings and explanation of Fabric capabilities
- Opening of a lakehouse

#### Tables, Files, and Onelake Explorer
- Explanation of Tables and files, parquet/Delta etc.
- Introduction of the Onelake Explorer by comparing structures
- Return to the Lakehouse and presentation of shortcuts

#### Shortcuts and Data Integration
- File type: Introduction of internal and external shortcuts with links on a Databricks ADLS Gen2 and an AWS S3
- Opening of AWS S3 and loading data into a Fabric table via wizard
- Introduction of table shortcuts with a demo shortcut on a Databricks Delta table, exploration of the underlying files of the table

#### Working with Delta Tables
- Story about DB + Fabric and generally third parties exposing Delta

#### Lakehouse and Warehouse Concepts
- Switching the Lakehouse to Readonly Warehouse and explanation of the difference between pure Warehouse and Lakehouse
- Focus on the fact that all tables are tables and no longer shortcuts

#### Modeling and Semantic Models
- Explanation of modeling with a DAX measure
- Explanation and creation of a semantic model, explanation of the chaining of semantic models
- Opening of a semantic model with the quick data explorer
- Creation from scratch of a report in direct lake mode
- Demo of copilot on the semantic model

#### Copilot Features and Demonstrations
- Activation of copilot in notebooks
- Explanation of copilot to the right and copilot in the code
- Demo copilot exchange for loading into a dataframe of a table
- Demo of a %code cell for loading and filtering
- Explanation of %translate to translate code

#### Data Wrangling and Stream Processing
- Loading of a dataset and opening of the data wrangler, manipulation sort and filter and back of the code in the notebook
- Back in the WS and opening/creation of a real-time stream with creation of a custom app entry and explanation
- Creation of the output on a data explorer or lakehouse base explaining the event processor (demo aggregate, filter, etc.) and telling the story around complex event processing

#### Monitoring and Real-time Analysis
- Back in the notebook and execution of the cell that sends to the custom app entry of the stream
- Presentation of notebook monitoring / and scheduling
- Go into the stream processor and show that the events are received
- Go into the KQL base and show that the data is stored
- Activation of lakehouse sync in the KQL base
- Definition of a query set and creation of a real-time PBI report on the query set as a source
- Retrieval in the lakehouse of a shortcut on the sync data of the KQL base

