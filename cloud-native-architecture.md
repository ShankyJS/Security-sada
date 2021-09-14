# Google Cloud Architecture

Principle 1: Design for Automation
- Huge impact on governance.
  - Prove compliance.
  - Change management/Approvals.

## Hierarchy Impact:

Things to consider when designing your organization layout.

IAM: Group structure/sprwal.
Governance: Policy enforcement points.
Billing/Cost Management: Enable chargebacks.

Examples: 

It's better to start looking at this details before creating the projects. At the beginning a simple project can be OK. But after some time, this can produce a lot of issues with physical limits, you need to work on this herarchy before hands so you can review in a best way the Billing, governance and IAM. (And always try to automate and replicate).

## Organization Hierarchy:

Structure your organization so you can manage resources efficiently and effectively. 

Resources are tied to a > Project > Folders > Organization.

### Organization:

What: 
- Root node and hierarchical super-node of projects.
- Closely associated with a Workspace/Cloud Identity account.
- Single directory containing the organization's users and groups.

Why: 
- Central resurces management: All projects created by members of the organization will belong to the organization by default.
- Apply policies across all resources: IAM policies. Organization policies with inheritance.

### Folder:

What:
- Nodes in organiation hierarchy.
- Used to model a workflow and access pattern.
- Contains projects.
- Up to ten levels deep (hard limit).
- Flexible: Modifying the folder tree and moving projects is possible. Be mindful of policies inheritance.

Why: 

- Grouping similar projects together to constantly apply policies (IAM and Organization policies).
- Enumerating projects that belong to part of the organisation.
- Integration: with other functionalities (BigQuery slot reservation herarchy).

In short: You want to decide on a folder structure in line with how policies should be applied.

### Project:

- Contains resources.
- Projects are completely separate from one another Useful to group related resources from a functional and access standpoint.
- Projects can be part of an organization.
- An IAM enforcement point.
- Provisioning is simple and free of charge.

## Hierarchy

## Best practices.

Accomodating multiple business units:

- Use folders to group projects based on business units, development environments and teams to share common:
    - IAM Permissions (inheritance model)
    - Organizational policies (exceptions can be made per project).

- Use multiple organizations only if multiple teams handle data subject to mutually exclusive compliance policies for example (HIPAA data needs to separated from PCI data).
    - Requires managing multiple Cloud Identity account (users, groups, domains).
    - Decentralized administration between the two organizations/resources.
    - Different IAM and Policy between the two organizations.

### Best practice for folders

-Hierarchy: 
    - Do not try to model your organization hierarchy for the sake of it.
    - Do model a workflow and access pattern.
    - However, the structure might end up somewhat resembling the organization hierarchy.
- Levels:
    - In most cases three or four folders levels are sufficient.
- Extensible:
    - Folders structure is flexible and easily extensible. You can start simple, and add more levels when needed.

### Recommended project organization

- One project per application or service for each environment.
- Additional possible attributes: data classification.
- Consistent project ID naming scheme for all company projects.

Examples:

Project per application or service: "company-departement-product-${environment}".

### One project for each application and environment.

Considerations for solutions:

- Billing isolation: Possibilities for different billing accounts, easy cost visibility per workload and environment.
- Quotas and limits: Separate by environment and workloads.
- Administrative complexity: Access management separate by environment and workload with additional management overhead.
- Blast radius: Misconfiguration issues only impact workloads specific environments.
- Separation of duties: Business unites and data sensity classifications are separate.
