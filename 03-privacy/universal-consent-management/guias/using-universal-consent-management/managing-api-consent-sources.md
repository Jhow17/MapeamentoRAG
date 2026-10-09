---
title: "Managing API consent sources"
slug: "managing-api-consent-sources"
updated: 2026-06-19T09:04:02Z
published: 2026-06-19T09:04:02Z
canonical: "helpcenter.securiti.ai/managing-api-consent-sources"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Managing API consent sources

You can add the name of your consent sources in the API consent sources library. You can either specify the consent source name in the payload of the API when uploading consents via the API or create a consent source in the library.

> [!NOTE]
> Note
> 
> Securiti uses the API to ingest consent records, while consent sources define where consent originates, such as a website, mobile app, or call center. The **API** **Consent Sources** library maintains these sources for consistent tracking. If all records come through one API flow, a single consent source may suffice. Multiple sources apply when you need to track different collection channels.

With API consent sources dashboard, you can:

- Add an API consent source.
- Edit, clone, and delete existing API consent sources.
- View unique IDs in the ID column for each record.
- Filter out API consent sources from the dashboard by using a single property or combining multiple properties:
  - ID
  - Name
- Set pagination options to control the number of IDs per page view.

### Using the top-level filter

The top-level filter lets you combine different properties of the API Consent Source and apply filters accordingly. It takes precedence over other filters, working from the top down and determining the result values in the grid view.

To use the top-level filter:

1. From the upper left corner of the API Consent Source dashboard, click **+**, as shown below. ![top_level_filter_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-db2fd7f0-4854-232a-b70d-1e0bf3a791ff.png)
2. On the popup, search API consent source by ID or name.

For instance, if you want to filter API consent source by name (property), click **Name**, and from the right, type the name of the API consent source and press **Enter**. Once done, near the bottom of the popup, click **Apply**, as shown below. ![top_level_filter_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d244638b-5de5-7525-fbb7-f406617161c2.png)
3. Repeat the same step for other properties according to your search needs. Once you apply all required properties, near the bottom of the popup, click **Apply**. Securiti builds a query based on your selected properties and displays the filtered results, as shown below. ![top_level_filter_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0c303963-ed35-727b-eae7-362f549eb066.png)
4. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below. ![top_level_filter_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-965b9574-e0a3-cf5f-3a00-998abbcad3a6.png)

### Adding a new API consent source

To add a new API consent source:

1. In Securiti, open **Universal Consent Management** choose **Universal Consent Configurations > API Consent Sources**.
2. Near the upper right corner of the page, click **+ Add API Consent Source**.
3. On the Add API Consent Source popup, enter the name for your API consent source as shown below, then click **Add API Consent Source** to save it.

![adding_api_consetn_source.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e96417ec-60e3-2790-4269-e7ccdc63381d.png)
