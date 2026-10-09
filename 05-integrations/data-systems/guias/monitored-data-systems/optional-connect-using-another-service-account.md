---
title: "(Optional) Connect using another service account"
slug: "optional-connect-using-another-service-account"
updated: 2026-04-28T04:13:56Z
published: 2026-04-28T04:13:56Z
canonical: "helpcenter.securiti.ai/optional-connect-using-another-service-account"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Connect using another service account

If you want to connect using the service account of a different project, consider the scenario below:

Assuming you have your Pod and service account created in **Project A** while your SQL instances are in **Project B**, you need to follow the procedure below.

1. Go to **IAM & Admin > Service Accounts** in the project A where you initially created the service account.
2. Record the email address of the service account for later use.
3. Add an IAM user in your SQL Cloud Instance and grant SELECT on the required tables using the command below.

```plaintext
GRANT SELECT on "<table_name>" to "<iam_username_email>";
```
4. Navigate to the destination project B where you want to grant the service account Permissions.
5. Go to **IAM & Admin > IAM** and click **Add**.
6. Use the service account email you recorded earlier and grant the necessary role for the project (e.g., "Kubernetes Engine Cluster Viewer" or a custom role as needed).
7. Proceed to [Activate the Google Cloud SQL for MySQL connector in Securiti](/latest/docs/activate-the-google-cloud-sql-for-mysql-connector-in-securiti) or [(New UI) Connecting Google Cloud SQL for MySQL (self-hosted) with Securiti](/latest/docs/new-ui-connecting-google-cloud-sql-for-mysql-self-hosted-with-securiti).
