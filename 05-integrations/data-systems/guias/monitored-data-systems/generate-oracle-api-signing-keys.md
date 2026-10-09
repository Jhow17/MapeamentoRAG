---
title: "Generate Oracle API signing keys"
slug: "generate-oracle-api-signing-keys"
updated: 2026-07-20T20:30:44Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/generate-oracle-api-signing-keys"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Generate Oracle API signing keys

Use the following OpenSSL commands in the MacOS command terminal to generate the required API signing key. For more information, see [Oracle’s guide](https://docs.oracle.com/en-us/iaas/Content/API/Concepts/apisigningkey.htm).

If you are using a Windows-based system, install GitBash for Windows before running the required OpenSSL commands.

1. Enter the command below to create an .OCI directory for storing your Credentials.

`mkdir ~/.oci`

![OOBMkDirectory.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3529b8cf-ce31-96c8-e9c5-d3ea912c8cbd.jpg)
2. Record the key to use later.

`openssl genrsa -out ~/.oci/oci_api_key.pem -aes128 2048`
3. Set and verify a coinciding passphrase as shown below. This is used subsequently in the following key generation processes

![OObVerifyPassPhrase.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bd5317b9-0667-e6f3-c193-a3949ab6de69.jpg)
4. Enter the command below to set read-only Permissions on your private key file.

`chmod go-rwx ~/.oci/oci_api_key.pem`

![OObSavingKey.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-49f324c5-933c-ae79-1194-15b106190429.jpg)

Save and store the key file safely on your computer for uploading it later during Activation.
5. Enter the command below to generate a public key.

`openssl rsa -pubout -in ~/.oci/oci_api_key.pem -out ~/.oci/oci_api_key_public.pem`
6. Enter the command below to generate your public key’s fingerprint in a format such as (1a:2b:3c etc.).

`openssl rsa -pubout -outform DER -in ~/.oci/oci_api_key.pem | openssl md5 -c`

![OObFingerprintCopy.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c2b71787-7c33-47bd-babb-126f0ace08e5.jpg)
7. Record the generated value to use later in the Connector Activation process.

`cat ~/.oci/oci_api_key_public.pem | pbcopy`
8. Proceed to [Save the public access key to your Oracle user account](/latest/docs/save-the-public-access-key-to-your-oracle-user-account).
