# Module 09 - Integrate with Azure Synapse Analytics

## Introduction

Registering an Azure Purview account to a Synapse workspace allows you to discover Azure Purview assets, interact with them through Synapse specific capabilities, and push lineage information to Azure Purview.

## 1. Azure Data Lake Storage Gen2 Account Access

> :bulb: **Did you know?**
>
> One of the key benefits of integrating Azure Synapse Analytics with Azure Purview, is the ability to discover Azure Purview assets from within Synapse Studio (i.e. no need to swtich between user experiences), with added abilities using Synapse specific capabilities (e.g. SELECT TOP 100). 
>
> Note: Before we can demonstrate the ability to query external data sources from Azure Synapse Analytics, we need to ensure our account has the appropriate level of access (i.e. `Storage Blob Data Reader`).

1. Navigate to the **Azure Data Lake Storage Gen2 account** (e.g. `pvlab{randomId}adls`), select **Access Control (IAM)**, and then click **Add role assignment**.

    ![Storage Access Control](./images/module09/09.01-storage-access.png)

2. Filter the list of roles available by searching for `Storage Blob Data Reader`, select the **Storage Blob Data Reader** role from the list, and click **Next**.

    ![Storage RBAC Assignment](./images/module09/09.02-storage-rbac.png)

3. To add your account click **Select members**, search for your account by typing your username into the text box, select your account from the list, and click **Select**.

    ![Storage RBAC Assignment](./images/module09/09.16-rbac-members.png)

4. Click **Review + assign** to progress to the final confirmation screen and then click **Review + assign** once more.

    ![Storage RBAC Assignment](./images/module09/09.17-rbac-review.png)

<div align="right"><a href="#module-09---integrate-with-azure-synapse-analytics">↥ back to top</a></div>

## 2. Connect to a Purview Account

1. Within the Azure portal, open the Synapse workspace and click **Open Synapse Studio**.

    ![Open Synapse Studio](./images/module09/09.08-synapse-studio.png)

2. Navigate to **Manage** > **Azure Purview (Preview)** and click **Connect to a Purview account**.

    ![Connect to a Purview Account](./images/module09/09.09-synapse-connect.png)

3. Select your **Purview account** from the drop-down menu and click **Apply**.

    ![Select a Purview Account](./images/module09/09.10-synapse-purview.png)

4. Once the connection has been established, you will receive a notification that **Registration succeeded**. Switch to the **Purview account** tab to confirm that the Purview account is connected. On this page, you will also see a list of integration capabilities that are now available (e.g. Azure Purview search, Synapse Pipeline lineage, etc).

    > :bulb: **Did you know?**
    >
    > When connecting a Synapse workspace to Purview, Synapse will attempt to add the necessary Purview role assignment (i.e. `Data Curator`) to the Synapse managed identity automatically. This operation will be successful if you belong to the **Collection admins** role on the Purview root collection and have access to the Azure Purview account. For more information, check out [Connect a Synapse workspace to an Azure Purview account](https://docs.microsoft.com/en-us/azure/synapse-analytics/catalog-and-governance/quickstart-connect-azure-purview).

    ![Purview Account Registered](./images/module09/09.11-synapse-success.png)

5. To validate that Synapse was able to succesfully add the Synapse managed identity to the Data Curator role, navigate to **Purview Studio** > **Data map** > **Collections** > **YOUR_ROOT_COLLECTION**, switch to the **Role assignments** tab and expand **Data curators**. You should be able to see the Synapse Service Principal listed as one of the Data curators. This will provide Synapse read/write access to the catalog.

    ![](./images/module09/09.18-synapsemi-curator.png)

<div align="right"><a href="#module-09---integrate-with-azure-synapse-analytics">↥ back to top</a></div>

## 3. Search a Purview Account

1. Within the Synapse workspace, navigate to the **Data** screen and perform a **keyword search** (e.g. `parquet`). Notice that the search bar now defaults to searching the entire Purview catalog as opposed to the Synapse workspace only.

    ![Search Purview Account](./images/module09/09.12-synapse-search.png)

2. Click to open the **asset details** of one of the items (e.g. `twitter_handles.parquet`).

    ![Open Asset Details](./images/module09/09.13-synapse-open.png)

3. Notice the special Synapse-specific menu items such as **Connect** and **Develop**. For supported file types such as parquet, you can quickly generate sample code to query the external source by navigating to **Develop** > **New SQL script** > **Select top 100**.

    ![Select Top 100](./images/module09/09.14-synapse-select.png)

4. To execute the query, click **Run**. Note: The user executing the query must have the appropriate level of access (e.g. Storage Blob Data Reader), see step 1 for more details..

    ![Run Query](./images/module09/09.15-synapse-run.png)

<div align="right"><a href="#module-09---integrate-with-azure-synapse-analytics">↥ back to top</a></div>
