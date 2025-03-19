# Scenario 5: Preparing for Audits with Compliance Manager

Purview streamlines audit preparation, reducing operational overhead. This demo will go through features of the Complaince Manager solution in Microsoft Purview.

## Key outcomes

- Showcase the governance dashboard to visualize compliance coverage. The compliance dashboard gives you a real-time view of your governance posture.
- Generate a compliance report to share with auditors. You can quickly address gaps and generate reports for auditors, saving time and effort
- Highlight actionable insights for addressing gaps in compliance. You can generate domain-specific reports for internal reviews or external audits

## Permissions

See [here](https://learn.microsoft.com/en-us/purview/purview-permissions#azure-roles-in-the-purview-portal) and [here](https://learn.microsoft.com/en-us/defender-office-365/scc-permissions) for a full overview of Permissions in the Purview portal. Focus on security and compliance roles to understand the scope of each role related to Security, Audit and Compliance.

For the purposes of this demo, you need the **Audit Manager** role to view any audit reports. Consider the **Insights reader** role to obtain read-only access to _all Insights reports_ in the Data Estate Insights app. Insights readers need to have at least **data reader** role access to a collection to view reports about that specific collection.

## Setup

- Requires an E5 or similar license (more informatio here)
- Enable a compliance dashboard in Purview mapped to PCI DSS or GDPR.
- Include a mix of compliant and non-compliant datasets.

## Steps

- Navigate to the Compliance Dashboard.
- Show an overview of sensitivity label coverage across datasets.
- Highlight compliance gaps for PCI DSS and suggest remediation steps.
- Generate a compliance report for a dataset to demonstrate audit readiness.
- Open the governance dashboard for the Retail Banking Governance domain.
- Highlight metrics like:
  - Number of assets governed.
  - Sensitivity label coverage.
  - Access policy compliance.
- Generate a domain-specific report summarizing the governance posture for audit purposes.

## Useful Materials

- [Purview risk and compliance](https://learn.microsoft.com/en-us/purview/purview-compliance)
- [Purview auditing experiences](https://learn.microsoft.com/en-us/purview/audit-solutions-overview)
