---
title: "NFS FAQs"
slug: "nfs-faqs"
updated: 2026-07-22T19:21:35Z
published: 2026-07-22T19:21:35Z
canonical: "helpcenter.securiti.ai/nfs-faqs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# NFS FAQs

[1. Which versions of NFS does the connector currently support?](https://helpcenter.securiti.ai/docs/nfs-faqs)

[2. Is there a recommended reading and writing size (e.g., 8192 KB) and time out value?](https://helpcenter.securiti.ai/docs/nfs-faqs)

[3. What format should the NFS path follow?](https://helpcenter.securiti.ai/docs/nfs-faqs)

[4. What type of credentials and permissions are required (e.g., service account with read-only access to the NFS mount)?](https://helpcenter.securiti.ai/docs/nfs-faqs)

---

### FAQ

#### 1. Which versions of NFS does the connector currently support?

Securiti development team has tested NFS up to version 3 with successful working. We have not yet tested with the version 4 yet.

#### 2. Is there a recommended reading and writing size (e.g., 8192 KB) and time out value?

We recommend using a large size (up to 1048576 Bytes), but this recommendation primarily depends upon the network and resources available on the Appliance. The NFS client successfully receives more data in each network request as the value increases. The default timeout for NFS is 60 seconds. Keep in mind that these fields are optional. You can specify the values in these fields based on your use case.

For Instance, if the NFS host takes time to respond when connecting to the Appliance, you can increase the timeout value.

#### 3. What format should the NFS path follow?

Enter the complete NFS path in this format:

`/&lt;directory&gt;/&lt;directory&gt;/&lt;nfs_mount_point&gt;`

> [!WARNING]
> **Warning**
> 
> Do not add a trailing slash (`/`) at the end of the NFS path.
> 
> For example, `/&lt;directory&gt;/&lt;directory&gt;/&lt;nfs_mount_point&gt;/` is incorrect.

#### 4. What type of credentials and permissions are required (e.g., service account with read-only access to the NFS mount)?

We only need read-only access for performing scanning. No specific Permissions are necessary in the form of a service account or user account. The Connector primarily requires access from the pods to the NFS host and drive. The NFS host and drive should be accessible and mountable within the Pod Appliance.
