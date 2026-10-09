---
title: "Troubleshooting for Amazon S3 connector"
slug: "troubleshooting-for-amazon-s3-connector"
updated: 2025-10-30T19:14:50Z
published: 2025-11-03T06:13:51Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-amazon-s3-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Amazon S3 connector

This section covers troubleshooting possible issues during Amazon S3 data system configuration and integration with Securiti.

For more information, see [Amazon's official documentation for troubleshooting common issues](https://docs.aws.amazon.com/AmazonS3/latest/API/ErrorResponses.html#ErrorCodeList).

### Resolving "SignatureDoesNotMatch" Error in Amazon S3 API Calls

When configuring the Amazon S3 connector, if the appliance is connected with BURP Proxy, you may encounter a "SignatureDoesNotMatch" error across various flows, including authentication and discovery scans.

```plaintext
error SignatureDoesNotMatch: The request signature we calculated does not match the signature you provided. Check your key and signing method.
```

See [AWS Documentation on Signature Version 4](https://docs.aws.amazon.com/general/latest/gr/signature-version-4.html), for more information on the signing process.

This error occurs because BURP Proxy is not correctly signing the requests to Amazon S3 with the appropriate Amazon credentials. The calculated signature does not match the provided signature, which is due to the absence of proper signing by BURP Proxy.

To resolve this issue you need to reconfigure your connector appliance.

1. Install the AWS SigV4 Extension in BURP Suite. The AWS SigV4 extension is necessary for Burp Suite to correctly sign AWS API requests.
2. Configure the AWS SigV4 Extension. Ensure that the extension is properly configured with the correct AWS credentials.

This configuration allows BURP Suite to sign the S3 API requests with the right credentials, preventing the "SignatureDoesNotMatch" error.
3. Test the configuration. After configuring the extension, test the S3 API calls again to ensure that the requests are signed correctly and the error no longer occurs.
