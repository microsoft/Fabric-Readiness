# Fabric Readiness Hands-on Day - Instructor guide

## What is an "Hands-on Day"?

Fabric Readiness hands-on day (HOD) is a full day tailored to discover and explore Microsoft Fabric, providing participants with a comprehensive understanding and hands-on experience in a real-world context.

## How to organise an Hands-on Day?

The HOD can be organized virtually or in-person. To organize it, you'll need: 
- A number of instructors based on the number of attendees (A ratio of 1:6 - 1:10 is recomended).
- Either provide a Fabric tenant, or ensure that all attendees will have access to the tenant.

The HOD is divided in two half-days. They both have a keynote/presentation time, and a hands-on lab.
- **Morning**: The content of the morning is fixed. Please follow the proposed agenda.
- **Afternoon**: The afternoon content allows for more personalization
    - You can choose the afternoon lab depending on your audience: Data Science, Realtime, Datawarehouse
    - During the keynote, if you are a Microsoft Partner, do not hesitate to take a few minutes to introduce how you can help your customers in implementing Microsoft Fabric. 

> If something is unclear in this doc, or if you have additional questions, please open an issue so we can help you!

### Prepare for the delivery

- Download the latest content from the GitHub repository
- Become familiar with the latest product updates [https://blog.fabric.microsoft.com/]
- Choose which labs you'll run in the afternoon
- Create a backup tenant with username/passwords.

Please reach out through GitHub issues with any questions.

### Logistics

- Make sure you have good network connectivity
- Ensure you have additional proctors/moderators to support the attendees.

### Preparing tenants for the labs

Microsoft Fabric labs requires a specific environment: 
- A Microsoft 365 Tenant (some labs use OneDrive, and thus will not work with Azure AD-only tenants)
- An access to Microsoft Fabric (The tenant admin needs to enable it)
- An access to a Microsoft Fabric Capacity: Trial, Premium or Azure "F SKU".

While the amount of volume processed in the labs is small (in the 100's MBs), all participants will create and interact with a Spark session. The way [Fabric Spark Session & nodes](https://learn.microsoft.com/fabric/data-engineering/spark-compute) works may create some limitations depending on your environment.

#### About Fabric Trials

Microsoft offres a free, 60 days trial of Microsoft Fabric. Yet, you need to be aware of few limitations: 
- There is a limited availability of Fabric Trial per tenant. If other people within your organization have already redeemed a Trial, you might not be able to redeem one.
- Each Fabric Trial has a limited capacity, that will not be usable by too many people at once.

#### How much capacity do you need?

With the default configuration, you need an F4 capacity per attendee (either with each attendee having an F4 capacity, or with one shared capacity for the entire class). Each capacity unit - an F4 has 4 capacity units - allows you to get 8 Spark vCore (1CU = 2vCore). The default Spark pool - the Starter pool - nodes are using 8 vCore. 

If Fabric cost is a concern for your delivery, you can optimize it by creating a custom pool with only small instance and only one node. While you'll gain in terms of hourly cost, you need to be aware that each session start will take approximately 3 minutes instead of 10 seconds, and most code will take twice as much time to execute. You can also pause the capacity outside the labs time, and thus only paying for a Fabric capacity for something like 3-4 hours for the HOD.

| Capacity | Maximum recomended number of attendees with default settings |  Maximum recomended number of attendees with custom pools |
| ---|---|---| 
| F2    | 1 | 1 | 
| F4    | 1 | 1 | 
| F8    | 2 | 4 | 
| F16   | 4 | 8 | 
| F32   | 8 | 16 | 
| F64   | 16 | 32 |
| F128  | 32 | 64 |
| F256  | 64 | 128 |

> Note: there are some optimizations in place that will allow to outgrow these number of attendees with a specific capacity. To offer the best learning experience, we recommend to stay within these limits.

## How to deliver an Hands-on Day?

### Keynotes

We will provide slides notes in the future to help you deliver this content. Meanwhile, you can [watch this Microsoft Ignite session](https://ignite.microsoft.com/en-US/sessions/1eff13d6-1924-435a-8778-111d7131f061?source=/speakers/e25ab775-304e-4b10-bd32-2a30396c420d). Please also take time to read the latest product updates on the [Updates Blog](https://blog.fabric.microsoft.com/en-GB/blog/). New features are announced monthly, and some decks may not be up to date with the latest feature launches.

### Labs

We encourage you to take the time to go through each and every lab. They are straightforward, yet you need to know them to ensure a great learner experience. As said in the keynotes, Microsoft Fabric is evolving rapidly. If the labs have not caught-up with one of the product releases, please open an issue on this repository.

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

