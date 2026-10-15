---
title: "Using EDC Ingestion"
slug: "edc-ingestion"
updated: 2026-09-24T08:58:41Z
published: 2026-09-24T08:58:41Z
canonical: "helpcenter.securiti.ai/edc-ingestion"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Using EDC Ingestion

### EDC ingestion configuration

**Scenario**

As a data engineer, you need to integrate metadata from your DBT models into the enterprise catalog. Native discovery doesn’t support this source. With EDC Ingestion, you configure the DBT connector through the UI, pulling metadata directly into EDC using DataHub plugins. This gives governance teams full visibility into your transformation pipelines without manual effort.

#### What is EDC ingestion?

EDC ingestion lets you configure, and execute metadata ingestion using third-party connectors developed by the DataHub community using the Enterprise Data Catalog user interface. This makes getting metadata into Securiti platform easier than before. This capability augments the connector support provided by the Sensitive Data Intelligence module. The EDC ingestion capability allows you to easily configure and execute these additional connectors providing support for sources not supported by Sensitive Data Intelligence like ETL tools like DBT or models from Looker.

> [!NOTE]
> **Note**
> 
> EDC ingestion runs using DataHub plugins. For detail information about these plugins, refer to the DH documentation, specifically the Sources section. For example, for Snowflake ingestion, you can refer to this [Snowflake specific data source](https://docs-website-2uuxmgza2-acryldata.vercel.app/docs/generated/ingestion/sources/snowflake).

#### EDC ingestion prerequisites

- You must whitelist the appropriate URL for outbound access, based on your region:

EDC ingestion plugins runs on your’s on-premise pod and make outbound API calls to one of the above URLs, depending on your region.
  - edc.app.securiti.ai

For US region
  - edc.app1.securiti.ai

For US (GCP) region
  - edc.app2.securiti.ai

For Jakarta region
  - edc.app3.securiti.ai

For Montreal region
  - edc.app4.securiti.ai

For Sydney region
  - edc.app5.securiti.ai

For UAE region
  - edc.app6.securiti.ai

For Mumbai region
  - edc.app.eu.securiti.ai

For EU region
  - edc.app7.securiti.ai

For KSA region
  - edc.app8.securiti.ai

For Qatar region
- Before starting an EDC ingestion job, ensure that the pod has at least **6 GB** of free memory.

#### EDC ingestion steps

To perform EDC ingestion:

1. Open Enterprise Data Catalog. From the left menu, choose **Settings** > **EDC** **Ingestion**.

![Ingestion_EDC.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5005cb09-bafa-f0ff-6b99-c6b718519f6d.png)

> [!NOTE]
> **Note**
> 
> You can also access the EDC ingestion option from the general settings.
> 
> 1. Open System Settings.
> 2. Choose **Integrations** > **EDC** **Ingestion**.

- Before ingesting any metadata, you must create a new ingestion source. On the **Manage Ingestion** page, click **+ Create new source**.
- On the **New ingestion Source** popup, complete the following three steps:

#### Step 1: Choose type

Select a recipe template corresponding to the source type that you like to extract metadata from. Select from a range of integrations that are natively supported, including Snowflake, Postgres, and Kafka.

> [!NOTE]
> **Important**
> 
> - The given data sources are provided by the DataHub community. Before usage, it is essential to familiarize yourself with them. We strongly recommend testing their connections and settings first via a local CLI on your desktops.
>   - For detailed instructions on how to successfully ingest metadata into EDC from each source, please refer to this [link](/v1/docs/securiti-pods-and-elastic-pods). Note that EDC is compatible with DataHub.
> - For a successful ingestion of a BigQuery, do not add a platform instance in the recipe file, as it is restricted by EDC.
> - The Other option, located at the end of the ingestion sources list, is intended for advanced users. The recipe will be executed from the selected Pod and any references to files must be visible from the selected Pod.
> 
> Read more information on [recipe configuration](/v1/docs/securiti-pods-and-elastic-pods) to learn how to correctly configure recipes.

#### Step 2: Configure recipe

Before configuring the recipe, create your secret first.

#### Why do you need to create secrets?

For production use cases, sensitive configuration values, such as database usernames and passwords, should be hidden from plain view within your ingestion recipe. To accomplish this, you can create and embed Secrets. Secrets are named values that are encrypted and stored within Securiti storage layer.

#### Creating secrets

To create secrets:

1. Open the **Manage Ingestion** page and click the **Secrets** tab.
2. On the left side of the page, click **+ Create new secret**.
3. On the **Create a new Secret** popup, enter the following details:

| Field Name | Description |
| --- | --- |
| Name | This is the secret name. This is what you use to reference the secret from your recipes. |
| Value | This is the value of your secret, which is encrypted and stored securely within the Data Catalog. |
| Description | This is the secret description to help keep track of your secret. |

#### 

#### Configuring ingestion recipe

Once done, now configure the ingestion recipe through form or in YAML. A recipe is a set of configurations that Securiti uses to extract metadata from a 3rd party system. To define a recipe through form, configure the following options:

| Settings | Field Name | Description |
| --- | --- | --- |
| **Pods** |  |  |
| Execute with Pod | Pod id on which the ingestion will execute. |
| **Connection settings** | This is the example for MySQL. You may encounter different input fields as per the selected data system. |
| Host and Port | The host and port where MySQL is running. For example, **localhost:5432**. Note: this host must be accessible on the network where EDC is running (or allowed via an IP Allow List, AWS PrivateLink, etc). |
| Username | The MySQL username for extracting metadata. |
| Password | The MySQL password for the user.This field requires you to use a Data Catalog Secret, defined in the previous topic. |
| Password | Enter the Data Catalog secret password. The correct format is **${SecretValue}**. |
| **Test Connection** | The Test Connection authenticates your connection with the selected ingestion source. When you enter a valid username and password and click **Test Connection**, Securiti shows you the successful connection message as shown below. ![EDC_-_test_connection_-_success.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ca38767d-3652-0c81-2629-e91b68b837bd.png) However, when you enter the wrong username or password and click Test connection button, Securiti shows you the specific error message regarding the failed connection. > [!NOTE] > **Note** > > - The **Test Connection** option is enabled for selective data systems. > - The **Test Connection** option for Databricks Unity Catalog provides a detailed log report with insights into each connection test. > - When you click **Test Connection**, the system validates the connection through three key checks, **Basic Connectivity**, **Usage Stats**, and **Data Profiling**, and displays a pass (✔) or fail (✖) status for each step. > > ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(836).png) > > ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(837).png) |
| **Filter settings** | This is an example of MySQL. You may encounter different filters as per the selected data system. For example, in the case of Kafka, you can apply filter patterns on topics. |
| Databases | Shows **Allow** and **Deny** patterns for the databases to be included or excluded. > [!NOTE] > **Note** > > When configuring database allow or deny patterns, use specific regular expressions to avoid unintended merges. Without precise regex, all matching databases may be merged together, leading to unexpected behavior. > > Use precise regex to ingest exact databases. > > **Example** > > **^db_name$** > > This matches only the database named **db_name**, avoiding unintended matches with similar names. |
| Schemas | Shows **Allow** and **Deny** patterns for the schemas to be included or excluded. |
| Tables | Shows **Allow** and **Deny** patterns for the tables to be included or excluded. |
| Views | Shows **Allow** and **Deny** patterns for the views to be included or excluded. |
| **Advanced settings** | Shows you the list of options to be enabled or disabled from the ingestion source. Simply, mark the checkbox for the features you want to include in extraction. ![EDC_-_Advanced_settings_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4477ecbc-c775-70b7-c7cc-8664af390eb9.png) |

> [!NOTE]
> **Note**
> 
> If you choose to create a recipe through the UI option, you can still view and update the recipe in the YAML file in parallel. To do so, on the upper right corner of the page, click **YAML** to view the recipe.
> 
> YAML file most often consists of the following parts:
> 
> - A source type: The type of system you must extract metadata from (For example, Snowflake, MySQL, Postgres).
> - A source config: A set of configurations specific to the source type.
> 
> ![Screenshot_2025-07-01_at_2_52_41_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0dd64439-0aae-74a1-77cc-04310b525e4d.png)
> 
> **Executing SQL Server ingestion**
> 
> To execute SQL Server ingestion successfully, especially when encryption is required by the server, follow these two essential steps.
> 
> **Update recipe configuration**
> 
> To meet the server’s encryption requirement, you must enable SSL and trust the server certificate in your connection configuration. This ensures the ODBC connection can securely communicate with SQL Server.
> 
> Add under **config**:
> 
> ```yaml
> use_odbc: 
> "True"uri_args:  
>     driver: "ODBC Driver 18 for SQL Server"  
>     Encrypt: "yes"  
>     TrustServerCertificate: "Yes"  
>     ssl: "True"
> ```
> 
> **Grant required SQL permissions**
> 
> The SQL job also needs permission to access system metadata and object dependencies. Granting these permissions ensures it can read job details and resolve dependencies during execution.
> 
> Run the following SQL (replace **USERNAME** and **DATA_DB_NAME** as needed):
> 
> ```sql
> USE MSDB;
> GRANT SELECT ON OBJECT::msdb.dbo.sysjobsteps TO [USERNAME];
> GRANT SELECT ON OBJECT::msdb.dbo.sysjobs TO [USERNAME];
> USE [DATA_DB_NAME];
> GRANT VIEW DEFINITION TO [USERNAME];
> GRANT SELECT ON OBJECT::sys.sql_expression_dependencies TO [USERNAME];
> ```
> 
> 
> 
> If a user does not have permissions on **sysjobs** and **sysjobsteps**, successful SQL Server ingestion requires setting **include_jobs** to **false** in the recipe file. Additionally, setting **convert_urns_to_lowercase** to true ensures that table- and column-level lineage can still be captured while avoiding issues caused by case sensitivity.

In the ingestion recipe, the value of **profiling.max_workers** is directly proportional to the number of connections your database instance can support.

By default, the connection count is set to **16**. However, if you want ingestion with profiling to run faster and your database instance can handle more connections, you can increase this value accordingly.

Update the recipe as shown below with the appropriate number of workers based on your database’s connection limits:

```yaml
profiling:
  enabled: true
  max_workers: <profiling worker count>
  profile_table_level_only: true
```

Make sure the value you set for **max_workers** does not exceed the maximum number of connections your database instance can safely support.

#### EDC ingestion linking to data system instances

EDC ingestion configurations are simplified to streamline metadata registration for the following data systems:

- Databricks

> [!NOTE]
> Note
> 
> Securiti supports **OAuth 2.0 authentication** for Databricks ingestion, enabling secure and seamless connectivity using existing connector configurations.
- PostgreSQL
- Snowflake

> [!NOTE]
> Note
> 
> To successfully execute data quality checks, use **Basic Authentication**, **OAuth 2.0 authentication** or **Key Pair Authentication** to activate and connect to the Snowflake data system.
- Salesforce
- Cassandra

You can select an existing connector instance—already configured for discovery scans—directly within the EDC ingestion workflow. This enables EDC to automatically reuse connection details such as names, IDs, tokens, and platform instance information, ensuring consistent recipe and URN generation.

This prevents duplication issues when ingesting metadata from the same system using both Sensitive Data Intelligence discovery scans and EDC Ingestion, letting you benefit from the unique capabilities of each approach.

To configure the recipe:

1. Expand the **Connection** section.
2. From the **Platform** **Instance** dropdown, select the existing connector instance.

> [!NOTE]
> **Note**
> 
> For Snowflake, you have to select the appropriate user role to use when extracting metadata from the source system.

#### Customizing the browsePath transformer in the ingestion recipe

You can fully customize the BrowsePath transformer in your EDC ingestion pipelines. This lets you enforce a consistent folder structure—for example, matching your SDI conventions—or to introduce any bespoke hierarchy you need.

#### Setting custom browse paths in EDC ingestion

To set your browse path dynamically, you can use the built-in transformer **set_dataset_browse_path**. EDC provides special variables to help construct paths dynamically, but these are entirely optional—you can also directly specify a fixed path if preferred.

Special variables available:

- ENV: the ingestion environment (for example Prod, UAT, Dev)

Env could be from a fixed set of allowed values. Below is a list of available environment variables, along with their descriptions to help you make the best selection:

| Value | Description |
| --- | --- |
| PROD | Designates production fabrics. |
| DEV | Designates development fabrics. |
| TEST | Designates testing fabrics. |
| QA | Designates quality assurance fabrics. |
| UAT | Designates user acceptance testing fabrics. |
| EI | Designates early integration fabrics. |
| PRE | Designates pre-production fabrics. |
| STG | Designates staging fabrics. |
| NON_PROD | Designates non-production fabrics. |
| CORP | Designates corporation fabrics. |
- PLATFORM: the data platform (for example, snowflake, mysql, postgres)
- DATASET_PARTS: your dataset’s hierarchical parts, typically represented as **database/schema/table**

**Example configuration**

Here's how to configure the transformer within your ingestion YAML recipe:

```yaml
source:
    type: snowflake 
    config:  
        account_id:"<your-account>"    
        username: "<username>"    
        password: "<password>"   
        database: "<database>"    
        schema: "<schema>"
transformers:  
    - type: set_dataset_browse_path    
    config:      
        replace_existing: true  # remove existing browse paths      
        path_templates:        
            - "/ENV/PLATFORM/DATASET_PARTS"  # dynamic example        
            - "/fixed/path/example"  # fixed example
sink:  
    type: datahub-rest  
    config:    
        server: "https://your-datahub-instance/api/gms"    
        token: "${DATAHUB_TOKEN}"
```

**Example result**

For dynamic paths:

```bash
/uat/snowflake/sales_db/public/orders
```

For fixed paths:

```bash
/fixed/path/example
```

#### Using fixed and dynamic values together

You can combine fixed strings with dynamic variables:

```yaml
transformers:  
    - type: set_dataset_browse_path    
    config:      
        replace_existing: true      
        path_templates:        
            - "/ENV/PLATFORM/my-fixed-string/DATASET_PARTS"
```

This would yield:

```bash
/uat/snowflake/my-fixed-string/sales_db/public/orders
```

> [!NOTE]
> **Note**
> 
> The automatic transformer override has been completely removed. If you do not explicitly configure the transformer, datasets will have no custom browse path set.

#### Defining any arbitrary hierarchy

You aren’t limited to an SDI layout—you can supply any text in the path. For example, to group by a custom tag:

```yaml
transformers:  
    - type: "set_dataset_browse_path"    
    config:      
        path_templates:        
            - /ENV/<Your_Text>/DATASET_PARTS
```

In the above example, **<Your_Text>** could be anything (For example, team name, or environment tag).

#### Default behavior

When no transformer is specified, datasets are ingested into the production environment path by default. In other words, if you omit the **set_dataset_browse_path** transformer entirely, EDC falls back to its built-in default:

```bash
/prod/<platform_instance(if provided)>/database_name/schemaName
```

- **prod** is the hard-coded environment.
- **<platform_instance>** appears only if you have set one.
- **database_name** and **schemaName** are your source’s database and schema.

#### Step 3: Finish

In the **Name** field, give your ingestion source a name. Click **Save & Run** to immediately run the ingestion. However, click **Save** to save the ingestion to run it later.

#### Performing actions on ingestion sources

On the **Manage Ingestion** page, you can perform the following actions:

| Actions | Details |
| --- | --- |
| View source details | You can view the following source details: - Source type - Source name - Execution count - Last execution - Current status |
| Search for sources | On the top right corner, enter the source name in the search bar. |
| Copy the ingestion source URN | On the right side of any row in the sources table, click the copy icon to copy the ingestion source URN. |
| Edit the ingestion source | On the right side of any row in the sources table, click **Edit** button to edit the ingestion source. You can only edit the ingestion source before running it. Once you have run it, then you can only view the ingestion via the recipe file. |
| Run the ingestion source | On the right side of any row in the sources table, click **Run** button to run the ingestion source. |
| Delete the ingestion source | On the right side of any row in the sources table, click the delete button to delete the ingestion source. Deleting any ingestion terminates all the scheduled ingestion runs. |
| Ingestion source details | - Click the **+** icon located on the left side of the ingestion source row to view the following details: - Requested at - Started at - Duration - Status - Source - Click the copy icon located at the right side of the row to copy the URN of the execution test. - Click **Details** to view the following details of the ingestion: - Status - Ingested assets - Logs collected during the ingestion run - Click **ROLLBACK** to delete the ingested data. - For example, suppose you have ingested ten datasets (table or views) through the ingestion. When you click **ROLLBACK**, Securiti deletes the ten ingested datasets (table or views). |

#### Running an ingestion source

Click **Run** to execute the ingestion. This means that your request to execute ingestion has been successfully picked up by the ingestion executor. Shortly after, you see the **Current Status** of the ingestion get changed.

You see the **Current Status** as completed if ingestion is successful. The different statuses of the ingestion are as follows:

| Ingestion Status | Description |
| --- | --- |
| Created | Ingestion is created successfully. You can edit and rerun the created ingestion at any time. |
| Scheduled | Ingestion is scheduled successfully. You cannot edit and rerun the scheduled EDC ingestion, can only view it. |
| Running | Ingestion is in a running state. You cannot edit and rerun the running EDC ingestion. |
| Completed | Ingestion is executed successfully. You can rerun but cannot edit the completed ingestion at any time. |
| Failed | Ingestion is not executed successfully. You cannot edit and rerun the failed EDC ingestion, but can only view it. |

> [!NOTE]
> **Note**
> 
> - You can view the reason behind a failed ingestion by hovering on the **Failed** status in the current status column.
> - When one or more tables are deleted from a database and a discovery scan is re-run, the corresponding datasets in EDC are now automatically updated to reflect those deletions. This ensures that the EDC remains consistent with the latest database structure and discovery scan results.
> - Discovery scans take precedence over dataset import and EDC Ingestion. Re-running a discovery scan resets a dataset's metadata to what the scan detects, removing anything added through dataset import or EDC Ingestion.
> 
> For example, a discovery scan registers a dataset with two lineage relationships. You add one through dataset import and one through EDC Ingestion, giving the dataset four. Re-running the discovery scan leaves only the original two.
> 
> After re-running a discovery scan, re-run the dataset import and EDC Ingestion in their original order to restore the overwritten metadata.

#### Debugging a failed ingestion

The following common reasons can be the cause for failure:

- **Recipe misconfiguration:** A recipe has not provided the required or expected configurations for the ingestion source.
- **Failure to resolve secrets:** If the Securiti platform is unable to find secrets that were referenced by your Recipe configuration, the ingestion run will fail. Verify that the names of the secrets referenced in your recipe match those which have been created.
- **Connectivity reachability:** If Securiti platform is unable to reach a data source, for example due to DNS resolution failures, metadata ingestion will fail. Ensure that the network where Securiti is deployed has access to the data source which you are trying to reach.

### Ingesting xml files in EDC

To ingest XML files into the EDC:

1. Open Enterprise Data Catalog. From the left menu, choose **Settings > Enterprise Data Catalog > EDC Ingestion**.

> [!NOTE]
> **Note**
> 
> You can also access the EDC ingestion option from the general settings.
> 
> 1. Open **System Settings**
> 2. Choose **Integrations > EDC Ingestion**.
2. Before ingesting any metadata, you must create a new ingestion source. On the **Manage Ingestion** page, click **+ Create new source**.
3. On the **New ingestion Source** popup, complete the following three steps:

#### Step 1: Choose type

- Navigate through the list of available ingestion sources and select **XML**.

#### Step 2: Configure recipe

Configure the ingestion recipe through a form or in YAML. A recipe is a set of configurations that Securiti uses to extract metadata from a 3rd party system. To define a recipe through form, configure the following options:

| Settings | Description |
| --- | --- |
| Pods | Expand the **Pods** menu to enter the Pod name on which the ingestion will execute. |
| Connection | Expand the Connection menu to enter the Platform details from which the XML files will be ingested. Currently, the supported platforms are: - Amazon S3 - Cassandra DB - NFS - S3 Compatible Storage connectors - SMB 1. Select a platform from the **Platform** menu. 2. From the **Select Platform Instance**, select the [instance](/v1/docs/managing-data-system-connectors) created for the platform. 3. From the **Select Environment** menu, select the [deployment environment](/v1/docs/datasets) (For example, PROD, DEV). |
| File path | Expand the File Path menu to specify the file paths where XML files are expected to be in that specific location. For example, **/xml_inferred_lineage**. |

#### Step 3: Finish up

In the **Name** field, give your ingestion source a name. Click **Save & Run** to immediately run the ingestion. However, click **Save** to save the ingestion to run it later.

The steps you need to perform after **Step 3** are the same as those for other ingestion sources. For detailed instructions, refer to the sections Performing Actions on Ingestion Sources and Running an Ingestion Source.

> [!NOTE]
> **Note**
> 
> - Once the files are successfully ingested into the EDC, you can locate them under the **Datasets** section within the relevant platform folders. Among their many uses, these XML files can also serve as both producers and consumers in [Inferred lineage](/v1/docs/inferred-lineage) jobs.

An Enterprise Data Catalog (EDC) is a centralized inventory and metadata management tool for an organization's data assets. It helps organizations manage and govern their data by providing a comprehensive view of data sources, data lineage, data definitions, data usage, and data quality.

The Securiti platform includes a wide range of techniques for sensitive data detection that includes powerful artificial intelligence (AI) and machine learning (ML) detection techniques. The customers' requirements may vary as to whether they intend to detect sensitive data or classify data as sensitive.

A URN, or Uniform Resource Name, is a Uniform Resource Identifier (URI) that is used to uniquely identify a resource, but without specifying its location or how to access it.
