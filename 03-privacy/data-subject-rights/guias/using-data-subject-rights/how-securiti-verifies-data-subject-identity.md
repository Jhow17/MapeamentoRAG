---
title: "How Securiti verifies data subject identity"
slug: "how-securiti-verifies-data-subject-identity"
updated: 2026-09-14T14:53:27Z
published: 2026-09-14T14:53:27Z
canonical: "helpcenter.securiti.ai/how-securiti-verifies-data-subject-identity"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# How Securiti verifies data subject identity

For a DSR request submitted through a Securiti DSR form, Securiti uses one of the following processes to validate the request as described in the following sections. These processes ensure that the request comes from a real data subject, and that they are who they assert they are.

### Default identity verification

With its default identity validation, Securiti shows the data subject a random four digit number, and later requests the number in an email sent to their address. After the data subject supplies the correct number, Securiti creates an account for them that they use to track their DSR request, and any other DSR requests they submit to your organization:

1. The data subject visits your company website and follows a link to the [DSR request form](/v1/docs/creating-and-publishing-dsr-request-forms).
2. The data subject fills out the form and submits it.
3. Securiti shows the data subject a random four-digit code number that they later use to verify their email address. The code helps protect them from unauthorized access to their personal data. Securiti also prompts them to check their email for a verification link.
4. Securiti sends a verification email to the email address provided by the Data Subject, with a “Confirm Email” button to verify their email address.

> [!NOTE]
> **Note**
> 
> Securiti lets data subjects resend the verification email 4 times in consecutive intervals of 10 sec, 30 sec, and 1 min. Once they reach the maximum limit, Securiti prevents them from sending any more verification emails and ask them submit another request
> 
> ![Screenshot_2024-04-26_at_2_08_52_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0a00c04-f520-9f20-5a05-101248ba3b04.png)
5. The data subject opens the email message and clicks the confirmation button, and is redirected to a page that prompts them for the four-digit code number. By entering the code number, the data subject proves that they are the person who submitted the original DSR request, and verifies that the email address they provided is correct and valid.
6. They enter the code and click **Verify**.
7. If the code entered matches the one shown to the Data Subject when they submitted their DSR form, Securiti:
  - Shows the data subject a Success page that includes a request ID and also the information provided on the DSR form.
  - Creates a DSR request for the data subject in our DSR dashboard.
  - Creates an account for the data subject on the [DSR request center](/v1/docs/understanding-the-dsr-request-center) for your organization's Securiti account. The request center is where the data subject logs in to monitor the status of their request, and to get the final report for Access and Port requests. The request center also lets them exchange messages with the owner of their DSR request in Securiti.

### Passwordless identity verification

You can configure Securiti so that data subjects do not have to explicitly create an account on the data subject portal in order to submit DSR requests, view reports, or communicate with DSR request or subtask owners. That way they do not need a password to track their requests.

> [!NOTE]
> **Note**
> 
> If you enable this feature, Securiti maintains backward compatibility for existing DSR requests and data subject portal accounts.

With passwordless authentication enabled, when a data subject submits a DSR request:

1. The data subject visits your company website and follows a link to your [DSR request form](/v1/docs/creating-and-publishing-dsr-request-forms).
2. The data subject fills out the form and submits it.
3. Securiti redirects the data subject to a page that tells them that it has sent them a verification email message. It also sends the verification email to the email address provided by the data subject, with a “Confirm Email” button to verify their email address.
4. When they open the email and click the "Confirm Email" link, Securiti redirects them to a Request Submitted page that confirms their request is being processed and shows them information about the request. Securiti also sends them a second email with a link.
5. The data subject uses the link in that second email message to access the Privacy Central portal and track their DSR request without having to set up an account or a password. The link applies specifically to that one DSR request. If the data subject submits any additional DSR requests, Securiti sends them unique links that they use to track each request.

To enable passwordless access:

1. In the Data Subject Rights module, choose **Settings > Privacy Central Settings**.
2. Click **Edit** (pencil icon) on the right side to open the Account Setup in edit mode as shown below.

![Privacy Central settings for data subject rights and account access configuration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 6.35.48 PM.png)
3. Click **Save**.

### Identity verification with Unico

When you have configured Securiti to use Unico (formerly Acesso Digital):

1. The data subject visits your company website and follows a link to a DSR form that you have configured as described in [Configuring identity verification with Unico](/v1/docs/configuring-identity-verification-with-unico).
2. The data subject fills out the form and submits it.
3. Securiti redirects them to a page that tells them to expect a verification email as shown below.

![RN_IDV_7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4674dcda-a1fe-6ba7-9192-cbb408890c45.png)
4. When they click the confirmation link, Securiti sends them a second email, and also redirects them to an information page as shown below.

![RN_IDV_9.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1bb165d4-8652-38d5-9a8f-4b552ed6f3e3.png)
5. When they click the verify link on the email or on this page, they are redirected to a page that verifies their identity via Unico using a photograph as shown below. The photograph may appear distorted, but this does not affect verification.

![RN_IDV_10__1-2-3_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66c34753-92e8-a274-273b-defd99424e02.png)

![RN_IDV_11.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-69ee3d08-cc35-8351-8ee6-d92a6c40369a.png)

![RN_IDV_12.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b868bfab-bbd9-ffcb-486f-ebe60b732692.png)

![RN_IDV_13.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-26f775e1-c2c6-e2f8-e066-45839401a2dd.png)
6. After Unico verifies their identity, they see a confirmation page as shown below, and can then use the data subject portal to monitor the progress of their DSR request.

![RN_IDV_14.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a93f420-6175-6bb4-c4c1-a3a31fc7da24.png)

### Identity verification with ID.me

When you have configured Securiti to use ID.me:

1. The data subject visits your company website and follows a link to a DSR form that you have configured as described in [Configuring identity verification with ID.me](/v1/docs/configuring-identity-verification-with-idme).
2. The data subject fills out the form and submits it.
3. Securiti shows the data subject a random four-digit code number that they later use to verify their email address. The code helps protect them from unauthorized access to their personal data. Securiti also prompts them to check their email for a verification link.
4. Securiti sends a verification email to the email address provided by the data subject, with a “**Confirm Email**” button to verify their email address.
5. The data subject opens the email message and clicks the confirmation button, and is redirected to a page that prompts them for the four-digit code number. By entering the code number, the data subject proves that they are the person who submitted the original DSR request, and verifies that the email address they provided is correct and valid.
6. They enter the code and click **Verify**.
7. If the code entered matches the one shown to the data subject when they submitted their DSR form, Securiti shows the Data Subject a page that tells them that they must also verify their identity with ID.me. The page also asks them to create an account. When they click **Create Account**, Securiti redirects them to a page with another Verify button.
8. When the data subject clicks Verify, Securiti redirects them to an ID.me page where they login or create an account and verify their identity.
9. Once the data subject verifies their identity with ID.me, they are redirected back to a Securiti page with a Proceed button. When they click Proceed, Securiti:
  - Creates a DSR request for the data subject in our DSR dashboard, with identity verification status as shown below.

![ID_verify_details_in_DSR_workbench.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bee453e4-8633-2a49-73a8-86b063bb10b9.png)
  - Asks the data subject to log in to the [DSR request center](/v1/docs/understanding-the-dsr-request-center) for your organization's Securiti account. The request center is where the data subject logs in to monitor the status of their request, and to get the final report for Access and Port requests. The request center also lets them exchange messages with the owner of their DSR request in Securiti.

### Identity verification with Jumio

When you have configured Securiti to use Jumio:

1. The data subject visits your company website and follows a link to a DSR form that you have configured as described in [Configuring identity verification with Jumio](/v1/docs/configuring-identity-verification-with-jumio).
2. The data subject fills out the form and submits it.
3. Securiti sends the data subject an email to confirm the validity of their email address. The email contains a link.
4. When the data subject clicks the link in the email, it redirects them to a page that shows the status of their request, and informs them that they must verify their identity with Jumio.

![RN_DSR_Jumio5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b4e7813c-aa24-1858-6b2f-a518e94d96f5.png)

Meanwhile, Securiti also sends the Data Subject a followup email with a link that they can use to open their request in the request center.
5. When the data subject clicks the link, it redirects them to their request in the DSR request center. The request has a Verify button as shown below.

![RN_DSR_Jumio7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4ca97435-15d8-5f77-ab47-50304753311f.png)
6. When the data subject clicks Verify, it redirects them to the page shown below.

![RN_DSR_Jumio8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8c89d568-24a5-3552-d33b-3a4b2cae2ed9.png)
7. When they click Verify on that page, it redirects them to Jumio to verify their ID as shown in the following sequence.

![RN_DSR_Jumio9.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4cf47000-db32-3fce-1a85-9749e7d2e131.png)

![RN_DSR_Jumio10.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4988c3f9-ec2d-be71-c801-9de373668fb1.png)

![RN_DSR_Jumio11.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-db6aa1fe-8995-8bd0-f22b-be2b65dbeae0.png)
8. After they submit their identity documents and photos, Jumio redirects them back to Securiti as shown below.

![RN_DSR_Jumio12.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6c2ef3b3-8e3f-1f29-91bc-bd4559a8f475.png)
9. When they click Proceed, it redirects them to their DSR request in the request center. The request is marked as “Verification in Progress” until Jumio completes the verification.

The process typically takes a few minutes to complete. If there is a communication issue between Securiti and Jumio, Securiti re-tries the request up to six times on five minute intervals. If there is no response within 30 minutes, the Data Subject should re-submit the request. However, they must wait 4 hours before resubmitting.
10. Once Jumio finishes verifying their identity, Securiti accepts their DSR request, and changes the Verify button on their request to Messages as shown below.

![RN_DSR_Jumio14.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-154c4e15-c96a-f16c-c220-1fa12a39d760.png)

---

### FAQs

#### 1. If we submit an internal form, how do we communicate with the data subject?

When submitting a DSR request via an internal firm, you have the option to invite the data subject to create a Privacy Central account by marking the "Create or associate with the Data Subject account in Privacy Central Portal" checkbox. When you submit DSR request, Securiti send an email to the data subject. The email invites them to create an account so that they can later log in to the Securiti portal to access their report.

## Related

- [Configuring identity verification with ID.me](/configuring-identity-verification-with-idme.md)
- [Configuring identity verification with Jumio](/configuring-identity-verification-with-jumio.md)
- [Configuring identity verification with Unico](/configuring-identity-verification-with-unico.md)
