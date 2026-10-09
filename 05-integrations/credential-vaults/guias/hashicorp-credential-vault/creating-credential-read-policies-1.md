---
title: "Creating credential read policies"
slug: "creating-credential-read-policies-1"
updated: 2026-01-23T16:03:04Z
published: 2026-01-23T16:03:04Z
canonical: "helpcenter.securiti.ai/creating-credential-read-policies-1"
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Creating credential read policies

For each `{{credential_path}}` you created in [Storing data system credentials in HashiCorp vault](/latest/docs/storing-data-system-credentials-in-hashicorp-vault), create a credential policy using the below command in the HashiCorp CLI:

```plaintext
vault policy write jenkins -<<EOF
path "{{credential_path}}" {
capabilities = [ "read" ]
}
EOF
```

For **AWS Secrets Engine**, create and edit the credential read policy in the vault as shown below.

```plaintext
path "secret/*" {
capabilities = [ "read" ]
}
path "aws/*" {
capabilities = [ "read" ]
}
```

Proceed to [Configuring HashiCorp vault instance in Securiti](/latest/docs/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti), and then to [Creating keyrings for HashiCorp](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp).
