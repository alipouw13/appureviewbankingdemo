# Scenario 5: Automate workflow with Microsoft Purview Workflows

Workflows allow organizations to automate and standardize data governance processes, reducing manual effort and ensuring compliance.

## Key outcomes and talking points

- Showcase Increased Efficiency
  - Automates governance tasks (e.g., data access approvals, classification changes).
  - Reduces manual work and administrative overhead.
- Standardized Compliance
  - Ensures governance workflows align with internal policies and external regulations.
  - Tracks approvals and decisions for audit purposes.
- Show how workflows enable improved Data Steward Collaboration
  - Facilitates role-based data access requests, approvals, and metadata changes.
  - Provides a structured process for data owners and stewards.
- Show how workflows integrate with the Microsoft Ecosystem
  - Works seamlessly with Microsoft Purview Data Catalog, Microsoft Entra ID, and Azure Logic Apps for advanced automation.

## Permissions

To set up and run workflows in Microsoft Purview, ensure the following permissions are granted from the _Governance Domains > Roles_ for each specific governance domain.

| Purview Roles             | Data Strategy Role(s)                  | Data Management Role       | Permissions                                                                 | Sample Security Group                  |
|---------------------------|----------------------------------------|----------------------------|-----------------------------------------------------------------------------|----------------------------------------|
| Workflow admin            | Retail Banking Data Stewards, Retail Banking Data Product Owners    | (Governance) Data Steward |     Create, update, delete workflows      |     rb-pview-apfsipurviewdemo-datasteward-prod-us |
| Data steward | Retail Banking Data Stewards, Retail Banking Data Product Owners      |   (Governance) Data Steward   |  Approve requests from workflows               |      rb-pview-apfsipurviewdemo-datasteward-prod-us |
| Unified Catalog Reader | Retail Banking Data Consumer  | Data Consumer | Explore Unified Catalog and request access to certain data assets | rb-pview-apfsipurviewdemo-dataconsumer-prod-us |

## Setup

- Microsoft Purview account configured
- Necessary roles assigned to appropriate users (2 user accounts, one with Workflow admin and Data steward, one with Catalog reader)

## Steps

1. As a workflow admin, navigate to Purview Workflows (Solutions > Workflows)
2. Select new workflow > Data Access Approval
3. Configure Workflow Parameters
    - Workflow Name
    - Set triggers (eg: when data is classified as Confidential)
    - Add approvers
    - Add notifications for approval/rejection
    - If approved, grant access to resource
4. Apply workflow
5. Browse Unified Catalog as a Unified Catalog reader and request access to the resource type configured to the workflow
6. Switch to the workflow admin account to approve the request
7. Notice access change for the Catalog reader user

## Useful Materials

- [Workflows](https://learn.microsoft.com/en-us/purview/legacy/concept-workflow)
