# Scenario 1: Discovering and Classifying Banking Data using Microsoft Purview Data Map

Imagine your bank operates across multiple data sources: Azure Data Lake, on-prem SQL Server, and SaaS platforms. You need to catalog and classify sensitive customer data.

## Key outcomes and talking points

*Purview helps banks understand their data landscape and ensures sensitive data is identified*

- Purview’s automated classification helps you quickly identify sensitive data, such as customer PII or credit card information, ensuring compliance with regulations like GDPR and PCI DSS.
- With sensitivity labels, you can enforce access controls and track usage.

## Permissions

Below are the permissions required to execute this demo. They are not expansive of the permissions required to interact with governance domains and data products. See [this repo](https://github.com/alipouw13/appurviewdemo/blob/main/0-purview_governance_permissions.md) for details on roles and permissions in Microsoft Purview. Assume for this demo that we are registering and scanning sources at the Prod > US collection level.

| Purview Roles             | Data Strategy Role(s)                  | Data Management Role       | Permissions                                                                 | Sample Security Group                  |
|---------------------------|----------------------------------------|----------------------------|-----------------------------------------------------------------------------|----------------------------------------|
| Purview administrator          | Contoso International Bank IT Admins                 | (Governance) Governance Admin           | Create, edit, and delete domains and perform role assignments | cib-pview-apfsipurviewdemo-governanceadmin    |
| Domain administrator | Contoso International Bank IT Admins                | (Governance) Data Steward               |     Assign permissions within a domain and manage its resources.               | cib-pview-apfsipurviewdemo-datasteward           |
| Data steward   | Retail Banking Data Stewards, Retail Banking Data Product Owners                  | (Governance) Data Steward   |    Create, update, and read artifacts and policies within their governance domain. Can also read artifacts from other governance domains. *Requires Data Map permissions to read those data assets in Data Map.*                                | cib-pview-apfsipurviewdemo-datasteward-prod-us            |
| Data source administrator       | Contoso International Bank IT Admins                | (Governance) Data Steward, Publisher, Producer         |      Ability to manage data sources and scans. To create new scan rules, the user must be also granted as either Data reader or Data curator roles.                           | cib-pview-apfsipurviewdemo-datasteward-prod-us   |

Please note that the security groups follow the following naming convention. Please update this naming convention as you see fit.

*< lobprefix >-< resource >-< organization/applicaiton name>-< role >-< environment >*

## Considerations

- Classifications are done based on the first 28 rows or 1 MB of data in a given column
- Use Data Quality to define and enforce classification rules
- There are 3 levels of scans (different by source) - you may select one or allow Purview to automatically apply the highest scan level for the source:
  - L1: Captures basic information like file name, size, and location.
  - L2: Extracts schema details for structured data types like database tables and file formats.
  - L3: Performs a more thorough scan, including schema extraction and applying custom classification rules to a sampled portion of the data.

## Setup

- Define collection architecture relevant to your customer. Leave one collection to be created during the demo. See [here](https://github.com/alipouw13/appureviewbankingdemo/tree/main/reference) in the reference section for a sample Figma collection architecture.
- Pre-register and scan a few sources in hybrid environment (Azure SQL Database, on-prem SQL, and Azure Data Lake).
- Purview MI must have Data Owner access to SQL DB - see [here](https://learn.microsoft.com/en-us/purview/register-scan-azure-sql-database?tabs=sql-authentication#update-firewall-settings) for details. If the SQL SB is in a private network, you must also [install a self hosted integration runtime (SHIR)](https://www.microsoft.com/en-us/download/details.aspx?id=105539).
- Create a scan-set specific to your organization
- Use datasets containing mock financial information (e.g., customer PII, transaction data).
- Ensure you have a few resources that still need to be registered and scanned during the demo

## Steps

1. Navigate to the Microsoft Purview portal and select Data Map.
2. Go over Data Map purpose and best practice architecture.
    - Highlights: Review Data Map collection architecture best practices
3. Create a collection and review the roles.
    - Highlights: Data Map and collection roles
4. Show the list of registered sources (e.g., Azure Data Lake, on-prem SQL Server).
    - Highlights: Can only register a source once - one fabric registration per tenant.
5. Show how to register another source.
6. Run a pre-configured scan on one of the sources.
    - Highlights:
        - Scanning capabilities: scoped scans, classifications/custom classifications
        - Scoped scan reduces time taken for a scan
        - Differnece between scheduled scans, increamental scans and full scans
7. Navigate to Assets and demonstrate how Purview has cataloged the data.
    - Highlights:
        - Capabilities by source type
        - Highlight the classification tags automatically applied (e.g., "Credit Card Number," "Customer Name").
        - Open a dataset and show its sensitivity label (e.g., "Confidential – Banking Transactions").

## Useful Materials

- [Data Map domain and collection architecture best practices](https://learn.microsoft.com/en-us/purview/concept-best-practices-collections)
- [Unified Catalog data asset search](https://learn.microsoft.com/en-us/purview/unified-catalog-search)
- [Sensitivity labels in the Data Map](https://learn.microsoft.com/en-us/purview/how-to-automatically-label-your-content)
- [Classification of Data Map assets](https://learn.microsoft.com/en-us/purview/concept-classification)
- [Purview Roles and permissions](https://learn.microsoft.com/en-us/purview/data-governance-roles-permissions)
