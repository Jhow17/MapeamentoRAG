---
title: "Managing firewall profiles"
slug: "managing-firewall-profiles"
updated: 2025-12-05T02:14:46Z
published: 2025-12-05T02:14:46Z
canonical: "helpcenter.securiti.ai/managing-firewall-profiles"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Managing firewall profiles

You can perform the following actions on a Firewall profile:

- [View](/v1/docs/managing-firewall-profiles#viewing-a-firewall-profile)
- [Edit](/v1/docs/managing-firewall-profiles#editing-a-firewall-profile)
- [Test](/v1/docs/managing-firewall-profiles#testing-a-firewall-profile)
- [Disable](/v1/docs/managing-firewall-profiles#disabling-a-firewall-profile)
- [Delete](/v1/docs/managing-firewall-profiles#deleting-a-firewall-profile)

### Viewing a firewall profile

1. On the list of profiles, locate the card for the profile you want to view.
2. From the right side of the card, choose **Options** (three dots), and select **View**.

### Editing a firewall profile

1. On the list of profiles, locate the card for the profile you want to edit.
2. To the right side of the card, choose **Options** (three dots), and select **Edit**.
3. Update the firewall profile as required.
4. To save the changes, click **Save Firewall Profile**.

### Testing a firewall profile

To test a firewall profile:

1. In the **Options**, click **Test Profile**.

![129_FW_profile_options_Test_Copy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7b003b40-4076-df48-bf80-eac970763567(1).png)
2. In the **Test Profile** popup:
  1. Type your prompt.
  2. Press **Enter**. The relevant violations are displayed.

![129_test_FW_profile.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-62c1a70c-e624-b804-0ac0-6e571d37f771(1).png)
  3. To view the complete response log:

The **Response log** displays. This log displays the details relevant to the firewall profile.

![129_Test_FW_Response_Log.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d22d642b-ac23-0871-a238-e01e7614508c(1).png)
    - On the **Test Profile** popup, click the link **Troubleshoot this response by viewing the full response log**.
    - click the **download** icon.

![129_Response_log_link.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07d2525e-68e4-50ea-6a08-c10517641dc0(1).png)

### Disabling a firewall profile

1. On the list of profiles, locate the card for the profile you want to disable.
2. To the right side of the card, choose **Options** (three dots), and select **Disable**.

### Cloning a firewall profile

1. On the list of profiles, locate the card for the profile you want to clone.
2. To the right side of the card, choose **Options** (three dots), and select **Clone**. A dialog box displays with the name of the profile to be cloned as the name of the original profile with the word “duplicate” added to it. You can edit the name as required.
3. To clone the profile, click **Clone**.

### Deleting a firewall profile

1. On the list of profiles, locate the card for the profile you want to delete.
2. To the right side of the card, choose **Options** (three dots), and select **Delete**.
3. To confirm deletion, on the confirmation popup box, click **Delete Profile**.

A firewall profile is a collection of policies that control how firewalls are configured and dictate how firewalls are configured in pipelines.

A firewall serves as a protective barrier between the user prompts and the LLM and between the LLM and the source data.

## Related

- [Using firewall profiles](/using-firewall-profiles.md)
- [Creating firewall profiles](/creating-firewall-profiles.md)
- [Viewing findings for LLM firewalls](/viewing-findings-for-llm-firewalls.md)
