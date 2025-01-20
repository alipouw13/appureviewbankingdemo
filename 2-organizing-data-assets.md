# Scenario 2: Organizing Data Assets with Governance Domains and Data Products in the Unified Catalog
In this scenario, imagine you are a large bank that needs to manage data governance for different business units (e.g., Retail Banking, Corporate Banking, Risk Management, etc.). Each unit handles sensitive data and has unique governance requirements. Using Microsoft Purview’s governance domains, the bank can logically separate these units while maintaining centralized oversight.

Governance domains in Microsoft Purview allow you to logically group data assets, policies, and workflows for better management. This is particularly useful in a banking organization where different units have unique governance needs but operate under a unified governance strategy.

## Key outcomes and talking points
- Create 3 Governance Domains
- Create 2 Data Products
- Add Data Assets to Data Products
- Showcase applying governance policies to groups of assets (Data Products)


## Permissions
- Governance Admin
- Governance Domain Curator
- Governance Domain Owner
- Data Product Owner
- Policy Author (Domain-level)

## Setup
- Setup RBAC Groups for data strategy roles in one sample governance domain: Retail Banking IT Team (Data Steward), Retail Banking Analysts (Governance Admin Viewer), Retail Banking Admins (Governance Admin)

See below for a sample mapping of roles with the appropriate RBAC groups.

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