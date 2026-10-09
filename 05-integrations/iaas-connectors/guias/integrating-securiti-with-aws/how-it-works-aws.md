---
title: "How it works?"
slug: "how-it-works-aws"
status: "update"
updated: 2026-02-07T13:35:31Z
published: 2026-02-07T13:35:31Z
canonical: "helpcenter.securiti.ai/how-it-works-aws"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# How it works?

When you integrate AWS accounts into Securiti for onboarding, Securiti creates some IAM roles in the account being on-boarded. The following key roles are created for AWS integration:

- Master Account: Securiti assumes this role from its own account and then switches to each of the

member accounts where assets are to be discovered and scanned.
- Member Account: Securiti assumes this role on the account to be scanned using the credentials

from the respective master role.

Securiti also creates policies that allow it to assume these roles. Roles and permissions created by Securiti depends on scan options selected in step 3 when configuring your cloud account.

The following diagram shows the different roles and illustrates their function.

![AWS_IaaS_roles_permissions.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c6eda564-4f9b-8bde-456b-71a31c5b1d7d.jpg)

| Scope | Role | Purpose |
| --- | --- | --- |
| Master Account | SECURITI_ASSET_DIS- COVERY_MASTER_ROLE | Securiti assumes this role from its own account and then switches to each of the member accounts where assets are to be discovered |
| Member Ac- count | SECURITI_ASSET_DIS- COVERY_MEMBER_ROLE | Securiti assumes this role on the account to be scanned using the credentials from the respective master role |

## Related

- [Creating an AWS IaaS instance (version 1.111 and later)](/creating-an-aws-iaas-instance-version-1111-and-later.md)
- [Creating an AWS IaaS instance (version 1.110 and earlier)](/creating-an-aws-iaas-instance-version-1110-and-earlier.md)
