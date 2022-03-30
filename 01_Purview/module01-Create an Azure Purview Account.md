# Module 01 - Create an Azure Purview Account

## Introduction

To create and use the Azure Purview platform, you will need to provision an Azure Purview account.

## 1. Create an Azure Purview Account

1. Sign in to the [Azure portal](https://portal.azure.com), navigate to the **Home** screen, click **Create a resource**.

    ![Create a Resource](./images/module01/01.01-create-resource.png)  

2. Search the Marketplace for "Azure Purview" and click **Create**.

    ![Create Purview Resource](./images/module01/01.02-create-purview.png)

3. Provide the necessary inputs on the **Basics** tab.  

    > Note: The table below provides example values for illustrative purposes only, ensure to specify values that make sense for your deployment. If you have pre-deployed other Azure resources using the lab template, they would have been created with a `randomId`, it is recommended to use the same `randomId` for the Azure Purview account name as per the example below.

    | Parameter  | Example Value |
    | --- | --- |
    | Subscription | `YOUR_AZURE_SUBSCRIPTION` |
    | Resource group | `pvlab-rg` |
    | Purview account name | `pvlab-{randomId}-pv` |
    | Location | `YOUR_LOCATION` |
    | Managed Resource Group Name | `pvlab-rg-managed` |

    ![Purview Account Basics](./images/module01/_01.03-create-basic.png)

    > :bulb: **Did you know?**
    >
    > **Capacity Units** determine the size of the platform and is a **provisioned** (always on) set of resources that is needed to keep the Azure Purview platform up and running. 1 Capacity Unit is able to support approximately 25 data map operations per second and includes up to 2GB of metadata storage about data assets.
    >
    > Capacity Units are required regardless of whether you plan to invoke the Azure Purview API endpoints directly (i.e. ISV scenario) or indirectly via Purview Studio (GUI).
    >
    > Note: With the introduction of the [Elastic Data Map](https://docs.microsoft.com/en-us/azure/purview/concept-elastic-data-map), you no longer need to specify how many Capacity Units that you need. Azure Purview will scale capacity elastically based on the request load.
    > 
    > **vCore Hours** on the other hand, is the unit of measure for **serverless** compute that is needed to run a scan. You only pay per vCore Hour of scanning that you consume (rounded up to the nearest minute).
    >
    > For more information, check out the [Azure Purview Pricing](https://azure.microsoft.com/en-us/pricing/details/azure-purview/) page.

4. On the **Networking** tab, select **All networks**.
   
    ![Networking](./images/module01/_01.04-create-networking.png)

5. On the **Review + Create** tab, once the message in the ribbon returns "Validation passed", verify your selections and click **Create**.

    ![Create Purview Account](./images/module01/_01.05-create-create.png)

6. Wait several minutes while your deployment is in progress. Once complete, click **Go to resource**.

    ![Go to resource](./images/module01/_01.06-goto-resource.png)

<div align="right"><a href="#module-01---create-an-azure-purview-account">↥ back to top</a></div>

## 2. Grant Access to Azure Purview's Data Plane

By default, the identity used to create the Azure Purview account resource will have full access to Purview Studio. The following instructions detail how to provide access to additional users within your Azure Active Directory.

1. Navigate to your Azure Purview account and click **Open** within the **Open Purview Studio** tile.

    ![Access Control](./images/module01/_01.07-open-studio.png)

2. On the left-hand side, navigate to **Data map**.

    ![Add Role Assignment](./images/module01/_01.08-studio-datamap.png)

3. Select **Collections**.

    ![Collections](./images/module01/_01.09-datamap-collections.png)

4. Select **Role assignments**.

    ![Role assignments](./images/module01/_01.10-collections-roleassignments.png)

5. On the right-hand side of **Data curators**, click the **Add** icon.

    ![Add Role Assignment](./images/module01/_01.11-roleassignments-datacurator.png)

6. Search for another user within your Azure Active Directory, select their account, click **OK**.

    ![Add or Remove Data Curators](./images/module01/_01.12-datacurator-add.png)

    > :bulb: **Did you know?**
    >
    > Azure Purview has a set of predefined data plane roles that can be used to control who can access what.
    >
    > For more information, check out [Access control in Azure Purview](https://docs.microsoft.com/en-us/azure/purview/catalog-permissions).

    | Role  | Collections | Catalog | Sources/Scans | Description | 
    | --- | --- | --- | --- | --- |
    | Collection Admin | `Read/Write` | | | Manage collections and role assignments. |
    | Data Reader ||  `Read` |  | Access to catalog (read only). |
    | Data Curator || `Read/Write` |  | Access to catalog (read & write). |
    | Data Source Admin |  || `Read/Write` | Manage data sources and data scans. |

<div align="right"><a href="#module-01---create-an-azure-purview-account">↥ back to top</a></div>

