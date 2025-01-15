# Introduction
This repository goes through 6 banking and compliance scenarios leveraging Microsoft Purview as an end-to-end discoverability, compliance and audit solution.

## Microsoft Purview
In the banking industry, organizations generally face challenges including: regulatory compliance, sensitive data handling, and fragmented data. 
Microsoft Purview is a unified end-to-end data governance solution that provides enhanced discoverability and compliance (e.g., PCI DSS, GDPR) across your data estate.
Microsoft Purview simplifies audits.

![alt text](https://github.com/alipouw13/appureviewbankingdemo/blob/main/images/purview-overview.png)

# Permissions and Pre-requisites
- Microsoft Purview Enterprise. See [here](https://learn.microsoft.com/en-us/purview/upgrade#upgrade) for how to uprade from Microsoft Purview Free.
- [Audit (Standard)](https://learn.microsoft.com/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-purview-service-description#microsoft-purview-audit-standard): Microsoft 365 E5/A5/G5
- [Compliance manager](https://learn.microsoft.com/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-purview-service-description#microsoft-purview-compliance-manager): Office 365 and Microsoft 365 licenses, and to US Government Community Cloud (GCC), GCC High, and Department of Defense (DoD)
- [Sensitivity Labeling](https://learn.microsoft.com/en-us/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-purview-service-description#microsoft-purview-information-protection-sensitivity-labeling) (more granularity to this but at a high level): Microsoft 365 E5/A5/G5
  
# Technical setup checklist
1. Environment Configuration:
    - Set up a hybrid data environment (on-prem SQL, Azure Data Lake, Azure SQL Database).
    - Pre-load datasets with mock financial data for classification and lineage.
2. Governance Policies:
    - Configure sensitivity labels and access policies in Purview.
3. Compliance Dashboard:
    - Enable compliance mapping for PCI DSS or GDPR.
4. Business Glossary:
    - Populate the glossary with terms relevant to banking.
5. Integrated Systems:
    - Ensure integration with Microsoft Fabric for showcasing downstream use cases.
