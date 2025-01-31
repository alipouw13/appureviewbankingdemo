# Scenario 1: Discovering and Classifying Banking Data using Microsoft Purview Data Map
Imagine your bank operates across multiple data sources: Azure Data Lake, on-prem SQL Server, and SaaS platforms. You need to catalog and classify sensitive customer data.

## Key outcomes and talking points
*Purview helps banks understand their data landscape and ensures sensitive data is identified*
- Purview’s automated classification helps you quickly identify sensitive data, such as customer PII or credit card information, ensuring compliance with regulations like GDPR and PCI DSS.
- With sensitivity labels, you can enforce access controls and track usage.

## Permissions
Below are the permissions required to execute this demo. They are not expansive of the permissions required to interact with governance domains and data products. See [this repo](https://github.com/alipouw13/appurviewdemo/blob/main/0-purview_governance_permissions.md) for details on roles and permissions in Microsoft Purview.

- Purview Administrator
- Domain Administrator
- Data Steward
- Data Source Admin
- Purview MI must have Data Owner access to SQL DB - see here for details

## Setup
- Define collection architecture relevant to your customer. Leave one collection to be created during the demo. See [here]() in the reference section for a sample Figma collection architecture.
- Pre-register and scan a few sources in hybrid environment (Azure SQL Database, on-prem SQL, and Azure Data Lake).
- Create a scan-set specific to your organization
- Use datasets containing mock financial information (e.g., customer PII, transaction data).
- Ensure you have a few resources that still need to be registered and scanned during the demo

## Steps
1. Navigate to the Microsoft Purview portal and select Data Map.
2. Go over Data Map purpose and collection architecture.
    - Highlights:
    - Review collection architecture best practices here
3. Create a collection and review the roles.
    - Highlights
4. Show the list of registered sources (e.g., Azure Data Lake, on-prem SQL Server).
    - Highlights: Can only register a source once - one fabric registration per tenant.
5. Show how to register another source.
6. Run a pre-configured scan on one of the sources.
    - Highlights: 
        - Reduce cost associated with a scan 
        - Scheduled scans, increamental scans and full scans
        Scanning capabilities 
4. Navigate to Assets and demonstrate how Purview has cataloged the data.
    - Highlights: 
        - Capabilities by source type
        - Highlight the classification tags automatically applied (e.g., "Credit Card Number," "Customer Name").
        - Open a dataset and show its sensitivity label (e.g., "Confidential – Banking Transactions").

## Useful Materials
- Video walkthrough here