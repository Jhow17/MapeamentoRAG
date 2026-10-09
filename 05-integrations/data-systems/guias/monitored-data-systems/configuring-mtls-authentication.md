---
title: "Configuring mTLS authentication"
slug: "configuring-mtls-authentication"
updated: 2026-08-05T22:48:00Z
published: 2026-08-05T22:48:00Z
canonical: "helpcenter.securiti.ai/configuring-mtls-authentication"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring mTLS authentication

To generate certificates and users for mTLS authentication, perform the following steps:

1. To update the package list and install OpenSSL, run the following commands.

```plaintext
sudo apt update
sudo apt install openssl
```
2. Create a directory to store all your certificates and keys:
  1. To create a directory, run the following command.

```plaintext
sudo mkdir -p /etc/ssl/mongo
```
  2. To change the ownership to manage the file, run the following command.

```plaintext
sudo chown -R $USER:$USER /etc/ssl/mongo
```
3. Generate a self-signed certificate for your CA and enable authentication:

You can also create a MongoDB connection using one of the following methods:
  1. To create a private key and a self-signed certificate for your CA, run the following commands

```plaintext
# Navigate to the directory where certificates are stored
cd /etc/ssl/mongo

# Generate the private key with password protection
openssl genpkey -algorithm RSA -out ca.key -aes256

# Generate the self-signed certificate
openssl req -new -x509 -key ca.key -out ca.pem -days 365 -subj 
"/CN=myName/OU=myOrgUnit/O=myOrg/L=myLocality/ST=myState/C=US"
```

> [!NOTE]
> Note
> 
> - The ca.pem file is in PEM format, which is compatible with MongoDB.
> - The Common Name (CN) and optionally additional Distinguished Name fields must follow the **RFC 4514** format, as specified in [MongoDB documentation](https://www.mongodb.com/docs/atlas/security-self-managed-x509/#enter-user-information.).
  2. Enable certificate Self-managed X.509 certificate authentication.
    1. In the MongoDB Atlas console, open your project from the left sidebar.
    2. Under **Security**, click **Database & Network Access.**
    3. Under the **Network Access,** click **Advanced**.
    4. Under the **Advanced** page, enable the **Enable Self-Managed X.509 Authentication** toggle and upload the certificate generated in step 3 above.
    5. Save the changes. ![Settings page for self-managed X.509 authentication with upload and save options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/MongoDB-CA.png)
  - [Create a MongoDB connection without srv](/latest/docs/obtain-credentials-for-mongodb-without-srv-connection)
  - [Create a MongoDB+srv connection](/latest/docs/granting-db-permissions)
4. To generate the server certificate, run the following commands.

```plaintext
# Navigate to the directory where MongoDB certificates are stored
cd /etc/ssl/mongo

# Generate the private key with password protection
openssl genpkey -algorithm RSA -out server.key -aes256

# Generate the CSR
openssl req -new -key server.key -out server.csr -subj "/CN=myName/OU=myOrgUnit/O=myOrg/L=myLocality/ST=myState/C=US"

# Sign the CSR with your CA
openssl x509 -req -in server.csr -CA ca.pem -CAkey ca.key -CAcreateserial -out server.crt -days 3650

# Combine the server certificate and private key into a PEM file
cat server.crt server.key > server.pem
```
5. To generate a client certificate, run the following commands.

```plaintext
# Navigate to the directory where MongoDB certificates are stored
cd /etc/ssl/mongo

# Generate the private key with password protection
openssl genpkey -algorithm RSA -out client.key -aes256

# Generate the CSR
openssl req -new -key client.key -out client.csr -subj 
"/CN=myName/OU=myOrgUnit/O=myOrg/L=myLocality/ST=myState/C=US"

# Sign the CSR with your CA
openssl x509 -req -in client.csr -CA ca.pem -CAkey ca.key 
-CAcreateserial -out client.crt -days 3650

# Combine the client certificate and private key into a PEM file
cat client.crt client.key > client.pem
```

> [!NOTE]
> Note
> 
> The client.pem file contains both the certificate and the private key, required for client authentication.
6. Create a MongoDB user for X.509 Certificate Authentication
  1. Extract the subject from the client certificate to use as the MongoDB username.

```plaintext
openssl x509 -in /etc/ssl/mongo/client.crt -noout -subject

The output is as follows:
subject= C=US,ST=myState,L=myLocality,O=myOrg,OU=myOrgUnit,CN=myName
```
  2. Use this subject to create the MongoDB user.
    1. In the MongoDB Atlas console, under **Security**, click **Database & Network Access > Data Access > Database Users.**
    2. On the **Database Users** page, click **Add New Database User.**
    3. On the **Add New Database User** popup under the Certificate tab, enter the subject in the **Common Name** field. ![Form for adding a new database user with authentication method options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/MongoDB-User.png)
    4. Scroll down to the **Database User Privileges** section, under the **Built-in Roles**, assign the **Only read any database** role. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/MongoDB-builtin.png)
    5. Click **Add User**.
7. (Optional) Create a Java KeyStore (JKS) from Client PEM:
  1. Convert PEM to PKCS#12 Format

```plaintext
openssl pkcs12 -export -in client-cert.pem -inkey client-key.pem -out client.p12 -name client-alias
```
  2. Import PKCS#12 into JKS

```plaintext
keytool -importkeystore -srckeystore client.p12 -srcstoretype pkcs12 -destkeystore client.jks -deststoretype JKS -destalias client-alias
```
