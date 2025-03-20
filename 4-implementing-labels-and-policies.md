# Scenario 4: Implementing Sensitivity Labels and Policies with Microsoft Purview DLP and Information Protection

Governance policies and sensitivity labels protect sensitive data and ensure compliance with internal and external regulations. Data loss protection (DLP) aims to protect organization's sensitive data, and to reduce the risk from oversharing. DLP is a way to help prevent users from inappropriately sharing sensitive data with people who shouldn't have it. This demo demonstrates how Microsoft Purview can help customers protect sensitive data, enforce privacy per asset, and automate access governance, while meeting regulatory compliance and risk management requirements.

## Business problems addressed

- Data Privacy: Ensuring that customer financial and personal data is protected per asset.
- Access Control: Preventing unauthorized access to sensitive data through robust policies.
- Regulatory Compliance: Meeting industry regulations (e.g., GDPR, PCI DSS) with enforceable policies.
- Operational Efficiency: Streamlining the access approval process and enforcement of rules at scale.

## Key outcomes and talking points

- Privacy per Asset:
  - Showcase how each data asset is tagged with sensitivity labels.
  - Explain how labels drive encryption, access control, and auditing.
- Data Governance Access Policies:
  - Demonstrate restricting data access based on role and sensitivity.
  - Highlight integration with Azure Policy for scale and consistency.
- Simulated Access Request & Approval Workflow:
  - Walk through a simulated access request scenario.
  - Show how an approval workflow is triggered and managed, ensuring only authorized users get access.
- Enforcement through Azure Policy:
  - Discuss how Azure Policy can automatically enforce compliance rules.
  - Emphasize automated remediation and consistent rule application across environments.
- DLP Policy Implementation:
  - Illustrate setting up and monitoring Data Loss Prevention policies that restrict unauthorized sharing or movement of sensitive data.
- Information Protection via Sensitivity Labels:
  - Highlight how sensitivity labels drive actions in Microsoft Information Protection, securing data both at rest and in transit.

## Permissions

1. To create governance policies on data products, you need the _Data product owner_ role in the Unified Catalog. To note: Access policies can be applied on 3 levels in the unified catalog - see below for permissions required.
    - Governance domain owner (view and manage policies at the governance domain level)
    - Data product owner (view and manage policies at the data product level)
    - Data steward (view and manage policies in critical data elements (CDE) or glossary terms)
2. To create and manage sensitivity lables, you need one of the following roles. See [here](https://learn.microsoft.com/en-us/purview/get-started-with-sensitivity-labels#permissions-required-to-create-and-manage-sensitivity-labels) for more information.
    - Information Protection
    - Information Protection Admins
    - Information Protection Analysts
    - Information Protection Investigators
    - Information Protection Readers
3. To create and deploy DLP policies you need one of the following roles. See [here](https://learn.microsoft.com/en-us/purview/dlp-create-deploy-policy?tabs=purview#permissions) for more information.
    - Compliance administrator
    - Compliance data administrator
    - Information Protection
    - Information Protection administrator
    - Security administrator

## Setup

- In Unified Catalog, create a governance domain and 2 data products
- Register and scan Data assets (Fabric, storage account and SQL Server)
- Generate 5 glossary terms and CDEs
- Add data assets to your data products

## Steps

1. Define data access policies for accessing customer on one of your data products
2. Define a policy at the Governance Domain, Data Product and CDE level. See here for details on policies on [Data Products](https://learn.microsoft.com/en-us/purview/unified-catalog-access-policies#configure-data-product-access-policies)
3. Simulate a user trying to access a dataset without proper approval
4. Simulate a user requesting approval, approve and show user getting access
5. Navigate to DSPM for AI
6. Demonstrate [enabling default sensitivity labels](https://learn.microsoft.com/en-us/purview/mip-easy-trials#activate-the-default-labels-and-policies)
7. Navigate to Information protection > Sensitivity labels
8. Create a new label - review [documentation](https://learn.microsoft.com/en-us/purview/encryption-sensitivity-labels) on how to restrict access to content by using sensitivity labels to apply encryption

## Useful Materials

- [Information protection](https://learn.microsoft.com/en-us/purview/information-protection)
- [Default labels and policies](https://learn.microsoft.com/en-us/purview/mip-easy-trials)
- [Unified Catalog access policies](https://learn.microsoft.com/en-us/purview/unified-catalog-access-policies)
