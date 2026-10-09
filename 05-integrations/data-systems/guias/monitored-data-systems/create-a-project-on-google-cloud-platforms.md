---
title: "Create a project on Google Cloud Platforms"
slug: "create-a-project-on-google-cloud-platforms"
updated: 2025-10-31T07:39:07Z
published: 2025-11-03T06:14:28Z
canonical: "helpcenter.securiti.ai/create-a-project-on-google-cloud-platforms"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Create a project on Google Cloud Platforms

In order to link your Firebase or Firestore Configuration with Securiti for personal data synchronization and classification, you must create a project to act as an connecting interface.

1. Log in to your Google Cloud Platform dashboard at <*console.Cloud.google.com*>.
2. On the top menu bar, click **Select a Project**.

![GCP_Dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e3ddbe23-369d-15f3-84dc-e27f5c266f99.png)
3. On the Projects pop-up, click **New Project**.

![GCP_CreateNewProject.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21515c02-9c4b-c7bd-b901-8e494c569ec5.png)
4. Configure your new project by entering an appropriate name and saving it as a part of your administrative account:

![GCP_NewProject1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a4cea1ae-984a-2129-3d02-fc1a6c4c806b.png)

After you create the project, Google redirects you to your Google Cloud Platform dashboard.
5. Click **Select a Project** and select the new Project you have created (in this case, "InitialSteps").

![GCP_NewProject2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-207c8bdf-21b9-cc1c-47e7-e1ab9b7834a8.png)
6. Open the left sidebar and navigate to **API & Services > Dashboard**. ![GCP_LeftSidebarAPIs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6af7b423-7378-33ae-486b-b2a27820a530.png)
7. On the dashboard for API & Services, click **+ Enable API and Services**.

![GCP_LeftSidebarAPIs1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f76944e1-76c5-6bdb-aa98-0489b80730f3.png)
8. Search for the **Admin SDK** on the Google API Marketplace and enable it for your project.

![GCP_LeftSidebarAPIs2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff54d5ca-b40c-e8ab-a351-b4b79d4c3512.png)
9. On the **Overview** page for the Admin SDK, click **Create Credentials**. These are needed for the SDK to function properly for our use case.

![GCP_LeftSidebarAPIs3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1049d8c8-f21e-3066-cace-24bcaea87966.png)
10. Select **Service Account** as your desired type of Credentials for your project.
11. Enter your desired details for the service account credential (such as assigning it an appropriate name) and proceed to create the service account.

![GCP_LeftSidebarAPIs4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e4be5b7-dfcf-ac79-b16e-3cb26044b59b.png)

Google redirects you to a list of service accounts associated with your Administrative account.
12. On the updated screen for service accounts, click the menu for the newly created service account for your project and select **Edit**.

![GCP_ServiceAccount1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2d1dff6a-b75f-ae23-9b83-71d761e80486.png)
13. Mark the checkbox for **Enable G Suite Domain-wide Delegation** for your service account and click **Save**.

![GCP_ServiceAccount2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cd038957-7731-79dd-704e-dee1fef71f04.png)
14. Confirm details for your G Suite enabled service account, enter an appropriate display name, and click **Save**.

![GCP_ServiceAccount3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f52a28fe-e965-96b2-ebf5-8e2907fce91b.png)
15. Navigate to the Firebase console homepage at <console.firebase.google.com> and click **Create a Project**.

![Fire_FBHome-Create_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-23674015-e01c-c74b-802a-be8a1a570dec.png)
16. Select your existing project as the project name (in this case, selecting InitialSteps) and proceed.

![GCP_FirebaseLink1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a4fd87a1-9f21-8cc4-3b3f-bba73f3d8ab0.png)
17. Enable Google Analytics for your project by selecting Default Account for Firebase and then click Add Firebase.

![GCP_FirebaseLink2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f32cd76a-99fb-b62c-f58e-73a51adf5a1f.png)
18. You are then shown a confirmation screen for your project being added as part of your Firebase Configuration.

![GCP_FirebaseLink3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fe7e364e-e4b5-b9d4-affc-f9854d1d7d49.png)
19. Proceed to [Obtain credentials for your Google Cloud Storage for Firebase or Google Cloud Firestore database](/v1/docs/obtain-credentials-for-your-google-cloud-storage-for-firebase-or-google-cloud-firestore-database).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
