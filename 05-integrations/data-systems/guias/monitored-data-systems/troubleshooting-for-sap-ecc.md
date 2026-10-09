---
title: "Troubleshooting for SAP ECC"
slug: "troubleshooting-for-sap-ecc"
updated: 2026-04-07T03:50:21Z
published: 2026-04-07T03:50:21Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-sap-ecc"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for SAP ECC

This page covers the troubleshooting guide for SAP ECC authentication and access errors.

## Failed SAP ECC DSR Robotic Automation

You see the following error message while executing DSR Robotic Automation :

```plaintext
failed to run database query, err : failed to run query on jdbc proxy, err : rpc error: code = Internal desc = class java.sql.SQLException,Error message =[sapado:executeoperation] Initialization of destination SAP--798385928-146 failed: Connect to SAP gateway failed connection parameters: TYPE=A DESTINATION=SAP--798385928-146 ASHOST=MRVSAPHCM04 SYSNR=01 PCS=1 LOCATION CPIC (TCP/IP) on local host with Unicode ERROR max no of 202 conversations exceeded TIME Thu Feb 19 12:45:17 2026 RELEASE 721 COMPONENT CPIC (TCP/IP) with Unicode VERSION 3 RC 466 MODULE r3cpic_mt.c LINE 14892 COUNTER 188 , query : SELECT T1."CPF_NUMBER" from "SAPERP"."T7BREFD_EEINFO" T1 WHERE T1."CPF_NUMBER" IN ('2***********') LIMIT 500
```

### Description

You see the above-mentioned error because the SAP conversation/connection limit is being exceeded. If increasing the limit is not preferred due to performance concerns, implement connection pooling to enforce a cap on SAP connections by following the resolution.

### Resolution

To enforce a cap on SAP connections:

1. In the **Authentication** section, click **Reconfigure**.
2. In the **Additional Connection String Options**, configure the connection pooling by following the example:

`UseConnectionPooling=true;PoolMaxSize=20;PoolMinSize=10;PoolIdleTimeout=200;PoolWaitTime=200;`

Use the table below to understand the connection pooling configurations:

| Configuration | Explanation |
| --- | --- |
| UseConnectionPooling | Enables the connection pooling feature, which allows the provider to reuse existing connections instead of creating new ones for each request. Requires `UseConnectionPooling=True.` |
| PoolMaxSize | Specifies the maximum number of connections allowed in the connection pool. If not provided, it defaults to 100. Requires `UseConnectionPooling=True.` |
| PoolMinSize | Specifies the minimum number of connections to be maintained in the connection pool at all times. Requires `UseConnectionPooling=True.` |
| PoolIdleTimeout | Specifies the maximum idle time, in seconds, that a connection can remain in the pool before being closed. Requires `UseConnectionPooling=True.` |
| PoolWaitTime | Specifies the maximum number of seconds a connection request waits for an available connection in the pool. Requires `UseConnectionPooling=True.` |
3. Click **Save Configuration and Continue.**
