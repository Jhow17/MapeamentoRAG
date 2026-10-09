---
title: "Amazon Redshift"
slug: "amazon-redshift-connectors-1"
status: "new"
updated: 2026-07-30T07:43:50Z
published: 2026-07-30T07:44:19Z
canonical: "helpcenter.securiti.ai/amazon-redshift-connectors-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Amazon Redshift

Amazon Redshift is a fully managed, petabyte-scale data warehouse service in the cloud. It lets organizations efficiently store, analyze, and query large volumes of structured and semi-structured data using SQL-based tools and business intelligence applications.

Amazon Redshift falls under the Monitored, structured data systems category. For more information, see [Data systems classification](/v1/docs/managing-data-system-connectors).

> [!NOTE]
> **Important**
> 
> The Redshift VPC workgroup security group may need the POD IP/Network whitelisted.

### Connection method for Amazon Redshift in Securiti

Securiti supports connecting to Amazon Redshift using a customer self hosted pod connector. See [Configuring Securiti pods](/latest/docs/securiti-pods-and-elastic-pods), for more information.

### Authentication methods for Amazon Redshift

Amazon Redshift supports the following authentication types for authenticating and integrating with Securiti.

| Authentication method | Authentication credentials |
| --- | --- |
| Basic | - User - Password |
| IAM Roles | - User - AWS Account - AWS IAM Role - AWS Region |

#### Keyring support for Amazon Redshift

You can use keyring during the connector configuration process to securely access your credentials from a vault. See [Using keyrings](/v1/docs/using-keyrings) for more information.

> [!NOTE]
> **Important**
> 
> Keyring support for Amazon Redshift is available only for **Basic** authentication.

Following credential vaults are supported for Amazon Redshift.

- **AWS Secrets Manager**. See [Configuring AWS Secrets Manager credential vaults](/v1/docs/configuring-credential-vaults-aws-secrets-manager-credential-vault) for more information.
- **CyberArk**. See [Configuring CyberArk credential vaults](/v1/docs/configuring-credential-vaults-cyberark-credential-vault) for more information.
- **CyberArk Conjur**. For more information, see [CyberArk Conjur credential vault](/v1/docs/configuring-credential-vaults-cyberark-conjur-credential-vault).

> [!NOTE]
> **Note**
> 
> CyberArk Conjur keyring is not supported for IAM Roles authentication method currently.
- **HashiCorp**. See [Configuring HashiCorp credential vaults](/v1/docs/configuring-credential-vaults-hashicorp-credential-vault) for more information.

### Prerequisites for configuring Amazon Redshift connector

You must fulfil the below prerequisites to connect your Amazon Redshift connector with Securiti.

- Use required driver files
- Grant read access (SELECT) permissions to database. See [AWS Documentation for Amazon Redshift Data API](https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonredshiftdataapi.html) for more information.
- For IAM Role based authentication, create AWS Master and Member account IDs before connector activation.

For more information, see [Prerequisites for configuring Amazon Redshift](/latest/docs/prerequisites-for-configuring-amazon-redshift).

### Use case and permissions for Amazon Redshift

This section covers use cases and permissions required for Amazon Redshift.

Securiti supports the following module features or scans for Amazon Redshift.

- Sensitive Data Intelligence (Discovery scan)
- Data Subject Rights (DSR)

| Modules | Permissions | Use case |
| --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights (DSR)) | **SELECT** (read) | Lets Securiti connect and access your Amazon Redshift database(s). This permission provides read access on database(s) for data scanning. |

You must provide the necessary permissions for these module features and scans that are supported for the following data entities.

- Database(s)
- Schemas within databases
- Tables and Views within schemas

### Steps to connect Amazon Redshift with Securiti

To connect the Amazon Redshift data system with Securiti, perform the procedures in the following topics:

1. [Prerequisites for configuring Amazon Redshift](/latest/docs/prerequisites-for-configuring-amazon-redshift)
2. (For IAM Roles authentication only) [Obtain credentials for role based authentication in Amazon Redshift](/latest/docs/obtain-credentials-for-role-based-authentication-in-amazon-redshift)
3. [Connecting Amazon Redshift with Securiti](/latest/docs/connecting-amazon-redshift-with-securiti)
4. [Configure discovery scans in Amazon Redshift](/latest/docs/configure-discovery-scans-in-amazon-redshift)

**Additional resources**

- [Fulfilling DSR requests for Amazon Redshift](/latest/docs/fulfilling-dsr-requests-for-amazon-redshift)
- [Table training for structured and hybrid data systems](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems)

A secure container for storing cryptographic keys or login credentials. See Managing keyrings, for more information.

Permissions refer to the minimum set of access details required to connect a data system with Securiti and allow scanning of data. Permissions could be of an administrative role where the user has all privileges to scan, share and access data, or it can be READ/WRITE only. Without the required permissions, data cannot be discovered or scanned for sensitive information.

## Related

- [Prerequisites for configuring Amazon Redshift](/prerequisites-for-configuring-amazon-redshift.md)
- [Obtain credentials for role based authentication in Amazon Redshift](/obtain-credentials-for-role-based-authentication-in-amazon-redshift.md)
- [Configure discovery scans in Amazon Redshift](/configure-discovery-scans-in-amazon-redshift.md)
- [Fulfilling DSR requests for Amazon Redshift](/fulfilling-dsr-requests-for-amazon-redshift.md)
