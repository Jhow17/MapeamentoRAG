---
title: "Troubleshooting guide for Tableau Server"
slug: "troubleshooting-guide-for-tableau-server"
updated: 2026-09-01T05:22:23Z
published: 2026-09-01T05:22:23Z
canonical: "helpcenter.securiti.ai/troubleshooting-guide-for-tableau-server"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting guide for Tableau Server

This section covers troubleshooting for the following issues when configuring the Tableau Server data system connector.

### Tableau connector activation fails with 401001 authentication error

When activating the Tableau connector, you may encounter the following error:

```plaintext
Request to access token failed with status: 401
{
  "error": {
    "summary": "Signin Error",
    "detail": "The personal access token you provided is invalid.",
    "code": "401001"
  }
}
```

The `401001` error means that Tableau could not authenticate using the configured **Personal Access Token (PAT)**. This can occur if the PAT is invalid, expired or revoked, or does not belong to the Tableau site configured in the connector.

#### Resolution

1. Verify that the Tableau server URL, site content URL, PAT name, and PAT secret configured in the connector are correct.
2. Test the PAT directly against the Tableau sign-in API. Use the same PAT and site details configured in the connector:

```plaintext
curl -X POST "https://et-tableau-uat.fmr.com/api/3.27/auth/signin" \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -d '{
    "credentials": {
      "personalAccessTokenName": "YOUR_PAT_TOKEN",
      "personalAccessTokenSecret": "YOUR_PAT_SECRET",
      "site": {"contentUrl": "<SiteName>"}
    }
  }'
```

Replace `YOUR_PAT_SECRET` , `YOUR_PAT_TOKEN`, and `&lt;SiteName&gt;` with the actual PAT secret, PAT name and Site name respectively.
3. Check the response from Tableau. If the request succeeds, the PAT is valid. Confirm that the connector is using the same PAT name, PAT secret, Tableau server URL, and site content URL as the successful request.
4. If the request returns `401001`, Tableau is rejecting the PAT directly. Verify that the PAT name and secret are correct, the PAT has not expired or been revoked, and the user associated with the PAT has access to the specified Tableau site.
5. If the existing PAT is invalid, expired, or revoked, generate a new Personal Access Token in Tableau and update the connector configuration.
