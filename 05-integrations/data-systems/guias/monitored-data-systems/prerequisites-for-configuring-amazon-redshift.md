---
title: "Prerequisites for configuring Amazon Redshift"
slug: "prerequisites-for-configuring-amazon-redshift"
updated: 2026-08-19T05:53:44Z
published: 2026-08-19T05:53:44Z
canonical: "helpcenter.securiti.ai/prerequisites-for-configuring-amazon-redshift"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for configuring Amazon Redshift

The sections below provide information for the drivers and permissions required as prerequisites for accessing Amazon Redshift databases.

> [!NOTE]
> **Important**
> 
> Amazon Redshift can be set up on AWS Instance only and free trial is not available

For more information, see [AWS documentation](https://docs.amazonaws.cn/en_us/redshift/latest/mgmt/redshift-iam-access-control-overview.html).

### Drivers required for Amazon Redshift

Securiti uses drivers provided by AWS for accessing Amazon Redshift's data. Following drivers are required based on the type of authentication you choose for your instance.

- **Basic authentication**: For Basic or password based authentication, use [this driver](https://s3.amazonaws.com/redshift-maven-repository/release/com/amazon/redshift/redshift-jdbc42-no-awssdk/1.2.36.1060/redshift-jdbc42-no-awssdk-1.2.36.1060.jar) for Amazon Redshift.
- **IAM roles authentication**: For role based authentication, you must extract and copy all the drivers in [this zip folder](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/redshift-jdbc42-2.0.0.7.zip) to the `/mnt/drivers` or the folder specific to your data source such as */mnt/drivers/100* etc.

### Granting database permissions in Amazon Redshift

You must have the permissions to access the schemas and tables of interest when activating the Amazon Redshift connector. **Read** permissions must be granted to all the schemas that require scanning.

Do the following to grant Amazon Redshift connector database permissions.

1. Enable "connect permissions" on all databases for scanning.
2. To enable usage permission:

```plaintext
- pg_catalog
 - information_schema 
- all schemas in all database that need to be scanned
```
3. To SELECT permissions for all tables in each of the schemas, so it scans all databases:

```plaintext
CREATE GROUP ro_securiti;
CREATE USER securiti WITH PASSWORD '<some-strong-password>' IN GROUP ro_securiti;

GRANT SELECT ON ALL TABLES IN SCHEMA <schema_name> TO GROUP ro_securiti;
```

> [!NOTE]
> **Note**
> 
> You can also create a group and grant select permissions on desired (or ALL) tables in all schemas for scanning.

### Acquire credentials for Basic authentication

> [!NOTE]
> **Note**
> 
> Skip this section if you are opting for IAM Roles authentication.

1. Log in to the Redshift AWS instance.

> [!NOTE]
> **Note**
> 
> We assume you have the AWS infrastructure running before connector activation or have access to its administrator to configure necessary permissions and data system authentication.
2. For **Basic** authentication, record the your Amazon Redshift username and password for later use.
3. Proceed to [Connecting Amazon Redshift with Securiti](/latest/docs/connecting-amazon-redshift-with-securiti).

### Acquire credentials for IAM Roles authentication

> [!NOTE]
> **Note**
> 
> Skip this section if you are opting for Basic authentication.

1. Log in to the Redshift AWS instance.

> [!NOTE]
> **Note**
> 
> We assume you have the AWS infrastructure running before connector activation or have access to its administrator to configure necessary permissions and data system authentication.
2. For **IAM Roles** based authentication, For more information, see [Obtain credentials for role based authentication in Amazon Redshift](/latest/docs/obtain-credentials-for-role-based-authentication-in-amazon-redshift).
3. Proceed to [Connecting Amazon Redshift with Securiti](/latest/docs/connecting-amazon-redshift-with-securiti).

## Related

- [Obtain credentials for role based authentication in Amazon Redshift](/obtain-credentials-for-role-based-authentication-in-amazon-redshift.md)
