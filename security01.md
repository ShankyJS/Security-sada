# CIS V8

CIS control: 3 - Segment Data processing and Storage based on Sensibity. Segment data processing and storage based on the sensitivy of the data. Do not process sensitive data on enterprise assets intended for lower sensibity data. 

## Implementing Guard Rails.

The effective policy for a resource is the union of the policy set at the resource and the policy inherited from its parent.

## Organizational policies:

The organization policy service constrains the allowed resource configurations. Policies can be applied to the org, folders and projects. 

Requires IAM role: Organization policy / Organization policy administrator.

Constraints every customer should have in place:

img here.

## Organization policy hierarchy evaluation:

1. In this example the organization Node defines a policy that allows red square and green cards in.

Resource 1: Defines a custom policy that sets inheritedFromParent to TRUE and allows blue diamond.


Additional considerations: 

Org Plicies changes:

SADA recommends: Periodically checking for new org policies.
- Have a dedicated test org or folder where you can test new policies before implementing them.
- Create a process to manage exceptions to Org Policies.

- Releases notes are available in the console and on the web.

- There are also open source examples of automated checks to alert you when a new policy is release


Additional considerations: 

Org Plicies changes:

SADA recommends: Periodically checking for new org policies.
- Have a dedicated test org or folder where you can test new policies before implementing them.
- Create a process to manage exceptions to Org Policies.

- Releases notes are available in the console and on the web.

- There are also open source examples of automated checks to alert you when a new policy is released.

Key decisions:

- Do you have data subject to mutually 
