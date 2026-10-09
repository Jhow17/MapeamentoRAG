---
title: "Acquire authentication credentials in Veeva Vault"
slug: "acquire-authentication-credentials-in-veeva-vault"
updated: 2025-10-31T06:40:11Z
published: 2025-11-03T07:38:02Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-veeva-vault"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Veeva Vault

1. Log in to your Veeva Vault Instance.
2. > [!NOTE]
> **Important**
> 
> This procedure assumes that you have the necessary account privileges and have recorded the Credentials before Connector Activation.

On the Veeva Vault dashboard, grant scopes (Permissions) to the Business Admin User (Vault Owner role) by selecting **Settings > Security Settings** and mark the checkboxes for the following:

See the following links for more information:
  - **API Access** - Controls general access to the API and allows you to make API calls successfully. It doesn't control the ability to authenticate. All users can authenticate to Vault without specific permission.
  - **Business Admins and System Admins have automatic access to all documents** - Enables Business Admin/System Admin User to allow complete access to (Read/Download) for all the documents for all users in the vault.
  - [https://developer.veevavault.com/docs/#authentication](/v1/docs/securiti-pods-and-elastic-pods)
  - [https://support.veeva.com/hc/en-us/articles/115004321268-How-is-Classic-Vault-Security-Applied-in-the-Document-Sharing-Settings-#](https://support.veeva.com/hc/en-us/articles/115004321268-How-is-Classic-Vault-Security-Applied-in-the-Document-Sharing-Settings-#)
  - [https://support.veeva.com/hc/en-us/articles/115003835893-Vault-System-Administrator-Unable-to-See-Any-Documents](https://support.veeva.com/hc/en-us/articles/115003835893-Vault-System-Administrator-Unable-to-See-Any-Documents)
3. Veeva Vault Connector uses the "One-Legged OAuth" params for Connector Activation:
  1. **Username** - Email of a Business Admin User or Vault Owner.
  2. **Password**
  3. **Vault DNS** - Home URL for Veeva Vault.

> [!NOTE]
> **Note**
> 
> For example, "test-domain-qualitydocs" is your Vault DNS for <*https://test-domain-qualitydocs.veevavault.com/ui/*>.

See [domain & DNS](https://support.veeva.com/hc/en-us/articles/231691107-What-is-the-Difference-Between-Domain-and-DNS-in-Vault-) and [Veeva Vault dev](/v1/docs/securiti-pods-and-elastic-pods) for more information.
4. Proceed to [Activate the Veeva Vault connector in Securiti](/v1/docs/activate-the-veeva-vault-connector-in-securiti).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
