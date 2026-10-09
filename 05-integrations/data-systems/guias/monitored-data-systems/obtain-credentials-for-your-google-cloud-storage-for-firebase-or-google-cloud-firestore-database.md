---
title: "Obtain credentials for your Google Cloud Storage for Firebase or Google Cloud Firestore database"
slug: "obtain-credentials-for-your-google-cloud-storage-for-firebase-or-google-cloud-firestore-database"
updated: 2026-04-28T04:30:08Z
published: 2026-04-28T04:30:08Z
canonical: "helpcenter.securiti.ai/obtain-credentials-for-your-google-cloud-storage-for-firebase-or-google-cloud-firestore-database"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain credentials for your Google Cloud Storage for Firebase or Google Cloud Firestore database

1. Log in to your Firebase administrative console at <console.firebase.google.com>.
2. Select your created project (in this case, named "Firebase-Project").

![FirebaseHome.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8bd564e6-af9c-3250-92b6-8576787390a9.png)

Google redirects you to the Firebase dashboard for your project.
3. Within the left sidebar, click the gear icon under Project Overview and select **Project Settings**.

![Fire_FB-ProjectSettingsfromDashboard_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff0e0a99-a9d6-2693-de30-f0a0fa21fa7c.png)
4. On the Settings menu, record the displayed project ID to use later. Then click **Service accounts**.

![Fire_FB-ProjectID-Name_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ba0d349e-ef7b-75a5-148d-8835d979724e.png)
5. On the screen for your service account (as shown per the enabled Admin SDK), click **Generate new private key**.

![Fire_FB-Generate_JSON_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d2f4eb71-fa37-4e30-8a53-b0c9ece3cc25.png)
6. On the confirmation pop-up for generating a private key, click **Generate key** and save the resulting .JSON key to an easily accessible directory on your system.

![Fire_FB-Confirm_JSON_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0bf9d4dd-7cc8-63e6-f21a-ce779be7cc5b.png)
7. On the left sidebar, open the Develop menu and navigate to the Storage section.
8. Record the link displayed at the top of the list of stored files on your Firebase directories as this serves as the Bucket ID during the Connector Activation process.

![Fire_FB-Copy_BucketID_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bdff1eb6-193e-5435-d373-06c523eef990.png)
9. Proceed to [Activate the Google Cloud Storage for Firebase or Google Cloud Firestore connector in Securiti](/latest/docs/activate-the-google-cloud-storage-for-firebase-or-google-cloud-firestore-connector-in-securiti), [(New UI) Connecting Google Cloud Firestore with Securiti](/latest/docs/new-ui-connecting-google-cloud-firestore-with-securiti) or [(New UI) Connecting Google Cloud Storage for Firebase with Securiti](/latest/docs/new-ui-connecting-google-cloud-storage-for-firebase-with-securiti).
