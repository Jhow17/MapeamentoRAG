---
title: "Managing SSH keys"
slug: "managing-ssh-keys"
updated: 2026-03-31T07:56:45Z
published: 2026-03-31T07:56:45Z
canonical: "helpcenter.securiti.ai/managing-ssh-keys"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Managing SSH keys

You use SSH key pairs to secure communication between Securiti and outside data systems; mostly in conjunction with workflows you create using the Workflow Orchestration module. When you generate a key pair, Securiti lets you copy the private key to configure in the outside data system, and uses the private key to validate communication with that system.

## Generating an SSH key pair

1. In Securiti, open **System Settings** and choose **Integrations > Credentials > SSH Key Pairs**.
2. On the SSH Keys page, near the upper right corner, click **Generate SSH Key Pair**.
3. On the SSH Key Pair Parameters popup, apply the following settings, then click **Generate**:

| Setting | Description |
| --- | --- |
| Name | Enter a convenient name for the key pair. |
| Bits | Choose the number of bits for the key pair from the menu. The default is 4096. |
| Description | Enter a description of the key pair that helps you remember what you use it for. |

1. On the list of key pairs, find the one you just created, and click **Copy** to copy the public key to the clipboard.
2. Configure the outside data system to use the public key when communicating with Securiti. See the data system documentation for details.

## Updating a key pair

Updating a key pair creates a new public and private key pair, and also lets you change the name, bits, and description if you want. After you update a key pair, you must also update the outside data system with the new public key.

1. On the list of key pairs, find the one you want to update, and at its right end choose **Options** (three dots) **> Update**.
2. (Optional) use the tools on the SSH Key Pair Parameters popup to update the name, bits, and description.
3. On the SSH Key Pair Parameters popup, click **Save**.
4. On the list of key pairs, find the one you just updated, and click **Copy** to copy the public key to the clipboard.
5. Configure the outside data system to use the new public key when communicating with Securiti. See the data system documentation for details.

## Deleting a key pair

On the list of key pairs, find the one you want to delete, and at its right end choose **Options** (three dots) **> Delete**, then click **Yes** to confirm the deletion

## Related

- [Managing Webhook URLs](/managing-credentials-managing-webhook-urls.md)
- [Using keyrings in Securiti](/creating-keyrings.md)
- [Creating keyrings for HashiCorp](/hashicorp-credential-vault-creating-keyrings-for-hashicorp.md)
