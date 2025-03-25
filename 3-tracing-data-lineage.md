# Scenario 3: Tracing Data Lineage for Regulatory Compliance in the Unified Catalog

Data lineage builds confidence in data accuracy and simplifies audit trails. This scenario focuses on tracking data movement across your data estate.

## Key outcomes and talking points

- Show end-to-end data lineage from ingestion to reporting in Purview.
- Discuss the ability to provide regulators with a transparent view of data flow.
- Discuss how lineage is limited to select sources
- DIscuss Live-view availability and value

## Talking points

- With Purview, you can track data from ingestion to reporting, ensuring transparency for regulators and internal audits.
- Lineage helps you quickly identify and resolve data quality issues
- Live view enables users with the proper permissions to find eligible resources and their data assets in the catalog without setup or scanning

## Permissions

Below are the permissions required to execute this demo. They are not expansive of the permissions required to interact with governance domains and data products. See [this repo](https://github.com/alipouw13/appurviewdemo/blob/main/0-purview_governance_permissions.md) for details on roles and permissions in Microsoft Purview.

## Setup

- Download the _bank_ excel in the [reference folder of this repo](https://github.com/alipouw13/appureviewbankingdemo/tree/main/reference) dataset representing banking customer transactions. Connect directly to excel or create a storage blob and upload the excel sheet there.
- Create a Fabric capacity (use a [Trial capacity](https://learn.microsoft.com/en-us/fabric/fundamentals/fabric-trial) for free)
- Create 3 lakehouses in Fabric: bronze, silver, gold
- Create 3 notebooks to manipulate data across layers
- Create a pipeline to orchestrate data movement from source to gold
- Create a sample Power BI report and semantic model using the data from the gold layer. See below for a sample [architecture](https://learn.microsoft.com/en-us/fabric/onelake/onelake-medallion-lakehouse-architecture):

![alt](https://github.com/alipouw13/appureviewbankingdemo/blob/main/images/architecture.png)

- Register and scan each of the above sources. Observe live view capabilities of the Lakehouses before scanning.

_See [this repo](https://github.com/alipouw13/apfsifabric_aiskillsdemo) for a sample metadata driven process using the nyc taxi data. Adjust the source to point to banking data if desired_

## Steps

- Navigate to the Data Map > Data assets
- Select the lineage tab on the data assets - show lineage from the Power BI report back to source

## Useful materials

- [Live view in Purview](https://learn.microsoft.com/en-us/purview/live-view)
