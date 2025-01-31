# Scenario 3: Tracing Data Lineage for Regulatory Compliance in the Unified Catalog
This scenario focuses ontracking data movement across your data estate.

## Key outcomes
- 

## Talking points

## Permissions
Below are the permissions required to execute this demo. They are not expansive of the permissions required to interact with governance domains and data products. See [this repo](https://github.com/alipouw13/appurviewdemo/blob/main/0-purview_governance_permissions.md) for details on roles and permissions in Microsoft Purview.

- 

## Setup
- Download this dataset representing banking customer transactions.
- Create 4 storage accounts: landing, bronze, silver, gold
- Create an ADF instance
- Create a Fabric capacity
- Create a pipeline moving data from landing to gold containers using ADF. 
- Create a sample Power BI report and semantic model using the data from the gold layer
- See below for a sample architecture.

*_Bonus_*
- Create a pipeline in Fabric moving data from landing to gold lakehouses
- Create another semantic model referencing the data in the gold lakehouse


## Steps

## Useful materials
- Video walkthrough here