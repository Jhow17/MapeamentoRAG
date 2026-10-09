---
title: "Using AWS Secrets Engine for dynamic credentials"
slug: "using-aws-secrets-engine-for-dynamic-credentials"
updated: 2026-01-23T16:17:57Z
published: 2026-01-23T16:17:57Z
canonical: "helpcenter.securiti.ai/using-aws-secrets-engine-for-dynamic-credentials"
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Using AWS Secrets Engine for dynamic credentials

> [!NOTE]
> **Important**
> 
> AWS Secrets Engine is supported for Amazon S3 data system credentials only.

When using **Auto-generate Dynamic Credentials** authentication type for your Amazon S3 data system connector, you must configure HashiCorp Vault to interact with AWS and manage the dynamic credentials.

Follow the procedure below to enable AWS Secrets Engine for HashiCorp. See [AWS Secrets Engine documentation](https://developer.hashicorp.com/vault/docs/secrets/aws) for more information.

1. Run the following command in HashiCorp Vault to enable the AWS secrets engine:

```bash
vault secrets enable aws
```
2. Authenticate AWS and store the credentials (replace ACCESS_KEY, SECRET_KEY, and REGION with your AWS account details):

```bash
vault write aws/config/root \
access_key=ACCESS_KEY \
secret_key=SECRET_KEY \
region=REGION
```
3. To use **federation tokens** for retrieving credentials. in HashiCorp:

This returns access token, secret key, and federation token.
  1. Create a Policy with permissions in Amazon S3 and add them to your user. See Amazon S3's documentation for more information.
  2. Enable a new secret in the HashiCorp vault of type federation_token.

```bash
vault write aws/roles/s3_creds \
credential_type=federation_token \
policy_arns=ARN_FOR_S3_POLICY
```
  3. As the above command executes successfully, request the credentials from the vault. To request credentials from vault with time to live (ttl) 15 minutes (minimum value for ttl) run the following command.

```bash
vault write aws/sts/s3_creds ttl=15m
```
4. To use **session tokens** for retrieving credentials. in HashiCorp:

> [!NOTE]
> **Note**
> 
> STS session tokens inherit any and all permissions granted to the user configured in aws/config/root.

This returns access token, secret key, and session token.
  1. Create a policy with permissions in Amazon S3 and add them to your user. See Amazon S3's documentation for more information.
  2. Enable a new secret in the HashiCorp vault of type session_token.

```bash
vault write aws/roles/session_token \
 credential_type=session_token
```
  3. As the above command executes successfully, request the credentials from the vault. To request credentials from vault with time to live (ttl) 15 minutes (minimum value for ttl) run the following command.

```bash
vault read aws/sts/session_token ttl=15m
```
5. Create [credential read policy in the vault for AWS Secrets Engine](/latest/docs/creating-credential-read-policies-1)
6. Proceed to [creating a keyring for your HashiCorp vault instance](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp)

Securiti policies translate data intelligence into actions. Each policy has rules that, when matched by a file, document, or resource, trigger a response.
