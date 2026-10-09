---
title: "What's new in 1.134"
slug: "whats-new-in-1134"
updated: 2026-03-16T10:20:23Z
published: 2026-03-16T10:20:23Z
canonical: "helpcenter.securiti.ai/whats-new-in-1134"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's new in 1.134

## July 15, 2025

Want to try different models without juggling tools or cloud accounts? You can now connect to OpenRouter and Google AI Studio right from Gencore AI.

With OpenRouter, you get easy access to models from OpenAI, Mistral, Google, and more - all through the familiar OpenAI API format. For Gemini models, use the new Google AI Studio option. No Vertex AI setup needed. Just add your API key and start experimenting. It’s a simple way to test, prototype, and build with multiple providers in one place.

[Read how to set up](/v1/docs/configuring-llm-providers)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-L4UX0YJO.png)

### Scan for Sensitive Data in Shopify Hosted in Your Environment

Your Shopify store isn’t just connected for handling DSR requests and Gencore Pipelines. With the support for the new self-hosted connector, you can scan both structured (customers, orders, products, locations) and unstructured (files, comments, blog articles) data entities across your Shopify environment. Sensitive data gets discovered and classified right away, so you can view it directly on the Sensitive Data Intelligence dashboards.

[Learn how to configure](/v1/docs/shopify-connectors)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KG7TKMML.png)

### Validation Workbench - Improve Classification Accuracy with Less Time Spent

Need to validate structured data classifications done by the platform, but have hundreds of columns to go through? Validation Workbench makes this manageable by showing a classification sample that you can review one-by-one at your own pace. Here, you can adjust classification results or flag items for later review. The Analytics Dashboard then highlights accuracy, precision rates, how much data you have reviewed, and what still needs attention.

[View the Validation Workbench docs and video tutorial](/v1/docs/using-the-validation-workbench-to-review-and-validate-classifications)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TMSGAA5Q.png)

### Templates and Rules for Easier Task Assignment

Workflows are great for setting up custom tasks. But as conditions pile up, they can get hard to manage.

Now you can use task templates and task rules to automate task creation for DSRs. With templates, you can define reusable task structures with subtasks, deadlines, and automation toggles, while rules trigger them automatically based on request type, jurisdiction, or form values. You can also create tasks without linking to data systems, which is helpful for reviews or steps that happen outside integrations.

[See detailed documentation here](/v1/docs/understanding-task-templates-and-rule-based-task-creation)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SZ64NNCX.png)

### Control How Data Subjects Can Message You

As DSR owners, now you can decide how people who have submitted data requests communicate with you. Maybe you just want quick context on a request or you would rather limit how many messages land in your view. This update lets you pick: can data subjects just reply, or also start the conversation. It works on open and closed requests, so you can handle follow-ups without going back and forth in email threads.

[Show me how to configure](/v1/docs/configuring-privacy-central-customization)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-81W2EN08.png)

### Collaborate Faster With Multi-Respondent Assignments

When you need multiple perspectives—legal, security, ops—you don’t have to coordinate offline anymore. You can now assign specific sections or questions in an assessment to different people. Everyone can respond in real time, like editing a shared doc. No one gets removed when new people are added. Everyone sees what’s happening, and each change gets tracked clearly. This helps when inputs need to come from different teams. Want to keep track of who said what? The updated question history now shows who made each change and when.

[See how to enable real-time collaboration in assessments](/v1/docs/answering-assessment-questions-in-securiti#answer-multirespondent-assessment-questions)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4I82912C.png)

### Pause or Stop Assessments With Cancel and Hold Status Controls

Hit pause, or stop completely. You now have more control over how assessments unfold. Pause an assessment mid-way without losing data. All due dates and reminders freeze, and editing is blocked until you’re ready to resume. Or, if the assessment needs to stop entirely, cancel it—reviewers and respondents are notified, reminders are turned off, and it won’t show up for reassessment. These new status controls help you manage exceptions more cleanly and avoid unwanted reminders, edits, or write-backs when things need to pause or stop.

[Learn how to do it](/v1/docs/understanding-workflow-stages-and-assessment-use-cases)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FS4VK0UD.png)

### Your Custom Fonts, Now in Privacy Notices

The fonts you use say a lot about your brand. Now, you can use your own in your privacy notices too. Upload and apply your custom fonts, see how it looks. Preview the result and publish when it feels just right. This enhancement gives your organization full control to create a visually consistent, on-brand privacy experience across every touchpoint.

[Learn how to import fonts](/v1/docs/creating-a-new-privacy-notice)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-MB36TKMA.png)

### Extend Consent Across Hybrid Platforms

React Native support is now live in MACM. You can scan your cross-platform apps for SDKs and Permissions, just like the native ones. And with our new React Native SDK, you can drop in a consent banner and preference center without building anything separately. It's one setup for both Android and iOS, so you can manage compliance from a single codebase.

[Explore the React Native SDK integration guide](/v1/docs/react-native-sdk-integration-and-implementation-guide)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Y8HS2AID.png)

### More Control Over Consent for Biometrics and Geolocation Cookies

Need to stay on top of consent rules for sensitive data such as biometrics and geolocation?

Now, two new cookie categories, Biometrics and Precise Geolocation, are a part of Securiti’s OOTB list. They show up automatically anywhere cookie category mapping is needed, no setup required. The offline scanner picks them up too. This addition of new cookie categories helps you keep consent requests aligned with privacy laws that treat biometric and geolocation data differently, especially where opt-in is required.

[Know more about new cookie categories](/v1/docs/understanding-the-hybrid-compliance-type)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GMPG4BKH.png)

### One CSV, Thousands of Cookies — Imported

If adding cookies manually feels slow and repetitive, this update is for you. Use a CSV file to upload all your cookies and trackers in one go. Just fill out the template and upload it to the Cookie & Tracker Library. It’s a simple way to save time when you're managing several domains.

[Learn how to bulk import cookies and trackers](/v1/docs/importing-cookies-and-trackers-in-bulk)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZP709F3G.png)

### New Compliance Coverage for China and UAE Regulations

Need to check compliance with China or UAE’s data laws? Start here.

You can now use Securiti’s built-in PIPL and PDPL frameworks to check if your practices align with local rules. Set up a project, use preloaded requirements, and run graph-based tests to catch gaps—like missing consent in China or storage violations in the UAE. Whether you’re validating cross-border transfers or mapping out rights processes, you won’t need to start from scratch. The system helps you apply principles like purpose limitation and lawful processing from day one.

[View the complete list of supported frameworks](/v1/docs/using-the-framework-dashboard)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FMOLTPQ5.png)

### Identify Anonymous SharePoint File Sharing Links

It’s not always obvious how someone got access to a file in SharePoint. Was it through the site? A shared link? Something else? That uncertainty can open up serious security gaps. Now, you can see access provisioned via SharePoint sharing links, including who’s using them—internally or externally. This helps you spot overly broad or anonymous access and take action when needed.

[Learn more about it](/v1/docs/microsoft-365-sharepoint-online)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5V8G92FQ.png)

### Create Custom SQL Checks for Data Quality Across Data Systems

Imagine you want to make sure every order in your system correctly links back to a customer, so you can catch missing or broken data before it causes bigger issues. Now you can. Write your own SQL tests and turn them into reusable checks. With custom expectation templates, you define the logic and thresholds that matter to your data. No need to rely on fixed formats. And it works across systems like Redshift, Snowflake, and BigQuery.

[View steps to create custom SQL checks](/v1/docs/data-quality-framework)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XC13DU9K.png)

[Embedded content](https://app.storylane.io/demo/jbqnbpcbuyqz?embed=inline)

[Embedded content](https://app.storylane.io/demo/7jjdx7cu0fbx?embed=inline)

[Embedded content](https://app.storylane.io/demo/7jjdx7cu0fbx?embed=inline)
