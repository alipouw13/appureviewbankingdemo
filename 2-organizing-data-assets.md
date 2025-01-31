# Scenario 2: Organizing Data Assets with Governance Domains and Data Products in the Unified Catalog
In this scenario, imagine you are a large bank that needs to manage data governance for different business units (e.g., Retail Banking, Corporate Banking, Risk Management, etc.). Each unit handles sensitive data and has unique governance requirements. Using Microsoft Purview’s governance domains, the bank can logically separate these units while maintaining centralized oversight.

Governance domains in Microsoft Purview allow you to logically group data assets, policies, and workflows for better management. This is particularly useful in a banking organization where different units have unique governance needs but operate under a unified governance strategy.

## Key outcomes
- Create 3 Governance domains
- Create 2 Data products
- Add Data assets to Data products
- Showcase applying governance policies to data products

## Talking points
- Each domain acts as an independent governance and security spaceensuring clarity and separation of ownership and resonsibilities
- Assigning domain owneership ensures accountability while allowing for decentalized governance
- Grouping assets into data products facilitates scalability of governance polies consistently applied at the data product and domain level
- Governance domains make it easier to track and manage assets across your organization
    - Enforce governance policies at the data product level while maintaining centralized visibility at the domain level
    - Ensure security and compliance tailored to the needs of each business unite, etc.

## Permissions
Below are the permissions required to execute this demo. They are not expansive of the permissions required to interact with governance domains and data products. See [this repo](https://github.com/alipouw13/appurviewdemo/blob/main/0-purview_governance_permissions.md) for details on roles and permissions in Microsoft Purview.
- Governance Admin
- Governance Domain Curator
- Governance Domain Owner
- Data Product Owner
- Policy Author (Domain-level)
- Workflow Admin

## Setup
- Setup RBAC Groups for data strategy roles in one sample governance domain (eg: Retail Banking): 
Retail Banking IT Team (Data Steward), Retail Banking Analysts (Data Catalog reader), Retail Banking Admins (Governance Admin)

| Purview Roles             | Data Strategy Role(s)                  | Data Management Role       | Permissions                                                                 |
|---------------------------|----------------------------------------|----------------------------|-----------------------------------------------------------------------------|
| Governance Admin          | Retail Banking Admins                 | (Governance) Governance Admin           | Full access to governance features, including creating and managing domains |
| Governance Domain Curator | Retail Banking Data Stewards, Retail Banking Data Product Owners                | (Governance) Data Steward               | Manage data assets and policies within a specific domain                    |
| Governance Domain Owner   | Retail Banking Data Stewards, Retail Banking Data Product Owners                  | (Governance) Data Steward, Publisher    | Ownership of a specific governance domain                                   |
| Data Product Owner        | Retail Banking Data Stewards, Retail Banking Data Product Owners                | (Governance) Data Steward, Publisher, Producer         | Manage data products and associated assets                                  |
| Policy Author (Domain-level) | Retail Banking Admins                                                          | (Governance) Governance Admin |                        Create and manage policies within a specific domain                         |
| Workflow Admin            | Retail Banking Data Stewards, Retail Banking Data Product Owners    | (Governance) Data Steward | Create and manage workflows |

## Steps
1. Navigate to the Microsoft Purview portal and click on Governance Domains in the menu.
2. Click on Add Domain and provide the following details:
    - Domain Name: "Retail Banking Governance"
    - Description: "Manages governance for customer accounts, transactions, and retail banking operations."
    - Owner: Assign to a specific team or individual (e.g., Retail Banking IT Team).
    - Type: Functional unit (Sales, Marketing...), **LOB (Xbox, office...)**, Data domain (customers, employees, executives), Regulatory (GDPR), Project
    - Repeat the process to create additional domains, such as:
        - Corporate Banking Governance
        - Risk Management Governance
3. Open the Retail Banking Governance domain.
4. Create a data product and add data assets.
5. See that the data product is now linked to the governance domain.
6. Within the Retail Banking governance domain, create a governance policy that restricts access to sensitive customer data:
    - Restrict access to the "Customer Accounts Dataset" to users in the Retail Banking Analysts group.
    - Enable workflow approvals for any access requests.


## Useful Materials
- Video walkthrough here