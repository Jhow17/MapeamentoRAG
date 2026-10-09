---
title: "Pods deployment API reference"
slug: "deployment-api-reference"
description: "The Pods Deployment APIs support pod deployment and management, EPod V2 installation using Helm, cluster status monitoring, node management, backup and restore operations, audit logging, event logging, custom registry configuration, AirGap bundle installation, EDSS installer, preflight diagnostics, API key authentication, and OAuth 2.0 authentication. Use these APIs to automate pod provisioning, manage cluster operations, monitor pod health, and integrate Securiti pod management into your infrastructure workflows. Pods Deployment APIs for creating, managing, and monitoring Securiti pods and EPod V2, including backup, restore, cluster status, and Helm installation."
updated: 2026-06-24T12:21:39Z
published: 2026-06-24T12:21:39Z
canonical: "helpcenter.securiti.ai/deployment-api-reference"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Pods deployment API reference

The Pods deployment APIs lets you to deploy, configure, and manage [Securiti Pods (cluster version v1.28 and later)](/latest/docs/pods-cluster-version-v128-and-later) and [Elastic Pods (EPods) V2](/latest/docs/elastic-pods-v2) within your own cloud infrastructure. Using these REST APIs, you can automate and manage several actions without performing these actions manually through the Securiti platform. See the table below for the major categories that the API supports:

| Category | Description |
| --- | --- |
| OAuth | Covers the authentication flow for generating access tokens used in OAuth 2.0 based API authentication for the Pods deployment APIs. |
| EPod V2 | Covers the full deployment and configuration lifecycle of Elastic Pods V2, including fetching cluster and node status, retrieving Helm install and register commands, downloading the values.yaml configuration file and image repository credentials in Base64, fetching Helm Chart and AirGap installation bundle URLs, and listing available images for custom registry setup. |
| Pod (cluster version v1.28 or later) | Covers the complete lifecycle management of standard Pods, including creating, listing, fetching, editing, and deleting pods, revoking pod keys, generating installation curl commands, downloading pod packages and the EDSS installer, downloading preflight diagnostic scripts, and generating and downloading pod health reports. |
| Backup and Restore | Covers pod data protection and recovery operations, including configuring the backup transfer protocol, verifying the backup protocol connection status, retrieving existing restore points, and adding new restore points for pod recovery. It supports both Pods and EPod V2. |
| Logs | Covers pod activity tracking and auditing, including fetching audit logs that record administrative actions and event logs that capture pod-level operational events for monitoring and troubleshooting purposes. |

The Pods deployment API is a REST API that accepts and returns data in JSON format. It supports two authentication methods, Simple API Key authentication using `X-API-KEY`, `X-API-SECRET`, and `X-TIDENT` headers, and OAuth 2.0 authentication using an access token. The API is available across all the Securiti supported regions, and also supports custom server URLs for on-premises deployments. A Postman collection is available for local testing and integration.

Use the [Pods deployment REST API documentation](https://securiti-doc-router.securiti.ai/modules/appliances/apidocs/index.html) to browse and test Pods and Elastic Pods (EPod V2) APIs, and to find granular request and response details of the various API calls.
