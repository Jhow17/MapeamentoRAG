---
title: "Self-hosted user portal deployment configuration"
slug: "self-hosted-user-portal-firewall-deployment"
updated: 2026-08-10T15:38:37Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/self-hosted-user-portal-firewall-deployment"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Self-hosted user portal deployment configuration

In the **Deployment Configuration** tab, you can configure firewall deployment type and Ingress.

## Firewall deployment

To enable firewall in Gencore AI pipeline or as a standalone Firewall API:

In the **Firewall** section:

1. Enable the **Firewall Deployment** toggle.
2. Select the **Firewall Deployment Type**:

| Firewall deployment type | Description |
| --- | --- |
| Sagemaker (AWS) | To deploy the firewall in Sagemaker AWS. |
| On-Premises | To deploy the firewall on premises. |

## Configuring Ingress

You can optionally configure the Ingress resource — including the Ingress Controller, TLS certificate, and annotations — used to make Gencore AI services accessible. You must install and provide the Ingress Controller and TLS certificate, as they are not included as part of this deployment. Once configured, the Ingress routes requests are sent to your custom domain to the appropriate service within the cluster, using the provided TLS certificate to enable HTTPS.

For Ingress related configurations, in the **Ingress** section:

1. Add the following information:

| Field | Description |
| --- | --- |
| Ingress Controller Class | Specify the Ingress controller class that processes the Ingress resource, such as nginx or traefik. |
| TLS Secret Name | Specify the Kubernetes secret containing the TLS certificate in the namespace used to enable HTTPS for the custom domain. |
| Custom Annotations | Specify key-value annotations that customize Ingress behavior, such as redirects, request-size limits, or certificate management settings. > [!NOTE] > Note > > You can add multiple Key-Value pairs |

![Configuration settings for User Portal ingress, including controller class and TLS secret name.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/User Portal - Ingress - 149.png)
2. To save changes, click **Save & Continue**.
