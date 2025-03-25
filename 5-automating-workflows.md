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
| Workflow Administrator   |                                       |                                |      Create, update, delete workflows      |                      rb-pview-apfsipurviewdemo-governanceadmin-prod-us |
| Data Steward / Datasource Admin  |                                       |                                |  Approve requests from workflows               |                      rb-pview-apfsipurviewdemo-governanceadmin-prod-us |


## Setup

- Microsoft Purview account configured.
- User assigned Purview Admin or Workflow Admin role.
- Necessary Azure roles assigned (e.g., Purview Data Reader for metadata access).
- Microsoft Entra ID (Azure AD) for user authentication.

## Steps

1. Navigate to Purview Workflows (Solutions > Workflows)
2. Select ew workflow > Data Access Approval
3. Configure Workflow Parameters
    - Workflow Name
    - Set triggers (eg: when data is classified as Confidential)
    - Add approvers
    - Add notifications for approval/rejection
    - If approbed, grant access to resource
4. Apply workflow

## Useful Materials

- [Workflows](https://learn.microsoft.com/en-us/purview/legacy/concept-workflow)
