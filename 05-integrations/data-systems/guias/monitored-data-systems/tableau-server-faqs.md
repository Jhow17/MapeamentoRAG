---
title: "Tableau Server FAQs"
slug: "tableau-server-faqs"
updated: 2026-09-01T05:22:31Z
published: 2026-09-01T05:22:31Z
canonical: "helpcenter.securiti.ai/tableau-server-faqs"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Tableau Server FAQs

This article answers frequently asked questions about the Tableau Server connector.

### Authentication and Access

****How does SAI handle Server Administrator tokens? Server Administrators have access to all sites, so is the administrator token itself a factor in authentication issues?****

SAI does not apply any special handling to Personal Access Tokens (PATs) belonging to Server Administrators or Site Administrators. SAI authenticates to Tableau using the configured Tableau Server URL, target site (**SiteName**`)`, and PAT. Once authentication succeeds, the resulting session uses the permissions associated with the PAT owner.

Therefore, administrator-level access does not change how SAI authenticates the PAT. If Tableau returns an **Invalid token** or **Missing token** error, it indicates that the authentication request was not accepted for the specified site or credentials. Verify that the PAT is valid and can authenticate directly to the configured site.

****Do I need to generate a separate PAT for each Tableau site that I want to connect to SAI?****

Each Tableau site that you want to connect should be configured as a separate SAI data system, because Tableau authentication is performed against the specific site (**SiteName**) configured for that data system.

A separate PAT is not required for every site. You can reuse the same PAT across multiple SAI data systems as long as the PAT can successfully authenticate to each target site and its owner has the required permissions.

If the PAT cannot authenticate to a particular site, use a different PAT, or an account with the appropriate access for that site's SAI data system.
