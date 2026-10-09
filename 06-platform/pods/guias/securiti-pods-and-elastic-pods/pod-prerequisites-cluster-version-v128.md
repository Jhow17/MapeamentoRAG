---
title: "Pod prerequisites (cluster version v1.28+)"
slug: "pod-prerequisites-cluster-version-v128"
updated: 2026-09-25T07:18:23Z
published: 2026-09-25T07:18:23Z
canonical: "helpcenter.securiti.ai/pod-prerequisites-cluster-version-v128"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Pod prerequisites (cluster version v1.28+)

Ensure that these prerequisites are met when you deploy pods. See also [Recommended pod provisioning (cluster version v1.28+)](/latest/docs/pods-recommended-pod-provisioning).

> [!NOTE]
> **Note**
> 
> Root user access on the host VM is required to install the Securiti Pod, as well as for certain pod operations and troubleshooting.

- The Linux server where you install the node must meet the following requirements:

| Requirement Category | Details |
| --- | --- |
| Operating system (OS) | Any of the following: - Ubuntu 22.04, 24.04, 26.04 - Centos 8.x, 9.x - Red Hat 9.x, 10.x - Amazon Linux 2023 - SUSE Linux version 15 - Oracle Linux 9, 10 |
| RAM | At least 64GB. |
| CPUs | Either 16 or 32 vCPUs. Other quantities of vCPUs are not supported. See [Recommended pod provisioning (cluster version v1.28+)](/v1/docs/pods-recommended-pod-provisioning) for our recommendations. > [!NOTE] > **Note** > > The CPUs must support the AVX instruction set. To verify, issue this command and check that the response shows that the AVX CPU flag is available on the machine: > > ```bash > grep -iFq avx /proc/cpuinfo && echo "avx requirement met" \|\| echo "avx requirement NOT met" > ``` CPU architecture must be x86_64. |
| Disk type | An SSD (not HDD) with these characteristics: - Choose a general purpose SSD that performs well for workloads with random IO (as opposed to long sequential reads or writes). - Ensure that 3000 IOPS or more are provisioned. |
| Disk space | At least 1 TB available. > [!NOTE] > **Note** > > The partition must be ext4, if it is xfs then make sure the ftype=1 parameter is passed during format, for example: > > ```bash > mkfs.xfs -n ftype=1 /mount-point > ``` Also: - The root partition (/) must be at least 75 GB in size. - The install folder must exist and have at least 1 TB available. The install folder is /mnt by default but you can change it to a different location if required. Please contact [support@securiti.ai](mailto:support@securiti.ai) to change the default folder. - The /tmp folder must exist and have at least 50 GB available. |
| Disk performance | The disk must have a minimum transfer rate of 50MB/s. |
- Each pod must be set up with outbound Internet connectivity enabled in order to:
  - Register for the appropriate user account in the Securiti cloud
  - Fetch updates from the Securiti cloud
  - Transfer detections, reporting data, and analytics information to the Securiti cloud
- For multiple nodes, the servers must have different hostnames.
- NTP service must be configured, verify `/etc/ntp.conf` for server address.
- VMWare ESXi VXLAN on Port 8472 must not be configured. It is required for Pod operations.
- You must configure a valid DNS in `/etc/resolv.conf`, and not a loopback address such as 127.0.1.1.
- If your IT policies block direct internet access, edit the applicable environmental variables in `/etc/environment` as shown in the samples below:
  - ```bash
http_proxy=10.151.20.176:3128
```

(sample)
  - ```bash
https_proxy=10.151.20.176:3128
```

(sample)
  - ```bash
no_proxy=0.0.0.0/0,.local
```

(enter exactly as shown)
- In the case of intercepting proxy addresses, install a CA cert as shown below:

```bash
openssl x509 -outform der -in CERTIFICATE.pem -out CERTIFICATE.crt
```

And then for CentOS:

```bash
cp CERTIFICATE.crt /etc/pki/ca-trust/source/anchors/ update-ca-trust
```

And then for Ubuntu:

```bash
sudo cp CERTIFICATE.crt /usr/local/share/ca-certificate sudo update-ca-certificates
```
- To check whether both the required URLs are accessible on your end, enter these commands:

```bash
curl -Is -m2  https://privaci-registry.s3.us-west-2.amazonaws.com  | head -n 1 | grep -q "HTTP" && echo "connection successful" || echo "connection failed"
                curl -Is -m2  <host> | head -n 1 | grep -q "HTTP" && echo "connection successful" || echo "connection failed"
```

Where *<host>* is:

After you complete the URL checks, allow-list the following URLs for the master and all secondary nodes for traffic outbound from the pod to SaaS. Use the set appropriate for your location:
  - US cloud: `https://app.securiti.ai`
  - US1 cloud: `https://app1.securiti.ai`
  - Indonesia Cloud: `https://app2.securiti.ai`
  - Canada Cloud: `https://app3.securiti.ai`
  - Australia Cloud: `https://app4.securiti.ai`
  - UAE Cloud: `https://app5.securiti.ai`
  - India Cloud: `https://app6.securiti.ai`
  - EU cloud: `https://app.eu.securiti.ai`
  - KSA cloud: `https://app7.securiti.ai`
  - Qatar Cloud: `https://app8.securiti.ai`
  - Sovereign deployment: Consult the administrator of your Sovereign deployment
  - For the US cloud:

| URL | Purpose |
| --- | --- |
| app.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| packages.securiti.ai, port 443 | It is the CDN for downloading the Securiti pod bundles. When you mark **Download from CDN** during Pods VM installation, it utilises this CDN URL. |
| prod-us-west-2-starport-layer-bucket.s3.us-west-2.amazonaws.com, port 443 | It is the URL for Pod's auto-updating and upgrading. |
| privaci-registry.s3.us-west-2.amazonaws.com, port 443 | It is the URL of an AWS S3 bucket used for storing metadata and logs. |
| securiti-state-718391394098.s3.us-west-2.amazonaws.com, port 443 | It is the default Securiti storage for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. The application only uses this storage when you have not configured Private Cloud Storage (PCS). For configuring PCS, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |
| d31wfa8az5rt1f.cloudfront.net | It is also the CDN URL for downloading the Pods VM bundle for installation. |
  - For the US1 cloud:

| URL | Purpose |
| --- | --- |
| app1.securiti.ai, port 443 | It is the main host URL of Securiti application of the specified region. |
| packages.securiti.ai, port 443 | It is the CDN for downloading the Securiti pod bundles. When you mark **Download from CDN** during Pods VM installation, it utilises this CDN URL. |
| storage.googleapis.com, port 443 | It is the URL that refers to the storage bucket of the cloud application. |
  - For the Canada cloud:

| URL | Purpose |
| --- | --- |
| app3.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| packages.securiti.ai, port 443 | Securiti CDN for appliance bundle download |
| prod-ca-central-1-starport-layer-bucket.s3.ca-central-1.amazonaws.com, port 443 | It is the URL for Pod's auto-updating and upgrading. |
| privaci-montreal-registry.s3.ca-central-1.amazonaws.com, port 443 | It is the URL of an AWS S3 bucket used for storing metadata and logs. |
| securiti-montreal-state-718391394098.s3.ca-central-1.amazonaws.com, port 443 | It is the default Securiti storage for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. The application only uses this storage when you have not configured Private Cloud Storage (PCS). For configuring PCS, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |
| d1wxubre8y9029.cloudfront.net | It is also the CDN URL for downloading the Pods VM bundle for installation. |
  - For the EU cloud:

| URL | Purpose |
| --- | --- |
| app.eu.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| packages.securiti.ai, port 443 | It is the CDN for downloading the Securiti pod bundles. When you mark **Download from CDN** during Pods VM installation, it utilizes this CDN URL. |
| prod-eu-west-1-starport-layer-bucket.s3.eu-west-1.amazonaws.com, port 443 | It is the URL for Pod's auto-updating and upgrading. |
| privaci-eu-registry.s3.eu-west-1.amazonaws.com, port 443 | It is the URL of an AWS S3 bucket used for storing metadata and logs. |
| securiti-eu-state-718391394098.s3.eu-west-1.amazonaws.com | It is the default Securiti storage for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. The application only uses this storage when you have not configured Private Cloud Storage (PCS). For configuring PCS, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |
| d17vfm9hd4ph8q.cloudfront.net | It is also the CDN URL for downloading the Pods VM bundle for installation. |
  - For the Indonesia cloud:

| URL | Purpose |
| --- | --- |
| app2.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| packages2.securiti.ai, port 443 | It is the CDN for downloading the Securiti pod bundles. When you mark **Download from CDN** during Pods VM installation, it utilises this CDN URL. |
| prod-ap-southeast-3-starport-layer-bucket.s3.ap-southeast-3.amazonaws.com, port 443 | It is the URL for Pod's auto-updating and upgrading. |
| privaci-jakarta-registry.s3.ap-southeast-3.amazonaws.com, port 443 | It is the URL of an AWS S3 bucket used for storing metadata and logs. |
| securiti-jakata-state-718391394098.s3.ap-southeast-3.amazonaws.com, port 443 | It is the default Securiti storage for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. The application only uses this storage when you have not configured Private Cloud Storage (PCS). For configuring PCS, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |
| d2nhybc0go9etk.cloudfront.net | It is also the CDN URL for downloading the Pods VM bundle for installation. |
  - For the Australia cloud:

| URL | Purpose |
| --- | --- |
| app4.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| packages4.securiti.ai, port 443 | It is the CDN for downloading the Securiti pod bundles. When you mark **Download from CDN** during Pods VM installation, it utilises this CDN URL. |
| prod-ap-southeast-2-starport-layer-bucket.s3.ap-southeast-2.amazonaws.com, port 443 | It is the URL for Pod's auto-updating and upgrading. |
| privaci-sydney-registry.s3.ap-southeast-2.amazonaws.com, port 443 | It is the URL of an AWS S3 bucket used for storing metadata and logs. |
| securiti-sydney-state-718391394098.s3.ap-southeast-2.amazonaws.com, port 443 | It is the default Securiti storage for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. The application only uses this storage when you have not configured Private Cloud Storage (PCS). For configuring PCS, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |
| d2ukknqt0z03bc.cloudfront.net | It is also the CDN URL for downloading the Pods VM bundle for installation. |
  - For the UAE cloud:

| URL | Purpose |
| --- | --- |
| app5.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| packages5.securiti.ai, port 443 | It is the CDN for downloading the Securiti pod bundles. When you mark **Download from CDN** during Pods VM installation, it utilises this CDN URL. |
| prod-me-central-1-starport-layer-bucket.s3.me-central-1.amazonaws.com, port 443 | It is the URL for Pod's auto-updating and upgrading. |
| privaci-uae-registry.s3.me-central-1.amazonaws.com, port 443 | It is the URL of an AWS S3 bucket used for storing metadata and logs. |
| securiti-uae-state-718391394098.s3.me-central-1.amazonaws.com, port 443 | It is the default Securiti storage for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. The application only uses this storage when you have not configured Private Cloud Storage (PCS). For configuring PCS, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |
| d1k2hmyn0i0qdq.cloudfront.net | It is also the CDN URL for downloading the Pods VM bundle for installation. |
  - For the India cloud:

| URL | Purpose |
| --- | --- |
| app6.securiti.ai | It is the host URL of the Securiti application within the defined region. |
| packages6.securiti.ai or https://d3fa0fvq9m4urk.cloudfront.net | It is the CDN for downloading the Securiti pod bundles. When you mark **Download from CDN** during Pods VM installation, it utilizes this CDN URL. |
| prod-ap-south-1-starport-layer-bucket.s3.ap-south-1.amazonaws.com | It is the URL for Pod's auto-updating and upgrading. |
| privaci-mumbai-registry.s3.ap-south-1.amazonaws.com/ | It is the URL of an AWS S3 bucket used for storing metadata and logs. |
| securiti-mumbai-state-718391394098.s3.ap-south-1.amazonaws.com | It is the default Securiti storage for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. The application only uses this storage when you have not configured Private Cloud Storage (PCS). For configuring PCS, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |
| dhth5mgsbl3e0.cloudfront.net | It is also the CDN URL for downloading the Pods VM bundle for installation. |
  - For the KSA cloud:

| URL | Purpose |
| --- | --- |
| app7.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| packages7.securiti.ai, port 443 or https://d1hbu0o5tcqqm5.cloudfront.net | It is the CDN for downloading the Securiti pod bundles. When you mark **Download from CDN** during Pods VM installation, it utilises this CDN URL. |
| storage.googleapis.com, port 443 | It is the URL for storing the states on the cloud. |
| me-central2-docker.pkg.dev | It is the URL for Pod's auto-updating and upgrading. |
| https://storage.cloud.google.com/securiti-artifacts-402060762925 | It is the URL of an AWS S3 bucket used for storing metadata and logs. |
| https://storage.cloud.google.com/securiti-state-419004438835 | It is the default Securiti storage for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. The application only uses this storage when you have not configured Private Cloud Storage (PCS). For configuring PCS, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |
  - For the Qatar cloud

| URL | Purpose |
| --- | --- |
| app8.securiti.ai, port 443 | It is the host URL of the Securiti application within the defined region. |
| packages8.securiti.ai, port 443 or https://dxjj2az777ndh.cloudfront.net | It is the CDN for downloading the Securiti pod bundles. When you mark **Download from CDN** during Pods VM installation, it utilises this CDN URL. |
| me-central1-docker.pkg.dev | It is the URL for Pod's auto-updating and upgrading. |
| https://storage.cloud.google.com/securiti-artifacts-818816799760 | It is the URL of an AWS S3 bucket used for storing metadata and logs. |
| https://storage.cloud.google.com/securiti-state-818816799760 | It is the default Securiti storage for storing Assessment attachments, DSR attachments, evidence files produced by discovery scans, etc. The application only uses this storage when you have not configured Private Cloud Storage (PCS). For configuring PCS, see [Private Cloud Storage](/latest/docs/private-cloud-storage). |
- Pods only initiate outbound connections to Securiti. Securiti does not initiate inbound traffic to the pod. If your firewall restricts outbound traffic by IP address instead of URL, allowlist the fixed or static IP addresses in the table below.

> [!NOTE]
> Note
> 
> You do not need to allowlist Securiti NAT IP addresses for pod operations. You only need them when Securiti cloud accesses your resources directly, for example with [Private Cloud Storage](/latest/docs/private-cloud-storage) or [SaaS data system connector](/latest/docs/data-systems-connector).

### Allowlisting Fixed or static IP addresses

| Production instance | Endpoint | IP address |
| --- | --- | --- |
| US Cloud | - `app.securiti.ai` - `dbaas.securiti.ai` | - `3.33.255.181` - `15.197.226.17` |
| `edc.app.securiti.ai` | - `99.83.154.190` - `75.2.75.41` |
| `wf-mt.app.securiti.ai` | - `99.83.192.141` - `13.248.185.49` |
| EU Cloud | - `app.eu.securiti.ai` - `dbaas.eu.securiti.ai` | - `13.248.146.34` - `76.223.10.152` |
| `edc.app.eu.securiti.ai` | - `13.248.157.18` - `76.223.17.131` |
| `wf-mt.app.eu.securiti.ai` | - `3.33.157.145` - `13.248.203.29` |
| US GCP Cloud | - `app1.securiti.ai` - `dbaas1.securiti.ai` | `130.211.15.136` |
| `wf-mt.app1.securiti.ai` | `34.117.180.251` |
| `edc.app1.securiti.ai` | `34.149.178.111` |
| Indonesia Cloud (Jakarta) | - `app2.securiti.ai` - `dbaas2.securiti.ai` | - `15.197.177.4` - `99.83.174.152` |
| `edc.app2.securiti.ai` | - `75.2.80.61` - `35.71.139.160` |
| `wf-mt.app2.securiti.ai` | - `75.2.24.0` - `35.71.162.135` |
| Canada Cloud (Montreal) | - `app3.securiti.ai` - `dbaas3.securiti.ai` | - `3.33.247.163` - `15.197.223.53` |
| `edc.app3.securiti.ai` | - `13.248.237.13` - `99.83.252.143` |
| `wf-mt.app3.securiti.ai` | - `75.2.30.3` - `99.83.173.145` |
| Australia Cloud (Sydney) | - `app4.securiti.ai` - `dbaas4.securiti.ai` | - `75.2.95.27` - `99.83.242.162` |
| `edc.app4.securiti.ai` | - `13.248.177.10` - `99.83.131.159` |
| `wf-mt.app4.securiti.ai` | - `52.223.22.58` - `99.83.129.186` |
| United Arab Emirates (UAE) Cloud | - `app5.securiti.ai` - `dbaas5securiti.ai` | - `75.2.112.22` - `76.223.121.184` |
| `edc.app5.securiti.ai` | - `13.248.249.42` - `76.223.78.161` |
| `wf-mt.app5.securiti.ai` | - `99.83.204.142` - `52.223.10.36` |
| India Cloud (Mumbai) | - `app6.securiti.ai` - `dbaas6.securiti.ai` | - `75.2.73.43` - `99.83.227.174` |
| `edc.app6.securiti.ai` | - `99.83.199.138` - `75.2.111.48` |
| `wf-mt.app6.securiti.ai` | - `99.83.153.136` - `15.197.164.36` |
| Kingdom of Saudi Arabia (KSA) Cloud | `app7.securiti.ai` | - `34.54.157.214` |
| State of Qatar Cloud | `app8.securiti.ai` `http://dbaas8.securiti.ai/` | - `34.54.165.185` |
| `app8.securiti.ai` | - `34.8.52.253` |
- The following ports on the machine or VM where you install the pod must be open within your network, and must not be used by any other service. However, pods use them only for intra-pod and intra-node communication, so they do not have to be open to the internet.

> [!NOTE]
> **Note**
> 
> These ports need to be exposed within the nodes running the pods, and they do not need to be exposed to any other external network. Securiti pods do not require any incoming network function. For single node pod clusters, the ports are not required to be exposed outside the node.

| Port | Protocol | Description |
| --- | --- | --- |
| 53 | TCP and UDP | Internal cluster DNS |
| 5000, 5001, 9100 | HTTPS | Docker registry |
| 6443 | HTTPS | Pod container API server |
| 8472 | VXLAN (UDP encapsulation) | Overlay network: used for internode communication within the cluster |
| 10001-10005 | TCP | Internal cluster ports for future use |
| 10248 - 10250, 10255 | HTTPS | Pod container components |
| 30000 - 32767 | HTTPS (depends on the services deployed) | Pod container internal services range |
| 31000, 31001 | HTTPS | Ranger API Server ports |
| 51820, 51821 | UDP | Required only for Flannel Wireguard with IPv4 |
| 8092 | HTTPS | Used by HTML converter |
| 4222, 4223 | TCP | Used by the NATS server for internal message communication |
| 9000 | HTTPS | Used by MinIO for S3 compatible object storage |
| 8443 | HTTPS | Used for inter-pod communication within the cluster |
| 80 | HTTP | Used for inter-pod communication within the cluster |
| 21433 | HTTPS | Used for secure inter-pod communication within the cluster |

After ensuring that your system meets these requirements, proceed to [Pod installation (cluster version v1.28+)](/v1/docs/pod-installation-cluster-version-v128).

## Related

- [Using the pre-flight diagnostic script (cluster version v1.28+)](/pods-using-the-pre-flight-diagnostic-script.md)
- [Pod quick install guides cluster version v1.28](/pod-quick-install-guides-cluster-version-v128-en.md)
- [Pod custom installation guides (cluster version v1.28+)](/podcustom-installation-guides.md)
