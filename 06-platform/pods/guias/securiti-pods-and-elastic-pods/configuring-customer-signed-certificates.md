---
title: "Configuring customer-signed certificates (cluster version v1.28+)"
slug: "configuring-customer-signed-certificates"
updated: 2025-12-09T12:20:33Z
published: 2025-12-09T12:20:33Z
canonical: "helpcenter.securiti.ai/configuring-customer-signed-certificates"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Configuring customer-signed certificates (cluster version v1.28+)

By default, Securiti pods use self-signed certificates to authenticate HTTP communication. If you must have customer-signed certificates for your pod deployments, before deploying the pod, use this procedure to place the certificates on the compute instance. When the CA certificates and keys are found at the correct location during the initial startup of the first node in the cluster, the pod installation bypasses the automatic generation of CA certificates.

1. Before deploying the pod, create the directory for the certificates if it does not already exist. For most pod deployments, use:

```bash
/mnt/rancher/k3s/server/tls
```

> [!NOTE]
> **Note**
> 
> The directory location might vary based on what the SECURITI_INSTALL_DIR variable in the installation script is set to.
2. In the certificate directory, place all of the following certificate files:

> [!NOTE]
> **Note**
> 
> Note that the public Certificate Authorities (CAs) will not issue the certificates to CN for internal use because they cannot verify the ownership. The suggested approach is to use a customer managed CA or an interim CA to sign cluster certificates.

If you want to use only an existing root CA certificate, you must provide the following files:

If you want to use existing root and intermediate CA certificates, provide the following files:

> [!NOTE]
> **Note**
> 
> - The etcd files are required even if embedded etcd is not in use.
> - Service.key is the private key used to sign service-account tokens. It does not have a corresponding certificate.
  - `server-ca.crt`
  - `server-ca.key`
  - `client-ca.crt`
  - `client-ca.key`
  - `request-header-ca.crt`
  - `request-header-ca.key`
  - `etcd/peer-ca.crt`
  - `etcd/peer-ca.key`
  - `etcd/server-ca.crt`
  - `etcd/server-ca.key`
  - `service.key`
  - `root-ca.pem`
  - `root-ca.key`
  - `root-ca.pem`
  - `intermediate-ca.pem`
  - `intermediate-ca.key`
3. Proceed to install the pod as described in [Pod installation (cluster version v1.28+)](/v1/docs/pod-installation-cluster-version-v128).

## Related

- [Using the pre-flight diagnostic script (cluster version v1.28+)](/pods-using-the-pre-flight-diagnostic-script.md)
- [Pod installation (cluster version v1.28+)](/pod-installation-cluster-version-v128.md)
- [Pod quick install guides cluster version v1.28](/pod-quick-install-guides-cluster-version-v128-en.md)
- [Pod custom installation guides (cluster version v1.28+)](/podcustom-installation-guides.md)
