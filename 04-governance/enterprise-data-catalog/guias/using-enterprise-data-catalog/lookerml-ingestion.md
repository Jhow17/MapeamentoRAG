---
title: "LookerML Ingestion"
slug: "lookerml-ingestion"
updated: 2026-10-05T09:25:04Z
published: 2026-10-05T09:25:04Z
canonical: "helpcenter.securiti.ai/lookerml-ingestion"
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# LookerML Ingestion

To ingest LookerML metadata into the EDC, read the following required configurations.

### Important capabilities

| **Capability** | **Status** | **Notes** |
| --- | --- | --- |
| Column-level lineage | ✅ | Enabled by default, configured using `extract_column_level_lineage` |
| Platform instance | ✅ | Supported using the `connection_to_platform_map` |
| Table-level lineage | ✅ | Supported by default |

This plugin extracts the following:

- LookML views from model files in a project
- Name, upstream table names, metadata for dimensions, measures, and dimension groups attached as tags
- If API integration is enabled (recommended), resolves table and view names by calling the Looker API, otherwise supports offline resolution of these names.

> [!NOTE]
> Note
> 
> To get complete Looker metadata integration (including Looker dashboards and charts and lineage to the underlying Looker views, you must also use the looker source module.

### Prerequisites

To use LookML ingestion through the UI, or automate github checkout through the cli, you must set up a GitHub deploy key for your Looker GitHub repository. For complete information, read [how to set up deploy keys for your Looker git repo](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/managing-deploy-keys#deploy-keys).

In a nutshell, there are three steps:

1. Generate a private-public ssh key pair. This ypically generates two files, for example, looker_edc_deploy_key (this is the private key) and looker_edc_deploy_key.pub (this is the public key).
2. Add the public key to your Looker git repo as a deploy key with read access (no need to provision write access). Follow the guide here for that.

### **Configuration options**

The following options control what the LookML source extracts, how it reaches your LookML repo, and how names and browse paths are constructed. A dot in a field path indicates a nested field in the YAML recipe.

#### General and extraction options

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `base_folder` | string(directory-path) |  | Required if not providing github configuration and deploy keys. A pointer to a local directory (accessible to the ingestion system) where the root of the LookML repo has been checked out (typically via a git clone). This is typically the root folder where the *.model.lkml and *.view.lkml files are stored. e.g. If you have checked out your LookML repo under /Users/jdoe/workspace/my-lookml-repo, then set `base_folder` to /Users/jdoe/workspace/my-lookml-repo. |
| `emit_reachable_views_only` | boolean | True | When enabled, only views that are reachable from explores defined in the model files are emitted |
| `extract_column_level_lineage` | boolean | True | When enabled, extracts column-level lineage from Views and Explores |
| `max_file_snippet_length` | integer | 512000 | When extracting the view definition from a lookml file, the maximum number of characters to extract. |
| `parse_table_names_from_sql` | boolean | False | See note below. |
| `populate_sql_logic_for_missing_descriptions` | boolean | False | When enabled, field descriptions will include the sql logic for computed fields if descriptions are missing |
| `process_isolation_for_sql_parsing` | boolean | False | When enabled, sql parsing will be executed in a separate process to prevent memory leaks. |
| `process_refinements` | boolean | False | When enabled, looker refinement will be processed to adapt an existing view. |
| `project_name` | string |  | Required if you don't specify the api section. The project name within which all the model files live. See (https://docs.looker.com/data-modeling/getting-started/how-project-works) to understand what the Looker project name should be. The simplest way to see your projects is to click on Develop followed by Manage LookML Projects in the Looker application. |
| `tag_measures_and_dimensions` | boolean | True | When enabled, attaches tags to measures, dimensions and dimension groups to make them more discoverable. When disabled, adds this information to the description of the column. |

#### Git and project dependencies

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `git_info` | GitInfo |  | Reference to your git location. If present, supplies handy links to your lookml on the dataset entity page. |
| `git_info.repo` | string |  | Name of your Git repo e.g. https://github.com/edc-project/edc or https://gitlab.com/gitlab-org/gitlab. If organization/repo is provided, we assume it is a GitHub repo. |
| `git_info.branch` | string | main | Branch on which your files live by default. Typically main or master. This can also be a commit hash. |
| `git_info.deploy_key` | string(password) |  | A private key that contains an ssh key that has been configured as a deploy key for this repository. See `deploy_key_file` if you want to use a file that contains this key. |
| `git_info.deploy_key_file` | string(file-path) |  | A private key file that contains an ssh key that has been configured as a deploy key for this repository. Use a file where possible, else see `deploy_key` for a config field that accepts a raw string. |
| `git_info.repo_ssh_locator` | string |  | The url to call git clone on. We infer this for github and gitlab repos, but it is required for other hosts. |
| `git_info.url_template` | string |  | Template for generating a URL to a file in the repo e.g. '{repo_url}/blob/{branch}/{file_path}'. We can infer this for GitHub and GitLab repos, and it is otherwise required.It supports the following variables: {repo_url}, {branch}, {file_path} |
| `project_dependencies` | One of map(str,union)(directory-path), map(str,union) |  |  |
| `project_dependencies.key.repo` | string |  | Name of your Git repo e.g. https://github.com/edc-project/edc or https://gitlab.com/gitlab-org/gitlab. If organization/repo is provided, we assume it is a GitHub repo. |
| `project_dependencies.key.branch` | string | main | Branch on which your files live by default. Typically main or master. This can also be a commit hash. |
| `project_dependencies.key.deploy_key` | string(password) |  | A private key that contains an ssh key that has been configured as a deploy key for this repository. See `deploy_key_file` if you want to use a file that contains this key. |
| `project_dependencies.key.deploy_key_file` | string(file-path) |  | A private key file that contains an ssh key that has been configured as a deploy key for this repository. Use a file where possible, else see `deploy_key` for a config field that accepts a raw string. |
| `project_dependencies.key.repo_ssh_locator` | string |  | The url to call git clone on. We infer this for github and gitlab repos, but it is required for other hosts. |
| `project_dependencies.key.url_template` | string |  | Template for generating a URL to a file in the repo e.g. '{repo_url}/blob/{branch}/{file_path}'. We can infer this for GitHub and GitLab repos, and it is otherwise required.It supports the following variables: {repo_url}, {branch}, {file_path} |

#### Naming and browse patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `explore_browse_pattern` | LookerNamingPattern | `{'pattern': '/{env}/{platform}/{project}/explores'…` | Pattern for providing browse paths to explores. Allowed variables are ['platform', 'env', 'project', 'model', 'name'] |
| `explore_browse_pattern.pattern` | string |  |  |
| `explore_naming_pattern` | LookerNamingPattern | `{'pattern': '{model}.explore.{name}'}` | Pattern for providing dataset names to explores. Allowed variables are ['platform', 'env', 'project', 'model', 'name'] |
| `explore_naming_pattern.pattern` | string |  |  |
| `view_browse_pattern` | LookerNamingPattern | `{'pattern': '/{env}/{platform}/{project}/views'}` | Pattern for providing browse paths to views. Allowed variables are ['platform', 'env', 'project', 'model', 'name'] |
| `view_browse_pattern.pattern` | string |  |  |
| `view_naming_pattern` | LookerNamingPattern | `{'pattern': '{project}.view.{name}'}` | Pattern for providing dataset names to views. Allowed variables are ['platform', 'env', 'project', 'model', 'name'] |
| `view_naming_pattern.pattern` | string |  |  |

#### Filter patterns

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `model_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | List of regex patterns for LookML models to include in the extraction. |
| `model_pattern.allow` | array(string) |  |  |
| `model_pattern.deny` | array(string) |  |  |
| `model_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |
| `view_pattern` | AllowDenyPattern | `{'allow': ['.*'], 'deny': [], 'ignoreCase': True}` | List of regex patterns for LookML views to include in the extraction. |
| `view_pattern.allow` | array(string) |  |  |
| `view_pattern.deny` | array(string) |  |  |
| `view_pattern.ignoreCase` | boolean | True | Whether to ignore case sensitivity during pattern matching. |

#### Transport options

| **Field** | **Type** | **Default** | **Description** |
| --- | --- | --- | --- |
| `transport_options` | TransportOptionsConfig |  | Populates the TransportOptions struct for looker client |
| `transport_options.headers` | map(str,string) |  |  |
| `transport_options.timeout` | integer |  |  |
