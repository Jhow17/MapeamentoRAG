---
title: "Crypto"
slug: "crypto-regular-node"
updated: 2026-01-09T08:58:09Z
published: 2026-01-09T08:58:09Z
canonical: "helpcenter.securiti.ai/crypto-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Crypto

In a workflow automation environment, a Crypto node is typically used to perform cryptographic functions, such as encryption, decryption, hashing, or signing of data. This node helps ensure the confidentiality, integrity, and authenticity of data as it moves through various stages of a workflow. By incorporating cryptographic operations, businesses can secure sensitive information, comply with data protection regulations, and mitigate risks associated with data breaches.

Please refer to the [node configurations](/v1/docs/crypto) to understand the node working and properties.

#### Example use case

As an example, let’s create a workflow that caters to a financial services company that handles vast amounts of sensitive data across various databases. To comply with data protection regulations (like GDPR or CCPA), the company implements a workflow to automatically secure the names of database tables that contain newly identified PD elements, thereby reducing risk exposure and enhancing data security.

The workflow starts with a Field Classification Trigger node that identifies new PD elements on the database. From the results obtained, the Crypto node hashes the sensitive information, in this case, the table name. This hashed value is then passed onto the compliance team via Slack node to notify about the updated data.

The following nodes are used in this workflow:

1. [Field Classification Trigger Node](/v1/docs/field-classification-trigger-node)
2. Crypto Node
3. [Slack Node](/v1/docs/slack)

#### Secure Data Management in Regulatory Compliance

1. Start the workflow by a Field Classification Trigger node that gets triggered based on any update in the PD elements.
2. From the updated results, choose the database table name and pass it on to the Crypto node to hash its value.

![Screenshot_2024-05-07_at_12_58_40_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e09882e7-7cbd-14a2-bbe0-cc27fdb29264.png)
3. Finish the workflow by adding a Slack node that notifies the relevant team with the updated dataset.
4. Connect the nodes and execute the workflow.

![Screenshot_2024-05-07_at_12_57_41_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0988a4f1-be38-a610-6076-b8ae47893593.png)
5. Once the workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| Encryption key | Choose or create credentials |
| Action | Encrypt | Encrypt a binary field using a key |
| Decrypt | Decrypt a binary field using a key |
| Hash | Hash a text in a specified format |
| Hmac | Hmac a text in a specified format |
| Sign | Sign a string using a private key |
| Type | AES | Use AES encryption/decryption |
| Key Size | 128 | Sets key size accordingly |
| 192 |
| 256 |
| Mode | CBC | Sets encryption mode accordingly |
| ECB |
| Input Property | Name of the binary property that holds the file data to be encrypted |
| Output property | Name of the binary property to which to write the data of the decrypted file |
