---
title: "Troubleshooting for Snowflake connector"
slug: "troubleshooting-for-snowflake-connector"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-snowflake-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Snowflake connector

This section covers troubleshooting for the possible issues that can occur during Snowflake Data System configuration and integration with Securiti.

As a first troubleshooting step, ensure that you are using the latest Snowflake JDBC driver supported by Securiti. Driver issues can cause connection failures, certificate-related errors, and proxy-related problems. If you are using an older driver version, update to the most recent stable version and test the connection again.

For more information, see [Snowflake's official documentation for troubleshooting common issues](https://docs.snowflake.com/en/user-guide/client-connectivity-troubleshooting/common-issues).

#### Authentication failure using Basic authentication method

If your Snowflake Connector is running into Authentication failure with the below error when using **Basic** Authentication method.

```plaintext
{"msg":"Exception in getTableNames...}
```

If you use a firewall or proxy with your Snowflake account, allowlist all URLs and port combinations on the Securiti pod, returned by the command below.

```plaintext
SELECT SYSTEM$ALLOWLIST()
```

> [!NOTE]
> **Important**
> 
> If your Snowflake account uses private connectivity to the Snowflake service, execute the `SYSTEM$ALLOWLIST_PRIVATELINK` instead of `SELECT SYSTEM$ALLOWLIST()` command.

For more information, see the [Allowing Hostnames topic in Snowflake documentation.](https://docs.snowflake.com/en/user-guide/hostname-allowlist)

#### Using `SnowCD` tool to identify connectivity issues

If you encounter connectivity issues with the Snowflake Connector, such as the error "`Timeout waiting for the download of #chunk0 (Total chunks: 1) retry=0`", it may be due to restricted URLs or network settings.

For more information, see the [official SnowCD Developer Resources](https://www.snowflake.com/en/developers/downloads/snowcd/).

Follow the procedure below to resolve the issue by allowlisting URLs and using the SnowCD tool.

1. Allowlist the required URLs, to ensure the Snowflake Connector can access necessary endpoints. See the above section **Authentication failure using Basic authentication method** for the query used to generate URLs for allowlisting.
2. Save the URLs that need to be allowlisted in a file named `allowlist.json`.
3. Move the `allowlist.json` file to the pod machine where you need to run `SnowCD`. Alternatively, create a new file on the Securiti pod and paste the output from the query into it.
4. Next, install the `SnowCD` tool on your Securiti pod.
  1. Run the below command to download `SnowCD`. You can also visit [SnowCD Downloads](https://www.snowflake.com/en/developers/downloads/snowcd/), for more information.

```plaintext
wget https://sfc-repo.snowflakecomputing.com/snowcd/linux/1.0.5/snowcd-1.0.5-linux_x86_64.gz
```
  2. Run the SHA256 checksum command to verify file integrity.

```plaintext
sha256sum snowcd-1.0.5-linux_x86_64.gz
```

The output should match the below shasum.

```plaintext
9f55f0dabf809559bedd722d727d3095056eba241e57cb9ee8c4efc616abb1dc
```
  3. Run the below command to decompress the file.

```plaintext
gunzip snowcd-1.0.5-linux_x86_64.gz
```
  4. Run the below command to make the file executable.

```plaintext
chmod +x snowcd-1.0.5-linux_x86_64
```
  5. Run the below command to rename the file.

```plaintext
mv snowcd-1.0.5-linux_x86_64 snowcd
```
5. Run the below command to verify URL accessibility using the `SnowCD` tool.

```plaintext
./snowcd allowlist.json
```

If you see the message `All checks passed`, it means that all URLs are accessible. On the contrary, if the URLs are inaccessible, `SnowCD` provides an error message listing the problematic URLs.

#### No active warehouse selected in the current session

This error occurs when a Snowflake session attempts to execute a query without having access to an active warehouse. It shows you the following error.

*No active warehouse selected in the current session. Select an active warehouse with the 'use warehouse' command.*

Even if the Snowflake user has the correct role, such as **SYSADMIN**, the warehouse, such as *COMPUTE_WH* might not have **USAGE** permission granted to that role. Without this permission, Snowflake does not let the role use the warehouse, resulting in the above error.

To resolve the error:

1. Verify which roles have access to the warehouse using the following command:

```plaintext
SHOW GRANTS ON WAREHOUSE compute_wh;
```

Look for the **USAGE** privilege and check if it has been granted to the appropriate role, such as **SYSADMIN**.
2. If the required role is missing the USAGE privilege, grant it using the following command:

```plaintext
GRANT USAGE ON WAREHOUSE compute_wh TO ROLE SYSADMIN;
```

This command explicitly lets the **SYSADMIN** role use the compute_wh warehouse.
3. Reconfigure the connector again to check if the error has been resolved.

#### JWT token is invalid error during key-pair authentication

If your Snowflake connector uses RSA key-pair authentication over Azure PrivateLink and fails with the `JWT token is invalid` error, follow these steps:

1. Reconfigure the connector using the PrivateLink account identifier, which includes the .privatelink suffix. See the example below:

`bp57731.uae-north.privatelink`

> [!NOTE]
> **Note**
> 
> Using the standard account identifier without the *.privatelink* suffix causes the connector to fail earlier with a communication error instead of reaching Snowflake.

1. After reconfiguring, if authentication still fails, note the **UUID** in the error message:

JWT token is invalid. [**uuid**]
2. Run the following queries in Snowflake, replacing UUID in each query with the *UUID* from your error message, to identify the exact cause:

**Query 1:**

```plaintext
SELECT JSON_EXTRACT_PATH_TEXT(SYSTEM$GET_LOGIN_FAILURE_DETAILS('uuid'), 'errorCode');
```

**Query 2:**

```plaintext
SELECT SYSTEM$GET_LOGIN_FAILURE_DETAILS('uuid');
```

> [!WARNING]
> **Important**
> 
> If the errorCode returned is `JWT_TOKEN_INVALID_ISSUE_TIME`, the token's issue time doesn't align with the Snowflake server's clock. This indicates a clock synchronization issue between the Securiti pod and the Snowflake server.

**Resolution:**

Update the chrony.conf file on your on-premises pod server to reference internal NTP servers. This resolves the clock synchronization issue and lets the connector authenticate successfully.
