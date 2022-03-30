# Module 07 - Insights

```diff
!                               << PLEASE READ BEFORE PROCEEDING >>                                
!                                                                                                  
! * Insights within Azure Purview can take several hours to surface post the completion of a scan. 
! * At this point of the workshop, only a limited number of data visualisations may be populated.  
! * To populate all reports with data, Azure Purview requires an environment with a variety of     
! sources and assets to be scanned that is beyond the scope of this workshop.                      
! * The screenshots and information below, has been provided so that you can conceptualise the type
! of insights that can be gleaned from a fully populated environment.                              
```

## Introduction

Insights provides customers, a single pane of glass view into their catalog and further aims to provide specific insights to the data source administrators, business users, data stewards, data officer, and security administrators. Azure Purview currently has the following reports available:

* Assets
* Scans
* Glossary
* Classification
* Sensitivity Labels

## 1. Asset Insights

1. Open Purview Studio, navigate to **Insights** > **Assets**.

    ![Assets Insights](./images/module07/07.01-assets-insights.png)

2. The Assets page displays the following **high-level metrics**.
    * Number of Source Types
    * Number of Assets
    * Number of Classified Assets
    * Number of Unique File Extensions

    ![Assets KPI](./images/module07/07.02-assets-kpi.png)

3. Further down the page you will find additional **data visualizations**, typically these tiles will allow interactive filtering and the ability to drill-down into the underlying detail by clicking **View details**. The Assets page includes the following **graphs**:

    **Asset count by source type**

    ![Assets Graph 01](./images/module07/07.03-assets-graph01.png)

    **Top file extensions (By count OR By size)**

    ![Assets Graph 02](./images/module07/07.04-assets-graph02.png)

    **Files not stored in resource sets**

    ![Assets Graph 03](./images/module07/07.05-assets-graph03.png)

    > :bulb: **Did you know?**
    >
    > Using the quick filters on the **Asset count by source type** graph and drilling into the details by clicking **View details**, is a quick and easy way of identifying which sources contain certain types of data.

<div align="right"><a href="#module-07---insights">↥ back to top</a></div>

## 2. Scan Insights

1. Open Purview Studio, navigate to **Insights** > **Scans**.

    ![Scan Insights](./images/module07/07.06-scans-insights.png)

2. The Scans page displays the following **high-level metrics**.
    * Number of Scans
    * Number of Succeeded (Scans)
    * Number of Canceled (Scans)
    * Number of Failed (Scans)

    ![Scan KPI](./images/module07/07.07-scans-kpi.png)

3. The Scans page includes the following **graphs**:
   
    **Scan status**

    ![Scan Graph 01](./images/module07/07.08-scans-graph01.png)

    > :bulb: **Did you know?**
    >
    > Clicking **View details** on the **Scan Status** graph will show scans that have occurred over the last 30 days with aggregated counts by status (Success, Failed, Canceled). Drilling further by clicking on a scan name will reveal the scan run history with quick action buttons to edit, delete, or run.

<div align="right"><a href="#module-07---insights">↥ back to top</a></div>

## 3. Glossary Insights

1. Open Purview Studio, navigate to **Insights** > **Glossary**.

    ![Glossary Insights](./images/module07/07.09-glossary-insights.png)

2. The Glossary page displays the following **high-level metrics**.
    * Total terms
    * Approved terms without assets
    * Expired terms with assets

    ![Glossary KPI](./images/module07/07.10-glossary-kpi.png)

3. The Glossary page includes the following **graphs**:
   
    **Top terms by asset count**

    ![Glossary Graph 01](./images/module07/07.11-glossary-graph01.png)

    **Status Overview (Terms with assets OR Terms without assets)**

    ![Glossary Graph 02](./images/module07/07.12-glossary-graph02.png)

    **Incomplete Terms**

    ![Glossary Graph 03](./images/module07/07.13-glossary-graph03.png)

    > :bulb: **Did you know?**
    >
    > Terms are considered **incomplete** if they are missing a definition, expert, or steward. If a term is missing more than one of these things, it is shown as **Missing multiple items**.

<div align="right"><a href="#module-07---insights">↥ back to top</a></div>

## 4. Classification Insights

1. Open Purview Studio, navigate to **Insights** > **Classification**.

    ![Classification Insights](./images/module07/07.14-classification-insights.png)

2. The Classification page displays the following **high-level metrics**.
    * Total assets classified
    * Files classified
    * Tables classified
    * Unique classifications found
    * Sources classified

    ![Classification KPI](./images/module07/07.15-classification-kpi.png)

3. The Classification page includes the following **graphs**:
   
    **Top sources with classified data**

    ![Classification Graph 01](./images/module07/07.16-classification-graph01.png)

    **Top classification categories**

    ![Classification Graph 02](./images/module07/07.17-classification-graph02.png)

    **Top classifications for files**

    ![Classification Graph 03](./images/module07/07.18-classification-graph03.png)

    **Top classifications for tables**

    ![Classification Graph 04](./images/module07/07.19-classification-graph04.png)

<div align="right"><a href="#module-07---insights">↥ back to top</a></div>

## 5. Sensitivity Labels Insights

1. Open Purview Studio, navigate to **Insights** > **Sensitivity Labels**.

    > :bulb: **Did you know?**
    >
    > **Sensitivity labels** state how sensitive data is in your organization. For example, data contained within a particular asset might be `highly confidential`. **Classifications** on the other hand indicate the type of data values (e.g. Driver's License Number, Email Address, SWIFT Code, etc) 
    >
    > Azure Purview's ability to apply sensitivity labels is due to the close integration with **Microsoft Information Protection** offered in Microsoft 365. Note: You must turn on Information Protection for Azure Purview in the Microsoft 365 compliance center. For more information, check out how to [Labeling in Azure Purview](https://docs.microsoft.com/en-us/azure/purview/create-sensitivity-label).

    ![Sensitivity Labels Insights](./images/module07/07.20-labels-insights.png)

2. The Sensitivity Labels page displays the following **high-level metrics**.
    * Total assets labeled
    * Files labeled
    * Tables labeled
    * Unique labels found
    * Sources labeled

    ![Sensitivity Labels KPI](./images/module07/07.21-labels-kpi.png)

3. The Sensitivity Labels page includes the following **graphs**:
   
    **Top sources with labeled data**

    ![Sensitivity Labels Graph 01](./images/module07/07.22-labels-graph01.png)

    **Top labels applied across sources**

    ![Sensitivity Labels Graph 02](./images/module07/07.23-labels-graph02.png)

    **Top labels for files**

    ![Sensitivity Labels Graph 03](./images/module07/07.24-labels-graph03.png)

    **Top labels for tables**

    ![Sensitivity Labels Graph 04](./images/module07/07.25-labels-graph04.png)

<div align="right"><a href="#module-07---insights">↥ back to top</a></div>
