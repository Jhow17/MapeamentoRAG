---
title: "Pods release notes"
slug: "pods-release-notes"
updated: 2026-09-21T21:00:01Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/pods-release-notes"
area: platform
modulo: pods
tipo: release
data_captura: 2026-10-08
---

# Pods release notes

## 1.151

### Release updates - September 2026

#### Introducing version selection for installing EPods V2

Securiti has introduced version selection in the Elastic Pods (EPods) V2 installation and upgrade process. This helps you complete change-control approvals, private registry image staging, and upgrade planning without restarting the process when a new patch release becomes available. You can now select a specific published release instead of always using the latest version. You can select a version later than your existing one, including patch releases. When you select a version, EPods V2 uses the same version for all installation artifacts, including container images, the Helm chart, and the installation command.

For more information, see [EPod V2 installation](/latest/docs/epod-v2-installation).

#### Security, confidentiality, and availability updates

Securiti has fixed the following critical, high, medium, and low severity CVEs in the 1.151 release of pod software (with cluster version v1.28 or later).

| Vulnerability ID | Severity |
| --- | --- |
| GHSA-5cc2-282f-jjq2 | Critical |
| [CVE-2026-15925](https://nvd.nist.gov/vuln/detail/CVE-2026-15925) | Critical |
| [CVE-2024-10979](https://nvd.nist.gov/vuln/detail/CVE-2024-10979) | High |
| [CVE-2024-7348](https://nvd.nist.gov/vuln/detail/CVE-2024-7348) | High |
| [CVE-2025-1094](https://nvd.nist.gov/vuln/detail/CVE-2025-1094) | High |
| [CVE-2026-39821](https://nvd.nist.gov/vuln/detail/CVE-2026-39821) | High |
| [CVE-2026-42151](https://nvd.nist.gov/vuln/detail/CVE-2026-42151) | High |
| [CVE-2026-42154](https://nvd.nist.gov/vuln/detail/CVE-2026-42154) | High |
| [CVE-2026-55677](https://nvd.nist.gov/vuln/detail/CVE-2026-55677) | High |
| [CVE-2026-56852](https://nvd.nist.gov/vuln/detail/CVE-2026-56852) | High |
| GHSA-6pjx-3pjc-mrj8 | High |
| GHSA-8g6f-qw9x-4q6q | High |
| GHSA-8rm2-7qqf-34qm | High |
| GHSA-9gm5-9rfh-m6vx | High |
| GHSA-f4v5-65jj-pcr2 | High |
| GHSA-ffg3-p8fm-mjx2 | High |
| GHSA-hp3v-5vw7-fx9w | High |
| GHSA-mrg3-qvqr-jw29 | High |
| GHSA-vfp3-v2gw-7wfq | High |
| GHSA-wg65-39gg-5wfj | High |
| GHSA-xrqw-3rrv-vx5w | High |
| [CVE-2024-10976](https://nvd.nist.gov/vuln/detail/CVE-2024-10976) | High |
| [CVE-2024-10977](https://nvd.nist.gov/vuln/detail/CVE-2024-10977) | High |
| [CVE-2024-10978](https://nvd.nist.gov/vuln/detail/CVE-2024-10978) | High |
| [CVE-2024-10979](https://nvd.nist.gov/vuln/detail/CVE-2024-10979) | High |
| [CVE-2024-4317](https://nvd.nist.gov/vuln/detail/CVE-2024-4317) | High |
| [CVE-2024-7348](https://nvd.nist.gov/vuln/detail/CVE-2024-7348) | High |
| [CVE-2025-1094](https://nvd.nist.gov/vuln/detail/CVE-2025-1094) | High |
| [CVE-2026-10051](https://nvd.nist.gov/vuln/detail/CVE-2026-10051) | High |
| [CVE-2026-15736](https://nvd.nist.gov/vuln/detail/CVE-2026-15736) | High |
| [CVE-2026-41178](https://nvd.nist.gov/vuln/detail/CVE-2026-41178) | High |
| [CVE-2026-41608](https://nvd.nist.gov/vuln/detail/CVE-2026-41608) | High |
| [CVE-2026-42151](https://nvd.nist.gov/vuln/detail/CVE-2026-42151) | High |
| [CVE-2026-42154](https://nvd.nist.gov/vuln/detail/CVE-2026-42154) | High |
| [CVE-2026-50219](https://nvd.nist.gov/vuln/detail/CVE-2026-50219) | High |
| [CVE-2026-55677](https://nvd.nist.gov/vuln/detail/CVE-2026-55677) | High |
| [CVE-2026-55830](https://nvd.nist.gov/vuln/detail/CVE-2026-55830) | High |
| [CVE-2026-56131](https://nvd.nist.gov/vuln/detail/CVE-2026-56131) | High |
| [CVE-2026-56132](https://nvd.nist.gov/vuln/detail/CVE-2026-56132) | High |
| [CVE-2026-56403](https://nvd.nist.gov/vuln/detail/CVE-2026-56403) | High |
| [CVE-2026-56404](https://nvd.nist.gov/vuln/detail/CVE-2026-56404) | High |
| [CVE-2026-56405](https://nvd.nist.gov/vuln/detail/CVE-2026-56405) | High |
| [CVE-2026-56406](https://nvd.nist.gov/vuln/detail/CVE-2026-56406) | High |
| [CVE-2026-56407](https://nvd.nist.gov/vuln/detail/CVE-2026-56407) | High |
| [CVE-2026-56408](https://nvd.nist.gov/vuln/detail/CVE-2026-56408) | High |
| [CVE-2026-56409](https://nvd.nist.gov/vuln/detail/CVE-2026-56409) | High |
| [CVE-2026-56410](https://nvd.nist.gov/vuln/detail/CVE-2026-56410) | High |
| [CVE-2026-56411](https://nvd.nist.gov/vuln/detail/CVE-2026-56411) | High |
| [CVE-2026-56412](https://nvd.nist.gov/vuln/detail/CVE-2026-56412) | High |
| [CVE-2026-7210](https://nvd.nist.gov/vuln/detail/CVE-2026-7210) | High |
| [CVE-2026-76825](https://nvd.nist.gov/vuln/detail/CVE-2026-76825) | High |
| [CVE-2026-9856](https://nvd.nist.gov/vuln/detail/CVE-2026-9856) | High |
| [CVE-2024-10976](https://nvd.nist.gov/vuln/detail/CVE-2024-10976) | Medium |
| [CVE-2024-10978](https://nvd.nist.gov/vuln/detail/CVE-2024-10978) | Medium |
| [CVE-2024-4317](https://nvd.nist.gov/vuln/detail/CVE-2024-4317) | Medium |
| [CVE-2026-41178](https://nvd.nist.gov/vuln/detail/CVE-2026-41178) | Medium |
| [CVE-2026-50219](https://nvd.nist.gov/vuln/detail/CVE-2026-50219) | Medium |
| [CVE-2026-56131](https://nvd.nist.gov/vuln/detail/CVE-2026-56131) | Medium |
| [CVE-2026-56132](https://nvd.nist.gov/vuln/detail/CVE-2026-56132) | Medium |
| [CVE-2026-56403](https://nvd.nist.gov/vuln/detail/CVE-2026-56403) | Medium |
| [CVE-2026-56404](https://nvd.nist.gov/vuln/detail/CVE-2026-56404) | Medium |
| [CVE-2026-56405](https://nvd.nist.gov/vuln/detail/CVE-2026-56405) | Medium |
| [CVE-2026-56406](https://nvd.nist.gov/vuln/detail/CVE-2026-56406) | Medium |
| [CVE-2026-56407](https://nvd.nist.gov/vuln/detail/CVE-2026-56407) | Medium |
| [CVE-2026-56408](https://nvd.nist.gov/vuln/detail/CVE-2026-56408) | Medium |
| [CVE-2026-56409](https://nvd.nist.gov/vuln/detail/CVE-2026-56409) | Medium |
| [CVE-2026-56410](https://nvd.nist.gov/vuln/detail/CVE-2026-56410) | Medium |
| [CVE-2026-56411](https://nvd.nist.gov/vuln/detail/CVE-2026-56411) | Medium |
| [CVE-2026-56412](https://nvd.nist.gov/vuln/detail/CVE-2026-56412) | Medium |
| [CVE-2026-6791](https://nvd.nist.gov/vuln/detail/CVE-2026-6791) | Medium |
| GHSA-23w6-3w8w-8484 | Medium |
| GHSA-4xgf-cpjx-pc3j | Medium |
| GHSA-5wrp-cwcj-q835 | Medium |
| GHSA-6hr6-w5qg-qmwg | Medium |
| GHSA-763m-79hh-57f2 | Medium |
| GHSA-gcjh-h69q-9w9g | Medium |
| GHSA-gr75-jv2w-4656 | Medium |
| GHSA-hwrj-9rr4-24xh | Medium |
| GHSA-jp53-mhqp-8xcg | Medium |
| GHSA-rrmf-rvhw-rf47 | Medium |
| GHSA-w7x5-g22v-xqhr | Medium |
| GO-2026-5158 | Medium |
| [CVE-2025-3000](https://nvd.nist.gov/vuln/detail/CVE-2025-3000) | Medium |
| [CVE-2026-55443](https://nvd.nist.gov/vuln/detail/CVE-2026-55443) | Medium |
| [CVE-2026-66053](https://nvd.nist.gov/vuln/detail/CVE-2026-66053) | Medium |
| [CVE-2026-6790](https://nvd.nist.gov/vuln/detail/CVE-2026-6790) | Medium |
| [CVE-2026-6791](https://nvd.nist.gov/vuln/detail/CVE-2026-6791) | Medium |
| [CVE-2026-71554](https://nvd.nist.gov/vuln/detail/CVE-2026-71554) | Medium |
| [CVE-2026-8384](https://nvd.nist.gov/vuln/detail/CVE-2026-8384) | Medium |
| [CVE-2026-84309](https://nvd.nist.gov/vuln/detail/CVE-2026-84309) | Medium |
| [CVE-2026-84310](https://nvd.nist.gov/vuln/detail/CVE-2026-84310) | Medium |
| [CVE-2026-84311](https://nvd.nist.gov/vuln/detail/CVE-2026-84311) | Medium |
| GHSA-4xgf-cpjx-pc3j | Medium |
| [CVE-2024-10977](https://nvd.nist.gov/vuln/detail/CVE-2024-10977) | Low |

The following CVEs are currently open and will be fixed in future releases. See the exploitability explanations for each of them below.

| PackageName | Type | Vulnerability ID | Severity | Title | Compensating Control |
| --- | --- | --- | --- | --- | --- |
| curl | apk | [CVE-2026-19931](https://nvd.nist.gov/vuln/detail/CVE-2026-19931) | Critical | No description. | Pod software components do not invoke or execute curl command line binaries dynamically inside running system containers. |
| libcrypto3 | apk | [CVE-2026-63073](https://nvd.nist.gov/vuln/detail/CVE-2026-63073) | Critical | Issue summary: OpenSSL CMP response validation passed an unexpected response | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| curl | apk | [CVE-2026-18924](https://nvd.nist.gov/vuln/detail/CVE-2026-18924) | Critical | No description. | Pod software components do not invoke or execute curl command line binaries dynamically inside running system containers. |
| netty-codec-http | java-archive | GHSA-57rv-r2g8-2cj3 | Critical | Netty has HttpClientCodec response desynchronization | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| netty-codec-http | java-archive | GHSA-xxqh-mfjm-7mv9 | Critical | Netty HTTP/1.0 TE+CL Coexistence Bypasses Smuggling Sanitization | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| netty-handler | java-archive | GHSA-c4c3-7fpv-j4q5 | Critical | Netty: SNI Routing Bypass via Fragmented TLS ClientHello Causing Fallback to Default SslContext | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to manipulate TLS handshakes. |
| libcrypto3 | apk | [CVE-2026-75803](https://nvd.nist.gov/vuln/detail/CVE-2026-75803) | Critical | Issue summary: ChaCha20-Poly1305 and AES-OCB decryption with an empty | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| [github.com/rabbitmq/amqp091-go](http://github.com/rabbitmq/amqp091-go) | go-module | GHSA-c5pq-fr2g-9jpf | Critical | RabbitMQ amqp091-go: Protocol Desynchronization and Frame Injection via Integer Overflow in readLongstr | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| [github.com/rabbitmq/amqp091-go](http://github.com/rabbitmq/amqp091-go) | go-module | GHSA-j497-x9hr-x34x | Critical | RabbitMQ amqp091-go: Silent Data Truncation and State Corruption via Shortstr Integer Overflow | Pod software doesn't allow inbound communication initiated by external parties. Path logic routing values map strictly to pre-validated variables. |
| [github.com/rabbitmq/amqp091-go](http://github.com/rabbitmq/amqp091-go) | go-module | GHSA-33mj-cw25-m34h | Critical | RabbitMQ amqp091-go: Missing Explicit TLS Minimum Version Configuration In URI Parser | This vulnerability can be exploited only if Pod software is configured to interact with untrusted service endpoints that serve invalid matching certificates. |
| jetty-http | java-archive | GHSA-355h-qmc2-wpwf | Critical | Jetty has HTTP Request Smuggling via Chunked Extension Quoted-String Parsing | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| jetty-security | java-archive | GHSA-2fvj-hgj9-j2gr | Critical | Eclipse Jetty Digest Authentication: ISO-8859-1 lossy encoding allows authentication bypass via character substitution | This vulnerability can be exploited only if Pod software is configured to rely on Digest authentication mechanisms for external callers. |
| spark-4.0-scala-2.13 | apk | [CVE-2026-75595](https://nvd.nist.gov/vuln/detail/CVE-2026-75595) | Critical | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| nltk | python | GHSA-x99w-6fgc-pmfw | Critical | NLTK: Allowlisted pickle loaders still permit code execution in current source | Pod software does not fetch or execute unvalidated remote model code structures dynamically over public networks. |
| nltk | python | GHSA-m4rf-3fr8-xwx3 | Critical | NLTK: JVM argument injection bypass via per-call options in the NLTK Stanford wrappers (incomplete fix of CVE-2026-12841) | Pod software components do not ingest or execute dynamic unvalidated external process arguments inside running system containers. |
| libcrypto3 | apk | [CVE-2026-34182](https://nvd.nist.gov/vuln/detail/CVE-2026-34182) | Critical | No description. | This vulnerability can be exploited only if Pod software is configured to rely on unsigned or untrusted CMS messaging payloads from external actors. |
| [google.golang.org/grpc](http://google.golang.org/grpc) | go-module | GHSA-p77j-4mvh-x3m3 | Critical | gRPC-Go has an authorization bypass via missing leading slash in :path | Pod software doesn't allow inbound communication initiated by external parties. Path logic routing values map strictly to pre-validated variables. |
| ecdsa | python | GHSA-wj6h-64fc-37mp | High | Minerva timing attack on P-256 in python-ecdsa | This vulnerability can be exploited only if Pod software is configured to interact with untrusted services that make use of arbitrary certificate chains for SSL. |
| stdlib | go-module | [CVE-2026-46600](https://nvd.nist.gov/vuln/detail/CVE-2026-46600) | High | Parsing an invalid SVCB or HTTPS RR can panic when the size of a parameter value overflows the message buffer. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| [golang.org/x/crypto](http://golang.org/x/crypto) | go-module | GO-2026-6355 | High | Previously; after a channel has been established; a malicious peer could send crafted messages that would deadlock the entire connection. | Pod software doesn't allow inbound communication initiated by external parties; external untrusted connections are rejected. |
| [golang.org/x/crypto](http://golang.org/x/crypto) | go-module | GO-2026-6354 | High | Previously; a channel registered in the mux's chanList is not usable until it is established. A malicious peer was able flood the channel's incomingRe... | Pod software doesn't allow inbound communication initiated by external parties; external untrusted connections are rejected. |
| libcrypto3 | apk | [CVE-2026-18798](https://nvd.nist.gov/vuln/detail/CVE-2026-18798) | High | Issue summary: QUIC server may double free QRX (QUIC record layer RX) object | Pod software does not implement or expose OpenSSL QUIC server processing listeners to inbound external calls. |
| libcrypto3 | apk | [CVE-2026-63076](https://nvd.nist.gov/vuln/detail/CVE-2026-63076) | High | Issue summary: OpenSSL CMP password based protection verification only | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| netty-handler | java-archive | GHSA-3qp7-7mw8-wx86 | High | Netty has an IPv6 Subnet Filter Bypass via Incorrect Comparator Masking | Pod software network reachability parameters navigate only to explicit internal target networks via infrastructure firewall filtering. |
| netty-codec-http | java-archive | GHSA-f6hv-jmp6-3vwv | High | Netty: HttpContentDecompressor maxAllocation bypass when Content-Encoding set to br/zstd/snappy leads to decompression bomb DoS | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| libcrypto3 | apk | [CVE-2026-14457](https://nvd.nist.gov/vuln/detail/CVE-2026-14457) | High | Issue summary: In a server or client configuration with RFC7250 Raw Public Keys (RPKs) | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| curl | apk | [CVE-2026-80231](https://nvd.nist.gov/vuln/detail/CVE-2026-80231) | High | No description. | Pod software components do not invoke or execute curl command line binaries dynamically inside running system containers. |
| elasticsearch-9.4-config | apk | [CVE-2026-54513](https://nvd.nist.gov/vuln/detail/CVE-2026-54513) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| jackson-databind | java-archive | GHSA-rmj7-2vxq-3g9f | High | jackson-databind has an array subtype allowlist bypass in BasicPolymorphicTypeValidator (allowIfSubTypeIsArray) | This vulnerability can be exploited only if unauthorized access to the pod is obtained to inject dynamic serialized payload chains. |
| elasticsearch-9.4-config | apk | [CVE-2026-54512](https://nvd.nist.gov/vuln/detail/CVE-2026-54512) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| jackson-databind | java-archive | GHSA-j3rv-43j4-c7qm | High | jackson-databind has a PolymorphicTypeValidator bypass via generic type parameters that allows arbitrary class instantiation | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| curl | apk | [CVE-2026-80229](https://nvd.nist.gov/vuln/detail/CVE-2026-80229) | High | No description. | Pod software components do not invoke or execute curl command line binaries dynamically inside running system containers. |
| elasticsearch-9.4-config | apk | [CVE-2026-54399](https://nvd.nist.gov/vuln/detail/CVE-2026-54399) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-9.4-config | apk | [CVE-2026-54428](https://nvd.nist.gov/vuln/detail/CVE-2026-54428) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| netty-handler | java-archive | GHSA-x4gw-5cx5-pgmh | High | Netty: SNI handler pre-allocates up to 16 MiB from nine attacker bytes | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to manipulate TLS handshakes. |
| log4j-core | java-archive | GHSA-3pxv-7cmr-fjr4 | High | Apache Log4j Core: Silent log event loss in XmlLayout due to unescaped XML 1.0 forbidden characters | Pod software processes run inside isolated, sandboxed namespaces; system log metrics are streamed securely to internal monitoring aggregators. |
| libcrypto3 | apk | [CVE-2026-14456](https://nvd.nist.gov/vuln/detail/CVE-2026-14456) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-63072](https://nvd.nist.gov/vuln/detail/CVE-2026-63072) | High | Issue summary: OpenSSL CMS decryption sizes the key-unwrap output buffer based | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| netty-codec-http | java-archive | GHSA-jppx-w49h-x2qq | High | Netty: [SpdyHttpDecoder] ByteBuf Reference Leak on RST_STREAM Leads to Native Memory Exhaustion | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| curl | apk | [CVE-2026-13608](https://nvd.nist.gov/vuln/detail/CVE-2026-13608) | High | No description. | Pod software components do not invoke or execute curl command line binaries dynamically inside running system containers. |
| elasticsearch-9.4-config | apk | [CVE-2026-56745](https://nvd.nist.gov/vuln/detail/CVE-2026-56745) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| curl | apk | [CVE-2026-80230](https://nvd.nist.gov/vuln/detail/CVE-2026-80230) | High | No description. | Pod software components do not invoke or execute curl command line binaries dynamically inside running system containers. |
| curl | apk | [CVE-2026-82209](https://nvd.nist.gov/vuln/detail/CVE-2026-82209) | High | No description. | Pod software components do not invoke or execute curl command line binaries dynamically inside running system containers. |
| libcrypto3 | apk | [CVE-2026-54874](https://nvd.nist.gov/vuln/detail/CVE-2026-54874) | High | Issue summary: Receiving a DTLS record for a future epoch while a handshake | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-63075](https://nvd.nist.gov/vuln/detail/CVE-2026-63075) | High | Issue summary: When OpenSSL processes QUIC traffic from a peer that repeatedly | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| zlib | apk | [CVE-2026-85091](https://nvd.nist.gov/vuln/detail/CVE-2026-85091) | High |  | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| netty-codec | java-archive | GHSA-mj4r-2hfc-f8p6 | High | Netty Lz4FrameDecoder is vulnerable to resource exhaustion | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| netty-handler | java-archive | GHSA-c653-97m9-rcg9 | High | Netty: Wrapping plain trust manager silently disables hostname verification | This vulnerability can be exploited only if Pod software is configured to interact with untrusted service endpoints that serve invalid matching certificates. |
| elasticsearch-9.4-config | apk | [CVE-2026-56819](https://nvd.nist.gov/vuln/detail/CVE-2026-56819) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-9.4-config | apk | [CVE-2026-55831](https://nvd.nist.gov/vuln/detail/CVE-2026-55831) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| netty-codec-http | java-archive | GHSA-6jqx-86gh-f27w | High | Netty SPDY SETTINGS frame count materializes unbounded settings map | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| curl | apk | [CVE-2026-82208](https://nvd.nist.gov/vuln/detail/CVE-2026-82208) | High | No description. | Pod software components do not invoke or execute curl command line binaries dynamically inside running system containers. |
| log4j-1.2-api | java-archive | GHSA-h383-gmxw-35v2 | High | Apache Log4j 1 to Log4j 2 bridge: silent log event loss in Log4j1XmlLayout due to unescaped XML 1.0 forbidden characters | Pod software processes run inside isolated, sandboxed namespaces; system log metrics are streamed securely to internal monitoring aggregators. |
| elasticsearch-9.4-config | apk | [CVE-2026-55833](https://nvd.nist.gov/vuln/detail/CVE-2026-55833) | High | v | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| netty-codec-http | java-archive | GHSA-mvh2-crg5-v77c | High | Netty SPDY zlib header block continues decoded expansion after maxHeaderSize truncation | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| busybox | apk | [CVE-2026-38754](https://nvd.nist.gov/vuln/detail/CVE-2026-38754) | High | No description. | Pod software components do not invoke or execute busybox command line binaries dynamically inside running system containers. |
| wget | apk | [CVE-2026-58469](https://nvd.nist.gov/vuln/detail/CVE-2026-58469) | High | No description. | Pod software components do not invoke or execute wget command line binaries dynamically inside running system containers. |
| busybox | apk | [CVE-2026-38755](https://nvd.nist.gov/vuln/detail/CVE-2026-38755) | High | No description. | Pod software components do not invoke or execute busybox command line binaries dynamically inside running system containers. |
| busybox | apk | [CVE-2026-38752](https://nvd.nist.gov/vuln/detail/CVE-2026-38752) | High | No description. | Pod software components do not invoke or execute busybox command line binaries dynamically inside running system containers. |
| elasticsearch-9.4-config | apk | [CVE-2026-59899](https://nvd.nist.gov/vuln/detail/CVE-2026-59899) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| netty-codec | java-archive | GHSA-558v-64gr-wgg4 | High | Netty: [Bzip2Decoder] Infinite Loop in RLE State Machine Leads to Event-Loop Thread Hang | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| netty-handler | java-archive | GHSA-fccg-mwvh-qqg4 | High | Netty: Fragmented ClientHello records trigger quadratic pre-handshake reassembly in default SNI parsing | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to manipulate TLS handshakes. |
| netty-codec-http | java-archive | GHSA-q4f6-jm68-57ww | High | Netty: [HttpContentEncoder] Unbounded Per-Connection Queue Growth via HTTP/1.1 Pipelining Leads to Denial of Service | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to trigger processing delays. |
| elasticsearch-9.4-config | apk | [CVE-2026-59901](https://nvd.nist.gov/vuln/detail/CVE-2026-59901) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| libcrypto3 | apk | [CVE-2026-54876](https://nvd.nist.gov/vuln/detail/CVE-2026-54876) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| elasticsearch-9.4-config | apk | [CVE-2026-59898](https://nvd.nist.gov/vuln/detail/CVE-2026-59898) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| busybox | apk | [CVE-2026-38753](https://nvd.nist.gov/vuln/detail/CVE-2026-38753) | High | No description. | Pod software components do not invoke or execute busybox command line binaries dynamically inside running system containers. |
| wget | apk | [CVE-2026-58471](https://nvd.nist.gov/vuln/detail/CVE-2026-58471) | High | No description. | Pod software components do not invoke or execute wget command line binaries dynamically inside running system containers. |
| wget | apk | [CVE-2026-58472](https://nvd.nist.gov/vuln/detail/CVE-2026-58472) | High | No description. | Pod software components do not invoke or execute wget command line binaries dynamically inside running system containers. |
| netty-codec-http | java-archive | GHSA-38f8-5428-x5cv | High | Netty vulnerable to HTTP Request Smuggling due to malformed Transfer-Encoding | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| netty-codec-http | java-archive | GHSA-4mp9-239f-g9hg | High | Netty: WebSockets V07/V08 handshaker missing Connection/Upgrade validation | Pod software doesn't allow inbound communication initiated by external parties; external untrusted connections are rejected. |
| elasticsearch | java-archive | GHSA-m9gh-789g-q5pv | High | Elasticsearch PKI Realm Authentication Bypass Vulnerability Allows User Impersonation Through Crafted Client Certificates | This vulnerability can be exploited only if unauthorized access to alter internal PKI validation profile parameters is achieved. |
| jackson-core | java-archive | GHSA-r7wm-3cxj-wff9 | High | jackson-core: Async parser maxNumberLength bypass via chunked digit accumulation (incomplete fix for GHSA-72hv-8253-57qq) | Pod software retries scanning on a malicious JSON tree string a couple of times and moves on; container memory limits insulate the platform host environment. |
| elasticsearch-9.4-config | apk | GHSA-93wv-jw9v-4972 | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-9.4-config | apk | GHSA-hf6x-8p5f-cgmf | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-9.4-config | apk | GHSA-v3jc-474w-2wm6 | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| mc | apk | [CVE-2026-84445](https://nvd.nist.gov/vuln/detail/CVE-2026-84445) | High | No description. | Pod software components do not invoke or execute mc command line binaries dynamically inside running system containers. |
| [google.golang.org/grpc](http://google.golang.org/grpc) | go-module | GHSA-2v4p-qf9q-27wj | High | gRPC-Go xDS servers: Denial of Service (DoS) via crash due to missing `:authority` and `Host` headers | Pod software doesn't allow inbound communication initiated by external parties. Internal targets map exclusively to trusted host tracking environments. |
| [github.com/apache/thrift](http://github.com/apache/thrift) | go-module | GHSA-8wv5-x4w7-5gww | High | Apache Thrift Python; Go; PHP and Java bindings have an Infinite Loop | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| minio | apk | [CVE-2026-43871](https://nvd.nist.gov/vuln/detail/CVE-2026-43871) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| [github.com/rabbitmq/amqp091-go](http://github.com/rabbitmq/amqp091-go) | go-module | GHSA-r9c8-gcjp-xfwh | High | RabbitMQ amqp091-go: Resource Exhaustion (OOM) via Unbounded Body Buffer Allocation | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| [github.com/rabbitmq/amqp091-go](http://github.com/rabbitmq/amqp091-go) | go-module | GHSA-xwwf-m8fg-p9q2 | High | RabbitMQ amqp091-go: Denial of Service via Sub-Spec Frame Size Negotiation | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| [github.com/rabbitmq/amqp091-go](http://github.com/rabbitmq/amqp091-go) | go-module | GHSA-4v58-74mf-rjx3 | High | RabbitMQ amqp091-go: Denial of Service via Malicious Field Length in AMQP Client | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| [google.golang.org/grpc](http://google.golang.org/grpc) | go-module | GHSA-vp52-pcj8-j9qc | High | gRPC-Go: Heap Memory Exhaustion (OOM) via HTTP/2 DATA Frame Fragmentation | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| mc | apk | [CVE-2026-84304](https://nvd.nist.gov/vuln/detail/CVE-2026-84304) | High | No description. | Pod software components do not invoke or execute mc command line binaries dynamically inside running system containers. |
| [github.com/rabbitmq/amqp091-go](http://github.com/rabbitmq/amqp091-go) | go-module | GHSA-rm6m-hrcw-jw33 | High | RabbitMQ amqp091-go: Consumer Message Flooding via Signed-to-Unsigned Integer Casting in Qos Configuration | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to trigger processing delays. |
| minio | apk | [CVE-2026-56855](https://nvd.nist.gov/vuln/detail/CVE-2026-56855) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| [github.com/rabbitmq/amqp091-go](http://github.com/rabbitmq/amqp091-go) | go-module | GHSA-6c5v-hqjr-5xxp | High | amqp091-go has a Potential Memory Exhaustion/Protocol Violation via Broker-Controlled Oversized Payload | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| minio | apk | [CVE-2026-79921](https://nvd.nist.gov/vuln/detail/CVE-2026-79921) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| [golang.org/x/crypto](http://golang.org/x/crypto) | go-module | GO-2026-6303 | High | The source-address critical option in the Permissions returned by an authentication callback was only enforced for the PublicKeyCallback and VerifiedP... | Pod software network reachability parameters navigate only to explicit internal target networks via infrastructure firewall filtering. |
| minio | apk | [CVE-2026-56854](https://nvd.nist.gov/vuln/detail/CVE-2026-56854) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| minio | apk | [CVE-2026-78662](https://nvd.nist.gov/vuln/detail/CVE-2026-78662) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| [github.com/rabbitmq/amqp091-go](http://github.com/rabbitmq/amqp091-go) | go-module | GHSA-27gv-rfvv-22mv | High | RabbitMQ amqp091-go: Plaintext Credential Exposure via Exported PLAIN Authentication Struct Fields | Pod software processes run inside isolated, sandboxed namespaces; system log metrics are streamed securely to internal monitoring aggregators. |
| [github.com/rabbitmq/amqp091-go](http://github.com/rabbitmq/amqp091-go) | go-module | GHSA-465g-fh3v-9jw4 | High | RabbitMQ amqp091-go: Connection Configuration Overwrite via Unsanitized TLS Path Parameter Injection | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| stdlib | go-module | GO-2026-5026 | High | The ToASCII and ToUnicode functions incorrectly accept Punycode-encoded labels that decode to an ASCII-only label. For example; ToUnicode('xn--example... | Pod software components run as a non-root system identity configuration; there is no path for execution parsing to alter parent namespace privileges. |
| stdlib | go-module | [CVE-2026-33818](https://nvd.nist.gov/vuln/detail/CVE-2026-33818) | High | Enforce a recursion limit in Unmarshal to prevent stack exhaustion when parsing deeply-nested; recursive structures. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| stdlib | go-module | [CVE-2026-56853](https://nvd.nist.gov/vuln/detail/CVE-2026-56853) | High | When a server is configured to support unencrypted HTTP/2; it reads a few bytes from each new connection to see if they contain the HTTP/2 client pref... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| stdlib | go-module | GO-2026-5972 | High | Enforce a recursion limit in Unmarshal to prevent stack exhaustion when parsing deeply-nested; recursive structures. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| stdlib | go-module | GO-2026-6089 | High | When a server is configured to support unencrypted HTTP/2; it reads a few bytes from each new connection to see if they contain the HTTP/2 client pref... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| stdlib | go-module | [CVE-2026-56859](https://nvd.nist.gov/vuln/detail/CVE-2026-56859) | High | Previously; DecodeElement would reset the depth counter causing it to never fire; this could lead to stack exhaustion. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| stdlib | go-module | [CVE-2026-56862](https://nvd.nist.gov/vuln/detail/CVE-2026-56862) | High | Handshake messages; such as KeyUpdate; are always considered as state-advancing; regardless of whether a handshake has been completed or not. As a res... | Pod software doesn't allow inbound communication initiated by external parties; external untrusted TLS handshakes are rejected. |
| stdlib | go-module | GO-2026-6088 | High | Previously; DecodeElement would reset the depth counter causing it to never fire; this could lead to stack exhaustion. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| stdlib | go-module | GO-2026-6090 | High | Handshake messages; such as KeyUpdate; are always considered as state-advancing; regardless of whether a handshake has been completed or not. As a res... | Pod software doesn't allow inbound communication initiated by external parties; external untrusted TLS handshakes are rejected. |
| stdlib | go-module | [CVE-2026-56864](https://nvd.nist.gov/vuln/detail/CVE-2026-56864) | High | A malicious GOSUMDB was capable of serving arbitrary module content not contained within the transparency log. This attack allows for a coordinating G... | Pod software components do not ingest or install dynamic dependencies or modules inside running system containers. |
| stdlib | go-module | [CVE-2026-56865](https://nvd.nist.gov/vuln/detail/CVE-2026-56865) | High | A malicious GOPROXY was previously capable of forging up to two sumdb tiles that allow for a requested module to bypass the GOSUMDB check and persist ... | Pod software components do not ingest or install dynamic dependencies or modules inside running system containers. |
| python-3.14 | apk | [CVE-2026-15308](https://nvd.nist.gov/vuln/detail/CVE-2026-15308) | High | No description. | Pod software does not execute or evaluate untrusted compression extraction archives natively within public directory runtimes. |
| libthrift | java-archive | GHSA-7pwc-h2j2-rjgj | High | Apache Thrift has an Improper Validation of Certificate with Host Mismatch Vulnerability | This vulnerability can be exploited only if Pod software is configured to interact with untrusted service endpoints that serve invalid matching certificates. |
| jline-remote-telnet | java-archive | GHSA-2r2c-cx56-8933 | High | JLine3 Telnet server: Unauthenticated Remote DoS via Unbounded Telnet NAWS Terminal Geometry | Pod software does not deploy or activate unauthenticated Telnet servers inside active runtime perimeters. |
| jline-remote-telnet | java-archive | GHSA-47qp-hqvx-6r3f | High | JLine3 Telnet server: Unauthenticated Remote Memory Exhaustion via Unbounded Telnet NEW-ENVIRON Variables | Pod software does not expose Telnet server interfaces to external public access profiles. |
| spark-4.0-scala-2.13 | apk | [CVE-2026-75596](https://nvd.nist.gov/vuln/detail/CVE-2026-75596) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| nltk | python | GHSA-8mgp-746c-j5xp | High | NLTK: Model-artifact APIs bypass pathsec and touch files outside allowed roots | This vulnerability can be exploited only if unauthorized access to the pod is obtained to map or deploy local malicious file paths. |
| jupyter-server | python | GHSA-c3mw-737p-c7g2 | High | Jupyter Server: 5xx request logging leaks token-bearing Referer header values | Pod software processes run inside isolated, sandboxed namespaces; system log metrics are streamed securely to internal monitoring aggregators. |
| nltk | python | GHSA-5gh2-94qg-qppq | High | NLTK AllowlistUnpickler dotted-name validation bypass allows remote code execution | Pod software does not fetch or execute unvalidated remote model code structures dynamically over public networks. |
| python-3.10 | apk | [CVE-2026-4224](https://nvd.nist.gov/vuln/detail/CVE-2026-4224) | High | No description. | Pod software retries scanning on a malicious XML file a couple of times and moves on; The processes will restart and pick up remaining work. |
| python-3.10 | apk | [CVE-2026-7210](https://nvd.nist.gov/vuln/detail/CVE-2026-7210) | High | `xml.parsers.expat` and `xml.etree.ElementTree` use insufficient entropy for Expat hash-flooding protection; which allows a crafted XML document to tr... | Pod software retries scanning on a malicious XML file a couple of times and moves on; The processes will restart and pick up remaining work. |
| nltk | python | GHSA-f833-7jw8-xwrv | High | NLTK: Symlink-based sandbox bypass in FramenetCorpusReader (bypasses the fix for CVE-2026-54292) | This vulnerability can be exploited only if unauthorized access to the pod is obtained to map or deploy local malicious symlinks. |
| nltk | python | GHSA-qx2g-xrx7-vfh8 | High | NLTK TweetTokenizer vulnerable to denial of service through catastrophic regex backtracking | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| python-3.10 | apk | [CVE-2026-3644](https://nvd.nist.gov/vuln/detail/CVE-2026-3644) | High | No description. | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| starlette | python | GHSA-82w8-qh3p-5jfq | High | Starlette: request.form() limits silently ignored for application/x-www-form-urlencoded enable DoS | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to send form floods. |
| starlette | python | GHSA-wqp7-x3pw-xc5r | High | Starlette: SSRF and NTLM credential theft via UNC paths in StaticFiles on Windows | Pod software runs on an isolated Linux container platform. Windows-specific UNC handling paths are not applicable. |
| nltk | python | GHSA-p4rw-rvv2-7xwr | High | NLTK: Corpus readers follow symlinks outside trusted roots despite pathsec enforcement | This vulnerability can be exploited only if unauthorized access to the pod is obtained to map or deploy local malicious symlinks. |
| nltk | python | GHSA-97qj-x29f-37w7 | High | NLTK: Entity-expansion DoS (billion laughs) via remaining raw ElementTree parses | Pod software retries scanning on a malicious XML file a couple of times and moves on; The processes will restart and pick up remaining work. |
| nltk | python | GHSA-ww6m-cw3f-q94g | High | NLTK: Quadratic-time DoS in PorterStemmer via long runs of 'y' | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| nltk | python | GHSA-w3v8-gmh9-3wv7 | High | NLTK: ReDoS in nltk.tgrep via unvalidated user-supplied regular expressions | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| nltk | python | GHSA-6ww7-3frv-cqxh | High | NLTK: pathsec SSRF protection can be bypassed when a proxy is configured | Pod software network reachability parameters navigate only to explicit internal target networks via infrastructure firewall filtering. |
| nltk | python | GHSA-3gq4-3j92-5w49 | High | NLTK: Corpus Reader Sandbox Bypass | This vulnerability can be exploited only if unauthorized access to the pod is obtained to map or deploy local malicious symlinks. |
| nltk | python | GHSA-6hwm-xvph-95vm | High | NLTK: Uncontrolled search path when invoking the Graphviz 'dot' binary | Pod software components do not invoke or execute Graphviz command line binaries dynamically inside running system containers. |
| libcrypto3 | apk | [CVE-2026-45447](https://nvd.nist.gov/vuln/detail/CVE-2026-45447) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-42764](https://nvd.nist.gov/vuln/detail/CVE-2026-42764) | High | No description. | Pod software does not implement or expose OpenSSL QUIC server processing listeners to inbound external calls. |
| libcrypto3 | apk | [CVE-2026-34183](https://nvd.nist.gov/vuln/detail/CVE-2026-34183) | High | No description. | Pod software does not implement or rely on the vulnerable OpenSSL QUIC stack elements for external routing protocols. |
| libcrypto3 | apk | [CVE-2026-34180](https://nvd.nist.gov/vuln/detail/CVE-2026-34180) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-7383](https://nvd.nist.gov/vuln/detail/CVE-2026-7383) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | [CVE-2026-33811](https://nvd.nist.gov/vuln/detail/CVE-2026-33811) | High | When using LookupCNAME with the cgo DNS resolver; a very long CNAME response can trigger a double-free of C memory and a crash. | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | GO-2026-4981 | High | When using LookupCNAME with the cgo DNS resolver; a very long CNAME response can trigger a double-free of C memory and a crash. | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | [CVE-2026-42499](https://nvd.nist.gov/vuln/detail/CVE-2026-42499) | High | Pathological inputs could cause DoS through consumePhrase when parsing an email address according to RFC 5322. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | GO-2026-4977 | High | Pathological inputs could cause DoS through consumePhrase when parsing an email address according to RFC 5322. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | [CVE-2026-39820](https://nvd.nist.gov/vuln/detail/CVE-2026-39820) | High | Well-crafted inputs reaching ParseAddress; ParseAddressList; and ParseDate were able to trigger excessive CPU exhaustion and memory allocations. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| stdlib | go-module | GO-2026-4986 | High | Well-crafted inputs reaching ParseAddress; ParseAddressList; and ParseDate were able to trigger excessive CPU exhaustion and memory allocations. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| [golang.org/x/net](http://golang.org/x/net) | go-module | GO-2026-4918 | High | When processing HTTP/2 SETTINGS frames; transport will enter an infinite loop of writing CONTINUATION frames if it receives a SETTINGS_MAX_FRAME_SIZE ... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| stdlib | go-module | [CVE-2026-33814](https://nvd.nist.gov/vuln/detail/CVE-2026-33814) | High | When processing HTTP/2 SETTINGS frames; transport will enter an infinite loop of writing CONTINUATION frames if it receives a SETTINGS_MAX_FRAME_SIZE ... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| libcrypto3 | apk | [CVE-2026-9076](https://nvd.nist.gov/vuln/detail/CVE-2026-9076) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| jq | apk | [CVE-2026-32316](https://nvd.nist.gov/vuln/detail/CVE-2026-32316) | High | No description. | Pod software components do not invoke or execute jq command line binaries dynamically inside running system containers. |
| libcrypto3 | apk | [CVE-2026-45445](https://nvd.nist.gov/vuln/detail/CVE-2026-45445) | High | No description. | Pod software does not use the specific cryptographic OCB block cipher mode pathways inside application implementations. |
| stdlib | go-module | GO-2026-5037 | High | (*x509.Certificate).VerifyHostname previously called matchHostnames in a loop over all DNS Subject Alternative Name (SAN) entries. This caused strings... | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | [CVE-2026-39836](https://nvd.nist.gov/vuln/detail/CVE-2026-39836) | High | The Dial and LookupPort functions panic on Windows when provided with an input containing a NUL (0). | Pod software runs on an isolated Linux container platform. Windows-specific operating system APIs are not applicable. |
| stdlib | go-module | GO-2026-4971 | High | The Dial and LookupPort functions panic on Windows when provided with an input containing a NUL (0). | Pod software runs on an isolated Linux container platform. Windows-specific operating system APIs are not applicable. |
| stdlib | go-module | [CVE-2026-27145](https://nvd.nist.gov/vuln/detail/CVE-2026-27145) | High | (*x509.Certificate).VerifyHostname previously called matchHostnames in a loop over all DNS Subject Alternative Name (SAN) entries. This caused strings... | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | [CVE-2026-42504](https://nvd.nist.gov/vuln/detail/CVE-2026-42504) | High | Decoding a maliciously-crafted MIME header containing many invalid encoded-words can consume excessive CPU. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | GO-2026-5038 | High | Decoding a maliciously-crafted MIME header containing many invalid encoded-words can consume excessive CPU. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| [golang.org/x/net](http://golang.org/x/net) | go-module | GO-2026-5942 | High | Parsing an invalid SVCB or HTTPS RR can panic when the size of a parameter value overflows the message buffer. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| [golang.org/x/text](http://golang.org/x/text) | go-module | GO-2026-5970 | High | A norm.Iter can enter an infinite loop when handling input containing invalid UTF-8 bytes. | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| jq | apk | [CVE-2026-40164](https://nvd.nist.gov/vuln/detail/CVE-2026-40164) | High | No description. | Pod software components do not invoke or execute jq command line binaries dynamically inside running system containers. |
| stdlib | go-module | [CVE-2026-39822](https://nvd.nist.gov/vuln/detail/CVE-2026-39822) | High | On Unix systems; opening a file in an os.Root improperly follows symlinks to locations outside of the Root when the final path component of the a path... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to map or deploy local malicious symlinks. |
| stdlib | go-module | GO-2026-4970 | High | On Unix systems; opening a file in an os.Root improperly follows symlinks to locations outside of the Root when the final path component of the a path... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to map or deploy local malicious symlinks. |
| libcrypto3 | apk | [CVE-2026-34181](https://nvd.nist.gov/vuln/detail/CVE-2026-34181) | High | No description. | This vulnerability can be exploited only if Pod software handles untrusted, externally-supplied PKCS#12 configuration profiles. |
| stdlib | go-module | [CVE-2026-42501](https://nvd.nist.gov/vuln/detail/CVE-2026-42501) | High | A malicious module proxy can exploit a flaw in the go command's validation of module checksums to bypass checksum database validation. This vulnerabil... | Pod software components do not ingest or install dynamic dependencies or modules inside running system containers. |
| pcre2 | apk | [CVE-2026-89157](https://nvd.nist.gov/vuln/detail/CVE-2026-89157) | High | PCRE2 before 10.48; on 32-bit platforms; has a pcre2_pattern_convert out-of-bounds write when an attacker can provide a large pattern. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| jq | apk | [CVE-2026-49839](https://nvd.nist.gov/vuln/detail/CVE-2026-49839) | High | No description. | Pod software components do not invoke or execute jq command line binaries dynamically inside running system containers. |
| pcre2 | apk | [CVE-2026-89161](https://nvd.nist.gov/vuln/detail/CVE-2026-89161) | High | In PCRE2 before 10.48; pcre2_jit_match mishandles a previously copied subject being passed in as a context. An incorrect free operation can occur. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| [google.golang.org/grpc](http://google.golang.org/grpc) | go-module | GHSA-hrxh-6v49-42gf | High | gRPC-Go: xDS RBAC and HTTP/2 Vulnerabilities | Pod software doesn't allow inbound communication initiated by external parties. Internal targets map exclusively to trusted host tracking environments. |

---

## 1.150

### Release updates - August 2026

#### Introducing warning banner for Pod v1.28+ hardware misconfiguration

Securiti has introduced a security warning for under-provisioned nodes on the Pods page. If a node's CPU, memory, or disk does not meet the recommended baseline, a warning icon appears with that node to highlight the issue. It also provides an advisory banner that appears with the main pod. This enhancement helps administrators quickly identify resource gaps and take corrective action before the pod impacts workload performance or stability.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5YD5YGN0.png)

For more information, see [Pod installation (cluster version v1.28+)](/latest/docs/pod-installation-cluster-version-v128).

#### Upgrading Elasticsearch for Pods v1.28 and later

Securiti has upgraded internal Elasticsearch (ES) from version v7 to v8 for Pods (v1.28 and later), as v7 has reached its end of life. You must upgrade your Pods to the latest version to receive ES v8. You might need to pause in-progress connector scans, depending on the scan type, because the process affects running scans.

> [!WARNING]
> Important
> 
> - For your running Data Inventory Syncs and Data Subject Rights (DSR) scans, you must pause or finish them before upgrading.
> - For running Discovery Scans, Securiti automatically pauses them before the upgrade and resumes afterward.
> - You might see this update in this release or in a subsequent release.

For more information, see [Updating pod software (cluster version v1.28+)](/latest/docs/pod-updating-pod-software).

#### Security, confidentiality, and availability updates

Securiti has fixed the following critical, high, medium, and low severity CVEs in the 1.150 release of pod software (with cluster version v1.28 or later).

| Vulnerability ID | Severity |
| --- | --- |
| [CVE-2026-33322](https://nvd.nist.gov/vuln/detail/CVE-2026-33322) | Critical |
| GHSA-272m-gcwp-mpwg | Critical |
| GHSA-4qhr-g3c6-fcfx | Critical |
| GHSA-5cx5-wh4m-82fh | Critical |
| GHSA-5gwj-m78q-7pq3 | Critical |
| [CVE-2026-10050](https://nvd.nist.gov/vuln/detail/CVE-2026-10050) | Critical |
| [CVE-2026-11940](https://nvd.nist.gov/vuln/detail/CVE-2026-11940) | Critical |
| [CVE-2026-12481](https://nvd.nist.gov/vuln/detail/CVE-2026-12481) | Critical |
| [CVE-2026-33322](https://nvd.nist.gov/vuln/detail/CVE-2026-33322) | Critical |
| [CVE-2026-56817](https://nvd.nist.gov/vuln/detail/CVE-2026-56817) | Critical |
| [CVE-2026-56820](https://nvd.nist.gov/vuln/detail/CVE-2026-56820) | Critical |
| [CVE-2026-11940](https://nvd.nist.gov/vuln/detail/CVE-2026-11940) | High |
| [CVE-2026-11972](https://nvd.nist.gov/vuln/detail/CVE-2026-11972) | High |
| [CVE-2026-14662](https://nvd.nist.gov/vuln/detail/CVE-2026-14662) | High |
| [CVE-2026-14664](https://nvd.nist.gov/vuln/detail/CVE-2026-14664) | High |
| [CVE-2026-14668](https://nvd.nist.gov/vuln/detail/CVE-2026-14668) | High |
| [CVE-2026-14669](https://nvd.nist.gov/vuln/detail/CVE-2026-14669) | High |
| [CVE-2026-14670](https://nvd.nist.gov/vuln/detail/CVE-2026-14670) | High |
| [CVE-2026-14671](https://nvd.nist.gov/vuln/detail/CVE-2026-14671) | High |
| [CVE-2026-14677](https://nvd.nist.gov/vuln/detail/CVE-2026-14677) | High |
| [CVE-2026-14679](https://nvd.nist.gov/vuln/detail/CVE-2026-14679) | High |
| [CVE-2026-14680](https://nvd.nist.gov/vuln/detail/CVE-2026-14680) | High |
| [CVE-2026-15741](https://nvd.nist.gov/vuln/detail/CVE-2026-15741) | High |
| [CVE-2026-15742](https://nvd.nist.gov/vuln/detail/CVE-2026-15742) | High |
| [CVE-2026-16239](https://nvd.nist.gov/vuln/detail/CVE-2026-16239) | High |
| [CVE-2026-18408](https://nvd.nist.gov/vuln/detail/CVE-2026-18408) | High |
| [CVE-2026-19385](https://nvd.nist.gov/vuln/detail/CVE-2026-19385) | High |
| [CVE-2026-3298](https://nvd.nist.gov/vuln/detail/CVE-2026-3298) | High |
| [CVE-2026-39821](https://nvd.nist.gov/vuln/detail/CVE-2026-39821) | High |
| [CVE-2026-40344](https://nvd.nist.gov/vuln/detail/CVE-2026-40344) | High |
| [CVE-2026-42151](https://nvd.nist.gov/vuln/detail/CVE-2026-42151) | High |
| [CVE-2026-42154](https://nvd.nist.gov/vuln/detail/CVE-2026-42154) | High |
| [CVE-2026-42765](https://nvd.nist.gov/vuln/detail/CVE-2026-42765) | High |
| [CVE-2026-4786](https://nvd.nist.gov/vuln/detail/CVE-2026-4786) | High |
| [CVE-2026-56852](https://nvd.nist.gov/vuln/detail/CVE-2026-56852) | High |
| [CVE-2026-6100](https://nvd.nist.gov/vuln/detail/CVE-2026-6100) | High |
| [CVE-2026-6464](https://nvd.nist.gov/vuln/detail/CVE-2026-6464) | High |
| [CVE-2026-6471](https://nvd.nist.gov/vuln/detail/CVE-2026-6471) | High |
| [CVE-2026-73500](https://nvd.nist.gov/vuln/detail/CVE-2026-73500) | High |
| [CVE-2026-9669](https://nvd.nist.gov/vuln/detail/CVE-2026-9669) | High |
| GHSA-2qj4-mmr9-4v2f | High |
| GHSA-5rvq-cxj2-64vf | High |
| GHSA-6hm5-jgcp-p838 | High |
| GHSA-6vch-q96h-7gc3 | High |
| GHSA-8rm2-7qqf-34qm | High |
| GHSA-9c4q-hq6p-c237 | High |
| GHSA-f2ff-p2ww-7p4p | High |
| GHSA-f4xh-w4cj-qxq8 | High |
| GHSA-fg7f-2386-8897 | High |
| GHSA-g6cj-pr64-35w5 | High |
| GHSA-g7hg-vrcf-mvmr | High |
| GHSA-h84g-69h7-mw6v | High |
| GHSA-hpcc-26xq-25fv | High |
| GHSA-hqp4-2352-xf5r | High |
| GHSA-m42h-3232-vpv3 | High |
| GHSA-p4gq-832x-fm9v | High |
| GHSA-prg7-hcfm-mfcr | High |
| GHSA-pwgv-4x5q-6m9f | High |
| GHSA-q6cq-mhr2-jmr5 | High |
| GHSA-qvv7-cg9c-w4x3 | High |
| GHSA-rpj2-4hq8-938g | High |
| GHSA-v2w2-w228-c444 | High |
| GHSA-v74w-7mr3-4qg3 | High |
| GHSA-vhch-2wf3-m8rp | High |
| GHSA-wc96-39fc-566f | High |
| GHSA-wg65-39gg-5wfj | High |
| GHSA-xgmm-8j9v-c9wx | High |
| GHSA-xh95-f55m-82fw | High |
| GO-2026-6107 | High |
| GO-2026-6222 | High |
| [CVE-2026-0864](https://nvd.nist.gov/vuln/detail/CVE-2026-0864) | High |
| [CVE-2026-11816](https://nvd.nist.gov/vuln/detail/CVE-2026-11816) | High |
| [CVE-2026-11972](https://nvd.nist.gov/vuln/detail/CVE-2026-11972) | High |
| CVE-2026-12061 | High |
| CVE-2026-12072 | High |
| CVE-2026-12074 | High |
| CVE-2026-12075 | High |
| [CVE-2026-12484](https://nvd.nist.gov/vuln/detail/CVE-2026-12484) | High |
| [CVE-2026-2297](https://nvd.nist.gov/vuln/detail/CVE-2026-2297) | High |
| [CVE-2026-3276](https://nvd.nist.gov/vuln/detail/CVE-2026-3276) | High |
| [CVE-2026-40344](https://nvd.nist.gov/vuln/detail/CVE-2026-40344) | High |
| [CVE-2026-41178](https://nvd.nist.gov/vuln/detail/CVE-2026-41178) | High |
| [CVE-2026-42151](https://nvd.nist.gov/vuln/detail/CVE-2026-42151) | High |
| [CVE-2026-42154](https://nvd.nist.gov/vuln/detail/CVE-2026-42154) | High |
| [CVE-2026-42765](https://nvd.nist.gov/vuln/detail/CVE-2026-42765) | High |
| [CVE-2026-4360](https://nvd.nist.gov/vuln/detail/CVE-2026-4360) | High |
| [CVE-2026-44891](https://nvd.nist.gov/vuln/detail/CVE-2026-44891) | High |
| [CVE-2026-48526](https://nvd.nist.gov/vuln/detail/CVE-2026-48526) | High |
| [CVE-2026-53539](https://nvd.nist.gov/vuln/detail/CVE-2026-53539) | High |
| [CVE-2026-54284](https://nvd.nist.gov/vuln/detail/CVE-2026-54284) | High |
| [CVE-2026-54293](https://nvd.nist.gov/vuln/detail/CVE-2026-54293) | High |
| [CVE-2026-55153](https://nvd.nist.gov/vuln/detail/CVE-2026-55153) | High |
| [CVE-2026-55223](https://nvd.nist.gov/vuln/detail/CVE-2026-55223) | High |
| [CVE-2026-55851](https://nvd.nist.gov/vuln/detail/CVE-2026-55851) | High |
| [CVE-2026-56740](https://nvd.nist.gov/vuln/detail/CVE-2026-56740) | High |
| [CVE-2026-56741](https://nvd.nist.gov/vuln/detail/CVE-2026-56741) | High |
| [CVE-2026-56816](https://nvd.nist.gov/vuln/detail/CVE-2026-56816) | High |
| [CVE-2026-56818](https://nvd.nist.gov/vuln/detail/CVE-2026-56818) | High |
| [CVE-2026-56821](https://nvd.nist.gov/vuln/detail/CVE-2026-56821) | High |
| [CVE-2026-56822](https://nvd.nist.gov/vuln/detail/CVE-2026-56822) | High |
| [CVE-2026-59893](https://nvd.nist.gov/vuln/detail/CVE-2026-59893) | High |
| [CVE-2026-59902](https://nvd.nist.gov/vuln/detail/CVE-2026-59902) | High |
| [CVE-2026-69247](https://nvd.nist.gov/vuln/detail/CVE-2026-69247) | High |
| [CVE-2026-69249](https://nvd.nist.gov/vuln/detail/CVE-2026-69249) | High |
| [CVE-2026-71491](https://nvd.nist.gov/vuln/detail/CVE-2026-71491) | High |
| [CVE-2026-73500](https://nvd.nist.gov/vuln/detail/CVE-2026-73500) | High |
| [CVE-2026-73507](https://nvd.nist.gov/vuln/detail/CVE-2026-73507) | High |
| [CVE-2026-7774](https://nvd.nist.gov/vuln/detail/CVE-2026-7774) | High |
| [CVE-2026-9669](https://nvd.nist.gov/vuln/detail/CVE-2026-9669) | High |
| GHSA-f4xh-w4cj-qxq8 | High |
| GHSA-rpj2-4hq8-938g | High |
| [CVE-2026-0864](https://nvd.nist.gov/vuln/detail/CVE-2026-0864) | Medium |
| [CVE-2026-12003](https://nvd.nist.gov/vuln/detail/CVE-2026-12003) | Medium |
| [CVE-2026-14663](https://nvd.nist.gov/vuln/detail/CVE-2026-14663) | Medium |
| [CVE-2026-14666](https://nvd.nist.gov/vuln/detail/CVE-2026-14666) | Medium |
| [CVE-2026-14678](https://nvd.nist.gov/vuln/detail/CVE-2026-14678) | Medium |
| [CVE-2026-1502](https://nvd.nist.gov/vuln/detail/CVE-2026-1502) | Medium |
| [CVE-2026-18024](https://nvd.nist.gov/vuln/detail/CVE-2026-18024) | Medium |
| [CVE-2026-2297](https://nvd.nist.gov/vuln/detail/CVE-2026-2297) | Medium |
| [CVE-2026-3276](https://nvd.nist.gov/vuln/detail/CVE-2026-3276) | Medium |
| [CVE-2026-35188](https://nvd.nist.gov/vuln/detail/CVE-2026-35188) | Medium |
| [CVE-2026-41178](https://nvd.nist.gov/vuln/detail/CVE-2026-41178) | Medium |
| [CVE-2026-4360](https://nvd.nist.gov/vuln/detail/CVE-2026-4360) | Medium |
| [CVE-2026-6470](https://nvd.nist.gov/vuln/detail/CVE-2026-6470) | Medium |
| [CVE-2026-7774](https://nvd.nist.gov/vuln/detail/CVE-2026-7774) | Medium |
| [CVE-2026-8328](https://nvd.nist.gov/vuln/detail/CVE-2026-8328) | Medium |
| GHSA-26c4-7vv6-867j | Medium |
| GHSA-3496-9g83-7v6x | Medium |
| GHSA-3g8r-4pfx-jmfh | Medium |
| GHSA-3j69-69wj-xqx2 | Medium |
| GHSA-58hv-7753-xmfq | Medium |
| GHSA-5wrp-cwcj-q835 | Medium |
| GHSA-72hv-8253-57qq | Medium |
| GHSA-993g-76c3-p5m4 | Medium |
| GHSA-cp6g-7hqx-qxhp | Medium |
| GHSA-fp3f-mc75-235c | Medium |
| GHSA-fwg2-594c-jp42 | Medium |
| GHSA-gcjh-h69q-9w9g | Medium |
| GHSA-gh82-f9x8-5frx | Medium |
| GHSA-jq35-7prp-9v3f | Medium |
| GHSA-m8wh-29wm-52mv | Medium |
| GHSA-p9jm-q85p-7mcp | Medium |
| GHSA-vffw-93wf-4j4q | Medium |
| GHSA-w7vc-732c-9m39 | Medium |
| GHSA-wh89-7897-x99h | Medium |
| [CVE-2026-12479](https://nvd.nist.gov/vuln/detail/CVE-2026-12479) | Medium |
| [CVE-2026-12480](https://nvd.nist.gov/vuln/detail/CVE-2026-12480) | Medium |
| [CVE-2026-12482](https://nvd.nist.gov/vuln/detail/CVE-2026-12482) | Medium |
| [CVE-2026-2303](https://nvd.nist.gov/vuln/detail/CVE-2026-2303) | Medium |
| [CVE-2026-35188](https://nvd.nist.gov/vuln/detail/CVE-2026-35188) | Medium |
| [CVE-2026-48522](https://nvd.nist.gov/vuln/detail/CVE-2026-48522) | Medium |
| [CVE-2026-48523](https://nvd.nist.gov/vuln/detail/CVE-2026-48523) | Medium |
| [CVE-2026-48524](https://nvd.nist.gov/vuln/detail/CVE-2026-48524) | Medium |
| [CVE-2026-48525](https://nvd.nist.gov/vuln/detail/CVE-2026-48525) | Medium |
| [CVE-2026-53537](https://nvd.nist.gov/vuln/detail/CVE-2026-53537) | Medium |
| [CVE-2026-53538](https://nvd.nist.gov/vuln/detail/CVE-2026-53538) | Medium |
| [CVE-2026-54911](https://nvd.nist.gov/vuln/detail/CVE-2026-54911) | Medium |
| [CVE-2026-59894](https://nvd.nist.gov/vuln/detail/CVE-2026-59894) | Medium |
| [CVE-2026-59919](https://nvd.nist.gov/vuln/detail/CVE-2026-59919) | Medium |
| [CVE-2026-59920](https://nvd.nist.gov/vuln/detail/CVE-2026-59920) | Medium |
| [CVE-2026-69248](https://nvd.nist.gov/vuln/detail/CVE-2026-69248) | Medium |
| [CVE-2026-71852](https://nvd.nist.gov/vuln/detail/CVE-2026-71852) | Medium |
| [CVE-2026-71870](https://nvd.nist.gov/vuln/detail/CVE-2026-71870) | Medium |
| [CVE-2026-8328](https://nvd.nist.gov/vuln/detail/CVE-2026-8328) | Medium |
| [CVE-2026-9335](https://nvd.nist.gov/vuln/detail/CVE-2026-9335) | Medium |
| GHSA-72hv-8253-57qq | Medium |
| [CVE-2026-14673](https://nvd.nist.gov/vuln/detail/CVE-2026-14673) | Low |
| [CVE-2026-16241](https://nvd.nist.gov/vuln/detail/CVE-2026-16241) | Low |
| [CVE-2026-4519](https://nvd.nist.gov/vuln/detail/CVE-2026-4519) | Low |
| [CVE-2026-6469](https://nvd.nist.gov/vuln/detail/CVE-2026-6469) | Low |
| GHSA-6jv3-5f52-599m | Low |
| GHSA-fhv5-28vv-h8m8 | Low |
| GHSA-v9pg-7xvm-68hf | Low |
| [CVE-2026-18503](https://nvd.nist.gov/vuln/detail/CVE-2026-18503) | Low |
| [CVE-2026-53540](https://nvd.nist.gov/vuln/detail/CVE-2026-53540) | Low |

The following CVEs are currently open and will be fixed in future releases. See the exploitability explanations for each of them below.

| PackageName | Type | Vulnerability ID | Severity | Title | Compensating Control |
| --- | --- | --- | --- | --- | --- |
| netty-codec-http | java-archive | GHSA-57rv-r2g8-2cj3 | Critical | Netty has HttpClientCodec response desynchronization | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| netty-codec-http | java-archive | GHSA-xxqh-mfjm-7mv9 | Critical | Netty HTTP/1.0 TE+CL Coexistence Bypasses Smuggling Sanitization | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| jetty-http | java-archive | GHSA-355h-qmc2-wpwf | Critical | Jetty has HTTP Request Smuggling via Chunked Extension Quoted-String Parsing | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| jetty-security | java-archive | GHSA-2fvj-hgj9-j2gr | Critical | Eclipse Jetty Digest Authentication: ISO-8859-1 lossy encoding allows authentication bypass via character substitution | This vulnerability can be exploited only if Pod software is configured to rely on Digest authentication mechanisms for external callers. |
| libcrypto3 | apk | [CVE-2026-34182](https://nvd.nist.gov/vuln/detail/CVE-2026-34182) | Critical | No description. | This vulnerability can be exploited only if Pod software is configured to rely on unsigned or untrusted CMS messaging payloads from external actors. |
| [google.golang.org/grpc](http://google.golang.org/grpc) | go-module | GHSA-p77j-4mvh-x3m3 | Critical | gRPC-Go has an authorization bypass via missing leading slash in :path | Pod software doesn't allow inbound communication initiated by external parties. Path logic routing values map strictly to pre-validated variables. |
| ecdsa | python | GHSA-wj6h-64fc-37mp | High | Minerva timing attack on P-256 in python-ecdsa | This vulnerability can be exploited only if Pod software is configured to interact with untrusted services that make use of arbitrary certificate chains for SSL. |
| stdlib | go-module | GO-2026-5026 | High | The ToASCII and ToUnicode functions incorrectly accept Punycode-encoded labels that decode to an ASCII-only label. For example; ToUnicode('xn--example... | Pod software components run as a non-root system identity configuration; there is no path for execution parsing to alter parent namespace privileges. |
| stdlib | go-module | [CVE-2026-56853](https://nvd.nist.gov/vuln/detail/CVE-2026-56853) | High | When a server is configured to support unencrypted HTTP/2; it reads a few bytes from each new connection to see if they contain the HTTP/2 client pref... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| stdlib | go-module | GO-2026-6089 | High | When a server is configured to support unencrypted HTTP/2; it reads a few bytes from each new connection to see if they contain the HTTP/2 client pref... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| stdlib | go-module | [CVE-2026-33818](https://nvd.nist.gov/vuln/detail/CVE-2026-33818) | High | Enforce a recursion limit in Unmarshal to prevent stack exhaustion when parsing deeply-nested; recursive structures. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| stdlib | go-module | [CVE-2026-56859](https://nvd.nist.gov/vuln/detail/CVE-2026-56859) | High | Previously; DecodeElement would reset the depth counter causing it to never fire; this could lead to stack exhaustion. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| stdlib | go-module | [CVE-2026-56862](https://nvd.nist.gov/vuln/detail/CVE-2026-56862) | High | Handshake messages; such as KeyUpdate; are always considered as state-advancing; regardless of whether a handshake has been completed or not. As a res... | Pod software doesn't allow inbound communication initiated by external parties; external untrusted TLS handshakes are rejected. |
| stdlib | go-module | GO-2026-5972 | High | Enforce a recursion limit in Unmarshal to prevent stack exhaustion when parsing deeply-nested; recursive structures. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| stdlib | go-module | GO-2026-6088 | High | Previously; DecodeElement would reset the depth counter causing it to never fire; this could lead to stack exhaustion. | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| stdlib | go-module | GO-2026-6090 | High | Handshake messages; such as KeyUpdate; are always considered as state-advancing; regardless of whether a handshake has been completed or not. As a res... | Pod software doesn't allow inbound communication initiated by external parties; external untrusted TLS handshakes are rejected. |
| stdlib | go-module | [CVE-2026-46600](https://nvd.nist.gov/vuln/detail/CVE-2026-46600) | High | Parsing an invalid SVCB or HTTPS RR can panic when the size of a parameter value overflows the message buffer. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | [CVE-2026-56864](https://nvd.nist.gov/vuln/detail/CVE-2026-56864) | High | A malicious GOSUMDB was capable of serving arbitrary module content not contained within the transparency log. This attack allows for a coordinating G... | Pod software components do not ingest or install dynamic dependencies or modules inside running system containers. |
| stdlib | go-module | [CVE-2026-56865](https://nvd.nist.gov/vuln/detail/CVE-2026-56865) | High | A malicious GOPROXY was previously capable of forging up to two sumdb tiles that allow for a requested module to bypass the GOSUMDB check and persist ... | Pod software components do not ingest or install dynamic dependencies or modules inside running system containers. |
| netty-handler | java-archive | GHSA-3qp7-7mw8-wx86 | High | Netty has an IPv6 Subnet Filter Bypass via Incorrect Comparator Masking | Pod software network reachability parameters navigate only to explicit internal target networks via infrastructure firewall filtering. |
| netty-codec-http | java-archive | GHSA-f6hv-jmp6-3vwv | High | Netty: HttpContentDecompressor maxAllocation bypass when Content-Encoding set to br/zstd/snappy leads to decompression bomb DoS | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| elasticsearch-9.4-config | apk | [CVE-2026-54513](https://nvd.nist.gov/vuln/detail/CVE-2026-54513) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| jackson-databind | java-archive | GHSA-rmj7-2vxq-3g9f | High | jackson-databind has an array subtype allowlist bypass in BasicPolymorphicTypeValidator (allowIfSubTypeIsArray) | This vulnerability can be exploited only if unauthorized access to the pod is obtained to inject dynamic serialized payload chains. |
| elasticsearch-9.4-config | apk | [CVE-2026-54512](https://nvd.nist.gov/vuln/detail/CVE-2026-54512) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| jackson-databind | java-archive | GHSA-j3rv-43j4-c7qm | High | jackson-databind has a PolymorphicTypeValidator bypass via generic type parameters that allows arbitrary class instantiation | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-9.4-config | apk | [CVE-2026-54399](https://nvd.nist.gov/vuln/detail/CVE-2026-54399) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-9.4-config | apk | [CVE-2026-54428](https://nvd.nist.gov/vuln/detail/CVE-2026-54428) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| netty-handler | java-archive | GHSA-x4gw-5cx5-pgmh | High | Netty: SNI handler pre-allocates up to 16 MiB from nine attacker bytes | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to manipulate TLS handshakes. |
| log4j-core | java-archive | GHSA-3pxv-7cmr-fjr4 | High | Apache Log4j Core: Silent log event loss in XmlLayout due to unescaped XML 1.0 forbidden characters | Pod software processes run inside isolated, sandboxed namespaces; system log metrics are streamed securely to internal monitoring aggregators. |
| libcrypto3 | apk | [CVE-2026-14456](https://nvd.nist.gov/vuln/detail/CVE-2026-14456) | High |  | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| netty-codec-http | java-archive | GHSA-jppx-w49h-x2qq | High | Netty: [SpdyHttpDecoder] ByteBuf Reference Leak on RST_STREAM Leads to Native Memory Exhaustion | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| elasticsearch-9.4-config | apk | [CVE-2026-56745](https://nvd.nist.gov/vuln/detail/CVE-2026-56745) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| netty-codec | java-archive | GHSA-mj4r-2hfc-f8p6 | High | Netty Lz4FrameDecoder is vulnerable to resource exhaustion | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| netty-handler | java-archive | GHSA-c653-97m9-rcg9 | High | Netty: Wrapping plain trust manager silently disables hostname verification | This vulnerability can be exploited only if Pod software is configured to interact with untrusted service endpoints that serve invalid matching certificates. |
| elasticsearch-9.4-config | apk | [CVE-2026-56819](https://nvd.nist.gov/vuln/detail/CVE-2026-56819) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-9.4-config | apk | [CVE-2026-55831](https://nvd.nist.gov/vuln/detail/CVE-2026-55831) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| netty-codec-http | java-archive | GHSA-6jqx-86gh-f27w | High | Netty SPDY SETTINGS frame count materializes unbounded settings map | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| log4j-1.2-api | java-archive | GHSA-h383-gmxw-35v2 | High | Apache Log4j 1 to Log4j 2 bridge: silent log event loss in Log4j1XmlLayout due to unescaped XML 1.0 forbidden characters | Pod software processes run inside isolated, sandboxed namespaces; system log metrics are streamed securely to internal monitoring aggregators. |
| elasticsearch-9.4-config | apk | [CVE-2026-55833](https://nvd.nist.gov/vuln/detail/CVE-2026-55833) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| netty-codec-http | java-archive | GHSA-mvh2-crg5-v77c | High | Netty SPDY zlib header block continues decoded expansion after maxHeaderSize truncation | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| busybox | apk | [CVE-2026-38754](https://nvd.nist.gov/vuln/detail/CVE-2026-38754) | High | No description. | Pod software components do not invoke or execute busybox command line binaries dynamically inside running system containers. |
| wget | apk | [CVE-2026-58469](https://nvd.nist.gov/vuln/detail/CVE-2026-58469) | High | No description. | Pod software components do not invoke or execute wget command line binaries dynamically inside running system containers. |
| busybox | apk | [CVE-2026-38752](https://nvd.nist.gov/vuln/detail/CVE-2026-38752) | High | No description. | Pod software components do not invoke or execute busybox command line binaries dynamically inside running system containers. |
| busybox | apk | [CVE-2026-38755](https://nvd.nist.gov/vuln/detail/CVE-2026-38755) | High | No description. | Pod software components do not invoke or execute busybox command line binaries dynamically inside running system containers. |
| elasticsearch-9.4-config | apk | [CVE-2026-59899](https://nvd.nist.gov/vuln/detail/CVE-2026-59899) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| netty-codec | java-archive | GHSA-558v-64gr-wgg4 | High | Netty: [Bzip2Decoder] Infinite Loop in RLE State Machine Leads to Event-Loop Thread Hang | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| netty-codec-http | java-archive | GHSA-q4f6-jm68-57ww | High | Netty: [HttpContentEncoder] Unbounded Per-Connection Queue Growth via HTTP/1.1 Pipelining Leads to Denial of Service | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to trigger processing delays. |
| elasticsearch-9.4-config | apk | [CVE-2026-59901](https://nvd.nist.gov/vuln/detail/CVE-2026-59901) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| libcrypto3 | apk | [CVE-2026-54876](https://nvd.nist.gov/vuln/detail/CVE-2026-54876) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| elasticsearch-9.4-config | apk | [CVE-2026-59898](https://nvd.nist.gov/vuln/detail/CVE-2026-59898) | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| busybox | apk | [CVE-2026-38753](https://nvd.nist.gov/vuln/detail/CVE-2026-38753) | High | No description. | Pod software components do not invoke or execute busybox command line binaries dynamically inside running system containers. |
| wget | apk | [CVE-2026-58471](https://nvd.nist.gov/vuln/detail/CVE-2026-58471) | High | No description. | Pod software components do not invoke or execute wget command line binaries dynamically inside running system containers. |
| wget | apk | [CVE-2026-58472](https://nvd.nist.gov/vuln/detail/CVE-2026-58472) | High | No description. | Pod software components do not invoke or execute wget command line binaries dynamically inside running system containers. |
| netty-codec-http | java-archive | GHSA-38f8-5428-x5cv | High | Netty vulnerable to HTTP Request Smuggling due to malformed Transfer-Encoding | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| netty-codec-http | java-archive | GHSA-4mp9-239f-g9hg | High | Netty: WebSockets V07/V08 handshaker missing Connection/Upgrade validation | Pod software doesn't allow inbound communication initiated by external parties; external untrusted connections are rejected. |
| elasticsearch | java-archive | GHSA-m9gh-789g-q5pv | High | Elasticsearch PKI Realm Authentication Bypass Vulnerability Allows User Impersonation Through Crafted Client Certificates | This vulnerability can be exploited only if unauthorized access to alter internal PKI validation profile parameters is achieved. |
| jackson-core | java-archive | GHSA-r7wm-3cxj-wff9 | High | jackson-core: Async parser maxNumberLength bypass via chunked digit accumulation (incomplete fix for GHSA-72hv-8253-57qq) | Pod software retries scanning on a malicious JSON tree string a couple of times and moves on; container memory limits insulate the platform host environment. |
| elasticsearch-9.4-config | apk | GHSA-93wv-jw9v-4972 | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-9.4-config | apk | GHSA-hf6x-8p5f-cgmf | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-9.4-config | apk | GHSA-v3jc-474w-2wm6 | High | No description. | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-8.19 | apk | [CVE-2026-72642](https://nvd.nist.gov/vuln/detail/CVE-2026-72642) | High | The native inference process that Elasticsearch uses to evaluate uploaded machine learning models accepts a model operation that computes a memory add... | Pod software does not fetch or execute unvalidated remote model code structures dynamically over public networks. |
| [github.com/labstack/echo/v4](http://github.com/labstack/echo/v4) | go-module | GHSA-vfp3-v2gw-7wfq | High | Echo: Encoded slash (%2F) bypasses route-level protection and exposes static files | Pod software doesn't allow inbound communication initiated by external parties. Path logic routing values map strictly to pre-validated variables. |
| kube-metrics-adapter | apk | [CVE-2026-55677](https://nvd.nist.gov/vuln/detail/CVE-2026-55677) | High | No description. | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the endpoint. |
| stdlib | go-module | GO-2026-5942 | High | Parsing an invalid SVCB or HTTPS RR can panic when the size of a parameter value overflows the message buffer. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| python-3.14 | apk | [CVE-2026-15308](https://nvd.nist.gov/vuln/detail/CVE-2026-15308) | High | No description. | Pod software does not execute or evaluate untrusted compression extraction archives natively within public directory runtimes. |
| libthrift | java-archive | GHSA-7pwc-h2j2-rjgj | High | Apache Thrift has an Improper Validation of Certificate with Host Mismatch Vulnerability | This vulnerability can be exploited only if Pod software is configured to interact with untrusted service endpoints that serve invalid matching certificates. |
| jline-remote-telnet | java-archive | GHSA-2r2c-cx56-8933 | High | JLine3 Telnet server: Unauthenticated Remote DoS via Unbounded Telnet NAWS Terminal Geometry | Pod software does not deploy or activate unauthenticated Telnet servers inside active runtime perimeters. |
| jline-remote-telnet | java-archive | GHSA-47qp-hqvx-6r3f | High | JLine3 Telnet server: Unauthenticated Remote Memory Exhaustion via Unbounded Telnet NEW-ENVIRON Variables | Pod software does not expose Telnet server interfaces to external public access profiles. |
| python-3.11 | apk | [CVE-2026-7210](https://nvd.nist.gov/vuln/detail/CVE-2026-7210) | High | `xml.parsers.expat` and `xml.etree.ElementTree` use insufficient entropy for Expat hash-flooding protection; which allows a crafted XML document to tr... | Pod software retries scanning on a malicious XML file a couple of times and moves on; The processes will restart and pick up remaining work. |
| jetty-server | java-archive | GHSA-f4v5-65jj-pcr2 | High | Eclipse Jetty: Cross-Request Leakage for trailers on HTTP/1.1 keep-alive connections | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| postgresql | java-archive | GHSA-j92g-9f8w-j867 | High | PostgreSQL JDBC Driver: Silent channel-binding authentication downgrade via unsupported certificate algorithms | This vulnerability can be exploited only if Pod software is configured to interact with untrusted database services using fallback parameters. |
| [golang.org/x/text](http://golang.org/x/text) | go-module | GO-2026-5970 | High | A norm.Iter can enter an infinite loop when handling input containing invalid UTF-8 bytes. | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| [golang.org/x/mod](http://golang.org/x/mod) | go-module | GO-2026-6180 | High | A malicious GOSUMDB was capable of serving arbitrary module content not contained within the transparency log. | Pod software components do not ingest or install dynamic dependencies or modules inside running system containers. |
| go | binary | [CVE-2026-39822](https://nvd.nist.gov/vuln/detail/CVE-2026-39822) | High | On Unix systems; opening a file in an os.Root improperly follows symlinks to locations outside of the Root when the final path component of the a path... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to map or deploy local malicious symlinks. |
| stdlib | go-module | GO-2026-4970 | High | On Unix systems; opening a file in an os.Root improperly follows symlinks to locations outside of the Root when the final path component of the a path... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to map or deploy local malicious symlinks. |
| [golang.org/x/mod](http://golang.org/x/mod) | go-module | GO-2026-6179 | High | A malicious GOPROXY was previously capable of forging up to two sumdb tiles that allow for a requested module to bypass the GOSUMDB check and persist ... | Pod software components do not ingest or install dynamic dependencies or modules inside running system containers. |
| python-3.10 | apk | [CVE-2026-4224](https://nvd.nist.gov/vuln/detail/CVE-2026-4224) | High | When an Expat parser with a registered ElementDeclHandler parses an inline | Pod software retries scanning on a malicious XML file a couple of times and moves on; The processes will restart and pick up remaining work. |
| starlette | python | GHSA-82w8-qh3p-5jfq | High | Starlette: request.form() limits silently ignored for application/x-www-form-urlencoded enable DoS | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to send form floods. |
| python-3.10 | apk | [CVE-2026-3644](https://nvd.nist.gov/vuln/detail/CVE-2026-3644) | High | The fix for CVE-2026-0672; which rejected control characters in http.cookies.Morsel; was incomplete. The Morsel.update(); \|= operator; and unpickling ... | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| starlette | python | GHSA-wqp7-x3pw-xc5r | High | Starlette: SSRF and NTLM credential theft via UNC paths in StaticFiles on Windows | Pod software runs on an isolated Linux container platform. Windows-specific UNC handling paths are not applicable. |
| libcrypto3 | apk | [CVE-2026-45447](https://nvd.nist.gov/vuln/detail/CVE-2026-45447) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-18798](https://nvd.nist.gov/vuln/detail/CVE-2026-18798) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-63076](https://nvd.nist.gov/vuln/detail/CVE-2026-63076) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-42764](https://nvd.nist.gov/vuln/detail/CVE-2026-42764) | High | No description. | Pod software does not implement or expose OpenSSL QUIC server processing listeners to inbound external calls. |
| libcrypto3 | apk | [CVE-2026-34183](https://nvd.nist.gov/vuln/detail/CVE-2026-34183) | High | No description. | Pod software does not implement or rely on the vulnerable OpenSSL QUIC stack elements for external routing protocols. |
| libcrypto3 | apk | [CVE-2026-34180](https://nvd.nist.gov/vuln/detail/CVE-2026-34180) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-14457](https://nvd.nist.gov/vuln/detail/CVE-2026-14457) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-7383](https://nvd.nist.gov/vuln/detail/CVE-2026-7383) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | [CVE-2026-33811](https://nvd.nist.gov/vuln/detail/CVE-2026-33811) | High | When using LookupCNAME with the cgo DNS resolver; a very long CNAME response can trigger a double-free of C memory and a crash. | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | GO-2026-4981 | High | When using LookupCNAME with the cgo DNS resolver; a very long CNAME response can trigger a double-free of C memory and a crash. | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | [CVE-2026-42499](https://nvd.nist.gov/vuln/detail/CVE-2026-42499) | High | Pathological inputs could cause DoS through consumePhrase when parsing an email address according to RFC 5322. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | GO-2026-4977 | High | Pathological inputs could cause DoS through consumePhrase when parsing an email address according to RFC 5322. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | [CVE-2026-39820](https://nvd.nist.gov/vuln/detail/CVE-2026-39820) | High | Well-crafted inputs reaching ParseAddress; ParseAddressList; and ParseDate were able to trigger excessive CPU exhaustion and memory allocations. | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | GO-2026-4986 | High | Well-crafted inputs reaching ParseAddress; ParseAddressList; and ParseDate were able to trigger excessive CPU exhaustion and memory allocations. | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| [golang.org/x/net](http://golang.org/x/net) | go-module | GO-2026-4918 | High | When processing HTTP/2 SETTINGS frames; transport will enter an infinite loop of writing CONTINUATION frames if it receives a SETTINGS_MAX_FRAME_SIZE ... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| stdlib | go-module | [CVE-2026-33814](https://nvd.nist.gov/vuln/detail/CVE-2026-33814) | High | When processing HTTP/2 SETTINGS frames; transport will enter an infinite loop of writing CONTINUATION frames if it receives a SETTINGS_MAX_FRAME_SIZE ... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| libcrypto3 | apk | [CVE-2026-9076](https://nvd.nist.gov/vuln/detail/CVE-2026-9076) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-63072](https://nvd.nist.gov/vuln/detail/CVE-2026-63072) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-45445](https://nvd.nist.gov/vuln/detail/CVE-2026-45445) | High | No description. | Pod software does not use the specific cryptographic OCB block cipher mode pathways inside application implementations. |
| stdlib | go-module | GO-2026-5037 | High | (*x509.Certificate).VerifyHostname previously called matchHostnames in a loop over all DNS Subject Alternative Name (SAN) entries. This caused strings... | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | [CVE-2026-39836](https://nvd.nist.gov/vuln/detail/CVE-2026-39836) | High | The Dial and LookupPort functions panic on Windows when provided with an input containing a NUL (0). | Pod software runs on an isolated Linux container platform. Windows-specific operating system APIs are not applicable. |
| stdlib | go-module | GO-2026-4971 | High | The Dial and LookupPort functions panic on Windows when provided with an input containing a NUL (0). | Pod software runs on an isolated Linux container platform. Windows-specific operating system APIs are not applicable. |
| stdlib | go-module | [CVE-2026-27145](https://nvd.nist.gov/vuln/detail/CVE-2026-27145) | High | (*x509.Certificate).VerifyHostname previously called matchHostnames in a loop over all DNS Subject Alternative Name (SAN) entries. This caused strings... | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | [CVE-2026-42504](https://nvd.nist.gov/vuln/detail/CVE-2026-42504) | High | Decoding a maliciously-crafted MIME header containing many invalid encoded-words can consume excessive CPU. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | GO-2026-5038 | High | Decoding a maliciously-crafted MIME header containing many invalid encoded-words can consume excessive CPU. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-54874](https://nvd.nist.gov/vuln/detail/CVE-2026-54874) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-63075](https://nvd.nist.gov/vuln/detail/CVE-2026-63075) | High | No description. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | [CVE-2026-34181](https://nvd.nist.gov/vuln/detail/CVE-2026-34181) | High | No description. | This vulnerability can be exploited only if Pod software handles untrusted, externally-supplied PKCS#12 configuration profiles. |
| stdlib | go-module | [CVE-2026-42501](https://nvd.nist.gov/vuln/detail/CVE-2026-42501) | High | A malicious module proxy can exploit a flaw in the go command's validation of module checksums to bypass checksum database validation. This vulnerabil... | Pod software components do not ingest or install dynamic dependencies or modules inside running system containers. |
| [google.golang.org/grpc](http://google.golang.org/grpc) | go-module | GHSA-hrxh-6v49-42gf | High | gRPC-Go: xDS RBAC and HTTP/2 Vulnerabilities | Pod software doesn't allow inbound communication initiated by external parties. Internal targets map exclusively to trusted host tracking environments. |

---

## 1.149

### Patch 2 updates - August 2026

#### Resolved issue

- Fixed an issue where manual and airgap pod updates failed on deprecated operating system versions due to the Kubernetes cgroups v1 deprecation (PRIV-255781).

### Release updates - August 2026

#### Preventing failed cluster upgrades from unsupported OS versions

Securiti has introduced a warning of an unsupported operating system (OS) when there is a new Kubernetes cluster upgrade for Pods V1.28 and later. Securiti automatically disables auto-upgrades for your cluster, directing you to upgrade your OS before the cluster upgrade can proceed. This prevents cluster upgrades from failing on incompatible operating systems.

For more information, see [Upgrading Pods cluster version](/latest/docs/upgrading-pods-cluster-version).

#### Upgrading K3s cluster version

Securiti has upgraded its supported K3s cluster version from **v1.34.7** to **v1.35.6**, with an intermediate hop to v1.34.7. This update provides important security enhancements, performance improvements, and bug fixes to ensure greater stability and compliance for production workloads.

For more information, see [Upgrading Pods cluster version](/latest/docs/upgrading-pods-cluster-version).

#### Removing support for operating systems

Securiti has removed support for the following operating systems (OS) from Pods (cluster version v1.28 and later):

- Ubuntu 20.04
- Red Hat 8.x
- Amazon Linux 2

As Kubernetes v1.35 and later require Cgroup v2, and these OS support Cgroup v1, you must upgrade to the supported OS versions.

For more information, see [Pod prerequisites (cluster version v1.28+)](/latest/docs/pod-prerequisites-cluster-version-v128).

#### Known issue

- Upgrading EPod V2 on OpenShift from version **1.148** to **1.149** does not remove legacy SCC resources from an earlier installation in Elastic Pods (EPods) V2. The pods continue running on the old SCC without the `NET_BIND_SERVICE` security fix (PRIV-252610).

**Workaround**: You must remove the legacy SCC resources manually after the [upgrade](/latest/docs/upgrade-epod-v2#removing-legacy-scc-resources-on-openshift), as Securiti does not access your cluster.

#### Security, confidentiality, and availability updates

Securiti has fixed the following critical, high, medium, and low severity CVEs in the 1.149 release of pod software (with cluster version v1.28 or later).

| Vulnerability | Severity |
| --- | --- |
| CVE-2025-15467 | Critical |
| CVE-2025-22871 | Critical |
| CVE-2025-68121 | Critical |
| CVE-2026-10536 | Critical |
| CVE-2026-11564 | Critical |
| CVE-2026-11856 | Critical |
| CVE-2026-27143 | Critical |
| CVE-2026-31789 | Critical |
| CVE-2026-8924 | Critical |
| CVE-2026-8925 | Critical |
| CVE-2026-8926 | Critical |
| CVE-2026-8927 | Critical |
| CVE-2026-9079 | Critical |
| GO-2025-3563 | Critical |
| GO-2026-4337 | Critical |
| ALAS2023-2026-2003 | High |
| CVE-2025-26519 | High |
| CVE-2025-4674 | High |
| CVE-2025-47907 | High |
| CVE-2025-52999 | High |
| CVE-2025-58187 | High |
| CVE-2025-58188 | High |
| CVE-2025-61723 | High |
| CVE-2025-61725 | High |
| CVE-2025-61726 | High |
| CVE-2025-61729 | High |
| CVE-2025-61731 | High |
| CVE-2025-61732 | High |
| CVE-2025-69419 | High |
| CVE-2025-69420 | High |
| CVE-2025-69421 | High |
| CVE-2025-9230 | High |
| CVE-2026-11352 | High |
| CVE-2026-11586 | High |
| CVE-2026-12064 | High |
| CVE-2026-25679 | High |
| CVE-2026-27140 | High |
| CVE-2026-27144 | High |
| CVE-2026-28387 | High |
| CVE-2026-28388 | High |
| CVE-2026-28389 | High |
| CVE-2026-28390 | High |
| CVE-2026-31790 | High |
| CVE-2026-32280 | High |
| CVE-2026-32281 | High |
| CVE-2026-32283 | High |
| CVE-2026-40200 | High |
| CVE-2026-50193 | High |
| CVE-2026-54512 | High |
| CVE-2026-54513 | High |
| CVE-2026-8286 | High |
| CVE-2026-8932 | High |
| CVE-2026-9080 | High |
| CVE-2026-9545 | High |
| CVE-2026-9546 | High |
| CVE-2026-9547 | High |
| GHSA-3wrr-7qpf-2prh | High |
| GHSA-4gmw-gg2m-w46p | High |
| GHSA-537c-gmf6-5ccf | High |
| GHSA-55h5-xmcq-c37v | High |
| GHSA-58pv-8j8x-9vj2 | High |
| GHSA-5xf7-4p34-54qr | High |
| GHSA-8rrh-rw8j-w5fx | High |
| GHSA-9rj7-rf2p-w77r | High |
| GHSA-g867-7843-wf8q | High |
| GHSA-h46c-h94j-95f3 | High |
| GHSA-h69g-9hx6-f3v4 | High |
| GHSA-hmq2-w58f-27jc | High |
| GHSA-jm78-9fvv-mhgr | High |
| GHSA-jwv3-5hgf-82ww | High |
| GHSA-wvpp-8hx9-p66j | High |
| GO-2024-3333 | High |
| GO-2025-3849 | High |
| GO-2025-4006 | High |
| GO-2025-4007 | High |
| GO-2025-4009 | High |
| GO-2025-4013 | High |
| GO-2025-4155 | High |
| GO-2026-4341 | High |
| GO-2026-4601 | High |
| GO-2026-4870 | High |
| GO-2026-4946 | High |
| GO-2026-4947 | High |
| CVE-2024-12797 | Medium |
| CVE-2024-13176 | Medium |
| CVE-2024-45336 | Medium |
| CVE-2024-45341 | Medium |
| CVE-2025-11143 | Medium |
| CVE-2025-15468 | Medium |
| CVE-2025-22866 | Medium |
| CVE-2025-4673 | Medium |
| CVE-2025-47906 | Medium |
| CVE-2025-47912 | Medium |
| CVE-2025-48924 | Medium |
| CVE-2025-49128 | Medium |
| CVE-2025-53864 | Medium |
| CVE-2025-58183 | Medium |
| CVE-2025-58185 | Medium |
| CVE-2025-58186 | Medium |
| CVE-2025-58189 | Medium |
| CVE-2025-61724 | Medium |
| CVE-2025-61727 | Medium |
| CVE-2025-61728 | Medium |
| CVE-2025-61730 | Medium |
| CVE-2025-66199 | Medium |
| CVE-2025-68160 | Medium |
| CVE-2025-69418 | Medium |
| CVE-2025-9231 | Medium |
| CVE-2025-9232 | Medium |
| CVE-2026-22795 | Medium |
| CVE-2026-22796 | Medium |
| CVE-2026-27142 | Medium |
| CVE-2026-27171 | Medium |
| CVE-2026-32282 | Medium |
| CVE-2026-32288 | Medium |
| CVE-2026-32289 | Medium |
| CVE-2026-54514 | Medium |
| CVE-2026-6042 | Medium |
| CVE-2026-8458 | Medium |
| GHSA-3wrr-7qpf-2prh | Medium |
| GHSA-5qjq-93h5-hrgp | Medium |
| GHSA-6w3m-4hhp-775q | Medium |
| GHSA-hh9p-6wh2-4mfc | Medium |
| GHSA-jxr7-mqhw-9p98 | Medium |
| GHSA-m2h6-j472-rp4c | Medium |
| GHSA-qxp5-gwg8-xv66 | Medium |
| GHSA-vvgc-356p-c3xw | Medium |
| GHSA-wf8f-6423-gfxg | Medium |
| GHSA-xwmg-2g98-w7v9 | Medium |
| GO-2025-3373 | Medium |
| GO-2025-3420 | Medium |
| GO-2025-3447 | Medium |
| GO-2025-3503 | Medium |
| GO-2025-3750 | Medium |
| GO-2025-3751 | Medium |
| GO-2025-3956 | Medium |
| GO-2025-4008 | Medium |
| GO-2025-4010 | Medium |
| GO-2025-4011 | Medium |
| GO-2025-4012 | Medium |
| GO-2025-4014 | Medium |
| GO-2025-4015 | Medium |
| GO-2025-4175 | Medium |
| GO-2026-4340 | Medium |
| GO-2026-4342 | Medium |
| GO-2026-4603 | Medium |
| GO-2026-4864 | Medium |
| GO-2026-4865 | Medium |
| GO-2026-4869 | Medium |
| CVE-2024-58251 | Low |
| CVE-2025-22873 | Low |
| CVE-2025-46394 | Low |
| CVE-2026-27139 | Low |
| GHSA-wjpw-4j6x-6rwh | Low |
| GO-2026-4403 | Low |
| GO-2026-4602 | Low |

The following CVEs are currently open and will be fixed in future releases. See the exploitability explanations for each of them below.

| Package name | Type | Vulnerability ID | Severity | Title | Compensating control |
| --- | --- | --- | --- | --- | --- |
| netty-codec-http | java-archive | GHSA-57rv-r2g8-2cj3 | Critical | Netty has HttpClientCodec response desynchronization | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| netty-codec-http | java-archive | GHSA-xxqh-mfjm-7mv9 | Critical | Netty HTTP/1.0 TE+CL Coexistence Bypasses Smuggling Sanitization | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| minio | apk | CVE-2026-33322 | Critical | minio | This vulnerability can be exploited only if unauthorized access to alter internal OIDC validation profile parameters is achieved. |
| libcrypto3 | apk | CVE-2026-34182 | Critical | libcrypto3 | This vulnerability can be exploited only if Pod software is configured to rely on unsigned or untrusted CMS messaging payloads from external actors. |
| minio | apk | GHSA-5cx5-wh4m-82fh | Critical | minio | This vulnerability can be exploited only if unauthorized access to alter internal OIDC validation profile parameters is achieved. |
| jetty-http | java-archive | GHSA-355h-qmc2-wpwf | Critical | Jetty has HTTP Request Smuggling via Chunked Extension Quoted-String Parsing | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| keras | python | GHSA-5gwj-m78q-7pq3 | Critical | Keras: Lambda deserialization can bypass safe mode and execute code | Pod software does not fetch or execute unvalidated remote model code structures dynamically over public networks. |
| netty-codec-xml | java-archive | GHSA-4qhr-g3c6-fcfx | Critical | Netty XML: Injection / Risky Sink — unconfigured XML factory with active DTD and entity handling | Pod software retries scanning on a malicious XML file a couple of times and moves on; container environments run inside isolated, sandboxed namespaces. |
| gawk | rpm | ALAS2023-2026-2035 | Critical | Use After Free vulnerability has been found in 'io.c' program file of gawk (do_getline_redir() routine). This issue may lead to a crash. It affects ga... | Pod software components do not invoke or execute gawk command line binaries dynamically inside running system containers. |
| netty-handler-ssl-ocsp | java-archive | GHSA-272m-gcwp-mpwg | Critical | Netty: Missing CertificateID Validation in OCSP Response Allows Replay Attacks | This vulnerability can be exploited only if Pod software is configured with custom, insecure non-standard certificate verification parameters. |
| transformers | python | GHSA-fgcw-684q-jj6r | Critical | huggingface/transformers: Arbitrary Code Execution During Model Initialization in the LightGlue Model Loading Path | Pod software does not fetch or execute unvalidated remote model code structures dynamically over public networks. |
| pillow | python | GHSA-62p4-gmf7-7g93 | Critical | Pillow: Out-of-bounds read via attacker-controlled row stride on Pillow's mmap path (McIdas AREA files) | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| langgraph-sdk | python | GHSA-w39p-vh2g-g8g5 | Critical | LangGraph SDK has unsafe URL path construction | Pod software doesn't allow inbound communication initiated by external parties. Path logic routing values map strictly to pre-validated variables. |
| [google.golang.org/grpc](http://google.golang.org/grpc) | go-module | GHSA-p77j-4mvh-x3m3 | Critical | gRPC-Go has an authorization bypass via missing leading slash in :path | Pod software doesn't allow inbound communication initiated by external parties. Path logic routing values map strictly to pre-validated variables. |
| [golang.org/x/text](http://golang.org/x/text) | go-module | GO-2026-5970 | High | A norm.Iter can enter an infinite loop when handling input containing invalid UTF-8 bytes. | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| cryptography | python | GHSA-g6cj-pr64-35w5 | High | cryptography: PKCS#7 EnvelopedData decryption exposes a Bleichenbacher oracle through distinguishable errors and timing | Pod software does not expose decryption operations or side-channel parsing vectors directly to external actors. |
| ecdsa | python | GHSA-wj6h-64fc-37mp | High | Minerva timing attack on P-256 in python-ecdsa | This vulnerability can be exploited only if Pod software is configured to interact with untrusted services that make use of arbitrary certificate chains for SSL. |
| [golang.org/x/net](http://golang.org/x/net) | go-module | GO-2026-5942 | High | Parsing an invalid SVCB or HTTPS RR can panic when the size of a parameter value overflows the message buffer. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | CVE-2026-39822 | High | On Unix systems; opening a file in an os.Root improperly follows symlinks to locations outside of the Root when the final path component of the a path... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to map or deploy local malicious symlinks. |
| stdlib | go-module | GO-2026-4970 | High | On Unix systems; opening a file in an os.Root improperly follows symlinks to locations outside of the Root when the final path component of the a path... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to map or deploy local malicious symlinks. |
| [google.golang.org/grpc](http://google.golang.org/grpc) | go-module | GHSA-hrxh-6v49-42gf | High | gRPC-Go: xDS RBAC and HTTP/2 Vulnerabilities | Pod software doesn't allow inbound communication initiated by external parties. Internal targets map exclusively to trusted host tracking environments. |
| netty-handler | java-archive | GHSA-3qp7-7mw8-wx86 | High | Netty has an IPv6 Subnet Filter Bypass via Incorrect Comparator Masking | Pod software network reachability parameters navigate only to explicit internal target networks via infrastructure firewall filtering. |
| netty-codec-http | java-archive | GHSA-f6hv-jmp6-3vwv | High | Netty: HttpContentDecompressor maxAllocation bypass when Content-Encoding set to br/zstd/snappy leads to decompression bomb DoS | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| netty-handler | java-archive | GHSA-x4gw-5cx5-pgmh | High | Netty: SNI handler pre-allocates up to 16 MiB from nine attacker bytes | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to manipulate TLS handshakes. |
| jackson-databind | java-archive | GHSA-j3rv-43j4-c7qm | High | jackson-databind has a PolymorphicTypeValidator bypass via generic type parameters that allows arbitrary class instantiation | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| jackson-databind | java-archive | GHSA-rmj7-2vxq-3g9f | High | jackson-databind has an array subtype allowlist bypass in BasicPolymorphicTypeValidator (allowIfSubTypeIsArray) | This vulnerability can be exploited only if unauthorized access to the pod is obtained to inject dynamic serialized payload chains. |
| log4j-core | java-archive | GHSA-3pxv-7cmr-fjr4 | High | Apache Log4j Core: Silent log event loss in XmlLayout due to unescaped XML 1.0 forbidden characters | Pod software processes run inside isolated, sandboxed namespaces; system log metrics are streamed securely to internal monitoring aggregators. |
| netty-codec-http | java-archive | GHSA-jppx-w49h-x2qq | High | Netty: [SpdyHttpDecoder] ByteBuf Reference Leak on RST_STREAM Leads to Native Memory Exhaustion | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| netty-handler | java-archive | GHSA-c653-97m9-rcg9 | High | Netty: Wrapping plain trust manager silently disables hostname verification | This vulnerability can be exploited only if Pod software is configured to interact with untrusted service endpoints that serve invalid matching certificates. |
| netty-codec | java-archive | GHSA-mj4r-2hfc-f8p6 | High | Netty Lz4FrameDecoder is vulnerable to resource exhaustion | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| log4j-1.2-api | java-archive | GHSA-h383-gmxw-35v2 | High | Apache Log4j 1 to Log4j 2 bridge: silent log event loss in Log4j1XmlLayout due to unescaped XML 1.0 forbidden characters | Pod software processes run inside isolated, sandboxed namespaces; system log metrics are streamed securely to internal monitoring aggregators. |
| netty-codec-http | java-archive | GHSA-6jqx-86gh-f27w | High | Netty SPDY SETTINGS frame count materializes unbounded settings map | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| netty-codec-http | java-archive | GHSA-mvh2-crg5-v77c | High | Netty SPDY zlib header block continues decoded expansion after maxHeaderSize truncation | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |
| wget | apk | CVE-2026-58469 | High | wget | Pod software components do not invoke or execute wget command line binaries dynamically inside running system containers. |
| netty-codec | java-archive | GHSA-558v-64gr-wgg4 | High | Netty: [Bzip2Decoder] Infinite Loop in RLE State Machine Leads to Event-Loop Thread Hang | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| netty-codec-http | java-archive | GHSA-q4f6-jm68-57ww | High | Netty: [HttpContentEncoder] Unbounded Per-Connection Queue Growth via HTTP/1.1 Pipelining Leads to Denial of Service | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to trigger processing delays. |
| wget | apk | CVE-2026-58471 | High | wget | Pod software components do not invoke or execute wget command line binaries dynamically inside running system containers. |
| wget | apk | CVE-2026-58472 | High | wget | Pod software components do not invoke or execute wget command line binaries dynamically inside running system containers. |
| netty-codec-http | java-archive | GHSA-38f8-5428-x5cv | High | Netty vulnerable to HTTP Request Smuggling due to malformed Transfer-Encoding | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| netty-codec-http | java-archive | GHSA-4mp9-239f-g9hg | High | Netty: WebSockets V07/V08 handshaker missing Connection/Upgrade validation | Pod software doesn't allow inbound communication initiated by external parties; external untrusted connections are rejected. |
| elasticsearch | java-archive | GHSA-m9gh-789g-q5pv | High | Elasticsearch PKI Realm Authentication Bypass Vulnerability Allows User Impersonation Through Crafted Client Certificates | This vulnerability can be exploited only if unauthorized access to alter internal PKI validation profile parameters is achieved. |
| jackson-core | java-archive | GHSA-r7wm-3cxj-wff9 | High | jackson-core: Async parser maxNumberLength bypass via chunked digit accumulation (incomplete fix for GHSA-72hv-8253-57qq) | Pod software retries scanning on a malicious JSON tree string a couple of times and moves on; container memory limits insulate the platform host environment. |
| elasticsearch-8.19 | apk | CVE-2026-56745 | High | elasticsearch-8.19 | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-8.19 | apk | CVE-2026-55831 | High | elasticsearch-8.19 | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-8.19 | apk | CVE-2026-55833 | High | elasticsearch-8.19 | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| netty-codec-http2 | java-archive | GHSA-93wv-jw9v-4972 | High | Netty: HTTP/2 decompression leaks ByteBuf reference count when the decompressor channel is already closed (Direct memory leak / OOM DoS) | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| elasticsearch-8.19 | apk | CVE-2026-59899 | High | elasticsearch-8.19 | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-8.19 | apk | CVE-2026-59901 | High | elasticsearch-8.19 | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| elasticsearch-8.19 | apk | CVE-2026-59898 | High | elasticsearch-8.19 | This vulnerability can be exploited only if unauthorized access to the pod is obtained to deliver or alter trusted configuration data profiles. |
| kube-metrics-adapter | apk | CVE-2026-56852 | High | kube-metrics-adapter | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the endpoint. |
| metrics-server | apk | CVE-2026-42151 | High | metrics-server | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| metrics-server | apk | GHSA-wg65-39gg-5wfj | High | metrics-server | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| libcrypto3 | apk | CVE-2026-45447 | High | libcrypto3 | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | CVE-2026-42764 | High | libcrypto3 | Pod software does not implement or expose OpenSSL QUIC server processing listeners to inbound external calls. |
| libcrypto3 | apk | CVE-2026-34183 | High | libcrypto3 | Pod software does not implement or rely on the vulnerable OpenSSL QUIC stack elements for external routing protocols. |
| libcrypto3 | apk | CVE-2026-34180 | High | libcrypto3 | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| mc | apk | CVE-2026-42154 | High | mc | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the remote read endpoint. |
| libcrypto3 | apk | CVE-2026-7383 | High | libcrypto3 | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | CVE-2026-45445 | High | libcrypto3 | Pod software does not use the specific cryptographic OCB block cipher mode pathways inside application implementations. |
| stdlib | go-module | GO-2026-5037 | High | (*x509.Certificate).VerifyHostname previously called matchHostnames in a loop over all DNS Subject Alternative Name (SAN) entries. This caused strings... | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| libcrypto3 | apk | CVE-2026-9076 | High | libcrypto3 | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | CVE-2026-27145 | High | (*x509.Certificate).VerifyHostname previously called matchHostnames in a loop over all DNS Subject Alternative Name (SAN) entries. This caused strings... | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | CVE-2026-42504 | High | Decoding a maliciously-crafted MIME header containing many invalid encoded-words can consume excessive CPU. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | GO-2026-5038 | High | Decoding a maliciously-crafted MIME header containing many invalid encoded-words can consume excessive CPU. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | apk | CVE-2026-42765 | High | libcrypto3 | This vulnerability can be exploited only if Pod software is configured with custom, insecure non-standard certificate verification parameters. |
| minio | apk | CVE-2026-40344 | High | minio | Pod software doesn't allow inbound communication initiated by external parties; write metrics and access functions are securely contained inside internal boundaries. |
| minio | apk | CVE-2026-46600 | High | minio | Pod software doesn't allow inbound communication initiated by external parties; write metrics and access functions are securely contained inside internal boundaries. |
| libcrypto3 | apk | CVE-2026-34181 | High | libcrypto3 | This vulnerability can be exploited only if Pod software handles untrusted, externally-supplied PKCS#12 configuration profiles. |
| mc | apk | GHSA-8rm2-7qqf-34qm | High | mc | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the endpoint. |
| minio | apk | GHSA-9c4q-hq6p-c237 | High | minio | Pod software doesn't allow inbound communication initiated by external parties; write metrics and access functions are securely contained inside internal boundaries. |
| [golang.org/x/net](http://golang.org/x/net) | go-module | GO-2026-4918 | High | When processing HTTP/2 SETTINGS frames; transport will enter an infinite loop of writing CONTINUATION frames if it receives a SETTINGS_MAX_FRAME_SIZE ... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| libthrift | java-archive | GHSA-7pwc-h2j2-rjgj | High | Apache Thrift has an Improper Validation of Certificate with Host Mismatch Vulnerability | This vulnerability can be exploited only if Pod software is configured to interact with untrusted service endpoints that serve invalid matching certificates. |
| python-3.14 | apk | CVE-2026-15308 | High | python-3.14 | Pod software does not execute or evaluate untrusted compression extraction archives natively within public directory runtimes. |
| jline-remote-telnet | java-archive | GHSA-2r2c-cx56-8933 | High | JLine3 Telnet server: Unauthenticated Remote DoS via Unbounded Telnet NAWS Terminal Geometry | Pod software does not deploy or activate unauthenticated Telnet servers inside active runtime perimeters. |
| jline-remote-telnet | java-archive | GHSA-47qp-hqvx-6r3f | High | JLine3 Telnet server: Unauthenticated Remote Memory Exhaustion via Unbounded Telnet NEW-ENVIRON Variables | Pod software does not expose Telnet server interfaces to external public access profiles. |
| jetty-security | java-archive | GHSA-2fvj-hgj9-j2gr | High | Eclipse Jetty Digest Authentication: ISO-8859-1 lossy encoding allows authentication bypass via character substitution | This vulnerability can be exploited only if Pod software is configured to rely on Digest authentication mechanisms for external callers. |
| spark-4.0-scala-2.13 | apk | CVE-2026-56819 | High | spark-4.0-scala-2.13 | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| python-3.11 | apk | CVE-2026-7210 | High | xml.parsers.expat and xml.etree.ElementTree use insufficient entropy for Expat hash-flooding protection; which allows a crafted XML document to tr... | Pod software retries scanning on a malicious XML file a couple of times and moves on; The processes will restart and pick up remaining work. |
| keras | python | GHSA-hqp4-2352-xf5r | High | Keras archive extraction utilities allow path traversal and arbitrary file writes | Pod software components do not ingest or extract raw unvalidated tar archive contents within custom persistent local pathways. |
| python-3.11 | apk | CVE-2026-9669 | High | bz2.BZ2Decompressor objects could be reused after a decompression error. If an application caught the resulting OSError and retried with the same deco... | Pod software retries scanning on a malicious archive file a couple of times and moves on; The processes will restart and pick up remaining work. |
| keras | python | GHSA-v2w2-w228-c444 | High | Keras: TorchModuleWrapper can deserialize unsafe PyTorch pickle data | Pod software does not fetch or execute unvalidated remote model code structures dynamically over public networks. |
| python | binary | CVE-2026-11940 | High | tarfile.extractall() with the 'data' or 'tar' | Pod software does not execute or evaluate untrusted compression extraction archives natively within public directory runtimes. |
| netty-codec-haproxy | java-archive | GHSA-q6cq-mhr2-jmr5 | High | Netty: [codec-haproxy] Signed-Byte Sentinel Collision in HAProxyMessageDecoder Leads to Unbounded Memory Exhaustion | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| python | binary | CVE-2026-6100 | High | Use-after-free (UAF) was possible in the lzma.LZMADecompressor; bz2.BZ2Decompressor; and gzip.GzipFile when a memory allocation fails with a `Me... | Pod software retries scanning on a malicious archive file a couple of times and moves on; The processes will restart and pick up remaining work. |
| python3 | rpm | ALAS2023-2026-1995 | High | The incremental HTML parser (html.parser.HTMLParser) allows for CPUdenial-of-service through repeated unterminated markup declarations whenprocessing ... | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| python | binary | CVE-2026-4224 | High | When an Expat parser with a registered ElementDeclHandler parses an inline | Pod software retries scanning on a malicious XML file a couple of times and moves on; The processes will restart and pick up remaining work. |
| netty-codec-http3 | java-archive | GHSA-hpcc-26xq-25fv | High | Netty: Memory Exhaustion via HTTP/3 Reserved Frame Types | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to send HTTP/3 frames. |
| python | binary | CVE-2026-11972 | High | When using the 'tarfile' module with a file opened in 'streaming mode' (mode='r\|') the tarfile module did not properly handle EOF; making archive pars... | Pod software retries scanning on a malicious streaming archive file a couple of times and moves on; runtime cgroup limits isolate host impact. |
| python | binary | CVE-2026-3644 | High | The fix for CVE-2026-0672; which rejected control characters in http.cookies.Morsel; was incomplete. The Morsel.update(); \|= operator; and unpickling ... | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| netty-codec-stomp | java-archive | GHSA-vhch-2wf3-m8rp | High | Netty: Denial of Service via Unbounded Headers in StompSubframeDecoder | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| python | binary | CVE-2026-3298 | High | The method 'sock_recvfrom_into()' of 'asyncio.ProacterEventLoop' (Windows only) was missing a boundary check for the data buffer when using nbytes par... | Pod software runs on an isolated Linux container platform. Windows-specific operating system APIs are not applicable. |
| java-17-amazon-corretto-devel | rpm | ALAS2023-2026-2022 | High | Vulnerability in the Oracle Java SE; Oracle GraalVM for JDK; Oracle GraalVM Enterprise Edition product of Oracle Java SE (component: JSSE). Supported... | This vulnerability can be exploited only if Pod software is configured to interact with untrusted service endpoints that serve invalid matching certificates. |
| jbig2dec-libs | rpm | ALAS2023-2026-2027 | High | An integer overflow in the jbig2_arith_iaid_ctx_new() function of Artifex commit cc37d0 allows attackers to cause a Denial of Service (DoS) via a craf... | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| python | binary | CVE-2026-4786 | High | Mitgation of CVE-2026-4519 was incomplete. If the URL contained '%action' the mitigation could be bypassed for certain browser types the 'webbrowser.... | Pod software logic functions do not stream dynamically built web page templates back into client-side browser windows. |
| jetty-server | java-archive | GHSA-f4v5-65jj-pcr2 | High | Eclipse Jetty: Cross-Request Leakage for trailers on HTTP/1.1 keep-alive connections | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| vim-data | rpm | ALAS2023-2026-1993 | High | Vim is an open source; command line text editor. Prior to 9.2.0736; the PHP omni-completion script in runtime/autoload/phpcomplete.vim interpolates a ... | Pod software components do not invoke or execute vim command line binaries dynamically inside running system containers. |
| postgresql | java-archive | GHSA-j92g-9f8w-j867 | High | PostgreSQL JDBC Driver: Silent channel-binding authentication downgrade via unsupported certificate algorithms | This vulnerability can be exploited only if Pod software is configured to interact with untrusted database services using fallback parameters. |
| netty-handler-ssl-ocsp | java-archive | GHSA-g7hg-vrcf-mvmr | High | Netty: Out-of-date OCSP Responses Accepted by OcspServerCertificateValidator | This vulnerability can be exploited only if Pod software is configured with custom, insecure non-standard certificate verification parameters. |
| python3-rpm | rpm | ALAS2023-2026-1991 | High | A heap buffer overflow exists in RPM's NDB database backend (lib/backend/ndb/rpmpkg.c) due to unchecked 32-bit arithmetic when parsing the slot table.... | Pod software processes are isolated; sorting and database arrays operate completely on predictable internal application data formats. |
| glib2 | rpm | ALAS2023-2026-2028 | High | A flaw was found in xdgmime. A heap-based buffer overflow can be triggered in _xdg_mime_magic_parse_magic_line() in the xdgmimemagic.c file on little-... | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| netty-handler-ssl-ocsp | java-archive | GHSA-wc96-39fc-566f | High | Netty: TOCTOU in OcspServerCertificateValidator | This vulnerability can be exploited only if Pod software is configured with custom, insecure non-standard certificate verification parameters. |
| libxml2 | rpm | ALAS2023-2026-1992 | High | libxml2 is vulnerable to multiple stack-based buffer overflows in the xmlcatalog utility when running in --shell mode. The usershell() function proces... | Pod software components do not invoke or shell-execute the xmlcatalog command line helper tool within runtime environments. |
| netty-codec-xml | java-archive | GHSA-v74w-7mr3-4qg3 | High | Netty: Denial of Service in XmlFrameDecoder via CPU Exhaustion | Pod software retries scanning on a malicious XML payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| nltk | python | GHSA-p4gq-832x-fm9v | High | Natural Language Toolkit (NLTK): URL-Encoded Path Traversal in nltk.data.load() Allows Arbitrary Local File Read | This vulnerability can be exploited only if unauthorized access to the pod is obtained to force local resource file path loading arguments. |
| pillow | python | GHSA-xj96-63gp-2gmr | High | Pillow: Heap out-of-bounds write in ImageFilter.RankFilter via integer overflow in ImagingExpand | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| pillow | python | GHSA-vjc4-5qp5-m44j | High | Pillow JPEG2000 tiled decode retains a growing scratch buffer and can be used for denial of service | Pod software retries scanning on a malicious file a couple of times and moves on; container memory limits insulate the platform host environment. |
| pillow | python | GHSA-45hq-cxwh-f6vc | High | Pillow BdfFontFile: Image.new() called without _decompression_bomb_check() — bomb protection bypass via font loading | Pod software retries scanning on a malicious file a couple of times and moves on; container memory limits insulate the platform host environment. |
| pillow | python | GHSA-5x94-69rx-g8h2 | High | Pillow: FontFile.compile(): Image.new() called without _decompression_bomb_check() | Pod software retries scanning on a malicious file a couple of times and moves on; container memory limits insulate the platform host environment. |
| pillow | python | GHSA-phj9-mv4w-65pm | High | Pillow GdImageFile._open(): image dimensions accepted without _decompression_bomb_check() | Pod software retries scanning on a malicious file a couple of times and moves on; container memory limits insulate the platform host environment. |
| pillow | python | GHSA-8v84-f9pq-wr9x | High | Pillow PcfFontFile._load_bitmaps(): Image.frombytes() called without _decompression_bomb_check() — bomb protection bypass via PCF font loading | Pod software retries scanning on a malicious file a couple of times and moves on; container memory limits insulate the platform host environment. |
| pillow | python | GHSA-6r8x-57c9-28j4 | High | Pillow: Heap out-of-bounds write Image.paste() / Image.crop() via signed coordinate overflow | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| pillow | python | GHSA-9hw9-ch79-4vh6 | High | Pillow: Controlled heap out-of-bounds write in Pillow ImageCmsTransform.apply() via output mode mismatch | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| pillow | python | GHSA-jjj6-mw9f-p565 | High | Pillow: Decompression Bomb DoS via PdfParser.PdfStream.decode() | Pod software retries scanning on a malicious file a couple of times and moves on; container memory limits insulate the platform host environment. |
| pyasn1 | python | GHSA-m4p7-r5rc-7g4j | High | pyasn1 BER/CER/DER decoder denial of service via unbounded long-form tag IDs | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| pyasn1 | python | GHSA-hm4w-wwcw-mr6r | High | pyasn1: Uncontrolled resource consumption when converting decoded REAL values | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| pyasn1 | python | GHSA-8ppf-4f7h-5ppj | High | pyasn1: Quadratic complexity in OBJECT IDENTIFIER and RELATIVE-OID processing allows denial of service | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| aiohttp | python | GHSA-cq5v-8q36-5273 | High | AIOHTTP: Out-of-bounds heap read in C HTTP response parser error path (malformed chunked response) | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| pillow | python | GHSA-pg7v-jwj7-p798 | High | Pillow EpsImagePlugin negative %%BeginBinary byte count causes infinite loop denial of service | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| pillow | python | GHSA-fj7v-r99m-22gq | High | Pillow TGA RLE encoder can serialize up to ~57 KB of adjacent heap data into generated images | Pod software retries scanning on a malicious file a couple of times and moves on; container environments run inside isolated, sandboxed namespaces. |
| langsmith | python | GHSA-f4xh-w4cj-qxq8 | High | LangSmith SDK TracingMiddleware: Arbitrary server-side file read | This vulnerability can be exploited only if unauthorized access to local internal tracing telemetry parameters is accomplished. |
| nltk | python | GHSA-6hm5-jgcp-p838 | High | Natural Language Toolkit (NLTK): Path Traversal in NKJPCorpusReader leads to Arbitrary File Read and bypasses the nltk.pathsec sandbox (ENFORCE=True) | This vulnerability can be exploited only if unauthorized access to the pod is obtained to force local resource file path loading arguments. |
| nltk | python | GHSA-fg7f-2386-8897 | High | Natural Language Toolkit (NLTK): ReDoS in NLTK ReviewsCorpusReader FEATURES regex | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| nltk | python | GHSA-qvv7-cg9c-w4x3 | High | Natural Language Toolkit (NLTK): DNS-rebinding SSRF filter bypass in nltk.pathsec.urlopen (nltk.download / nltk.data.load) defeats ENFORCE mode | Pod software outbound connection calls terminate strictly on explicit static targets, omitting cross-origin jump actions. |
| nltk | python | GHSA-xh95-f55m-82fw | High | Natural Language Toolkit (NLTK) has path traversal in FramenetCorpusReader.frame() that allows arbitrary XML file read; bypassing the nltk.pathsec san... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to force local resource file path loading arguments. |
| sqlite-libs | apk | CVE-2026-11822 | High | SQLite before 3.53.2 contains memory corruption vulnerabilities in the FTS5 full-text search extension that allow attackers to cause process crashes; ... | Pod software processes are isolated; database queries operate completely on predictable internal application data formats. |
| sqlite-libs | apk | CVE-2026-11824 | High | SQLite before 3.53.2 contains a heap-based buffer overflow vulnerability in the FTS5 full-text search extension that allows attackers to cause a crash... | Pod software processes are isolated; database queries operate completely on predictable internal application data formats. |
| starlette | python | GHSA-82w8-qh3p-5jfq | High | Starlette: request.form() limits silently ignored for application/x-www-form-urlencoded enable DoS | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to send form floods. |
| pyjwt | python | GHSA-xgmm-8j9v-c9wx | High | PyJWT: Public-key JWK accepted as HMAC secret enables forged HS256 tokens when mixed families are allowed | Pod software validates cryptographic identities exclusively through explicit signing keys obtained from a verified local vault service. |
| python-multipart | python | GHSA-5rvq-cxj2-64vf | High | python-multipart: Quadratic-time querystring parsing with semicolon separators causes CPU denial of service | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| starlette | python | GHSA-wqp7-x3pw-xc5r | High | Starlette: SSRF and NTLM credential theft via UNC paths in StaticFiles on Windows | Pod software runs on an isolated Linux container platform. Windows-specific UNC handling paths are not applicable. |
| vcrpy | python | GHSA-rpj2-4hq8-938g | High | VCR.py: Arbitrary code execution via unsafe YAML deserialization of cassette files | Pod software configuration parameters do not process or interpret untrusted test recording cassette files inside live runtime configurations. |
| stdlib | go-module | CVE-2026-33811 | High | When using LookupCNAME with the cgo DNS resolver; a very long CNAME response can trigger a double-free of C memory and a crash. | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | GO-2026-4981 | High | When using LookupCNAME with the cgo DNS resolver; a very long CNAME response can trigger a double-free of C memory and a crash. | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | go-module | CVE-2026-42499 | High | Pathological inputs could cause DoS through consumePhrase when parsing an email address according to RFC 5322. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | GO-2026-4977 | High | Pathological inputs could cause DoS through consumePhrase when parsing an email address according to RFC 5322. | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | CVE-2026-39820 | High | Well-crafted inputs reaching ParseAddress; ParseAddressList; and ParseDate were able to trigger excessive CPU exhaustion and memory allocations. | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | GO-2026-4986 | High | Well-crafted inputs reaching ParseAddress; ParseAddressList; and ParseDate were able to trigger excessive CPU exhaustion and memory allocations. | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | go-module | CVE-2026-33814 | High | When processing HTTP/2 SETTINGS frames; transport will enter an infinite loop of writing CONTINUATION frames if it receives a SETTINGS_MAX_FRAME_SIZE ... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| [golang.org/x/net](http://golang.org/x/net) | go-module | GO-2026-5026 | High | The ToASCII and ToUnicode functions incorrectly accept Punycode-encoded labels that decode to an ASCII-only label. For example; ToUnicode('xn--example... | Pod software components run as a non-root system identity configuration; there is no path for execution parsing to alter parent namespace privileges. |
| stdlib | go-module | CVE-2026-39836 | High | The Dial and LookupPort functions panic on Windows when provided with an input containing a NUL (0). | Pod software runs on an isolated Linux container platform. Windows-specific operating system APIs are not applicable. |
| stdlib | go-module | GO-2026-4971 | High | The Dial and LookupPort functions panic on Windows when provided with an input containing a NUL (0). | Pod software runs on an isolated Linux container platform. Windows-specific operating system APIs are not applicable. |
| stdlib | go-module | CVE-2026-42501 | High | A malicious module proxy can exploit a flaw in the go command's validation of module checksums to bypass checksum database validation. This vulnerabil... | Pod software components do not ingest or install dynamic dependencies or modules inside running system containers. |

---

## 1.148

### Release updates - July 2026

#### Introducing template-based installation for EPod V2

Securiti has introduced template-based installation for Elastic Pods (EPods) V2, providing an automated deployment option if you do not have an existing managed infrastructure. This cloud template provisions the complete AWS infrastructure suitable for EPods V2. It deploys services like Kubernetes cluster, networking, and databases, and Elastic Pods V2 itself in the infrastructure. This update reduces manual setup effort and configuration errors, letting you get a fresh infrastructure and deployment running faster.

> [!NOTE]
> Note
> 
> Use the deployment template without changing any parameter.

For more information, see [EPod V2 installation using cloud template](/latest/docs/epod-v2-installation-using-cloud-template).

#### Upgrading Elasticsearch for EPod V2

Securiti has upgraded internal Elasticsearch (ES) from version v7 to v8 for Elastic Pods (EPods) V2, as v7 has reached its end of life. You must upgrade your EPods V2 to the latest version to receive ES v8. You might need to pause in-progress connector scans, depending on the scan type, because the process affects running scans.

> [!WARNING]
> Important
> 
> - For your running Data Inventory Syncs and Data Subject Rights (DSR) scans, you must pause or finish them before upgrading.
> - For running Discovery Scans, Securiti automatically pauses them before the upgrade and resumes afterward.

For more information, see [Upgrading EPod V2](/latest/docs/upgrade-epod-v2).

#### Security, confidentiality, and availability updates

Securiti has fixed the following critical, high, medium, and low severity CVEs in the 1.148 release of pod software (with cluster version v1.28 or later).

| Vulnerability ID | Severity |
| --- | --- |
| [CVE-2026-2332](https://nvd.nist.gov/vuln/detail/CVE-2026-2332) | Critical |
| [CVE-2026-33117](https://nvd.nist.gov/vuln/detail/CVE-2026-33117) | Critical |
| [CVE-2026-42579](https://nvd.nist.gov/vuln/detail/CVE-2026-42579) | Critical |
| [CVE-2026-42581](https://nvd.nist.gov/vuln/detail/CVE-2026-42581) | Critical |
| [CVE-2026-42584](https://nvd.nist.gov/vuln/detail/CVE-2026-42584) | Critical |
| [CVE-2026-44727](https://nvd.nist.gov/vuln/detail/CVE-2026-44727) | Critical |
| [CVE-2026-45674](https://nvd.nist.gov/vuln/detail/CVE-2026-45674) | Critical |
| [CVE-2026-47691](https://nvd.nist.gov/vuln/detail/CVE-2026-47691) | Critical |
| [CVE-2026-5450](https://nvd.nist.gov/vuln/detail/CVE-2026-5450) | Critical |
| [CVE-2026-6100](https://nvd.nist.gov/vuln/detail/CVE-2026-6100) | Critical |
| [CVE-2026-6653](https://nvd.nist.gov/vuln/detail/CVE-2026-6653) | Critical |
| ALAS2023-2026-1853 | Critical |
| GHSA-574f-3g2m-x479 | Critical |
| GHSA-5cgq-3rg8-m6cv | Critical |
| GHSA-5pvg-856g-cp85 | Critical |
| GHSA-676x-f7gg-47vc | Critical |
| GHSA-89gr-r52h-f8rx | Critical |
| GHSA-97jf-46m3-8953 | Critical |
| GHSA-cm33-6792-r9fm | Critical |
| GHSA-f5wc-c3c7-36mc | Critical |
| GHSA-fcw5-x6j4-ccmp | Critical |
| GHSA-jppx-rxg9-jmrx | Critical |
| GHSA-rm3j-f69w-wqmq | Critical |
| GHSA-vgwf-h737-ff37 | Critical |
| GHSA-x527-x647-q7gg | Critical |
| GO-2026-5005 | Critical |
| GO-2026-5019 | Critical |
| GO-2026-5020 | Critical |
| [CVE-2026-11940](https://nvd.nist.gov/vuln/detail/CVE-2026-11940) | Critical |
| [CVE-2023-39810](https://nvd.nist.gov/vuln/detail/CVE-2023-39810) | High |
| [CVE-2025-12183](https://nvd.nist.gov/vuln/detail/CVE-2025-12183) | High |
| [CVE-2025-66418](https://nvd.nist.gov/vuln/detail/CVE-2025-66418) | High |
| [CVE-2025-66471](https://nvd.nist.gov/vuln/detail/CVE-2025-66471) | High |
| [CVE-2025-66566](https://nvd.nist.gov/vuln/detail/CVE-2025-66566) | High |
| [CVE-2025-67721](https://nvd.nist.gov/vuln/detail/CVE-2025-67721) | High |
| [CVE-2026-0636](https://nvd.nist.gov/vuln/detail/CVE-2026-0636) | High |
| [CVE-2026-11822](https://nvd.nist.gov/vuln/detail/CVE-2026-11822) | High |
| [CVE-2026-11824](https://nvd.nist.gov/vuln/detail/CVE-2026-11824) | High |
| [CVE-2026-1502](https://nvd.nist.gov/vuln/detail/CVE-2026-1502) | High |
| [CVE-2026-21441](https://nvd.nist.gov/vuln/detail/CVE-2026-21441) | High |
| [CVE-2026-22007](https://nvd.nist.gov/vuln/detail/CVE-2026-22007) | High |
| [CVE-2026-22013](https://nvd.nist.gov/vuln/detail/CVE-2026-22013) | High |
| [CVE-2026-22016](https://nvd.nist.gov/vuln/detail/CVE-2026-22016) | High |
| [CVE-2026-22018](https://nvd.nist.gov/vuln/detail/CVE-2026-22018) | High |
| [CVE-2026-22021](https://nvd.nist.gov/vuln/detail/CVE-2026-22021) | High |
| [CVE-2026-2297](https://nvd.nist.gov/vuln/detail/CVE-2026-2297) | High |
| [CVE-2026-23865](https://nvd.nist.gov/vuln/detail/CVE-2026-23865) | High |
| [CVE-2026-24281](https://nvd.nist.gov/vuln/detail/CVE-2026-24281) | High |
| [CVE-2026-24308](https://nvd.nist.gov/vuln/detail/CVE-2026-24308) | High |
| [CVE-2026-25087](https://nvd.nist.gov/vuln/detail/CVE-2026-25087) | High |
| [CVE-2026-26157](https://nvd.nist.gov/vuln/detail/CVE-2026-26157) | High |
| [CVE-2026-26158](https://nvd.nist.gov/vuln/detail/CVE-2026-26158) | High |
| [CVE-2026-2673](https://nvd.nist.gov/vuln/detail/CVE-2026-2673) | High |
| [CVE-2026-27140](https://nvd.nist.gov/vuln/detail/CVE-2026-27140) | High |
| [CVE-2026-28386](https://nvd.nist.gov/vuln/detail/CVE-2026-28386) | High |
| [CVE-2026-29181](https://nvd.nist.gov/vuln/detail/CVE-2026-29181) | High |
| [CVE-2026-33416](https://nvd.nist.gov/vuln/detail/CVE-2026-33416) | High |
| [CVE-2026-33636](https://nvd.nist.gov/vuln/detail/CVE-2026-33636) | High |
| [CVE-2026-33870](https://nvd.nist.gov/vuln/detail/CVE-2026-33870) | High |
| [CVE-2026-33871](https://nvd.nist.gov/vuln/detail/CVE-2026-33871) | High |
| [CVE-2026-34268](https://nvd.nist.gov/vuln/detail/CVE-2026-34268) | High |
| [CVE-2026-34282](https://nvd.nist.gov/vuln/detail/CVE-2026-34282) | High |
| [CVE-2026-34478](https://nvd.nist.gov/vuln/detail/CVE-2026-34478) | High |
| [CVE-2026-34479](https://nvd.nist.gov/vuln/detail/CVE-2026-34479) | High |
| [CVE-2026-34480](https://nvd.nist.gov/vuln/detail/CVE-2026-34480) | High |
| [CVE-2026-34481](https://nvd.nist.gov/vuln/detail/CVE-2026-34481) | High |
| [CVE-2026-3479](https://nvd.nist.gov/vuln/detail/CVE-2026-3479) | High |
| [CVE-2026-34993](https://nvd.nist.gov/vuln/detail/CVE-2026-34993) | High |
| [CVE-2026-35177](https://nvd.nist.gov/vuln/detail/CVE-2026-35177) | High |
| [CVE-2026-3644](https://nvd.nist.gov/vuln/detail/CVE-2026-3644) | High |
| [CVE-2026-39817](https://nvd.nist.gov/vuln/detail/CVE-2026-39817) | High |
| [CVE-2026-39819](https://nvd.nist.gov/vuln/detail/CVE-2026-39819) | High |
| [CVE-2026-39827](https://nvd.nist.gov/vuln/detail/CVE-2026-39827) | High |
| [CVE-2026-39828](https://nvd.nist.gov/vuln/detail/CVE-2026-39828) | High |
| [CVE-2026-39829](https://nvd.nist.gov/vuln/detail/CVE-2026-39829) | High |
| [CVE-2026-39830](https://nvd.nist.gov/vuln/detail/CVE-2026-39830) | High |
| [CVE-2026-39831](https://nvd.nist.gov/vuln/detail/CVE-2026-39831) | High |
| [CVE-2026-39832](https://nvd.nist.gov/vuln/detail/CVE-2026-39832) | High |
| [CVE-2026-39833](https://nvd.nist.gov/vuln/detail/CVE-2026-39833) | High |
| [CVE-2026-39834](https://nvd.nist.gov/vuln/detail/CVE-2026-39834) | High |
| [CVE-2026-39835](https://nvd.nist.gov/vuln/detail/CVE-2026-39835) | High |
| [CVE-2026-39881](https://nvd.nist.gov/vuln/detail/CVE-2026-39881) | High |
| [CVE-2026-4046](https://nvd.nist.gov/vuln/detail/CVE-2026-4046) | High |
| [CVE-2026-41080](https://nvd.nist.gov/vuln/detail/CVE-2026-41080) | High |
| [CVE-2026-42151](https://nvd.nist.gov/vuln/detail/CVE-2026-42151) | High |
| [CVE-2026-4224](https://nvd.nist.gov/vuln/detail/CVE-2026-4224) | High |
| [CVE-2026-42307](https://nvd.nist.gov/vuln/detail/CVE-2026-42307) | High |
| [CVE-2026-42501](https://nvd.nist.gov/vuln/detail/CVE-2026-42501) | High |
| [CVE-2026-42508](https://nvd.nist.gov/vuln/detail/CVE-2026-42508) | High |
| [CVE-2026-42577](https://nvd.nist.gov/vuln/detail/CVE-2026-42577) | High |
| [CVE-2026-42578](https://nvd.nist.gov/vuln/detail/CVE-2026-42578) | High |
| [CVE-2026-42583](https://nvd.nist.gov/vuln/detail/CVE-2026-42583) | High |
| [CVE-2026-42585](https://nvd.nist.gov/vuln/detail/CVE-2026-42585) | High |
| [CVE-2026-42587](https://nvd.nist.gov/vuln/detail/CVE-2026-42587) | High |
| [CVE-2026-4372](https://nvd.nist.gov/vuln/detail/CVE-2026-4372) | High |
| [CVE-2026-43869](https://nvd.nist.gov/vuln/detail/CVE-2026-43869) | High |
| [CVE-2026-43961](https://explore.alas.aws.amazon.com/CVE-2026-43961.html) | High |
| [CVE-2026-44250](https://nvd.nist.gov/vuln/detail/CVE-2026-44250) | High |
| [CVE-2026-4437](https://nvd.nist.gov/vuln/detail/CVE-2026-4437) | High |
| [CVE-2026-44431](https://nvd.nist.gov/vuln/detail/CVE-2026-44431) | High |
| [CVE-2026-44432](https://nvd.nist.gov/vuln/detail/CVE-2026-44432) | High |
| [CVE-2026-44656](https://nvd.nist.gov/vuln/detail/CVE-2026-44656) | High |
| [CVE-2026-44890](https://nvd.nist.gov/vuln/detail/CVE-2026-44890) | High |
| [CVE-2026-44892](https://nvd.nist.gov/vuln/detail/CVE-2026-44892) | High |
| [CVE-2026-44893](https://nvd.nist.gov/vuln/detail/CVE-2026-44893) | High |
| [CVE-2026-44894](https://nvd.nist.gov/vuln/detail/CVE-2026-44894) | High |
| [CVE-2026-45130](https://nvd.nist.gov/vuln/detail/CVE-2026-45130) | High |
| [CVE-2026-45186](https://nvd.nist.gov/vuln/detail/CVE-2026-45186) | High |
| [CVE-2026-4519](https://nvd.nist.gov/vuln/detail/CVE-2026-4519) | High |
| [CVE-2026-45292](https://nvd.nist.gov/vuln/detail/CVE-2026-45292) | High |
| [CVE-2026-46340](https://nvd.nist.gov/vuln/detail/CVE-2026-46340) | High |
| [CVE-2026-46483](https://nvd.nist.gov/vuln/detail/CVE-2026-46483) | High |
| [CVE-2026-46595](https://nvd.nist.gov/vuln/detail/CVE-2026-46595) | High |
| [CVE-2026-46597](https://nvd.nist.gov/vuln/detail/CVE-2026-46597) | High |
| [CVE-2026-46598](https://nvd.nist.gov/vuln/detail/CVE-2026-46598) | High |
| [CVE-2026-46601](https://nvd.nist.gov/vuln/detail/CVE-2026-46601) | High |
| [CVE-2026-47162](https://nvd.nist.gov/vuln/detail/CVE-2026-47162) | High |
| [CVE-2026-47167](https://nvd.nist.gov/vuln/detail/CVE-2026-47167) | High |
| [CVE-2026-47265](https://nvd.nist.gov/vuln/detail/CVE-2026-47265) | High |
| [CVE-2026-4786](https://nvd.nist.gov/vuln/detail/CVE-2026-4786) | High |
| [CVE-2026-48006](https://nvd.nist.gov/vuln/detail/CVE-2026-48006) | High |
| [CVE-2026-48059](https://nvd.nist.gov/vuln/detail/CVE-2026-48059) | High |
| [CVE-2026-48748](https://nvd.nist.gov/vuln/detail/CVE-2026-48748) | High |
| [CVE-2026-48863](https://nvd.nist.gov/vuln/detail/CVE-2026-48863) | High |
| [CVE-2026-48864](https://nvd.nist.gov/vuln/detail/CVE-2026-48864) | High |
| [CVE-2026-50011](https://nvd.nist.gov/vuln/detail/CVE-2026-50011) | High |
| [CVE-2026-50269](https://nvd.nist.gov/vuln/detail/CVE-2026-50269) | High |
| [CVE-2026-50593](https://nvd.nist.gov/vuln/detail/CVE-2026-50593) | High |
| [CVE-2026-52858](https://nvd.nist.gov/vuln/detail/CVE-2026-52858) | High |
| [CVE-2026-52859](https://nvd.nist.gov/vuln/detail/CVE-2026-52859) | High |
| [CVE-2026-52860](https://nvd.nist.gov/vuln/detail/CVE-2026-52860) | High |
| [CVE-2026-53615](https://explore.alas.aws.amazon.com/CVE-2026-53615.html) | High |
| [CVE-2026-5422](https://nvd.nist.gov/vuln/detail/CVE-2026-5422) | High |
| [CVE-2026-54273](https://nvd.nist.gov/vuln/detail/CVE-2026-54273) | High |
| [CVE-2026-54274](https://nvd.nist.gov/vuln/detail/CVE-2026-54274) | High |
| [CVE-2026-54275](https://nvd.nist.gov/vuln/detail/CVE-2026-54275) | High |
| [CVE-2026-54277](https://nvd.nist.gov/vuln/detail/CVE-2026-54277) | High |
| [CVE-2026-54278](https://nvd.nist.gov/vuln/detail/CVE-2026-54278) | High |
| [CVE-2026-54279](https://nvd.nist.gov/vuln/detail/CVE-2026-54279) | High |
| [CVE-2026-54280](https://nvd.nist.gov/vuln/detail/CVE-2026-54280) | High |
| [CVE-2026-5598](https://nvd.nist.gov/vuln/detail/CVE-2026-5598) | High |
| [CVE-2026-5928](https://nvd.nist.gov/vuln/detail/CVE-2026-5928) | High |
| [CVE-2026-6019](https://nvd.nist.gov/vuln/detail/CVE-2026-6019) | High |
| [CVE-2026-7210](https://nvd.nist.gov/vuln/detail/CVE-2026-7210) | High |
| [CVE-2026-7774](https://nvd.nist.gov/vuln/detail/CVE-2026-7774) | High |
| [CVE-2026-9149](https://nvd.nist.gov/vuln/detail/CVE-2026-9149) | High |
| [CVE-2026-9150](https://nvd.nist.gov/vuln/detail/CVE-2026-9150) | High |
| [CVE-2026-9669](https://nvd.nist.gov/vuln/detail/CVE-2026-9669) | High |
| ALAS2023-2026-1798 | High |
| ALAS2023-2026-1837 | High |
| ALAS2023-2026-1856 | High |
| ALAS2023-2026-1862 | High |
| ALAS2023-2026-1900 | High |
| ALAS2023-2026-1903 | High |
| ALAS2023-2026-1911 | High |
| ALAS2023-2026-1913 | High |
| ALAS2023-2026-1916 | High |
| ALAS2023-2026-1930 | High |
| ALAS2023-2026-1933 | High |
| [CVE-2026-39821](https://nvd.nist.gov/vuln/detail/CVE-2026-39821) | High |
| [CVE-2026-44249](https://nvd.nist.gov/vuln/detail/CVE-2026-44249) | High |
| [CVE-2026-45416](https://nvd.nist.gov/vuln/detail/CVE-2026-45416) | High |
| [CVE-2026-48043](https://nvd.nist.gov/vuln/detail/CVE-2026-48043) | High |
| [CVE-2026-50010](https://nvd.nist.gov/vuln/detail/CVE-2026-50010) | High |
| GHSA-29pf-2h5f-8g72 | High |
| GHSA-2fqr-mr3j-6wp8 | High |
| GHSA-2xpw-w6gg-jr37 | High |
| GHSA-3244-j874-rhc2 | High |
| GHSA-38jv-5279-wg99 | High |
| GHSA-445c-vh5m-36rj | High |
| GHSA-45gg-vh54-h5m9 | High |
| GHSA-45q3-82m4-75jr | High |
| GHSA-4fvr-rgm6-gqmc | High |
| GHSA-4grm-h2qv-h6w6 | High |
| GHSA-4m7w-qmgq-4wj5 | High |
| GHSA-57rv-r2g8-2cj3 | High |
| GHSA-5pvg-856g-cp85 | High |
| GHSA-5w86-c3rq-vjj7 | High |
| GHSA-5xrh-qmmq-w6ch | High |
| GHSA-63hw-fmq6-xxg2 | High |
| GHSA-676x-f7gg-47vc | High |
| GHSA-6ghj-frrj-jjj3 | High |
| GHSA-6jv9-x5w9-2ccm | High |
| GHSA-78mq-xcr3-xm33 | High |
| GHSA-7xrh-hqfc-g7qr | High |
| GHSA-8rm2-7qqf-34qm | High |
| GHSA-9x8q-7h8h-wcw9 | High |
| GHSA-c2rx-5r8w-8xr2 | High |
| GHSA-cc37-9q2j-3hfv | High |
| GHSA-cm33-6792-r9fm | High |
| GHSA-cmm3-54f8-px4j | High |
| GHSA-cmp6-m4wj-q63q | High |
| GHSA-crhr-qqj8-rpxc | High |
| GHSA-g3cq-j2xw-wf74 | High |
| GHSA-gf7q-q4j7-hp7c | High |
| GHSA-gm62-xv2j-4w53 | High |
| GHSA-h2qv-fj59-j46j | High |
| GHSA-hg6j-4rv6-33pg | High |
| GHSA-jg22-mg44-37j8 | High |
| GHSA-m6qw-4cw2-hm4m | High |
| GHSA-mf9v-mfxr-j63j | High |
| GHSA-mh2q-q3fh-2475 | High |
| GHSA-p93r-85wp-75v3 | High |
| GHSA-pwqr-wmgm-9rr8 | High |
| GHSA-q4h4-gmj2-qvw2 | High |
| GHSA-qccp-gfcp-xxvc | High |
| GHSA-rgxp-2hwp-jwgg | High |
| GHSA-rwm7-x88c-3g2p | High |
| GHSA-vqf4-7m7x-wgfc | High |
| GHSA-vx9q-rhv9-3jvg | High |
| GHSA-w35j-pv5h-q9q9 | High |
| GHSA-w879-237q-wc7r | High |
| GHSA-w9fj-cfpg-grvv | High |
| GHSA-wg65-39gg-5wfj | High |
| GHSA-xcgm-r5h9-7989 | High |
| GO-2026-4961 | High |
| GO-2026-5006 | High |
| GO-2026-5013 | High |
| GO-2026-5014 | High |
| GO-2026-5015 | High |
| GO-2026-5017 | High |
| GO-2026-5018 | High |
| GO-2026-5021 | High |
| GO-2026-5023 | High |
| GO-2026-5061 | High |
| GO-2026-5062 | High |
| GO-2026-5066 | High |
| [CVE-2025-13462](https://nvd.nist.gov/vuln/detail/CVE-2025-13462) | High |
| [CVE-2025-52999](https://nvd.nist.gov/vuln/detail/CVE-2025-52999) | High |
| [CVE-2026-42154](https://nvd.nist.gov/vuln/detail/CVE-2026-42154) | High |
| [CVE-2026-50193](https://nvd.nist.gov/vuln/detail/CVE-2026-50193) | High |
| [CVE-2024-45993](https://nvd.nist.gov/vuln/detail/CVE-2024-45993) | Medium |
| [CVE-2024-6763](https://nvd.nist.gov/vuln/detail/CVE-2024-6763) | Medium |
| [CVE-2025-12781](https://nvd.nist.gov/vuln/detail/CVE-2025-12781) | Medium |
| [CVE-2025-13462](https://nvd.nist.gov/vuln/detail/CVE-2025-13462) | Medium |
| [CVE-2025-2999](https://nvd.nist.gov/vuln/detail/CVE-2025-2999) | Medium |
| [CVE-2025-3001](https://nvd.nist.gov/vuln/detail/CVE-2025-3001) | Medium |
| [CVE-2025-50181](https://nvd.nist.gov/vuln/detail/CVE-2025-50181) | Medium |
| [CVE-2026-25645](https://nvd.nist.gov/vuln/detail/CVE-2026-25645) | Medium |
| [CVE-2026-32776](https://nvd.nist.gov/vuln/detail/CVE-2026-32776) | Medium |
| [CVE-2026-32777](https://nvd.nist.gov/vuln/detail/CVE-2026-32777) | Medium |
| [CVE-2026-32778](https://nvd.nist.gov/vuln/detail/CVE-2026-32778) | Medium |
| [CVE-2026-33813](https://nvd.nist.gov/vuln/detail/CVE-2026-33813) | Medium |
| [CVE-2026-3446](https://nvd.nist.gov/vuln/detail/CVE-2026-3446) | Medium |
| [CVE-2026-34477](https://nvd.nist.gov/vuln/detail/CVE-2026-34477) | Medium |
| [CVE-2026-34757](https://nvd.nist.gov/vuln/detail/CVE-2026-34757) | Medium |
| [CVE-2026-41417](https://nvd.nist.gov/vuln/detail/CVE-2026-41417) | Medium |
| [CVE-2026-42580](https://nvd.nist.gov/vuln/detail/CVE-2026-42580) | Medium |
| [CVE-2026-4438](https://nvd.nist.gov/vuln/detail/CVE-2026-4438) | Medium |
| [CVE-2026-44903](https://nvd.nist.gov/vuln/detail/CVE-2026-44903) | Medium |
| [CVE-2026-45409](https://nvd.nist.gov/vuln/detail/CVE-2026-45409) | Medium |
| [CVE-2026-45673](https://nvd.nist.gov/vuln/detail/CVE-2026-45673) | Medium |
| [CVE-2026-48155](https://nvd.nist.gov/vuln/detail/CVE-2026-48155) | Medium |
| [CVE-2026-48156](https://nvd.nist.gov/vuln/detail/CVE-2026-48156) | Medium |
| [CVE-2026-48735](https://nvd.nist.gov/vuln/detail/CVE-2026-48735) | Medium |
| [CVE-2026-49460](https://nvd.nist.gov/vuln/detail/CVE-2026-49460) | Medium |
| [CVE-2026-49461](https://nvd.nist.gov/vuln/detail/CVE-2026-49461) | Medium |
| [CVE-2026-50009](https://nvd.nist.gov/vuln/detail/CVE-2026-50009) | Medium |
| [CVE-2026-54276](https://nvd.nist.gov/vuln/detail/CVE-2026-54276) | Medium |
| [CVE-2026-54530](https://nvd.nist.gov/vuln/detail/CVE-2026-54530) | Medium |
| [CVE-2026-54531](https://nvd.nist.gov/vuln/detail/CVE-2026-54531) | Medium |
| [CVE-2026-54651](https://nvd.nist.gov/vuln/detail/CVE-2026-54651) | Medium |
| [CVE-2026-6860](https://nvd.nist.gov/vuln/detail/CVE-2026-6860) | Medium |
| GHSA-jm82-fx9c-mx94 | Medium |
| ALAS2023-2026-1785 | Medium |
| ALAS2023-2026-1832 | Medium |
| [CVE-2026-0636](https://nvd.nist.gov/vuln/detail/CVE-2026-0636) | Medium |
| [CVE-2026-22013](https://nvd.nist.gov/vuln/detail/CVE-2026-22013) | Medium |
| [CVE-2026-22021](https://nvd.nist.gov/vuln/detail/CVE-2026-22021) | Medium |
| [CVE-2026-23865](https://nvd.nist.gov/vuln/detail/CVE-2026-23865) | Medium |
| [CVE-2026-2673](https://nvd.nist.gov/vuln/detail/CVE-2026-2673) | Medium |
| [CVE-2026-3219](https://nvd.nist.gov/vuln/detail/CVE-2026-3219) | Medium |
| [CVE-2026-44431](https://nvd.nist.gov/vuln/detail/CVE-2026-44431) | Medium |
| [CVE-2026-45536](https://nvd.nist.gov/vuln/detail/CVE-2026-45536) | Medium |
| [CVE-2026-47244](https://nvd.nist.gov/vuln/detail/CVE-2026-47244) | Medium |
| [CVE-2026-50020](https://nvd.nist.gov/vuln/detail/CVE-2026-50020) | Medium |
| [CVE-2026-50560](https://nvd.nist.gov/vuln/detail/CVE-2026-50560) | Medium |
| [CVE-2026-5713](https://nvd.nist.gov/vuln/detail/CVE-2026-5713) | Medium |
| [CVE-2026-6357](https://nvd.nist.gov/vuln/detail/CVE-2026-6357) | Medium |
| GHSA-248m-82v9-q6g6 | Medium |
| GHSA-38f8-5428-x5cv | Medium |
| GHSA-3pxv-7cmr-fjr4 | Medium |
| GHSA-445c-vh5m-36rj | Medium |
| GHSA-52x6-gq3r-vpf4 | Medium |
| GHSA-5hgr-hg42-57jg | Medium |
| GHSA-65pc-fj4g-8rjx | Medium |
| GHSA-9m57-25v3-79x9 | Medium |
| GHSA-c2gf-v879-257j | Medium |
| GHSA-c3fc-8qff-9hwx | Medium |
| GHSA-cj93-chg6-vgv8 | Medium |
| GHSA-cq4q-cv5g-r8q5 | Medium |
| GHSA-fw8g-cg8f-9j28 | Medium |
| GHSA-g9xf-7f8q-9mcj | Medium |
| GHSA-gc5v-m9x4-r6x2 | Medium |
| GHSA-h383-gmxw-35v2 | Medium |
| GHSA-hpj7-wq8m-9hgp | Medium |
| GHSA-j543-4vmf-qm7v | Medium |
| GHSA-m2v9-299j-rv96 | Medium |
| GHSA-pq67-6m6q-mj2v | Medium |
| GHSA-qfhq-4f3w-5fph | Medium |
| GHSA-qpw4-5x99-6vjp | Medium |
| GHSA-vgrw-7cvw-pwgx | Medium |
| GHSA-w35j-pv5h-q9q9 | Medium |
| GHSA-wjqc-6w8f-h24c | Medium |
| GHSA-xmv7-r254-6q78 | Medium |
| GHSA-xxqh-mfjm-7mv9 | Medium |
| GO-2026-5016 | Medium |
| GO-2026-5033 | Medium |
| [CVE-2025-11143](https://nvd.nist.gov/vuln/detail/CVE-2025-11143) | Medium |
| [CVE-2025-48924](https://nvd.nist.gov/vuln/detail/CVE-2025-48924) | Medium |
| [CVE-2025-49128](https://nvd.nist.gov/vuln/detail/CVE-2025-49128) | Medium |
| [CVE-2025-53864](https://nvd.nist.gov/vuln/detail/CVE-2025-53864) | Medium |
| [CVE-2026-6653](https://nvd.nist.gov/vuln/detail/CVE-2026-6653) | Medium |
| [CVE-2026-57062](https://nvd.nist.gov/vuln/detail/CVE-2026-57062) | Low |
| ALAS2023-2026-1912 | Low |
| [CVE-2026-22007](https://nvd.nist.gov/vuln/detail/CVE-2026-22007) | Low |
| [CVE-2026-22018](https://nvd.nist.gov/vuln/detail/CVE-2026-22018) | Low |
| [CVE-2026-34268](https://nvd.nist.gov/vuln/detail/CVE-2026-34268) | Low |
| GHSA-45q3-82m4-75jr | Low |

The following CVEs are currently open and will be fixed in future releases. See the exploitability explanations for each of them below.

| Package Name | Type | Vulnerability ID | Severity | Description | Compensating Control |
| --- | --- | --- | --- | --- | --- |
| elasticsearch-9.4-config | chainguard | [CVE-2026-45674](https://nvd.nist.gov/vuln/detail/CVE-2026-45674) | Critical | netty-resolver-dns: Information disclosure and data manipulation due to improper CNAME record validation | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| elasticsearch-9.4-config | chainguard | [CVE-2026-47691](https://nvd.nist.gov/vuln/detail/CVE-2026-47691) | Critical | io.netty/netty-resolver-dns: Netty has Insufficient Bailiwick Validation for NS Records | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| libcrypto3 | chainguard | [CVE-2026-34182](https://nvd.nist.gov/vuln/detail/CVE-2026-34182) | Critical | openssl: CMS AuthEnvelopedData Processing May Accept Forged Messages | This vulnerability can be exploited only if Pod software is configured to rely on unsigned or untrusted CMS messaging payloads from external actors. |
| minio | chainguard | [CVE-2026-33322](https://nvd.nist.gov/vuln/detail/CVE-2026-33322) | Critical | MinIO has JWT Algorithm Confusion in OIDC Authentication | This vulnerability can be exploited only if unauthorized access to alter internal OIDC validation profile parameters is achieved. |
| glibc | chainguard | [CVE-2026-5450](https://nvd.nist.gov/vuln/detail/CVE-2026-5450) | Critical | glibc: Heap Buffer Overflow in scanf with %mc format specifier and large width | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| libcrypto3 | chainguard | [CVE-2026-31789](https://nvd.nist.gov/vuln/detail/CVE-2026-31789) | Critical | openssl: Heap buffer overflow on 32-bit systems from large X.509 certificate processing | Pod software runs on an isolated 64-bit Linux container platform. 32-bit architecture memory flaws are not applicable. |
| python-3.14 | chainguard | [CVE-2026-6100](https://nvd.nist.gov/vuln/detail/CVE-2026-6100) | Critical | python: Arbitrary code execution or info disclosure via use-after-free in decompression modules | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42579](https://nvd.nist.gov/vuln/detail/CVE-2026-42579) | Critical | netty: High integrity impact due to improper DNS domain name constraint enforcement | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42581](https://nvd.nist.gov/vuln/detail/CVE-2026-42581) | Critical | netty: HTTP Request Smuggling due to improper handling of conflicting HTTP/1.0 headers | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42584](https://nvd.nist.gov/vuln/detail/CVE-2026-42584) | Critical | netty: Incorrect HTTP response parsing leads to data confusion | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit parsing. |
| spark-operator | chainguard | [CVE-2026-39821](https://nvd.nist.gov/vuln/detail/CVE-2026-39821) | Critical | golang.org/x/net/idna: Privilege escalation via incorrect Punycode label processing | Pod software components run as a non-root system identity configuration; there is no path for execution parsing to alter parent namespace privileges. |
| gnutls | amazon | [CVE-2026-33845](https://nvd.nist.gov/vuln/detail/CVE-2026-33845) | Critical | gnutls: Denial of Service via DTLS zero-length fragment | Pod software does not open or listen on DTLS protocol pathways exposed to external actors. |
| com.azure:azure-security-keyvault-keys | jar | [CVE-2026-33117](https://nvd.nist.gov/vuln/detail/CVE-2026-33117) | Critical | Security feature bypass vulnerability in Azure Key Vault Keys library for Java | This vulnerability can be exploited only if unauthorized access to overwrite trusted backend endpoint references in application memory is obtained. |
| org.eclipse.jetty:jetty-http | jar | [CVE-2026-2332](https://nvd.nist.gov/vuln/detail/CVE-2026-2332) | Critical | org.eclipse.jetty/jetty-http: HTTP request smuggling via chunked extension quoted-string parsing | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the smuggling anomaly. |
| jupyter_server | python-pkg | [CVE-2026-44727](https://nvd.nist.gov/vuln/detail/CVE-2026-44727) | Critical | Jupyter Server: Stored XSS in NbconvertFileHandler via missing sandbox CSP | Pod software does not expose Jupyter server file interfaces directly to end-user browser components. |
| starlette | python-pkg | [CVE-2026-48710](https://nvd.nist.gov/vuln/detail/CVE-2026-48710) | Critical | starlette: Security restriction bypass via malformed HTTP Host header | Pod software doesn't allow inbound communication initiated by external parties. Internal targets map exclusively to trusted host tracking environments. |
| libcrypto3 | alpine | [CVE-2025-15467](https://nvd.nist.gov/vuln/detail/CVE-2025-15467) | Critical | openssl: Remote code execution or DoS via oversized Initialization Vector in CMS parsing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-68121](https://nvd.nist.gov/vuln/detail/CVE-2025-68121) | Critical | crypto/tls: Incorrect certificate validation during TLS session resumption | Pod software configuration enforces fresh TLS state handshake verification mappings and disables risky stateful session resumption variables. |
| stdlib | gobinary | [CVE-2025-22871](https://nvd.nist.gov/vuln/detail/CVE-2025-22871) | Critical | net/http: Request smuggling due to acceptance of invalid chunked data | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| cryptography | python-pkg | GHSA-537c-gmf6-5ccf | High | Vulnerable OpenSSL included in cryptography wheels | This vulnerability can be exploited only if Pod software is configured to interact with untrusted remote services that serve malicious cryptographic handshake frames or certificates. |
| ecdsa | python-pkg | [CVE-2024-23342](https://nvd.nist.gov/vuln/detail/CVE-2024-23342) | High | python-ecdsa: vulnerable to the Minerva attack | This vulnerability can be exploited only if Pod software is configured to interact with untrusted services that make use of arbitrary certificate chains for SSL. |
| [](https://github.com/prometheus/prometheus)[github.com/prometheus/prometheus](https://github.com/prometheus/prometheus) | gobinary | [CVE-2026-42151](https://nvd.nist.gov/vuln/detail/CVE-2026-42151) | High | Information disclosure of Azure OAuth client secret via config API | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| [](https://github.com/prometheus/prometheus)[github.com/prometheus/prometheus](https://github.com/prometheus/prometheus) | gobinary | [CVE-2026-42154](https://nvd.nist.gov/vuln/detail/CVE-2026-42154) | High | Denial of Service via uncontrolled memory allocation in remote read endpoint | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the remote read endpoint. |
| stdlib | gobinary | [CVE-2026-33811](https://nvd.nist.gov/vuln/detail/CVE-2026-33811) | High | net: golang: Denial of Service via long CNAME response in LookupCNAME | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | gobinary | [CVE-2026-33814](https://nvd.nist.gov/vuln/detail/CVE-2026-33814) | High | When processing HTTP/2 SETTINGS frames; transport will enter an infinite loop... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| stdlib | gobinary | [CVE-2026-39820](https://nvd.nist.gov/vuln/detail/CVE-2026-39820) | High | Well-crafted inputs reaching ParseAddress; ParseAddressList; and ParseDate trigger CPU exhaustion... | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2026-39823](https://nvd.nist.gov/vuln/detail/CVE-2026-39823) | High | CVE-2026-27142 fixed a vulnerability in which URLs were not correctly validated... | Pod software does not render or interpret URL parsing logic inside untrusted client-facing browser contexts. |
| stdlib | gobinary | [CVE-2026-39825](https://nvd.nist.gov/vuln/detail/CVE-2026-39825) | High | ReverseProxy can forward queries containing parameters not visible to... | Pod software does not expose or leverage a reverse proxy interface to forward traffic to backend microservices. |
| stdlib | gobinary | [CVE-2026-39836](https://nvd.nist.gov/vuln/detail/CVE-2026-39836) | High | ELSA-2026-22112: go-toolset security update (The Dial and LookupPort functions panic on Windows) | Pod software runs on an isolated Linux container platform. Windows-specific operating system APIs are not applicable. |
| stdlib | gobinary | [CVE-2026-42499](https://nvd.nist.gov/vuln/detail/CVE-2026-42499) | High | Pathological inputs could cause DoS through consumePhrase when parsing an email address | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2026-42504](https://nvd.nist.gov/vuln/detail/CVE-2026-42504) | High | Decoding a maliciously-crafted MIME header containing many invalid encodings causes DoS | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2026-39826](https://nvd.nist.gov/vuln/detail/CVE-2026-39826) | High | html/template: Cross-site scripting due to incorrect script tag escaping | Pod software does not parse or serve dynamic HTML templates directly to untrusted web browsers. |
| elasticsearch-9.4-config | chainguard | [CVE-2026-44249](https://nvd.nist.gov/vuln/detail/CVE-2026-44249) | High | netty-handler: IPv6 subnet rule bypass due to incorrect masking operation | Pod software network reachability parameters navigate only to explicit internal target networks via infrastructure firewall filtering. |
| elasticsearch-9.4-config | chainguard | [CVE-2026-45416](https://nvd.nist.gov/vuln/detail/CVE-2026-45416) | High | netty-handler: Denial of Service due to eager buffer allocation in TLS handshake | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to manipulate TLS handshakes. |
| elasticsearch-9.4-config | chainguard | [CVE-2026-48043](https://nvd.nist.gov/vuln/detail/CVE-2026-48043) | High | netty-codec-http2: Denial of Service due to resource leak | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| elasticsearch-9.4-config | chainguard | [CVE-2026-50010](https://nvd.nist.gov/vuln/detail/CVE-2026-50010) | High | netty-handler: Improper trust manager handling leads to hostname verification bypass | This vulnerability can be exploited only if Pod software is configured to interact with untrusted service endpoints that serve invalid matching certificates. |
| libcrypto3 | chainguard | [CVE-2026-45447](https://nvd.nist.gov/vuln/detail/CVE-2026-45447) | High | openssl: Heap Use-After-Free in OpenSSL PKCS7_verify() | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-34183](https://nvd.nist.gov/vuln/detail/CVE-2026-34183) | High | openssl: Unbounded Memory Growth in the QUIC PATH_CHALLENGE Handler | Pod software does not implement or rely on the vulnerable OpenSSL QUIC stack elements for external routing protocols. |
| libcrypto3 | chainguard | [CVE-2026-42764](https://nvd.nist.gov/vuln/detail/CVE-2026-42764) | High | openssl: NULL pointer dereference in QUIC server initial packet handling | Pod software does not implement or expose OpenSSL QUIC server processing listeners to inbound external calls. |
| libcrypto3 | chainguard | [CVE-2026-45445](https://nvd.nist.gov/vuln/detail/CVE-2026-45445) | High | openssl: AES-OCB IV Ignored on EVP_Cipher() Path | Pod software does not use the specific cryptographic OCB block cipher mode pathways inside application implementations. |
| libcrypto3 | chainguard | [CVE-2026-34180](https://nvd.nist.gov/vuln/detail/CVE-2026-34180) | High | openssl: Heap buffer over-read in ASN.1 decoding can lead to denial of service | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-34181](https://nvd.nist.gov/vuln/detail/CVE-2026-34181) | High | openssl: PKCS#12 Files with PBMAC1 Are Accepted with Short HMAC Keys | This vulnerability can be exploited only if Pod software handles untrusted, externally-supplied PKCS#12 configuration profiles. |
| libcrypto3 | chainguard | [CVE-2026-42765](https://nvd.nist.gov/vuln/detail/CVE-2026-42765) | High | openssl: Vulnerability when partial-chain certificate verification is enabled... | This vulnerability can be exploited only if Pod software is configured with custom, insecure non-standard partial-chain certificate paths. |
| libcrypto3 | chainguard | [CVE-2026-42766](https://nvd.nist.gov/vuln/detail/CVE-2026-42766) | High | openssl: Possible NULL Dereference in Password-Based CMS Decryption | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-42767](https://nvd.nist.gov/vuln/detail/CVE-2026-42767) | High | openssl: NULL Pointer Dereference in CRMF EncryptedValue Decryption | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-42768](https://nvd.nist.gov/vuln/detail/CVE-2026-42768) | High | openssl: Multi-RecipientInfo Bleichenbacher Oracle in CMS_decrypt() and PKCS7_decrypt() | Pod software does not expose decryption operations or side-channel parsing vectors directly to external actors. |
| libcrypto3 | chainguard | [CVE-2026-42769](https://nvd.nist.gov/vuln/detail/CVE-2026-42769) | High | openssl: Trust-Anchor Substitution via cert/issuer Typo in CMP rootCaKeyUpdate | This vulnerability can be exploited only if Pod software is configured to use the CMP root identity certificate synchronization feature against untrusted endpoints. |
| libcrypto3 | chainguard | [CVE-2026-42770](https://nvd.nist.gov/vuln/detail/CVE-2026-42770) | High | openssl: FFC-DH Peer Validation Uses Attacker-Supplied q | This vulnerability can be exploited only if Pod software establishes Diffie-Hellman handshakes using unvalidated target group key pairs. |
| libcrypto3 | chainguard | [CVE-2026-45446](https://nvd.nist.gov/vuln/detail/CVE-2026-45446) | High | openssl: Incorrect Tag Processing for Empty Messages in AES-GCM-SIV and AES-SIV modes | Pod software does not utilize the affected AES-GCM-SIV string block processing mechanisms inside internal business architectures. |
| libcrypto3 | chainguard | [CVE-2026-7383](https://nvd.nist.gov/vuln/detail/CVE-2026-7383) | High | openssl: Heap buffer overflow due to signed integer overflow in Unicode output sizing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-9076](https://nvd.nist.gov/vuln/detail/CVE-2026-9076) | High | openssl: Denial of Service due to heap out-of-bounds read in CMS password-based decryption | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| minio | chainguard | [CVE-2026-40344](https://nvd.nist.gov/vuln/detail/CVE-2026-40344) | High | MinIO has an Unauthenticated Object Write via Missing Signature Verification | Pod software doesn't allow inbound communication initiated by external parties; write metrics and access functions are securely contained inside internal boundaries. |
| busybox | chainguard | [CVE-2023-39810](https://nvd.nist.gov/vuln/detail/CVE-2023-39810) | High | busybox: CPIO command allows directory traversal | Pod software does not execute or evaluate untrusted CPIO extraction archives within local terminal runtimes. |
| busybox | chainguard | [CVE-2026-26157](https://nvd.nist.gov/vuln/detail/CVE-2026-26157) | High | busybox: Arbitrary file overwrite and potential code execution via incomplete path sanitization | This vulnerability can be exploited only if unauthorized access to the pod is obtained to invoke internal file utilities against crafted file configurations. |
| busybox | chainguard | [CVE-2026-26158](https://nvd.nist.gov/vuln/detail/CVE-2026-26158) | High | busybox: Arbitrary file modification via unvalidated tar archive entries | Pod software retries scanning on a malicious archive file a couple of times and moves on; the container environment is entirely stateless and ephemeral. |
| glibc | chainguard | [CVE-2026-4046](https://nvd.nist.gov/vuln/detail/CVE-2026-4046) | High | glibc: Denial of Service via iconv() function with specific character sets | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| glibc | chainguard | [CVE-2026-4437](https://nvd.nist.gov/vuln/detail/CVE-2026-4437) | High | glibc: Incorrect DNS response parsing via crafted DNS server response | Pod software doesn't allow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| glibc | chainguard | [CVE-2026-5928](https://nvd.nist.gov/vuln/detail/CVE-2026-5928) | High | glibc: Information disclosure or denial of service via ungetwc function | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-28386](https://nvd.nist.gov/vuln/detail/CVE-2026-28386) | High | openssl: Denial of Service due to out-of-bounds read in AES-CFB128 | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-28387](https://nvd.nist.gov/vuln/detail/CVE-2026-28387) | High | openssl: Arbitrary code execution due to use-after-free in DANE TLSA authentication | Pod software does not utilize DANE TLSA protocol implementations for connection validations. |
| libcrypto3 | chainguard | [CVE-2026-28388](https://nvd.nist.gov/vuln/detail/CVE-2026-28388) | High | openssl: Denial of Service due to NULL pointer dereference in delta CRL processing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-28389](https://nvd.nist.gov/vuln/detail/CVE-2026-28389) | High | openssl: Denial of Service vulnerability in CMS processing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-28390](https://nvd.nist.gov/vuln/detail/CVE-2026-28390) | High | openssl: Denial of Service due to NULL pointer dereference in CMS EnvelopedData processing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-2673](https://nvd.nist.gov/vuln/detail/CVE-2026-2673) | High | openssl: OpenSSL TLS 1.3 server may choose unexpected key agreement group | Pod software does not expose inbound TLS server listeners to unvalidated external callers. |
| libcrypto3 | chainguard | [CVE-2026-31790](https://nvd.nist.gov/vuln/detail/CVE-2026-31790) | High | openssl: Information Disclosure from Uninitialized Memory via Invalid RSA Public Key | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-22016](https://nvd.nist.gov/vuln/detail/CVE-2026-22016) | High | openjdk: Enhance Path Factories Redux | This vulnerability can be exploited only if unauthorized access to the pod is obtained to supply malicious filesystem paths. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-34282](https://nvd.nist.gov/vuln/detail/CVE-2026-34282) | High | openjdk: Enhance TLS connection handling | Pod software doesn't allow inbound communication initiated by external parties. Outbound TLS targets only explicit internal target destinations. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-22013](https://nvd.nist.gov/vuln/detail/CVE-2026-22013) | High | openjdk: Improve Kerberos credentialing | Pod software does not leverage or reference Kerberos configuration elements for operational lifecycle management. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-22021](https://nvd.nist.gov/vuln/detail/CVE-2026-22021) | High | openjdk: Enhance certificate chain validation | This vulnerability can be exploited only if Pod software is configured to interact with untrusted upstream endpoints using malicious certificate chains. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-23865](https://nvd.nist.gov/vuln/detail/CVE-2026-23865) | High | freetype: Information disclosure or denial of service via specially crafted font files | Pod software does not unpack, process, or render custom font file components inside internal execution loops. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-22007](https://nvd.nist.gov/vuln/detail/CVE-2026-22007) | High | openjdk: Enhance crypto algorithm support | This vulnerability can be exploited only if unauthorized access to the pod is obtained to alter cryptographic system algorithm defaults. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-22018](https://nvd.nist.gov/vuln/detail/CVE-2026-22018) | High | openjdk: Enhance Zip file reading | Pod software retries scanning on a malicious archive a couple of times and moves on; The processes will restart and pick up remaining work. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-34268](https://nvd.nist.gov/vuln/detail/CVE-2026-34268) | High | openjdk: Enhance key generation | This vulnerability can be exploited only if unauthorized access to the pod is obtained to monitor local cryptographic keys in memory. |
| py3-pip-wheel | chainguard | [CVE-2025-66418](https://nvd.nist.gov/vuln/detail/CVE-2025-66418) | High | urllib3: Unbounded decompression chain leads to resource exhaustion | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| py3-pip-wheel | chainguard | [CVE-2025-66471](https://nvd.nist.gov/vuln/detail/CVE-2025-66471) | High | urllib3: Streaming API improperly handles highly compressed data | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| py3-pip-wheel | chainguard | [CVE-2026-21441](https://nvd.nist.gov/vuln/detail/CVE-2026-21441) | High | urllib3: Decompression-bomb safeguard bypass when following HTTP redirects | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| py3-pip-wheel | chainguard | [CVE-2026-44432](https://nvd.nist.gov/vuln/detail/CVE-2026-44432) | High | urllib3: Denial of Service due to excessive HTTP response decompression | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| py3-pip-wheel | chainguard | [CVE-2026-44431](https://nvd.nist.gov/vuln/detail/CVE-2026-44431) | High | urllib3: Information disclosure via cross-origin redirects forwarding sensitive headers | Pod software outbound parameters navigate only to explicit internal allowlists; target routing endpoints do not jump origins. |
| py3-pip-wheel | chainguard | [CVE-2026-6357](https://nvd.nist.gov/vuln/detail/CVE-2026-6357) | High | pip: Arbitrary code execution via malicious wheel package installation | Pod software components do not ingest or install wheel packages dynamically inside running system containers. |
| python-3.14 | chainguard | [CVE-2026-3644](https://nvd.nist.gov/vuln/detail/CVE-2026-3644) | High | cpython: Incomplete control character validation in http.cookies | Pod software doesn't allow inbound communication initiated by external parties. Hence, cookie parsing streams are not reachable by external actors. |
| python-3.14 | chainguard | [CVE-2026-4224](https://nvd.nist.gov/vuln/detail/CVE-2026-4224) | High | cpython: Stack overflow parsing XML with deeply nested DTD content models | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| python-3.14 | chainguard | [CVE-2026-4786](https://nvd.nist.gov/vuln/detail/CVE-2026-4786) | High | python: Arbitrary code execution via command injection in webbrowser.open() API | This vulnerability can be exploited only if unauthorized access to the pod is obtained to force browser invocation loops. |
| python-3.14 | chainguard | [CVE-2026-7210](https://nvd.nist.gov/vuln/detail/CVE-2026-7210) | High | python: expat: Denial of Service via crafted XML document | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| python-3.14 | chainguard | [CVE-2026-1502](https://nvd.nist.gov/vuln/detail/CVE-2026-1502) | High | python: HTTP header injection via CR/LF in proxy tunnel headers | Pod software outbound proxy targets point strictly to validated, unmanipulated configuration variables. |
| python-3.14 | chainguard | [CVE-2026-9669](https://nvd.nist.gov/vuln/detail/CVE-2026-9669) | High | python: Denial of Service via out-of-bounds write in BZ2 decompression | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| python-3.14 | chainguard | [CVE-2026-2297](https://nvd.nist.gov/vuln/detail/CVE-2026-2297) | High | cpython: Logging Bypass in Legacy .pyc File Handling | This vulnerability can be exploited only if unauthorized access to the pod is obtained to introduce legacy precompiled code modules. |
| python-3.14 | chainguard | [CVE-2026-3479](https://nvd.nist.gov/vuln/detail/CVE-2026-3479) | High | python pkgutil.get_data(): Path Traversal via improper resource argument validation | This vulnerability can be exploited only if unauthorized access to the pod is obtained to manipulate local application execution configurations. |
| python-3.14 | chainguard | [CVE-2026-4519](https://nvd.nist.gov/vuln/detail/CVE-2026-4519) | High | python: Command-line option injection in webbrowser.open() via crafted URLs | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2025-66566](https://nvd.nist.gov/vuln/detail/CVE-2025-66566) | High | lz4-java: Information Disclosure via Insufficient Output Buffer Clearing | Pod software retries scanning on a malicious file a couple of times and moves on; the transient container runs inside an isolated, non-shared perimeter. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2025-67721](https://nvd.nist.gov/vuln/detail/CVE-2025-67721) | High | aircompressor Snappy and LZ4 Java-based decompressor can leak info from reused buffers | Pod software retries scanning on a malicious file a couple of times and moves on; transient memory scopes are destroyed upon container termination. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-0636](https://nvd.nist.gov/vuln/detail/CVE-2026-0636) | High | bouncycastle: BC-JAVA: LDAP injection vulnerability in LDAPStoreHelper.java | Pod software does not perform directory querying actions using the vulnerable bouncycastle LDAP helper components. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-24281](https://nvd.nist.gov/vuln/detail/CVE-2026-24281) | High | Apache ZooKeeper: Impersonation of servers or clients via reverse DNS spoofing | Pod software targets specific, hardcoded cluster IP definitions; it does not authorize topology validation via reverse PTR resolution lookup structures. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-24308](https://nvd.nist.gov/vuln/detail/CVE-2026-24308) | High | Apache ZooKeeper: Information disclosure via improper handling of configuration values | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-33870](https://nvd.nist.gov/vuln/detail/CVE-2026-33870) | High | io.netty/netty-codec-http: Request smuggling via incorrect parsing of HTTP/1.1 chunked values | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to pass malformed extensions. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-33871](https://nvd.nist.gov/vuln/detail/CVE-2026-33871) | High | netty: Denial of Service via HTTP/2 CONTINUATION frame floods | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to flood communication structures. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-34478](https://nvd.nist.gov/vuln/detail/CVE-2026-34478) | High | Apache Log4j Core: Log injection via CRLF sequences due to configuration attribute renames | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to inject tracking arguments. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-34479](https://nvd.nist.gov/vuln/detail/CVE-2026-34479) | High | Apache Log4j 1-to-Log4j 2 bridge: Log processing DoS due to improper XML escaping | Pod software does not implement or rely on the vulnerable configuration layout frameworks for active log pipelines. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-34480](https://nvd.nist.gov/vuln/detail/CVE-2026-34480) | High | Apache Log4j Core: Invalid XML output causes denial of service in logging | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-34481](https://nvd.nist.gov/vuln/detail/CVE-2026-34481) | High | Apache Log4j JsonTemplateLayout: Denial of Service via invalid JSON output | Pod software does not implement or leverage the JsonTemplateLayout structure parameters inside operational logging pipelines. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42577](https://nvd.nist.gov/vuln/detail/CVE-2026-42577) | High | Netty asynchronous event-driven framework vulnerability... | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to target netty routines. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42578](https://nvd.nist.gov/vuln/detail/CVE-2026-42578) | High | netty: HTTP Header Injection via HttpProxyHandler Disabled Validation | Pod software does not route out bound tracking metrics via proxy entities utilizing unvalidated request mapping arguments. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42583](https://nvd.nist.gov/vuln/detail/CVE-2026-42583) | High | Netty context propagation flaw... | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42585](https://nvd.nist.gov/vuln/detail/CVE-2026-42585) | High | netty: Request smuggling via malformed Transfer-Encoding parsing | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit request boundaries. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42587](https://nvd.nist.gov/vuln/detail/CVE-2026-42587) | High | netty: Denial of Service via unbounded memory allocation in HTTP content decompression | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-43869](https://nvd.nist.gov/vuln/detail/CVE-2026-43869) | High | Apache Thrift: Security bypass due to improper certificate validation | This vulnerability can be exploited only if Pod software is configured to leverage Thrift client handshakes against untrusted target backends. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-5598](https://nvd.nist.gov/vuln/detail/CVE-2026-5598) | High | bouncycastle: BC-JAVA: private key leakage via non-constant time comparisons | Pod software executes inside secure container perimeters; localized runtime loops do not expose timing metrics out to public networks. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2025-12183](https://nvd.nist.gov/vuln/detail/CVE-2025-12183) | High | lz4-java: Out-of-bounds memory operations lead to denial of service | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| spark-operator | chainguard | [CVE-2026-25679](https://nvd.nist.gov/vuln/detail/CVE-2026-25679) | High | net/url: Incorrect parsing of IPv6 host literals in net/url | Pod software navigates exclusively through structured configuration properties; it does not parse dynamic unvalidated IPv6 URL strings from external contexts. |
| spark-operator | chainguard | [CVE-2026-27140](https://nvd.nist.gov/vuln/detail/CVE-2026-27140) | High | cmd/go: Arbitrary Code Execution via malicious SWIG file names | Pod software components do not compilation-build or execute go tool evaluation pathways during production run steps. |
| spark-operator | chainguard | [CVE-2026-29181](https://nvd.nist.gov/vuln/detail/CVE-2026-29181) | High | [](https://github.com/open-telemetry/opentelemetry-go)[github.com/open-telemetry/opentelemetry-go](https://github.com/open-telemetry/opentelemetry-go): DoS via crafted multi-value baggage headers | Pod software doesn't allow inbound communication initiated by external parties. Trace header ingestion loops are managed purely inside trusted localized perimeters. |
| spark-operator | chainguard | [CVE-2026-32280](https://nvd.nist.gov/vuln/detail/CVE-2026-32280) | High | crypto/x509: Denial of Service vulnerability in certificate chain building | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to pass complex target validation paths. |
| spark-operator | chainguard | [CVE-2026-32281](https://nvd.nist.gov/vuln/detail/CVE-2026-32281) | High | crypto/x509: Denial of Service via inefficient certificate chain validation | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to trigger processing delays. |
| spark-operator | chainguard | [CVE-2026-32283](https://nvd.nist.gov/vuln/detail/CVE-2026-32283) | High | crypto/tls: Denial of Service via multiple TLS 1.3 key update messages | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to flood key update events. |
| spark-operator | chainguard | [CVE-2026-42501](https://nvd.nist.gov/vuln/detail/CVE-2026-42501) | High | A malicious module proxy can exploit a flaw in the go command's validation... | This vulnerability can be exploited only if Pod software is configured to interact with untrusted upstream module proxies during runtime operations. |
| spark-operator | chainguard | [CVE-2026-39817](https://nvd.nist.gov/vuln/detail/CVE-2026-39817) | High | The "go tool pack" subcommand vulnerability... | Pod software components do not invoke compilation tools or target file creation tools inside operational loops. |
| spark-operator | chainguard | [CVE-2026-39819](https://nvd.nist.gov/vuln/detail/CVE-2026-39819) | High | The "go bug" command writes to two files with predictable names... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to view local debugging temporary directories. |
| spark-operator | chainguard | [CVE-2026-27139](https://nvd.nist.gov/vuln/detail/CVE-2026-27139) | High | os: FileInfo can escape from a Root in golang os module | This vulnerability can be exploited only if unauthorized access to the pod is obtained to invoke chroot file escapes via terminal manipulation. |
| libsolv | amazon | [CVE-2026-48863](https://nvd.nist.gov/vuln/detail/CVE-2026-48863) | High | libsolv: Stack-based buffer overflow in libsolv EdDSA PGP signature verification | Pod software components do not evaluate PGP signature payloads inside automated system metadata checking loops. |
| libsolv | amazon | [CVE-2026-48864](https://nvd.nist.gov/vuln/detail/CVE-2026-48864) | High | libsolv: Heap buffer overflow in libsolv repopagestore via unchecked decompression | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libsolv | amazon | [CVE-2026-9149](https://nvd.nist.gov/vuln/detail/CVE-2026-9149) | High | libsolv: Heap buffer overflow in libsolv repo_add_solv via negative maxsize | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libsolv | amazon | [CVE-2026-9150](https://nvd.nist.gov/vuln/detail/CVE-2026-9150) | High | libsolv: Stack-based buffer overflow in libsolv's Debian metadata parser | Pod software components do not read or interpret debian package configuration descriptors during application execution. |
| aiohttp | python-pkg | [CVE-2026-34993](https://nvd.nist.gov/vuln/detail/CVE-2026-34993) | High | aiohttp: Arbitrary code execution via untrusted input to CookieJar.load() | This vulnerability can be exploited only if unauthorized access to the pod is obtained to feed malformed state persistence profiles into cookie parsing. |
| aiohttp | python-pkg | [CVE-2026-47265](https://nvd.nist.gov/vuln/detail/CVE-2026-47265) | High | python-aiohttp: Information disclosure via improper handling of cookies during redirects | Pod software outbound configuration options point to explicit matching destination targets; it does not trigger random redirects outside trust realms. |
| nltk | python-pkg | [CVE-2026-54293](https://nvd.nist.gov/vuln/detail/CVE-2026-54293) | High | Natural Language Toolkit: URL-Encoded Path Traversal in nltk.data.load() | This vulnerability can be exploited only if unauthorized access to the pod is obtained to force local resource file path loading arguments. |
| gnutls | amazon | [CVE-2026-42011](https://nvd.nist.gov/vuln/detail/CVE-2026-42011) | High | gnutls: Security bypass due to incorrect name constraint handling | This vulnerability can be exploited only if Pod software is configured to connect to untrusted endpoints utilizing custom name constraint routing fields. |
| gnutls | amazon | [CVE-2026-42012](https://nvd.nist.gov/vuln/detail/CVE-2026-42012) | High | gnutls: Certificate validation bypass due to improper handling of URI and SRV SANs | This vulnerability can be exploited only if Pod software targets external unverified domains hosting custom URI/SRV SAN identifiers. |
| gnutls | amazon | [CVE-2026-42013](https://nvd.nist.gov/vuln/detail/CVE-2026-42013) | High | gnutls: Certificate validation bypass due to oversized Subject Alternative Name | This vulnerability can be exploited only if Pod software is configured to validate untrusted infrastructure components using malicious oversized certificates. |
| gnutls | amazon | [CVE-2026-5419](https://nvd.nist.gov/vuln/detail/CVE-2026-5419) | High | gnutls: Information disclosure via timing side-channel in PKCS#7 padding removal | Pod software executes computations inside isolated networks; timing variances are not visible or measurable from public tracking contexts. |
| libssh2 | amazon | [CVE-2026-7598](https://nvd.nist.gov/vuln/detail/CVE-2026-7598) | High | libssh2: integer overflow via large username or password arguments | Pod software communicates strictly with pre-authenticated internal SSH host keys using hardcoded length-controlled identity strings. |
| io.netty:netty-codec-classes-quic | jar | [CVE-2026-44894](https://nvd.nist.gov/vuln/detail/CVE-2026-44894) | High | netty-codec-classes-quic: Netty: Denial of Service amplification via improper QUIC token validation | Pod software does not leverage or expose QUIC validation transport listeners to external environments. |
| io.netty:netty-codec-haproxy | jar | [CVE-2026-44893](https://nvd.nist.gov/vuln/detail/CVE-2026-44893) | High | netty-codec-haproxy: Denial of Service via malformed HAProxy message | Pod software does not ingest raw HAProxy PROXY header protocols directly from external public ingress paths. |
| io.netty:netty-codec-haproxy | jar | [CVE-2026-48059](https://nvd.nist.gov/vuln/detail/CVE-2026-48059) | High | netty-codec-haproxy: Denial of Service via memory leak from crafted PROXY protocol headers | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| io.netty:netty-codec-http3 | jar | [CVE-2026-44892](https://nvd.nist.gov/vuln/detail/CVE-2026-44892) | High | Netty framework HTTP/3 codec validation defect... | Pod software does not process or open HTTP/3 network sockets accessible to untrusted networks. |
| io.netty:netty-codec-http3 | jar | [CVE-2026-48748](https://nvd.nist.gov/vuln/detail/CVE-2026-48748) | High | netty: Denial of Service due to memory exhaustion in HTTP/3 codec | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| io.netty:netty-codec-redis | jar | [CVE-2026-44250](https://nvd.nist.gov/vuln/detail/CVE-2026-44250) | High | netty-codec-redis: Denial of Service via crafted Redis payload with deeply nested arrays | Pod software connects exclusively to a dedicated internal Redis cluster; parsing logic is not accessible to external inputs. |
| io.netty:netty-codec-redis | jar | [CVE-2026-44890](https://nvd.nist.gov/vuln/detail/CVE-2026-44890) | High | netty-codec-redis: Denial of Service via crafted Redis payloads | Pod software processes are isolated; inner tracking data communication pathways are inaccessible to external callers. |
| io.netty:netty-codec-redis | jar | [CVE-2026-48006](https://nvd.nist.gov/vuln/detail/CVE-2026-48006) | High | netty-codec-redis: Pooled ByteBuf Leak in RedisArrayAggregator | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| io.netty:netty-codec-redis | jar | [CVE-2026-50011](https://nvd.nist.gov/vuln/detail/CVE-2026-50011) | High | netty-codec-redis: Denial of Service via malicious Redis array header | Pod software connects exclusively to verified internal infrastructure; parsing layers are not reachable by external callers. |
| io.netty:netty-transport-sctp | jar | [CVE-2026-46340](https://nvd.nist.gov/vuln/detail/CVE-2026-46340) | High | netty-transport-sctp: Denial of Service due to unbounded memory growth from SctpMessage fragments | Pod software does not activate or use SCTP transport sockets across running application frameworks. |
| io.opentelemetry:opentelemetry-api | jar | [CVE-2026-45292](https://nvd.nist.gov/vuln/detail/CVE-2026-45292) | High | opentelemetry-java: Denial of Service due to unbounded memory allocation when parsing oversized baggage | Pod software retries scanning on a malicious telemetry string a couple of times and moves on; The processes will restart and pick up remaining work. |
| org.jline:jline-remote-telnet | jar | GHSA-2r2c-cx56-8933 | High | JLine3 Telnet server: Unauthenticated Remote DoS via Unbounded Telnet NAWS Terminal Geometry | Pod software does not deploy or activate unauthenticated Telnet servers inside active runtime perimeters. |
| org.jline:jline-remote-telnet | jar | GHSA-47qp-hqvx-6r3f | High | JLine3 Telnet server: Unauthenticated Remote Memory Exhaustion via Unbounded Telnet NEW-ENVIRON Variables | Pod software does not expose Telnet server interfaces to external public access profiles. |
| pyarrow | python-pkg | [CVE-2026-25087](https://nvd.nist.gov/vuln/detail/CVE-2026-25087) | High | apache-arrow: Denial of Service via Use After Free vulnerability when reading IPC files | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| starlette | python-pkg | [CVE-2026-48818](https://nvd.nist.gov/vuln/detail/CVE-2026-48818) | High | starlette: SSRF and NTLM credential theft via UNC paths in StaticFiles on Windows | Pod software runs on an isolated Linux container platform. Windows-specific UNC handling paths are not applicable. |
| starlette | python-pkg | [CVE-2026-54283](https://nvd.nist.gov/vuln/detail/CVE-2026-54283) | High | Starlette: request.form() limits silently ignored for form-urlencoded enable DoS | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to send form floods. |
| PyJWT | python-pkg | [CVE-2026-48526](https://nvd.nist.gov/vuln/detail/CVE-2026-48526) | High | python-pyjwt: Authentication bypass due to forged JSON Web Tokens | Pod software validates cryptographic identities exclusively through explicit signing keys obtained from a verified local vault service. |
| python-multipart | python-pkg | [CVE-2026-53539](https://nvd.nist.gov/vuln/detail/CVE-2026-53539) | High | python-multipart: Quadratic-time querystring parsing causes CPU denial of service | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2024-12797](https://nvd.nist.gov/vuln/detail/CVE-2024-12797) | High | openssl: RFC7250 handshakes with unauthenticated servers don't abort as expected | Pod software connection definitions require explicit, fully-authenticated mutual TLS configurations; unauthenticated fallback is disabled. |
| libcrypto3 | alpine | [CVE-2025-69421](https://nvd.nist.gov/vuln/detail/CVE-2025-69421) | High | openssl: Denial of Service via malformed PKCS#12 file processing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2025-69419](https://nvd.nist.gov/vuln/detail/CVE-2025-69419) | High | openssl: Arbitrary code execution due to out-of-bounds write in PKCS#12 processing | This vulnerability can be exploited only if unauthorized access to the pod is obtained to load local identity files. |
| libcrypto3 | alpine | [CVE-2025-9230](https://nvd.nist.gov/vuln/detail/CVE-2025-9230) | High | openssl: Out-of-bounds read & write in RFC 3211 KEK Unwrap | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2025-15468](https://nvd.nist.gov/vuln/detail/CVE-2025-15468) | High | openssl: Denial of Service via NULL pointer dereference in QUIC protocol handling | Pod software does not apply or expose OpenSSL QUIC interfaces to external calling perimeters. |
| libcrypto3 | alpine | [CVE-2025-66199](https://nvd.nist.gov/vuln/detail/CVE-2025-66199) | High | openssl: Denial of Service due to excessive memory allocation in TLS 1.3 certificate compression | Pod software retries scanning on a malicious handshake attempt a couple of times and moves on; runtime cgroup boundaries clamp resource consumption. |
| libcrypto3 | alpine | [CVE-2025-68160](https://nvd.nist.gov/vuln/detail/CVE-2025-68160) | High | openssl: Denial of Service due to out-of-bounds write in BIO filter | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2025-69418](https://nvd.nist.gov/vuln/detail/CVE-2025-69418) | High | openssl: Info disclosure via specific low-level OCB encryption/decryption calls | Pod software does not call the low-level vulnerable OpenSSL OCB cipher variants inside internal code logic frameworks. |
| libcrypto3 | alpine | [CVE-2025-69420](https://nvd.nist.gov/vuln/detail/CVE-2025-69420) | High | openssl: Denial of Service via malformed TimeStamp Response | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2026-22795](https://nvd.nist.gov/vuln/detail/CVE-2026-22795) | High | openssl: Denial of Service due to type confusion in PKCS#12 file processing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2026-22796](https://nvd.nist.gov/vuln/detail/CVE-2026-22796) | High | openssl: Denial of Service via type confusion in PKCS#7 signature verification | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| musl | alpine | [CVE-2025-26519](https://nvd.nist.gov/vuln/detail/CVE-2025-26519) | High | musl libc 0.9.13 through 1.2.5 has an out-of-bounds write... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to invoke low-level memory allocation manipulations. |
| musl | alpine | [CVE-2026-40200](https://nvd.nist.gov/vuln/detail/CVE-2026-40200) | High | musl: Arbitrary code execution and DoS via stack-based memory corruption in qsort | Pod software processes are isolated; sorting arrays operate completely on predictable internal application data formats. |
| zlib | alpine | [CVE-2026-22184](https://nvd.nist.gov/vuln/detail/CVE-2026-22184) | High | zlib: Arbitrary code execution via buffer overflow in untgz utility | Pod software do not use or shell-execute the untgz command line helper tool within runtime environments. |
| [](http://golang.org/x/net)[golang.org/x/net](http://golang.org/x/net) | gobinary | [CVE-2025-22872](https://nvd.nist.gov/vuln/detail/CVE-2025-22872) | High | golang.org/x/net/html: Incorrect Neutralization of Input During Web Page Generation | Pod software logic functions do not stream dynamically built web page templates back into client-side browser windows. |
| stdlib | gobinary | [CVE-2025-61726](https://nvd.nist.gov/vuln/detail/CVE-2025-61726) | High | golang: net/url: Memory exhaustion in query parameter parsing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-61729](https://nvd.nist.gov/vuln/detail/CVE-2025-61729) | High | crypto/x509: Denial of Service due to excessive resource consumption via crafted certificates | Pod software doesn't allow inbound communication initiated by external parties. Outbound connection validation hooks point strictly to pre-authenticated keys. |
| stdlib | gobinary | [CVE-2024-45336](https://nvd.nist.gov/vuln/detail/CVE-2024-45336) | High | golang: net/http: sensitive headers incorrectly sent after cross-domain redirect | Pod software outbound parameters map strictly to specific internal endpoints; connection loops are restricted from executing cross-domain shifts. |
| stdlib | gobinary | [CVE-2025-4673](https://nvd.nist.gov/vuln/detail/CVE-2025-4673) | High | net/http: Sensitive headers not cleared on cross-origin redirect | Pod software outbound connection calls terminate strictly on explicit static targets, omitting cross-origin jump actions. |
| stdlib | gobinary | [CVE-2025-47906](https://nvd.nist.gov/vuln/detail/CVE-2025-47906) | High | os/exec: Unexpected paths returned from LookPath in os/exec | This vulnerability can be exploited only if unauthorized access to the pod is obtained to skew system environment PATH parameters locally. |
| stdlib | gobinary | [CVE-2025-47907](https://nvd.nist.gov/vuln/detail/CVE-2025-47907) | High | database/sql: Postgres Scan Race Condition | Pod software business data handlers apply thread-safe localized structures when querying across target repository connections. |
| stdlib | gobinary | [CVE-2025-47912](https://nvd.nist.gov/vuln/detail/CVE-2025-47912) | High | net/url: Insufficient validation of bracketed IPv6 hostnames | Pod software relies entirely on specific pre-validated URL parameters; untrusted bracket parsing strings are rejected at the edge gateway. |
| stdlib | gobinary | [CVE-2025-58183](https://nvd.nist.gov/vuln/detail/CVE-2025-58183) | High | golang: archive/tar: Unbounded allocation when parsing GNU sparse map | Pod software retries scanning on a malicious archive file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-58185](https://nvd.nist.gov/vuln/detail/CVE-2025-58185) | High | encoding/asn1: Parsing DER payload can cause memory exhaustion | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-58187](https://nvd.nist.gov/vuln/detail/CVE-2025-58187) | High | crypto/x509: Quadratic complexity when checking name constraints | Pod software doesn't allow inbound communication initiated by external parties. Hence, there is no scope for an external caller to pass complex target verification paths. |
| stdlib | gobinary | [CVE-2025-58188](https://nvd.nist.gov/vuln/detail/CVE-2025-58188) | High | crypto/x509: Panic when validating certificates with DSA public keys | Pod software doesn't allow inbound communication initiated by external parties; external untrusted certificates are rejected. |
| stdlib | gobinary | [CVE-2025-58189](https://nvd.nist.gov/vuln/detail/CVE-2025-58189) | High | crypto/tls: go crypto/tls ALPN negotiation error contains attacker controlled information | Pod software doesn't allow inbound communication initiated by external parties. Local system configuration filters reject random ALPN parameters. |
| stdlib | gobinary | [CVE-2025-61723](https://nvd.nist.gov/vuln/detail/CVE-2025-61723) | High | encoding/pem: Quadratic complexity when parsing some invalid inputs | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-61724](https://nvd.nist.gov/vuln/detail/CVE-2025-61724) | High | net/textproto: Excessive CPU consumption in Reader.ReadResponse | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-61725](https://nvd.nist.gov/vuln/detail/CVE-2025-61725) | High | net/mail: Excessive CPU consumption in ParseAddress in net/mail | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-61727](https://nvd.nist.gov/vuln/detail/CVE-2025-61727) | High | golang: crypto/x509: excluded subdomain constraint does not restrict wildcard SANs | Pod software connections utilize strict explicit routing maps rather than reliance on complex wildcard subdomain fallback parsing. |
| stdlib | gobinary | [CVE-2025-61728](https://nvd.nist.gov/vuln/detail/CVE-2025-61728) | High | golang: archive/zip: Excessive CPU consumption when building archive index | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-61730](https://nvd.nist.gov/vuln/detail/CVE-2025-61730) | High | crypto/tls: Handshake messages may be processed at the incorrect encryption level | Pod software doesn't allow inbound communication initiated by external parties. Outbound endpoints connect via dedicated TLS profiles. |
| stdlib | gobinary | [CVE-2026-27142](https://nvd.nist.gov/vuln/detail/CVE-2026-27142) | High | html/template: URLs in meta content attribute actions are not escaped | Pod software does not perform dynamic HTML meta attribute creation loops inside untrusted client runtimes. |
| stdlib | gobinary | [CVE-2026-32282](https://nvd.nist.gov/vuln/detail/CVE-2026-32282) | High | golang: internal/syscall/unix: Root.Chmod can follow symlinks out of the root | This vulnerability can be exploited only if unauthorized access to the pod is obtained to write arbitrary local symlinks. |
| stdlib | gobinary | [CVE-2026-32288](https://nvd.nist.gov/vuln/detail/CVE-2026-32288) | High | archive/tar: golang: Denial of Service via maliciously-crafted archives | Pod software retries scanning on a malicious archive file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2026-32289](https://nvd.nist.gov/vuln/detail/CVE-2026-32289) | High | html/template: Cross-Site Scripting (XSS) via improper context tracking | Pod software interfaces do not pipe raw data strings back to web browsers through variable script templates. |
| stdlib | gobinary | [CVE-2025-58186](https://nvd.nist.gov/vuln/detail/CVE-2025-58186) | High | golang.org/net/http: Lack of limit when parsing cookies can cause memory exhaustion | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |

---

## 1.147

### Release updates - June 2026

#### Introducing Internal Autoscaling for EPod V2

Securiti has introduced **Internal** autoscaling for Elastic Pods (EPods) V2, providing an additional scaling option for Kubernetes deployments. Unlike external autoscaling solutions, Internal Autoscaling operates within EPods V2 and does not require additional cluster-level components or permissions. This is suitable for environments with restricted Kubernetes permissions. This enhancement automatically adjusts worker pod capacity based on workload demand, improves optimizes resource utilization with minimum permissions, while keeping its deployment and operational management simple in EPods V2.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

For more information, See **Customization** page in [EPod V2 installation in Securiti](/latest/docs/epod-v2-installation).

#### Introducing application-level resource quota management

Securiti has introduced application-level resource quota management for Elastic Pods (EPods) V2. It lets EPods V2 manage workload scheduling and quota enforcement without cluster-level PriorityClass resources. When quota limits reaches, EPods V2 automatically queues on-demand and scan jobs, and schedules them as capacity becomes available. It supports restricted Kubernetes RBAC environments, maintains workload continuity, and reduces the cluster level permissions.

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

#### Security, confidentiality, and availability updates

Securiti has fixed the following critical, high, medium, and low severity CVEs in the 1.147 release of pod software (with cluster version v1.28 or later).

| Vulnerability ID | Severity |
| --- | --- |
| [CVE-2026-42496](https://nvd.nist.gov/vuln/detail/CVE-2026-42496) | Critical |
| [CVE-2026-8376](https://nvd.nist.gov/vuln/detail/CVE-2026-8376) | Critical |
| [CVE-2026-8838](https://nvd.nist.gov/vuln/detail/CVE-2026-8838) | Critical |
| ALAS2023-2026-1805 | Critical |
| ALAS2023-2026-1819 | Critical |
| [CVE-2026-39830](https://nvd.nist.gov/vuln/detail/CVE-2026-39830) | Critical |
| [CVE-2026-39831](https://nvd.nist.gov/vuln/detail/CVE-2026-39831) | Critical |
| [CVE-2026-39832](https://nvd.nist.gov/vuln/detail/CVE-2026-39832) | Critical |
| [CVE-2026-39833](https://nvd.nist.gov/vuln/detail/CVE-2026-39833) | Critical |
| [CVE-2026-39834](https://nvd.nist.gov/vuln/detail/CVE-2026-39834) | Critical |
| [CVE-2026-46595](https://nvd.nist.gov/vuln/detail/CVE-2026-46595) | Critical |
| GHSA-29h4-r29x-hchv | Critical |
| [CVE-2026-25680](https://nvd.nist.gov/vuln/detail/CVE-2026-25680) | High |
| [CVE-2026-25681](https://nvd.nist.gov/vuln/detail/CVE-2026-25681) | High |
| [CVE-2026-27136](https://nvd.nist.gov/vuln/detail/CVE-2026-27136) | High |
| [CVE-2026-32952](https://nvd.nist.gov/vuln/detail/CVE-2026-32952) | High |
| [CVE-2026-33810](https://nvd.nist.gov/vuln/detail/CVE-2026-33810) | High |
| [CVE-2026-39827](https://nvd.nist.gov/vuln/detail/CVE-2026-39827) | High |
| [CVE-2026-39828](https://nvd.nist.gov/vuln/detail/CVE-2026-39828) | High |
| [CVE-2026-39829](https://nvd.nist.gov/vuln/detail/CVE-2026-39829) | High |
| [CVE-2026-39830](https://nvd.nist.gov/vuln/detail/CVE-2026-39830) | High |
| [CVE-2026-39831](https://nvd.nist.gov/vuln/detail/CVE-2026-39831) | High |
| [CVE-2026-39832](https://nvd.nist.gov/vuln/detail/CVE-2026-39832) | High |
| [CVE-2026-39833](https://nvd.nist.gov/vuln/detail/CVE-2026-39833) | High |
| [CVE-2026-39834](https://nvd.nist.gov/vuln/detail/CVE-2026-39834) | High |
| [CVE-2026-39835](https://nvd.nist.gov/vuln/detail/CVE-2026-39835) | High |
| [CVE-2026-40898](https://nvd.nist.gov/vuln/detail/CVE-2026-40898) | High |
| [CVE-2026-41066](https://nvd.nist.gov/vuln/detail/CVE-2026-41066) | High |
| [CVE-2026-41145](https://nvd.nist.gov/vuln/detail/CVE-2026-41145) | High |
| [CVE-2026-41602](https://nvd.nist.gov/vuln/detail/CVE-2026-41602) | High |
| [CVE-2026-42497](https://nvd.nist.gov/vuln/detail/CVE-2026-42497) | High |
| [CVE-2026-42502](https://nvd.nist.gov/vuln/detail/CVE-2026-42502) | High |
| [CVE-2026-42506](https://nvd.nist.gov/vuln/detail/CVE-2026-42506) | High |
| [CVE-2026-42561](https://nvd.nist.gov/vuln/detail/CVE-2026-42561) | High |
| [CVE-2026-42586](https://nvd.nist.gov/vuln/detail/CVE-2026-42586) | High |
| [CVE-2026-44248](https://nvd.nist.gov/vuln/detail/CVE-2026-44248) | High |
| [CVE-2026-44307](https://nvd.nist.gov/vuln/detail/CVE-2026-44307) | High |
| [CVE-2026-44660](https://nvd.nist.gov/vuln/detail/CVE-2026-44660) | High |
| [CVE-2026-44843](https://nvd.nist.gov/vuln/detail/CVE-2026-44843) | High |
| [CVE-2026-45134](https://nvd.nist.gov/vuln/detail/CVE-2026-45134) | High |
| [CVE-2026-46595](https://nvd.nist.gov/vuln/detail/CVE-2026-46595) | High |
| [CVE-2026-46597](https://nvd.nist.gov/vuln/detail/CVE-2026-46597) | High |
| [CVE-2026-46598](https://nvd.nist.gov/vuln/detail/CVE-2026-46598) | High |
| [CVE-2026-9538](https://nvd.nist.gov/vuln/detail/CVE-2026-9538) | High |
| ALAS2023-2026-1721 | High |
| [CVE-2026-23479](https://nvd.nist.gov/vuln/detail/CVE-2026-23479) | High |
| [CVE-2026-23631](https://nvd.nist.gov/vuln/detail/CVE-2026-23631) | High |
| [CVE-2026-25243](https://nvd.nist.gov/vuln/detail/CVE-2026-25243) | High |
| [CVE-2026-25588](https://nvd.nist.gov/vuln/detail/CVE-2026-25588) | High |
| [CVE-2026-25589](https://nvd.nist.gov/vuln/detail/CVE-2026-25589) | High |
| [CVE-2026-33810](https://nvd.nist.gov/vuln/detail/CVE-2026-33810) | High |
| [CVE-2026-39829](https://nvd.nist.gov/vuln/detail/CVE-2026-39829) | High |
| [CVE-2026-40898](https://nvd.nist.gov/vuln/detail/CVE-2026-40898) | High |
| [CVE-2026-41145](https://nvd.nist.gov/vuln/detail/CVE-2026-41145) | High |
| [CVE-2026-41602](https://nvd.nist.gov/vuln/detail/CVE-2026-41602) | High |
| [CVE-2026-42151](https://nvd.nist.gov/vuln/detail/CVE-2026-42151) | High |
| [CVE-2026-42154](https://nvd.nist.gov/vuln/detail/CVE-2026-42154) | High |
| [CVE-2026-46597](https://nvd.nist.gov/vuln/detail/CVE-2026-46597) | High |
| GHSA-2h4p-vjrc-8xpq | High |
| GHSA-3644-q5cj-c5c7 | High |
| GHSA-c38f-wx89-p2xg | High |
| GHSA-hv4r-mvr4-25vw | High |
| GHSA-jfg9-48mv-9qgx | High |
| GHSA-pjcq-xvwq-hhpj | High |
| GHSA-pjwx-r37v-7724 | High |
| GHSA-pp6c-gr5w-3c5g | High |
| GHSA-rgrr-p7gp-5xj7 | High |
| GHSA-vfmq-68hx-4jfw | High |
| GHSA-vvgj-x9jq-8cj9 | High |
| GHSA-wf45-q9ch-q8gh | High |
| GO-2026-4961 | High |
| GO-2026-5032 | High |
| [CVE-2025-67735](https://nvd.nist.gov/vuln/detail/CVE-2025-67735) | Medium |
| [CVE-2025-68161](https://nvd.nist.gov/vuln/detail/CVE-2025-68161) | Medium |
| [CVE-2025-71176](https://nvd.nist.gov/vuln/detail/CVE-2025-71176) | Medium |
| [CVE-2026-27794](https://nvd.nist.gov/vuln/detail/CVE-2026-27794) | Medium |
| [CVE-2026-41425](https://nvd.nist.gov/vuln/detail/CVE-2026-41425) | Medium |
| CVE-2026-41479 | Medium |
| [CVE-2026-42600](https://nvd.nist.gov/vuln/detail/CVE-2026-42600) | Medium |
| [CVE-2026-44681](https://nvd.nist.gov/vuln/detail/CVE-2026-44681) | Medium |
| [CVE-2026-7010](https://nvd.nist.gov/vuln/detail/CVE-2026-7010) | Medium |
| GHSA-vmhf-c436-hxj4 | Medium |
| ALAS2023-2026-1765 | Medium |
| [CVE-2026-25680](https://nvd.nist.gov/vuln/detail/CVE-2026-25680) | Medium |
| [CVE-2026-25681](https://nvd.nist.gov/vuln/detail/CVE-2026-25681) | Medium |
| [CVE-2026-27136](https://nvd.nist.gov/vuln/detail/CVE-2026-27136) | Medium |
| [CVE-2026-39827](https://nvd.nist.gov/vuln/detail/CVE-2026-39827) | Medium |
| [CVE-2026-39828](https://nvd.nist.gov/vuln/detail/CVE-2026-39828) | Medium |
| [CVE-2026-39835](https://nvd.nist.gov/vuln/detail/CVE-2026-39835) | Medium |
| [CVE-2026-42502](https://nvd.nist.gov/vuln/detail/CVE-2026-42502) | Medium |
| [CVE-2026-42506](https://nvd.nist.gov/vuln/detail/CVE-2026-42506) | Medium |
| [CVE-2026-42600](https://nvd.nist.gov/vuln/detail/CVE-2026-42600) | Medium |
| [CVE-2026-44903](https://nvd.nist.gov/vuln/detail/CVE-2026-44903) | Medium |
| [CVE-2026-46598](https://nvd.nist.gov/vuln/detail/CVE-2026-46598) | Medium |
| GHSA-4xh5-x5gv-qwph | Medium |
| GHSA-6w46-j5rx-g56g | Medium |
| GHSA-84h7-rjj3-6jx4 | Medium |
| GHSA-jj8c-mmj3-mmgv | Medium |
| GHSA-mhr3-j7m5-c7c9 | Medium |
| GHSA-mq26-g339-26xf | Medium |
| GHSA-r95x-qfjj-fjj2 | Medium |
| GHSA-vvgj-x9jq-8cj9 | Medium |
| GHSA-w8p2-r796-3vmq | Medium |
| GHSA-xh8f-g2qw-gcm7 | Medium |
| GO-2026-4962 | Medium |
| GO-2026-5031 | Medium |
| [CVE-2026-41488](https://nvd.nist.gov/vuln/detail/CVE-2026-41488) | Low |
| [CVE-2026-44405](https://nvd.nist.gov/vuln/detail/CVE-2026-44405) | Low |
| [CVE-2025-49112](https://nvd.nist.gov/vuln/detail/CVE-2025-49112) | Low |
| GHSA-6vgw-5pg2-w6jp | Low |
| GHSA-r374-rxx8-8654 | Low |
| GHSA-r7w7-9xr2-qq2r | Low |

The following CVEs are currently open and will be fixed in future releases. See the exploitability explanations for each of them below.

| Package Name | Type | Vulnerability ID | Severity | Description | Compensating Control |
| --- | --- | --- | --- | --- | --- |
| elasticsearch-9.4-config | chainguard | [CVE-2026-45674](https://nvd.nist.gov/vuln/detail/CVE-2026-45674) | Critical | netty-resolver-dns: Information disclosure and data manipulation due to improper CNAME record validation | Pod software doesn't alLow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| elasticsearch-9.4-config | chainguard | [CVE-2026-47691](https://nvd.nist.gov/vuln/detail/CVE-2026-47691) | Critical | io.netty/netty-resolver-dns: Netty has Insufficient Bailiwick Validation for NS Records | Pod software doesn't alLow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| libcrypto3 | chainguard | [CVE-2026-34182](https://nvd.nist.gov/vuln/detail/CVE-2026-34182) | Critical | openssl: CMS AuthEnvelopedData Processing May Accept Forged Messages | This vulnerability can be exploited only if Pod software is configured to rely on unsigned or untrusted CMS messaging payloads from external actors. |
| minio | chainguard | [CVE-2026-33322](https://nvd.nist.gov/vuln/detail/CVE-2026-33322) | Critical | MinIO has JWT Algorithm Confusion in OIDC Authentication | This vulnerability can be exploited only if unauthorized access to alter internal OIDC validation profile parameters is achieved. |
| glibc | chainguard | [CVE-2026-5450](https://nvd.nist.gov/vuln/detail/CVE-2026-5450) | Critical | glibc: Heap Buffer OverfLow in scanf with %mc format specifier and large width | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| libcrypto3 | chainguard | [CVE-2026-31789](https://nvd.nist.gov/vuln/detail/CVE-2026-31789) | Critical | openssl: Heap buffer overfLow on 32-bit systems from large X.509 certificate processing | Pod software runs on an isolated 64-bit Linux container platform. 32-bit architecture memory flaws are not applicable. |
| python-3.14 | chainguard | [CVE-2026-6100](https://nvd.nist.gov/vuln/detail/CVE-2026-6100) | Critical | python: Arbitrary code execution or info disclosure via use-after-free in decompression modules | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42579](https://nvd.nist.gov/vuln/detail/CVE-2026-42579) | Critical | netty: High integrity impact due to improper DNS domain name constraint enforcement | Pod software doesn't alLow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42581](https://nvd.nist.gov/vuln/detail/CVE-2026-42581) | Critical | netty: HTTP Request Smuggling due to improper handling of conflicting HTTP/1.0 headers | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42584](https://nvd.nist.gov/vuln/detail/CVE-2026-42584) | Critical | netty: Incorrect HTTP response parsing leads to data confusion | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit parsing. |
| spark-operator | chainguard | [CVE-2026-39821](https://nvd.nist.gov/vuln/detail/CVE-2026-39821) | Critical | golang.org/x/net/idna: Privilege escalation via incorrect Punycode label processing | Pod software components run as a non-root system identity configuration; there is no path for execution parsing to alter parent namespace privileges. |
| gnutls | amazon | [CVE-2026-33845](https://nvd.nist.gov/vuln/detail/CVE-2026-33845) | Critical | gnutls: Denial of Service via DTLS zero-length fragment | Pod software does not open or listen on DTLS protocol pathways exposed to external actors. |
| com.azure:azure-security-keyvault-keys | jar | [CVE-2026-33117](https://nvd.nist.gov/vuln/detail/CVE-2026-33117) | Critical | Security feature bypass vulnerability in Azure Key Vault Keys library for Java | This vulnerability can be exploited only if unauthorized access to overwrite trusted backend endpoint references in application memory is obtained. |
| org.eclipse.jetty:jetty-http | jar | [CVE-2026-2332](https://nvd.nist.gov/vuln/detail/CVE-2026-2332) | Critical | org.eclipse.jetty/jetty-http: HTTP request smuggling via chunked extension quoted-string parsing | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the smuggling anomaly. |
| jupyter_server | python-pkg | CVE-2026-44727 | Critical | Jupyter Server: Stored XSS in NbconvertFileHandler via missing sandbox CSP | Pod software does not expose Jupyter server file interfaces directly to end-user browser components. |
| starlette | python-pkg | [CVE-2026-48710](https://nvd.nist.gov/vuln/detail/CVE-2026-48710) | Critical | starlette: Security restriction bypass via malformed HTTP Host header | Pod software doesn't alLow inbound communication initiated by external parties. Internal targets map exclusively to trusted host tracking environments. |
| libcrypto3 | alpine | [CVE-2025-15467](https://nvd.nist.gov/vuln/detail/CVE-2025-15467) | Critical | openssl: Remote code execution or DoS via oversized Initialization Vector in CMS parsing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-68121](https://nvd.nist.gov/vuln/detail/CVE-2025-68121) | Critical | crypto/tls: Incorrect certificate validation during TLS session resumption | Pod software configuration enforces fresh TLS state handshake verification mappings and disables risky stateful session resumption variables. |
| stdlib | gobinary | [CVE-2025-22871](https://nvd.nist.gov/vuln/detail/CVE-2025-22871) | Critical | net/http: Request smuggling due to acceptance of invalid chunked data | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the desync. |
| cryptography | python-pkg | GHSA-537c-gmf6-5ccf | High | Vulnerable OpenSSL included in cryptography wheels | This vulnerability can be exploited only if Pod software is configured to interact with untrusted remote services that serve malicious cryptographic handshake frames or certificates. |
| ecdsa | python-pkg | [CVE-2024-23342](https://nvd.nist.gov/vuln/detail/CVE-2024-23342) | High | python-ecdsa: vulnerable to the Minerva attack | This vulnerability can be exploited only if Pod software is configured to interact with untrusted services that make use of arbitrary certificate chains for SSL. |
| [github.com/prometheus/prometheus](https://github.com/prometheus/prometheus) | gobinary | [CVE-2026-42151](https://nvd.nist.gov/vuln/detail/CVE-2026-42151) | High | Information disclosure of Azure OAuth client secret via config API | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| [github.com/prometheus/prometheus](https://github.com/prometheus/prometheus) | gobinary | [CVE-2026-42154](https://nvd.nist.gov/vuln/detail/CVE-2026-42154) | High | Denial of Service via uncontrolled memory allocation in remote read endpoint | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the remote read endpoint. |
| stdlib | gobinary | [CVE-2026-33811](https://nvd.nist.gov/vuln/detail/CVE-2026-33811) | High | net: golang: Denial of Service via long CNAME response in LookupCNAME | Pod software doesn't alLow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| stdlib | gobinary | [CVE-2026-33814](https://nvd.nist.gov/vuln/detail/CVE-2026-33814) | High | When processing HTTP/2 SETTINGS frames; transport will enter an infinite loop... | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| stdlib | gobinary | [CVE-2026-39820](https://nvd.nist.gov/vuln/detail/CVE-2026-39820) | High | Well-crafted inputs reaching ParseAddress; ParseAddressList; and ParseDate trigger CPU exhaustion... | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2026-39823](https://nvd.nist.gov/vuln/detail/CVE-2026-39823) | High | CVE-2026-27142 fixed a vulnerability in which URLs were not correctly validated... | Pod software does not render or interpret URL parsing logic inside untrusted client-facing browser contexts. |
| stdlib | gobinary | [CVE-2026-39825](https://nvd.nist.gov/vuln/detail/CVE-2026-39825) | High | ReverseProxy can forward queries containing parameters not visible to... | Pod software does not expose or leverage a reverse proxy interface to forward traffic to backend microservices. |
| stdlib | gobinary | [CVE-2026-39836](https://nvd.nist.gov/vuln/detail/CVE-2026-39836) | High | ELSA-2026-22112: go-toolset security update (The Dial and LookupPort functions panic on Windows) | Pod software runs on an isolated Linux container platform. Windows-specific operating system APIs are not applicable. |
| stdlib | gobinary | [CVE-2026-42499](https://nvd.nist.gov/vuln/detail/CVE-2026-42499) | High | Pathological inputs could cause DoS through consumePhrase when parsing an email address | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2026-42504](https://nvd.nist.gov/vuln/detail/CVE-2026-42504) | High | Decoding a maliciously-crafted MIME header containing many invalid encodings causes DoS | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2026-39826](https://nvd.nist.gov/vuln/detail/CVE-2026-39826) | High | html/template: Cross-site scripting due to incorrect script tag escaping | Pod software does not parse or serve dynamic HTML templates directly to untrusted web browsers. |
| elasticsearch-9.4-config | chainguard | [CVE-2026-44249](https://nvd.nist.gov/vuln/detail/CVE-2026-44249) | High | netty-handler: IPv6 subnet rule bypass due to incorrect masking operation | Pod software network reachability parameters navigate only to explicit internal target networks via infrastructure firewall filtering. |
| elasticsearch-9.4-config | chainguard | [CVE-2026-45416](https://nvd.nist.gov/vuln/detail/CVE-2026-45416) | High | netty-handler: Denial of Service due to eager buffer allocation in TLS handshake | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to manipulate TLS handshakes. |
| elasticsearch-9.4-config | chainguard | [CVE-2026-48043](https://nvd.nist.gov/vuln/detail/CVE-2026-48043) | High | netty-codec-http2: Denial of Service due to resource leak | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit the vulnerability. |
| elasticsearch-9.4-config | chainguard | [CVE-2026-50010](https://nvd.nist.gov/vuln/detail/CVE-2026-50010) | High | netty-handler: Improper trust manager handling leads to hostname verification bypass | This vulnerability can be exploited only if Pod software is configured to interact with untrusted service endpoints that serve invalid matching certificates. |
| libcrypto3 | chainguard | [CVE-2026-45447](https://nvd.nist.gov/vuln/detail/CVE-2026-45447) | High | openssl: Heap Use-After-Free in OpenSSL PKCS7_verify() | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-34183](https://nvd.nist.gov/vuln/detail/CVE-2026-34183) | High | openssl: Unbounded Memory Growth in the QUIC PATH_CHALLENGE Handler | Pod software does not implement or rely on the vulnerable OpenSSL QUIC stack elements for external routing protocols. |
| libcrypto3 | chainguard | [CVE-2026-42764](https://nvd.nist.gov/vuln/detail/CVE-2026-42764) | High | openssl: NULL pointer dereference in QUIC server initial packet handling | Pod software does not implement or expose OpenSSL QUIC server processing listeners to inbound external calls. |
| libcrypto3 | chainguard | [CVE-2026-45445](https://nvd.nist.gov/vuln/detail/CVE-2026-45445) | High | openssl: AES-OCB IV Ignored on EVP_Cipher() Path | Pod software does not use the specific cryptographic OCB block cipher mode pathways inside application implementations. |
| libcrypto3 | chainguard | [CVE-2026-34180](https://nvd.nist.gov/vuln/detail/CVE-2026-34180) | High | openssl: Heap buffer over-read in ASN.1 decoding can lead to denial of service | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-34181](https://nvd.nist.gov/vuln/detail/CVE-2026-34181) | High | openssl: PKCS#12 Files with PBMAC1 Are Accepted with Short HMAC Keys | This vulnerability can be exploited only if Pod software handles untrusted, externally-supplied PKCS#12 configuration profiles. |
| libcrypto3 | chainguard | [CVE-2026-42765](https://nvd.nist.gov/vuln/detail/CVE-2026-42765) | High | openssl: Vulnerability when partial-chain certificate verification is enabled... | This vulnerability can be exploited only if Pod software is configured with custom, insecure non-standard partial-chain certificate paths. |
| libcrypto3 | chainguard | [CVE-2026-42766](https://nvd.nist.gov/vuln/detail/CVE-2026-42766) | High | openssl: Possible NULL Dereference in Password-Based CMS Decryption | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-42767](https://nvd.nist.gov/vuln/detail/CVE-2026-42767) | High | openssl: NULL Pointer Dereference in CRMF EncryptedValue Decryption | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-42768](https://nvd.nist.gov/vuln/detail/CVE-2026-42768) | High | openssl: Multi-RecipientInfo Bleichenbacher Oracle in CMS_decrypt() and PKCS7_decrypt() | Pod software does not expose decryption operations or side-channel parsing vectors directly to external actors. |
| libcrypto3 | chainguard | [CVE-2026-42769](https://nvd.nist.gov/vuln/detail/CVE-2026-42769) | High | openssl: Trust-Anchor Substitution via cert/issuer Typo in CMP rootCaKeyUpdate | This vulnerability can be exploited only if Pod software is configured to use the CMP root identity certificate synchronization feature against untrusted endpoints. |
| libcrypto3 | chainguard | [CVE-2026-42770](https://nvd.nist.gov/vuln/detail/CVE-2026-42770) | High | openssl: FFC-DH Peer Validation Uses Attacker-Supplied q | This vulnerability can be exploited only if Pod software establishes Diffie-Hellman handshakes using unvalidated target group key pairs. |
| libcrypto3 | chainguard | [CVE-2026-45446](https://nvd.nist.gov/vuln/detail/CVE-2026-45446) | High | openssl: Incorrect Tag Processing for Empty Messages in AES-GCM-SIV and AES-SIV modes | Pod software does not utilize the affected AES-GCM-SIV string block processing mechanisms inside internal business architectures. |
| libcrypto3 | chainguard | [CVE-2026-7383](https://nvd.nist.gov/vuln/detail/CVE-2026-7383) | High | openssl: Heap buffer overfLow due to signed integer overfLow in Unicode output sizing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-9076](https://nvd.nist.gov/vuln/detail/CVE-2026-9076) | High | openssl: Denial of Service due to heap out-of-bounds read in CMS password-based decryption | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| minio | chainguard | [CVE-2026-40344](https://nvd.nist.gov/vuln/detail/CVE-2026-40344) | High | MinIO has an Unauthenticated Object Write via Missing Signature Verification | Pod software doesn't alLow inbound communication initiated by external parties; write metrics and access functions are securely contained inside internal boundaries. |
| busybox | chainguard | [CVE-2023-39810](https://nvd.nist.gov/vuln/detail/CVE-2023-39810) | High | busybox: CPIO command alLows directory traversal | Pod software does not execute or evaluate untrusted CPIO extraction archives within local terminal runtimes. |
| busybox | chainguard | [CVE-2026-26157](https://nvd.nist.gov/vuln/detail/CVE-2026-26157) | High | busybox: Arbitrary file overwrite and potential code execution via incomplete path sanitization | This vulnerability can be exploited only if unauthorized access to the pod is obtained to invoke internal file utilities against crafted file configurations. |
| busybox | chainguard | [CVE-2026-26158](https://nvd.nist.gov/vuln/detail/CVE-2026-26158) | High | busybox: Arbitrary file modification via unvalidated tar archive entries | Pod software retries scanning on a malicious archive file a couple of times and moves on; the container environment is entirely stateless and ephemeral. |
| glibc | chainguard | [CVE-2026-4046](https://nvd.nist.gov/vuln/detail/CVE-2026-4046) | High | glibc: Denial of Service via iconv() function with specific character sets | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| glibc | chainguard | [CVE-2026-4437](https://nvd.nist.gov/vuln/detail/CVE-2026-4437) | High | glibc: Incorrect DNS response parsing via crafted DNS server response | Pod software doesn't alLow inbound communication initiated by external parties. Internal resolution points strictly to a trusted upstream DNS cluster. |
| glibc | chainguard | [CVE-2026-5928](https://nvd.nist.gov/vuln/detail/CVE-2026-5928) | High | glibc: Information disclosure or denial of service via ungetwc function | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-28386](https://nvd.nist.gov/vuln/detail/CVE-2026-28386) | High | openssl: Denial of Service due to out-of-bounds read in AES-CFB128 | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-28387](https://nvd.nist.gov/vuln/detail/CVE-2026-28387) | High | openssl: Arbitrary code execution due to use-after-free in DANE TLSA authentication | Pod software does not utilize DANE TLSA protocol implementations for connection validations. |
| libcrypto3 | chainguard | [CVE-2026-28388](https://nvd.nist.gov/vuln/detail/CVE-2026-28388) | High | openssl: Denial of Service due to NULL pointer dereference in delta CRL processing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-28389](https://nvd.nist.gov/vuln/detail/CVE-2026-28389) | High | openssl: Denial of Service vulnerability in CMS processing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-28390](https://nvd.nist.gov/vuln/detail/CVE-2026-28390) | High | openssl: Denial of Service due to NULL pointer dereference in CMS EnvelopedData processing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | chainguard | [CVE-2026-2673](https://nvd.nist.gov/vuln/detail/CVE-2026-2673) | High | openssl: OpenSSL TLS 1.3 server may choose unexpected key agreement group | Pod software does not expose inbound TLS server listeners to unvalidated external callers. |
| libcrypto3 | chainguard | [CVE-2026-31790](https://nvd.nist.gov/vuln/detail/CVE-2026-31790) | High | openssl: Information Disclosure from Uninitialized Memory via Invalid RSA Public Key | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-22016](https://nvd.nist.gov/vuln/detail/CVE-2026-22016) | High | openjdk: Enhance Path Factories Redux | This vulnerability can be exploited only if unauthorized access to the pod is obtained to supply malicious filesystem paths. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-34282](https://nvd.nist.gov/vuln/detail/CVE-2026-34282) | High | openjdk: Enhance TLS connection handling | Pod software doesn't alLow inbound communication initiated by external parties. Outbound TLS targets only explicit internal target destinations. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-22013](https://nvd.nist.gov/vuln/detail/CVE-2026-22013) | High | openjdk: Improve Kerberos credentialing | Pod software does not leverage or reference Kerberos configuration elements for operational lifecycle management. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-22021](https://nvd.nist.gov/vuln/detail/CVE-2026-22021) | High | openjdk: Enhance certificate chain validation | This vulnerability can be exploited only if Pod software is configured to interact with untrusted upstream endpoints using malicious certificate chains. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-23865](https://nvd.nist.gov/vuln/detail/CVE-2026-23865) | High | freetype: Information disclosure or denial of service via specially crafted font files | Pod software does not unpack, process, or render custom font file components inside internal execution loops. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-22007](https://nvd.nist.gov/vuln/detail/CVE-2026-22007) | High | openjdk: Enhance crypto algorithm support | This vulnerability can be exploited only if unauthorized access to the pod is obtained to alter cryptographic system algorithm defaults. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-22018](https://nvd.nist.gov/vuln/detail/CVE-2026-22018) | High | openjdk: Enhance Zip file reading | Pod software retries scanning on a malicious archive a couple of times and moves on; The processes will restart and pick up remaining work. |
| openjdk-21-default-jvm | chainguard | [CVE-2026-34268](https://nvd.nist.gov/vuln/detail/CVE-2026-34268) | High | openjdk: Enhance key generation | This vulnerability can be exploited only if unauthorized access to the pod is obtained to monitor local cryptographic keys in memory. |
| py3-pip-wheel | chainguard | [CVE-2025-66418](https://nvd.nist.gov/vuln/detail/CVE-2025-66418) | High | urllib3: Unbounded decompression chain leads to resource exhaustion | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| py3-pip-wheel | chainguard | [CVE-2025-66471](https://nvd.nist.gov/vuln/detail/CVE-2025-66471) | High | urllib3: Streaming API improperly handles Highly compressed data | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| py3-pip-wheel | chainguard | [CVE-2026-21441](https://nvd.nist.gov/vuln/detail/CVE-2026-21441) | High | urllib3: Decompression-bomb safeguard bypass when folLowing HTTP redirects | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| py3-pip-wheel | chainguard | [CVE-2026-44432](https://nvd.nist.gov/vuln/detail/CVE-2026-44432) | High | urllib3: Denial of Service due to excessive HTTP response decompression | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| py3-pip-wheel | chainguard | [CVE-2026-44431](https://nvd.nist.gov/vuln/detail/CVE-2026-44431) | High | urllib3: Information disclosure via cross-origin redirects forwarding sensitive headers | Pod software outbound parameters navigate only to explicit internal alLowlists; target routing endpoints do not jump origins. |
| py3-pip-wheel | chainguard | [CVE-2026-6357](https://nvd.nist.gov/vuln/detail/CVE-2026-6357) | High | pip: Arbitrary code execution via malicious wheel package installation | Pod software components do not ingest or install wheel packages dynamically inside running system containers. |
| python-3.14 | chainguard | [CVE-2026-3644](https://nvd.nist.gov/vuln/detail/CVE-2026-3644) | High | cpython: Incomplete control character validation in http.cookies | Pod software doesn't alLow inbound communication initiated by external parties. Hence, cookie parsing streams are not reachable by external actors. |
| python-3.14 | chainguard | [CVE-2026-4224](https://nvd.nist.gov/vuln/detail/CVE-2026-4224) | High | cpython: Stack overfLow parsing XML with deeply nested DTD content models | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| python-3.14 | chainguard | [CVE-2026-4786](https://nvd.nist.gov/vuln/detail/CVE-2026-4786) | High | python: Arbitrary code execution via command injection in webbrowser.open() API | This vulnerability can be exploited only if unauthorized access to the pod is obtained to force browser invocation loops. |
| python-3.14 | chainguard | [CVE-2026-7210](https://nvd.nist.gov/vuln/detail/CVE-2026-7210) | High | python: expat: Denial of Service via crafted XML document | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| python-3.14 | chainguard | [CVE-2026-1502](https://nvd.nist.gov/vuln/detail/CVE-2026-1502) | High | python: HTTP header injection via CR/LF in proxy tunnel headers | Pod software outbound proxy targets point strictly to validated, unmanipulated configuration variables. |
| python-3.14 | chainguard | [CVE-2026-9669](https://nvd.nist.gov/vuln/detail/CVE-2026-9669) | High | python: Denial of Service via out-of-bounds write in BZ2 decompression | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| python-3.14 | chainguard | [CVE-2026-2297](https://nvd.nist.gov/vuln/detail/CVE-2026-2297) | High | cpython: Logging Bypass in Legacy .pyc File Handling | This vulnerability can be exploited only if unauthorized access to the pod is obtained to introduce legacy precompiled code modules. |
| python-3.14 | chainguard | [CVE-2026-3479](https://nvd.nist.gov/vuln/detail/CVE-2026-3479) | High | python pkgutil.get_data(): Path Traversal via improper resource argument validation | This vulnerability can be exploited only if unauthorized access to the pod is obtained to manipulate local application execution configurations. |
| python-3.14 | chainguard | [CVE-2026-4519](https://nvd.nist.gov/vuln/detail/CVE-2026-4519) | High | python: Command-line option injection in webbrowser.open() via crafted URLs | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2025-66566](https://nvd.nist.gov/vuln/detail/CVE-2025-66566) | High | lz4-java: Information Disclosure via Insufficient Output Buffer Clearing | Pod software retries scanning on a malicious file a couple of times and moves on; the transient container runs inside an isolated, non-shared perimeter. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2025-67721](https://nvd.nist.gov/vuln/detail/CVE-2025-67721) | High | aircompressor Snappy and LZ4 Java-based decompressor can leak info from reused buffers | Pod software retries scanning on a malicious file a couple of times and moves on; transient memory scopes are destroyed upon container termination. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-0636](https://nvd.nist.gov/vuln/detail/CVE-2026-0636) | High | bouncycastle: BC-JAVA: LDAP injection vulnerability in LDAPStoreHelper.java | Pod software does not perform directory querying actions using the vulnerable bouncycastle LDAP helper components. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-24281](https://nvd.nist.gov/vuln/detail/CVE-2026-24281) | High | Apache ZooKeeper: Impersonation of servers or clients via reverse DNS spoofing | Pod software targets specific, hardcoded cluster IP definitions; it does not authorize topology validation via reverse PTR resolution lookup structures. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-24308](https://nvd.nist.gov/vuln/detail/CVE-2026-24308) | High | Apache ZooKeeper: Information disclosure via improper handling of configuration values | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-33870](https://nvd.nist.gov/vuln/detail/CVE-2026-33870) | High | io.netty/netty-codec-http: Request smuggling via incorrect parsing of HTTP/1.1 chunked values | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to pass malformed extensions. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-33871](https://nvd.nist.gov/vuln/detail/CVE-2026-33871) | High | netty: Denial of Service via HTTP/2 CONTINUATION frame floods | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to flood communication structures. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-34478](https://nvd.nist.gov/vuln/detail/CVE-2026-34478) | High | Apache Log4j Core: Log injection via CRLF sequences due to configuration attribute renames | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to inject tracking arguments. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-34479](https://nvd.nist.gov/vuln/detail/CVE-2026-34479) | High | Apache Log4j 1-to-Log4j 2 bridge: Log processing DoS due to improper XML escaping | Pod software does not implement or rely on the vulnerable configuration layout frameworks for active log pipelines. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-34480](https://nvd.nist.gov/vuln/detail/CVE-2026-34480) | High | Apache Log4j Core: Invalid XML output causes denial of service in logging | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-34481](https://nvd.nist.gov/vuln/detail/CVE-2026-34481) | High | Apache Log4j JsonTemplateLayout: Denial of Service via invalid JSON output | Pod software does not implement or leverage the JsonTemplateLayout structure parameters inside operational logging pipelines. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42577](https://nvd.nist.gov/vuln/detail/CVE-2026-42577) | High | Netty asynchronous event-driven framework vulnerability... | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to target netty routines. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42578](https://nvd.nist.gov/vuln/detail/CVE-2026-42578) | High | netty: HTTP Header Injection via HttpProxyHandler Disabled Validation | Pod software does not route out bound tracking metrics via proxy entities utilizing unvalidated request mapping arguments. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42583](https://nvd.nist.gov/vuln/detail/CVE-2026-42583) | High | Netty context propagation flaw... | This vulnerability can be exploited only if unauthorized access to the pod is obtained. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42585](https://nvd.nist.gov/vuln/detail/CVE-2026-42585) | High | netty: Request smuggling via malformed Transfer-Encoding parsing | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to exploit request boundaries. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-42587](https://nvd.nist.gov/vuln/detail/CVE-2026-42587) | High | netty: Denial of Service via unbounded memory allocation in HTTP content decompression | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-43869](https://nvd.nist.gov/vuln/detail/CVE-2026-43869) | High | Apache Thrift: Security bypass due to improper certificate validation | This vulnerability can be exploited only if Pod software is configured to leverage Thrift client handshakes against untrusted target backends. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2026-5598](https://nvd.nist.gov/vuln/detail/CVE-2026-5598) | High | bouncycastle: BC-JAVA: private key leakage via non-constant time comparisons | Pod software executes inside secure container perimeters; localized runtime loops do not expose timing metrics out to public networks. |
| spark-4.0-scala-2.13 | chainguard | [CVE-2025-12183](https://nvd.nist.gov/vuln/detail/CVE-2025-12183) | High | lz4-java: Out-of-bounds memory operations lead to denial of service | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| spark-operator | chainguard | [CVE-2026-25679](https://nvd.nist.gov/vuln/detail/CVE-2026-25679) | High | net/url: Incorrect parsing of IPv6 host literals in net/url | Pod software navigates exclusively through structured configuration properties; it does not parse dynamic unvalidated IPv6 URL strings from external contexts. |
| spark-operator | chainguard | [CVE-2026-27140](https://nvd.nist.gov/vuln/detail/CVE-2026-27140) | High | cmd/go: Arbitrary Code Execution via malicious SWIG file names | Pod software components do not compilation-build or execute go tool evaluation pathways during production run steps. |
| spark-operator | chainguard | [CVE-2026-29181](https://nvd.nist.gov/vuln/detail/CVE-2026-29181) | High | [github.com/open-telemetry/opentelemetry-go](https://github.com/open-telemetry/opentelemetry-go): DoS via crafted multi-value baggage headers | Pod software doesn't alLow inbound communication initiated by external parties. Trace header ingestion loops are managed purely inside trusted localized perimeters. |
| spark-operator | chainguard | [CVE-2026-32280](https://nvd.nist.gov/vuln/detail/CVE-2026-32280) | High | crypto/x509: Denial of Service vulnerability in certificate chain building | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to pass complex target validation paths. |
| spark-operator | chainguard | [CVE-2026-32281](https://nvd.nist.gov/vuln/detail/CVE-2026-32281) | High | crypto/x509: Denial of Service via inefficient certificate chain validation | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to trigger processing delays. |
| spark-operator | chainguard | [CVE-2026-32283](https://nvd.nist.gov/vuln/detail/CVE-2026-32283) | High | crypto/tls: Denial of Service via multiple TLS 1.3 key update messages | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to flood key update events. |
| spark-operator | chainguard | [CVE-2026-42501](https://nvd.nist.gov/vuln/detail/CVE-2026-42501) | High | A malicious module proxy can exploit a flaw in the go command's validation... | This vulnerability can be exploited only if Pod software is configured to interact with untrusted upstream module proxies during runtime operations. |
| spark-operator | chainguard | [CVE-2026-39817](https://nvd.nist.gov/vuln/detail/CVE-2026-39817) | High | The "go tool pack" subcommand vulnerability... | Pod software components do not invoke compilation tools or target file creation tools inside operational loops. |
| spark-operator | chainguard | [CVE-2026-39819](https://nvd.nist.gov/vuln/detail/CVE-2026-39819) | High | The "go bug" command writes to two files with predictable names... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to view local debugging temporary directories. |
| spark-operator | chainguard | [CVE-2026-27139](https://nvd.nist.gov/vuln/detail/CVE-2026-27139) | High | os: FileInfo can escape from a Root in golang os module | This vulnerability can be exploited only if unauthorized access to the pod is obtained to invoke chroot file escapes via terminal manipulation. |
| libsolv | amazon | [CVE-2026-48863](https://access.redhat.com/security/cve/cve-2026-48863) | High | libsolv: Stack-based buffer overfLow in libsolv EdDSA PGP signature verification | Pod software components do not evaluate PGP signature payloads inside automated system metadata checking loops. |
| libsolv | amazon | [CVE-2026-48864](https://nvd.nist.gov/vuln/detail/CVE-2026-48864) | High | libsolv: Heap buffer overfLow in libsolv repopagestore via unchecked decompression | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libsolv | amazon | [CVE-2026-9149](https://nvd.nist.gov/vuln/detail/CVE-2026-9149) | High | libsolv: Heap buffer overfLow in libsolv repo_add_solv via negative maxsize | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libsolv | amazon | [CVE-2026-9150](https://nvd.nist.gov/vuln/detail/CVE-2026-9150) | High | libsolv: Stack-based buffer overfLow in libsolv's Debian metadata parser | Pod software components do not read or interpret debian package configuration descriptors during application execution. |
| aiohttp | python-pkg | [CVE-2026-34993](https://nvd.nist.gov/vuln/detail/CVE-2026-34993) | High | aiohttp: Arbitrary code execution via untrusted input to CookieJar.load() | This vulnerability can be exploited only if unauthorized access to the pod is obtained to feed malformed state persistence profiles into cookie parsing. |
| aiohttp | python-pkg | [CVE-2026-47265](https://nvd.nist.gov/vuln/detail/CVE-2026-47265) | High | python-aiohttp: Information disclosure via improper handling of cookies during redirects | Pod software outbound configuration options point to explicit matching destination targets; it does not trigger random redirects outside trust realms. |
| nltk | python-pkg | [CVE-2026-54293](https://www.cve.org/CVERecord?id=CVE-2026-54293) | High | Natural Language Toolkit: URL-Encoded Path Traversal in nltk.data.load() | This vulnerability can be exploited only if unauthorized access to the pod is obtained to force local resource file path loading arguments. |
| gnutls | amazon | [CVE-2026-42011](https://nvd.nist.gov/vuln/detail/CVE-2026-42011) | High | gnutls: Security bypass due to incorrect name constraint handling | This vulnerability can be exploited only if Pod software is configured to connect to untrusted endpoints utilizing custom name constraint routing fields. |
| gnutls | amazon | [CVE-2026-42012](https://nvd.nist.gov/vuln/detail/CVE-2026-42012) | High | gnutls: Certificate validation bypass due to improper handling of URI and SRV SANs | This vulnerability can be exploited only if Pod software targets external unverified domains hosting custom URI/SRV SAN identifiers. |
| gnutls | amazon | [CVE-2026-42013](https://nvd.nist.gov/vuln/detail/CVE-2026-42013) | High | gnutls: Certificate validation bypass due to oversized Subject Alternative Name | This vulnerability can be exploited only if Pod software is configured to validate untrusted infrastructure components using malicious oversized certificates. |
| gnutls | amazon | [CVE-2026-5419](https://nvd.nist.gov/vuln/detail/CVE-2026-5419) | High | gnutls: Information disclosure via timing side-channel in PKCS#7 padding removal | Pod software executes computations inside isolated networks; timing variances are not visible or measurable from public tracking contexts. |
| libssh2 | amazon | [CVE-2026-7598](https://nvd.nist.gov/vuln/detail/CVE-2026-7598) | High | libssh2: integer overfLow via large username or password arguments | Pod software communicates strictly with pre-authenticated internal SSH host keys using hardcoded length-controlled identity strings. |
| io.netty:netty-codec-classes-quic | jar | [CVE-2026-44894](https://nvd.nist.gov/vuln/detail/CVE-2026-44894) | High | netty-codec-classes-quic: Netty: Denial of Service amplification via improper QUIC token validation | Pod software does not leverage or expose QUIC validation transport listeners to external environments. |
| io.netty:netty-codec-haproxy | jar | [CVE-2026-44893](https://nvd.nist.gov/vuln/detail/CVE-2026-44893) | High | netty-codec-haproxy: Denial of Service via malformed HAProxy message | Pod software does not ingest raw HAProxy PROXY header protocols directly from external public ingress paths. |
| io.netty:netty-codec-haproxy | jar | [CVE-2026-48059](https://nvd.nist.gov/vuln/detail/CVE-2026-48059) | High | netty-codec-haproxy: Denial of Service via memory leak from crafted PROXY protocol headers | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| io.netty:netty-codec-http3 | jar | [CVE-2026-44892](https://nvd.nist.gov/vuln/detail/CVE-2026-44892) | High | Netty framework HTTP/3 codec validation defect... | Pod software does not process or open HTTP/3 network sockets accessible to untrusted networks. |
| io.netty:netty-codec-http3 | jar | [CVE-2026-48748](https://nvd.nist.gov/vuln/detail/CVE-2026-48748) | High | netty: Denial of Service due to memory exhaustion in HTTP/3 codec | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| io.netty:netty-codec-redis | jar | [CVE-2026-44250](https://nvd.nist.gov/vuln/detail/CVE-2026-44250) | High | netty-codec-redis: Denial of Service via crafted Redis payload with deeply nested arrays | Pod software connects exclusively to a dedicated internal Redis cluster; parsing logic is not accessible to external inputs. |
| io.netty:netty-codec-redis | jar | [CVE-2026-44890](https://nvd.nist.gov/vuln/detail/CVE-2026-44890) | High | netty-codec-redis: Denial of Service via crafted Redis payloads | Pod software processes are isolated; inner tracking data communication pathways are inaccessible to external callers. |
| io.netty:netty-codec-redis | jar | [CVE-2026-48006](https://nvd.nist.gov/vuln/detail/CVE-2026-48006) | High | netty-codec-redis: Pooled ByteBuf Leak in RedisArrayAggregator | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| io.netty:netty-codec-redis | jar | [CVE-2026-50011](https://nvd.nist.gov/vuln/detail/CVE-2026-50011) | High | netty-codec-redis: Denial of Service via malicious Redis array header | Pod software connects exclusively to verified internal infrastructure; parsing layers are not reachable by external callers. |
| io.netty:netty-transport-sctp | jar | [CVE-2026-46340](https://nvd.nist.gov/vuln/detail/CVE-2026-46340) | High | netty-transport-sctp: Denial of Service due to unbounded memory growth from SctpMessage fragments | Pod software does not activate or use SCTP transport sockets across running application frameworks. |
| io.opentelemetry:opentelemetry-api | jar | [CVE-2026-45292](https://nvd.nist.gov/vuln/detail/CVE-2026-45292) | High | opentelemetry-java: Denial of Service due to unbounded memory allocation when parsing oversized baggage | Pod software retries scanning on a malicious telemetry string a couple of times and moves on; The processes will restart and pick up remaining work. |
| org.jline:jline-remote-telnet | jar | GHSA-2r2c-cx56-8933 | High | JLine3 Telnet server: Unauthenticated Remote DoS via Unbounded Telnet NAWS Terminal Geometry | Pod software does not deploy or activate unauthenticated Telnet servers inside active runtime perimeters. |
| org.jline:jline-remote-telnet | jar | GHSA-47qp-hqvx-6r3f | High | JLine3 Telnet server: Unauthenticated Remote Memory Exhaustion via Unbounded Telnet NEW-ENVIRON Variables | Pod software does not expose Telnet server interfaces to external public access profiles. |
| pyarrow | python-pkg | [CVE-2026-25087](https://nvd.nist.gov/vuln/detail/CVE-2026-25087) | High | apache-arrow: Denial of Service via Use After Free vulnerability when reading IPC files | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| starlette | python-pkg | [CVE-2026-48818](https://nvd.nist.gov/vuln/detail/CVE-2026-48818) | High | starlette: SSRF and NTLM credential theft via UNC paths in StaticFiles on Windows | Pod software runs on an isolated Linux container platform. Windows-specific UNC handling paths are not applicable. |
| starlette | python-pkg | [CVE-2026-54283](https://www.cve.org/CVERecord?id=CVE-2026-54283) | High | Starlette: request.form() limits silently ignored for form-urlencoded enable DoS | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to send form floods. |
| PyJWT | python-pkg | [CVE-2026-48526](https://nvd.nist.gov/vuln/detail/CVE-2026-48526) | High | python-pyjwt: Authentication bypass due to forged JSON Web Tokens | Pod software validates cryptographic identities exclusively through explicit signing keys obtained from a verified local vault service. |
| python-multipart | python-pkg | [CVE-2026-53539](https://www.cve.org/CVERecord?id=CVE-2026-53539) | High | python-multipart: Quadratic-time querystring parsing causes CPU denial of service | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2024-12797](https://nvd.nist.gov/vuln/detail/CVE-2024-12797) | High | openssl: RFC7250 handshakes with unauthenticated servers don't abort as expected | Pod software connection definitions require explicit, fully-authenticated mutual TLS configurations; unauthenticated fallback is disabled. |
| libcrypto3 | alpine | [CVE-2025-69421](https://nvd.nist.gov/vuln/detail/CVE-2025-69421) | High | openssl: Denial of Service via malformed PKCS#12 file processing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2025-69419](https://nvd.nist.gov/vuln/detail/CVE-2025-69419) | High | openssl: Arbitrary code execution due to out-of-bounds write in PKCS#12 processing | This vulnerability can be exploited only if unauthorized access to the pod is obtained to load local identity files. |
| libcrypto3 | alpine | [CVE-2025-9230](https://nvd.nist.gov/vuln/detail/CVE-2025-9230) | High | openssl: Out-of-bounds read & write in RFC 3211 KEK Unwrap | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2025-15468](https://nvd.nist.gov/vuln/detail/CVE-2025-15468) | High | openssl: Denial of Service via NULL pointer dereference in QUIC protocol handling | Pod software does not apply or expose OpenSSL QUIC interfaces to external calling perimeters. |
| libcrypto3 | alpine | [CVE-2025-66199](https://nvd.nist.gov/vuln/detail/CVE-2025-66199) | High | openssl: Denial of Service due to excessive memory allocation in TLS 1.3 certificate compression | Pod software retries scanning on a malicious handshake attempt a couple of times and moves on; runtime cgroup boundaries clamp resource consumption. |
| libcrypto3 | alpine | [CVE-2025-68160](https://nvd.nist.gov/vuln/detail/CVE-2025-68160) | High | openssl: Denial of Service due to out-of-bounds write in BIO filter | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2025-69418](https://nvd.nist.gov/vuln/detail/CVE-2025-69418) | High | openssl: Info disclosure via specific Low-level OCB encryption/decryption calls | Pod software does not call the Low-level vulnerable OpenSSL OCB cipher variants inside internal code logic frameworks. |
| libcrypto3 | alpine | [CVE-2025-69420](https://nvd.nist.gov/vuln/detail/CVE-2025-69420) | High | openssl: Denial of Service via malformed TimeStamp Response | Pod software retries scanning on a malicious payload a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2026-22795](https://nvd.nist.gov/vuln/detail/CVE-2026-22795) | High | openssl: Denial of Service due to type confusion in PKCS#12 file processing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| libcrypto3 | alpine | [CVE-2026-22796](https://nvd.nist.gov/vuln/detail/CVE-2026-22796) | High | openssl: Denial of Service via type confusion in PKCS#7 signature verification | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| musl | alpine | [CVE-2025-26519](https://nvd.nist.gov/vuln/detail/CVE-2025-26519) | High | musl libc 0.9.13 through 1.2.5 has an out-of-bounds write... | This vulnerability can be exploited only if unauthorized access to the pod is obtained to invoke Low-level memory allocation manipulations. |
| musl | alpine | [CVE-2026-40200](https://nvd.nist.gov/vuln/detail/CVE-2026-40200) | High | musl: Arbitrary code execution and DoS via stack-based memory corruption in qsort | Pod software processes are isolated; sorting arrays operate completely on predictable internal application data formats. |
| zlib | alpine | [CVE-2026-22184](https://nvd.nist.gov/vuln/detail/CVE-2026-22184) | High | zlib: Arbitrary code execution via buffer overfLow in untgz utility | Pod software do not use or shell-execute the untgz command line helper tool within runtime environments. |
| [golang.org/x/net](http://golang.org/x/net) | gobinary | [CVE-2025-22872](https://nvd.nist.gov/vuln/detail/CVE-2025-22872) | High | golang.org/x/net/html: Incorrect Neutralization of Input During Web Page Generation | Pod software logic functions do not stream dynamically built web page templates back into client-side browser windows. |
| stdlib | gobinary | [CVE-2025-61726](https://nvd.nist.gov/vuln/detail/CVE-2025-61726) | High | golang: net/url: Memory exhaustion in query parameter parsing | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-61729](https://nvd.nist.gov/vuln/detail/CVE-2025-61729) | High | crypto/x509: Denial of Service due to excessive resource consumption via crafted certificates | Pod software doesn't alLow inbound communication initiated by external parties. Outbound connection validation hooks point strictly to pre-authenticated keys. |
| stdlib | gobinary | [CVE-2024-45336](https://nvd.nist.gov/vuln/detail/CVE-2024-45336) | High | golang: net/http: sensitive headers incorrectly sent after cross-domain redirect | Pod software outbound parameters map strictly to specific internal endpoints; connection loops are restricted from executing cross-domain shifts. |
| stdlib | gobinary | [CVE-2025-4673](https://nvd.nist.gov/vuln/detail/CVE-2025-4673) | High | net/http: Sensitive headers not cleared on cross-origin redirect | Pod software outbound connection calls terminate strictly on explicit static targets, omitting cross-origin jump actions. |
| stdlib | gobinary | [CVE-2025-47906](https://nvd.nist.gov/vuln/detail/CVE-2025-47906) | High | os/exec: Unexpected paths returned from LookPath in os/exec | This vulnerability can be exploited only if unauthorized access to the pod is obtained to skew system environment PATH parameters locally. |
| stdlib | gobinary | [CVE-2025-47907](https://nvd.nist.gov/vuln/detail/CVE-2025-47907) | High | database/sql: Postgres Scan Race Condition | Pod software business data handlers apply thread-safe localized structures when querying across target repository connections. |
| stdlib | gobinary | [CVE-2025-47912](https://nvd.nist.gov/vuln/detail/CVE-2025-47912) | High | net/url: Insufficient validation of bracketed IPv6 hostnames | Pod software relies entirely on specific pre-validated URL parameters; untrusted bracket parsing strings are rejected at the edge gateway. |
| stdlib | gobinary | [CVE-2025-58183](https://nvd.nist.gov/vuln/detail/CVE-2025-58183) | High | golang: archive/tar: Unbounded allocation when parsing GNU sparse map | Pod software retries scanning on a malicious archive file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-58185](https://nvd.nist.gov/vuln/detail/CVE-2025-58185) | High | encoding/asn1: Parsing DER payload can cause memory exhaustion | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-58187](https://nvd.nist.gov/vuln/detail/CVE-2025-58187) | High | crypto/x509: Quadratic complexity when checking name constraints | Pod software doesn't alLow inbound communication initiated by external parties. Hence, there is no scope for an external caller to pass complex target verification paths. |
| stdlib | gobinary | [CVE-2025-58188](https://nvd.nist.gov/vuln/detail/CVE-2025-58188) | High | crypto/x509: Panic when validating certificates with DSA public keys | Pod software doesn't alLow inbound communication initiated by external parties; external untrusted certificates are rejected. |
| stdlib | gobinary | [CVE-2025-58189](https://nvd.nist.gov/vuln/detail/CVE-2025-58189) | High | crypto/tls: go crypto/tls ALPN negotiation error contains attacker controlled information | Pod software doesn't alLow inbound communication initiated by external parties. Local system configuration filters reject random ALPN parameters. |
| stdlib | gobinary | [CVE-2025-61723](https://nvd.nist.gov/vuln/detail/CVE-2025-61723) | High | encoding/pem: Quadratic complexity when parsing some invalid inputs | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-61724](https://nvd.nist.gov/vuln/detail/CVE-2025-61724) | High | net/textproto: Excessive CPU consumption in Reader.ReadResponse | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-61725](https://nvd.nist.gov/vuln/detail/CVE-2025-61725) | High | net/mail: Excessive CPU consumption in ParseAddress in net/mail | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-61727](https://nvd.nist.gov/vuln/detail/CVE-2025-61727) | High | golang: crypto/x509: excluded subdomain constraint does not restrict wildcard SANs | Pod software connections utilize strict explicit routing maps rather than reliance on complex wildcard subdomain fallback parsing. |
| stdlib | gobinary | [CVE-2025-61728](https://nvd.nist.gov/vuln/detail/CVE-2025-61728) | High | golang: archive/zip: Excessive CPU consumption when building archive index | Pod software retries scanning on a malicious file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2025-61730](https://nvd.nist.gov/vuln/detail/CVE-2025-61730) | High | crypto/tls: Handshake messages may be processed at the incorrect encryption level | Pod software doesn't alLow inbound communication initiated by external parties. Outbound endpoints connect via dedicated TLS profiles. |
| stdlib | gobinary | [CVE-2026-27142](https://nvd.nist.gov/vuln/detail/CVE-2026-27142) | High | html/template: URLs in meta content attribute actions are not escaped | Pod software does not perform dynamic HTML meta attribute creation loops inside untrusted client runtimes. |
| stdlib | gobinary | [CVE-2026-32282](https://nvd.nist.gov/vuln/detail/CVE-2026-32282) | High | golang: internal/syscall/unix: Root.Chmod can folLow symlinks out of the root | This vulnerability can be exploited only if unauthorized access to the pod is obtained to write arbitrary local symlinks. |
| stdlib | gobinary | [CVE-2026-32288](https://nvd.nist.gov/vuln/detail/CVE-2026-32288) | High | archive/tar: golang: Denial of Service via maliciously-crafted archives | Pod software retries scanning on a malicious archive file a couple of times and moves on; The processes will restart and pick up remaining work. |
| stdlib | gobinary | [CVE-2026-32289](https://nvd.nist.gov/vuln/detail/CVE-2026-32289) | High | html/template: Cross-Site Scripting (XSS) via improper context tracking | Pod software interfaces do not pipe raw data strings back to web browsers through variable script templates. |
| stdlib | gobinary | [CVE-2025-58186](https://nvd.nist.gov/vuln/detail/CVE-2025-58186) | High | golang.org/net/http: Lack of limit when parsing cookies can cause memory exhaustion | Pod software retries scanning on a malicious payload a couple of times and moves on; container memory limits insulate the platform host environment. |

## Related

- [Pod prerequisites (cluster version v1.28+)](/pod-prerequisites-cluster-version-v128.md)
- [Securiti Hosted Scanning](/securiti-hosted-scanning.md)
- [Elastic Pods V2](/elastic-pods-v2.md)
