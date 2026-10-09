---
title: "Using Custom Registry with EPod V2"
slug: "using-custom-registry-with-epod-v2"
updated: 2025-10-30T18:19:58Z
published: 2025-11-03T06:13:35Z
canonical: "helpcenter.securiti.ai/using-custom-registry-with-epod-v2"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Using Custom Registry with EPod V2

Selecting Custom Registry lets you move the images from the Securiti registry into your custom registry. This is helpful when you have restricted your clusters and infrastructure to pull images from only a single controlled registry. Make sure your cluster, where you intend to install the Epod V2, has access to your custom registry. To proceed with it, follow these steps:

1. On the **Credentials File** tab:
  1. Download the Credentials File to download the file that contains the credentials that you need to pull the images from the Securiti registry into your custom registry.

![Settings page for Elastic Pods V2 with credentials file instructions and download option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/credentials_Epodv2.png)

If you have already registered the pod, it doesn't let you download the credentials file due to the following reasons:

![Credentials file section showing usage warning and Kubernetes command for deployment.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/credentials_file_restricted_Epodv2(1).png)

> [!TIP]
> Note
> 
> If you don't have access to the credentials file, you can:
> 
> 1. Create a new EPod V2 cluster.
> 2. Download its credentials file.
> 3. Apply the credentials to your preregistered EPod V2, as mentioned in the procedure Step 1.b.
> 
> This lets you use the new credentials file that is crucial for upgrading your EPod V2.
    - To prevent accidental overwriting of the valid license key or credentials.
    - To reduce the risk of image pull failures during upgrades.
  2. Move the downloaded file into the “**~/.docker/config**” directory.
  3. Click **Save and Continue**.
2. On the **List of Images** tab, you see a list of images. Copy the list and save it in your preferred directory.

![15_List_of_images.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-324dc0e8-07b1-1ce9-d4dd-396f1e0628a6(2).png)
  1. Now you must pull the images and push them into your own custom registry depending upon your infrastructure policies. Use the following command.

```bash
docker pull <image>:<tag>
```

See the example below.

```bash
docker pull app.securiti.ai/foundri/dd-connector:<tag>
docker tag <my-registry>/foundri/dd-connector:<tag>
docker push <my-registry>/foundri/dd-connector:<tag>
```

You must repeat the above steps for all the images.

> [!TIP]
> **Note**
> 
> You must use the same image repository and tag names from the List of Images page.

If the custom registry requires authentication, the application uses a Kubernetes secret to pull the images. Create a Kubernetes secret named registrykey and apply it to the install namespace. The config.yaml file and all deploying images automatically reference this secret name.

## Related

- [EPod V2 installation in Securiti](/epod-v2-installation.md)
- [Managing EPod V2](/managing-epod-v2.md)
- [Upgrading EPod V2](/upgrade-epod-v2.md)
- [Prerequisites for EPod V2](/prerequisites-for-epod-v2.md)
