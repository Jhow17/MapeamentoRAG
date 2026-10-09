---
title: "(Optional) Configure the HashiCorp OAuth token for Azure Data Lake Storage (ADLS) Gen2"
slug: "optional-configure-the-hashicorp-oauth-token-for-azure-data-lake-storage-adls-gen2"
updated: 2025-10-30T19:25:45Z
published: 2025-11-03T06:14:10Z
canonical: "helpcenter.securiti.ai/optional-configure-the-hashicorp-oauth-token-for-azure-data-lake-storage-adls-gen2"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Configure the HashiCorp OAuth token for Azure Data Lake Storage (ADLS) Gen2

If you want to use HashiCorp credential vaults to store and manage OAuth credentials for the Azure Data Lake Gen 2 data system:

1. If you haven’t already done so, configure the HashiCorp Vault as described in [HashiCorp credential vault](/v1/docs/hashicorp-credential-vault), and perform the procedure in the subsection on OAuth authentication.
2. Do the following to create a directory and configure the access token in the vault:
  1. Create a directory inside the secrets engine vault like this:

```plaintext
ault secrets enable -path=oauth2 passthrough-plugin
```
  2. Create the server for client credentials flow:

```plaintext
vault write oauth2/servers/azure_data_lake_storage \ 
provider=microsoft_azure_ad \
client_id={{CLIENT_ID}} \
client_secret={{CLIENT_SECRET}} \
provider_options=tenant={{tenant_id}}
```
  3. Get and write the credentials on the desired path:

```plaintext
ault write oauth2/self/azure_data_lake_storage server=azure_data_lake_storage
scopes=https://graph.microsoft.com/.default
```
  4. Verify by reading the access token from the path mentioned above, and making sure it returns a valid token:

```plaintext
vault read oauth2/self/azure_data_lake_storage
```

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
