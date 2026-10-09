---
title: "Edit Image"
slug: "edit-image-regular-node"
updated: 2026-02-12T14:27:24Z
published: 2026-02-12T14:27:24Z
canonical: "helpcenter.securiti.ai/edit-image-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Edit Image

The Edit Image node in Securiti’s Workflows module allows you to automate various manipulations and modifications to images within your workflow. This includes tasks like:

- Basic editing such as cropping, resizing, rotating, blurring.
- More advanced operations such as adding text on the image or adding a border.
- Getting all the details of the image

Refer to the [Node configurations section](/v1/docs/edit-image) to understand the node working and properties.

#### Example use case

As an example, let’s create a workflow that streamlines the process of fetching the user profile pictures and editing them according to the standards. The workflow leverages the Edit Image node within to automate user profile picture optimization, simultaneously enhancing user experience and minimizing storage costs.

The **HTTP request** node fetches the user profile picture using the API endpoint. The **Edit image** node then resizes the image as per the set standards and simultaneously uploads the image on Google Drive using the **Google Drive** node. This ensures consistent image sizes and formats across user profiles, enhancing the visual appeal and maintaining consistency.

The following nodes are used in this workflow:

1. [HTTP Request Node](/v1/docs/http-request)
2. Edit Image Node
3. [Google Drive Node](/v1/docs/google-drive)

#### Automated profile picture management

1. Add the HTTP Request node to use the API endpoint that [fetches the user profile picture](https://docs.securiti.ai/modules/system-settings/apidocs/index.html#operation/fetch_users_profile_photo) against the user ID.
2. Add the Edit Image node to update the image size as per the standard used for all the images. Look at the screenshot below for reference.

![Screenshot_2024-02-20_at_3_53_48_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cd3ae986-1130-221f-3bfc-91de688b44b8.png)
3. Add the Google Drive node to upload the updated image on Google Drive account.
4. Connect the nodes and execute the workflow.

![Screenshot_2024-02-20_at_12_55_28_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7c40c8ca-3b3d-208b-cd88-07d96cb2beb2.png)
5. Upon successful execution, the workflow node will provide a successful response. After the workflow runs successfully, you can access the results in two formats i.e. table view and JSON response

![Screenshot_2024-02-20_at_12_56_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-395c128b-2699-e908-4fab-125001cd5cc2.png)

#### Node configuration

| Parameters | Description |
| --- | --- |
| Operation |  | Specify the operation to perform on the image |
| Blur | Choose this option to blur the entire image to make it less sharp |
| Border | Choose this option to add a border to the image. |
| Crop | Choose this option to crop the image. |
| Get information | Choose this option to return information about the image such as resolution. |
| Rotate | Choose this option to rotate the image. |
| Property Name | Specify the name of the binary property in which the image data can be found. |
| Blur | Specify the strength of the blur effect. |
| Sigma | Specify the sigma (variance) value for the blur. |
| Border Width | Specify the width of the vertical segments in pixels. |
| Border Height | Specify the height of the horizontal segments in pixels. |
| Border color | Specify the hex value for the border color. |
| Width | Specify the width in pixels to which to crop the image. |
| Height | Specify the height in pixels to which to crop the image. |
| Position X | Specify the horizontal position in pixels of the left edge of the crop window. |
| Position Y | Specify the vertical position in pixels of the top edge of the crop window. |
| Rotate | Specify the amount of rotation, in degrees. |
| Background color | Specify the Hex value for the color to apply behind the rotated image. |
