---
title: "Configuring HashiCorp vault instance in Securiti"
slug: "hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti"
updated: 2026-04-28T04:11:21Z
published: 2026-04-28T04:11:21Z
canonical: "helpcenter.securiti.ai/hashicorp-credential-vault-configuring-hashicorp-vault-instance-in-securiti"
stale: true
area: integrations
modulo: credential-vaults
tipo: guia
data_captura: 2026-10-06
---

# Configuring HashiCorp vault instance in Securiti

We assume you have fulfilled the following prerequisites:

- [Setting up the OAuth plugin with HashiCorp](/latest/docs/installing-and-setting-up-oauth2-secrets-engine)

> [!NOTE]
> Note
> 
> This procedure is required only for data systems supporting OAuth plugin with HashiCorp.

- [Setting up HashiCorp Vault and acquiring authentication credentials](/latest/docs/hashicorp-credential-vault-authentication-methods-in-hashicorp-vault)
- [Storing data system credentials in HashiCorp vault](/latest/docs/storing-data-system-credentials-in-hashicorp-vault)
  - [Configuring the OAuth token for data system](/latest/docs/storing-data-system-credentials-in-hashicorp-vault)

> [!NOTE]
> Note
> 
> This procedure is required only for data systems supporting OAuth plugin with HashiCorp.

- [Creating credential read policies for credential paths](/latest/docs/creating-credential-read-policies-1)

Configure and connect your vault instance with Securiti, following the procedure below.

1. In Securiti, open the main menu and select **Integrations > Credential Vaults**.
2. On the Credential Vaults page, near the upper right corner of the page, click **Add Integration** to create a new instance.
3. From the catalog of available credential vaults, select **HashiCorp**.
4. On the **Basic Information** tab, enter a name and location for the HashiCorp vault instance, and if you want, also choose additional co-owners (by default you are the owner).
5. Click **Create Instance & Continue**.
6. On the **Authentication** tab, select a pod(s) from the **Pod Configuration** menu where a vault authenticates.

> [!NOTE]
> Note
> 
> - Securiti authenticates the vault only on the pods you select. You can choose all pods, a single pod, or multiple pods for a vault instance. If you select **ALL**, Securiti runs vault authentication across all pods.
> - You can update pod selection after creation without recreating the vault configuration.
> - Only vaults associated with the same pod as the data system connector appear as available keyrings during connector configuration.
7. On the **Authentication** tab, apply the following settings:

| Setting | Description |
| --- | --- |
| Host | Enter the host URL you obtained in HashiCorp. The URL must start with either `HTTP:` or `HTTPS:` |
| Port | Enter the port, often `8200`. |
| (Optional) Namespace | Enter the namespace for your tenant within the HashiCorp Vault Enterprise environment This is an optional parameter required when using isolated environment(s) in the vault. See [HashiCorp vault enterprise namespaces documentation](https://developer.hashicorp.com/vault/docs/enterprise/namespaces), for more information. See an example below. `teamB/engineering` |
8. In **Authentication Method** field, select one of the following:

See the subsequent sections for more information on authentication credentials required for each method.
  - AppRole
  - AWS IAM Role
  - Username & Password
  - **AppRole** **authentication**:

For AppRole authentication in HashiCorp Vault, two methods are supported for storing and accessing secrets.

Following values are required when configuring the connector.

| Setting | Description |
| --- | --- |
| (Optional)AppRole Mount Path | Enter the custom mount path where your AppRole is enabled. Leave this field empty if you are using the default `auth/approle/login` path. In case of a custom path like `custom-approle`, the complete path becomes, `auth/custom-approle/login.` See an example below of a custom mount path value: `custom-approle/securiti` > [!NOTE] > **Note** > > Custom mount path for AppRole is supported from pod version 1.134.0-01p and above. |
| AppRole ID | Enter the AppRole ID you acquired in [Authentication methods in HashiCorp vault](/latest/docs/hashicorp-credential-vault-authentication-methods-in-hashicorp-vault) |
| (Optional) Upload Role Secret to Pod Cluster | Enable the toggle depending if you are storing your secret on your pod and leave it disabled if stored on Securiti cloud. - If the toggle is disabled, enter the secret in the text box below it. - If you are storing the secret on your pod, provide the path to secret. The secret can be configured using the following methods: - Method 1: Place a secret file containing the role secret in the indicated location on every node in every Securiti pod cluster in your environment. > [!WARNING] > **Important** > > Starting with release 1.133.0, Securiti deprecates the manual method of uploading keys to pod nodes. - Method 2 (Recommended): Configure the secret using Securiti’s CLI utility as described below. |
| Enter Secret | In case you are not storing the secret on pod, enter your AppRole secret ID you acquired in [Authentication methods in HashiCorp vault](/latest/docs/hashicorp-credential-vault-authentication-methods-in-hashicorp-vault) |
| (Optional) Enable Mutual TLS (mTLS) | Enable the toggle to activate mutual TLS (mTLS) authentication, requiring you to use a valid certificate along with their credentials. Once enabled, you must provide values for the following: > [!NOTE] > **Note** > > - If you are using the V1 (older) appliance, replace `/mnt/securiti-app/secrets` with `/mnt/secrets` in the specified path. > - You must create a HashiCorp vault instance prior to using mTLS. The Client certificate and key must be placed on the appliance at the path for each vault instance. - **Client Certificate Path**: Provide the path that points to the PEM-formatted client certificate file. You must place the client certificate file in the following path, on each node of every pod cluster. Replace `{instanceID}` with your HashiCorp vault instance identifier, as shown below: `/mnt/securiti-app/secrets/vault/hashicorp/{instanceID}/cert_2086.pem` - **Client Key Path**: Provide the path that points to the PEM-formatted private key file corresponding to the client certificate. You must place the client certificate file in the following path, on each node of every pod cluster. Replace `{instanceID}` with your HashiCorp vault instance identifier, as shown below: `/mnt/securiti-app/secrets/vault/hashicorp/{instanceID}2086/cert_key_2086.pem` |

#### Configuring AppRole authentication on pod:
    - Securiti cloud: You can upload and store your role secrets in the Securiti cloud where they are encrypted automatically.
    - Pod clusters: You can choose to store your role secrets locally on your pod VMs.
    - **Method 1: File-based secret configuration**

This method lets you provide your secret in a file. If you are using a version of pod earlier than 1.121, you can pass the App Role information using a file at the specified location on the pod. Place the credential or secret file in the designated location and provide the secret path when configuring the connector.

> [!WARNING]
> **Important**
> 
> Starting with release 1.133.0, Securiti deprecates the manual method of uploading keys to pod nodes.
    - **(Recommended) Method 2: Configure the secret with Securiti’s CLI utility**

This method lets you store your secret in an encrypted form on your pod.

> [!WARNING]
> **Important**
> 
> - For enhanced security, we recommend you set up the secret using the 'securitictl' CLI utility, which securely stores credentials in encrypted form within the pod.
> - The Securiti CLI utility is available for pod versions 1.121 and above.

To configure it using Securiti’s CLI utility, follow the procedure below.
      1. Login to the Master node of your pod cluster and run the following command to provision the vault secret.

```bash
kubectl get pod | grep config-controller
```
      2. Use the pod name returned by the above command and run the following commands in sequence.

```bash
kubectl exec -it <config-controller-pod-name> -- sh
```

```bash
securitictl configure-vault-secret
```
      3. Provide the **AppRole ID** and **App Secret** when prompted. The App Secret is encrypted and stored securely.

> [!NOTE]
> **Note**
> 
> The App Secret will be masked during input to prevent exposure of sensitive information.
      4. Type **exit** to leave the configuration controller pod.
  - **AWS IAM Role** **authentication**:

For AWS IAM Role authentication, you need to provide the following values as described in the table below.

| Setting | Description |
| --- | --- |
| Vault AWS IAM Role | Enter the vault AWS IAM Role. |
| AWS IAM Server ID Header | (Optional) If you have configured a AWS IAM Server ID Header, enter it here. |
| AWS IAM Role Mount Path | (Optional) If you have configured a path other than the default "AWS," enter the path here. |
  - **Username & Password authentication**:

> [!WARNING]
> **Important**
> 
> The **Username & Password** authentication method is supported for pod versions 1.124 and above.
> 
> For Username & Password authentication, you need to provide the following values as described in the table below.

| Setting | Description |
| --- | --- |
| Username | Enter the vault username with assigned policy, that you recorded when creating a policy in vault. |
| Password | Enter your vault password. |
| (Optional) Configure Password on Pod clusters | Enable the toggle to store your password on pod. By enabling this option, your password is safely stored and accessed from pod eliminating the need to specify it in the **Password** field. > [!WARNING] > **Important** > > You can store your passwords on pod for pod versions 1.124 and above only. See the section below to read about storing passwords on pod. |
| (Optional) Enable Mutual TLS (mTLS) | Enable the toggle to activate mutual TLS (mTLS) authentication, requiring you to use a valid certificate along with their credentials. Once enabled, you must provide values for the following: > [!NOTE] > **Note** > > If you are using the V1 (older) appliance, replace `/mnt/securiti-app/secrets` with `/mnt/secrets` in the specified path. - **Client Certificate Path**: Provide the path that points to the PEM-formatted client certificate file. You must place the client certificate file in the following path, on each node of every pod cluster: `/mnt/securiti-app/secrets/vault/hashicorp/2086/cert_2086.pem` - **Client Key Path**: Provide the path that points to the PEM-formatted private key file corresponding to the client certificate. You must place the client certificate file in the following path, on each node of every pod cluster: `/mnt/securiti-app/secrets/vault/hashicorp/2086/cert_key_2086.pem` |

#### Specifying password for HashiCorp vault
    - **Method 1: Specify password on Securiti UI**

You can specify password directly in the **Instance Setup** tab for your vault instance, in **Password** field. To store your password on pod and use a secure method, see the method below.
    - **(Recommended) Method 2: Store the password in pod with Securiti’s CLI utility**

This method lets you store your pod using securitictl utility. To do so, record your HashiCorp's vault instance ID from the URL as shown below.

The instance ID can be located from the end of the URL.

![hashicorp_instanceID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-44c4d92c-20c6-9e84-c30f-e9b5f8d4d37b(3).png)

To configure it using Securiti’s CLI utility, follow the procedure below.
      1. Log in to your pod and execute the following command in your configuration controller.

```bash
kubectl exec deployments/priv-appliance-config-controller -it -- sh
```
      2. Use the Securiti cli utility to save your password on pod by running the command below.

```bash
securitictl configure-vault-secret
```
      3. Select **Username Password** as the authentication type.
      4. Enter your vault instance ID that you recorded in step a.
      5. Enter your password to store on pod and press enter. Password is successfully saved on pod.
      6. (Optional) Verify the password availability for your vault instance by running the command below.

```bash
kubectl exec statefulset/priv-appliance-redis-master -it -- bash -c 'redis-cli -a $REDIS_PASSWORD get "vault:hashicorp:secret:id:{{ID}}"'
```

Replace {{ID}} with the vault ID recorded in step a. If you get an encrypted value, this means that the password is configured for the vault.
9. Click **Test and Save**.
10. On the **Test Connection** popup, click **Yes, proceed with testing**. Securiti validates the authentication information.
11. View the connection status in the **Overview** tab.
12. Proceed to [Creating keyrings for HashiCorp](/latest/docs/hashicorp-credential-vault-creating-keyrings-for-hashicorp)

A cluster is comprised of a primary node and up to nine secondary nodes.

Each pod has a master node that manages the activities of the secondary nodes.

## Related

- [Creating keyrings for HashiCorp](/hashicorp-credential-vault-creating-keyrings-for-hashicorp.md)
- [Azure Key Vault](/configuring-credential-vaults-azure-key-vault.md)
- [GCP Secret Manager credential vault](/configuring-credential-vaults-gcp-secret-manager-credential-vault.md)
