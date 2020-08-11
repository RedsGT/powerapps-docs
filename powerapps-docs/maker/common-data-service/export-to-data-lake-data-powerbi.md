---
title: "Analyze Common Data Service exported to Azure Data Lake Storage Gen2 data with Power BI | MicrosoftDocs"
ms.custom: ""
ms.date: 07/29/2020
ms.reviewer: "matp"
author: sabinn-msft
ms.service: powerapps
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "powerapps"
ms.assetid: 
ms.author: "matp"
manager: "kvivek"
search.audienceType: 
  - maker
search.app: 
  - PowerApps
  - D365CE
---

# Analyze Common Data Service data in Azure Data Lake Storage Gen2 with Power BI

After exporting data from Common Data Service to Azure Data Lake Storage Gen2
with the Export to Data Lake service, you can use Power BI to create business
reports and analytics. This can be useful for sales managers and sales associates to refine and build additional reports and dashboards in Power BI.

This article shows you how to perform the following tasks: 

1. Connect the Data Lake Storage Gen2 storage container containing the exported Common Data Service data to Power BI.

2. Create a report in Power BI that graphs account owners and their respective total account revenue.

## Prerequisites

This section describes the prerequisites necessary to consume Common Data Service data with Power BI by using the Export to Data Lake service.
-  **Power BI Desktop**. [Get it now](https://powerbi.microsoft.com/downloads/)

-  **Export to data lake:** This guide assumes that you have already exported data from Common Data Service by using the [Export to Data Lake service](export-to-data-lake.md). In this example, account entity data is exported to the data lake and will generate a report by using the account entity fields.

## Connect the Data Lake Storage Gen2 storage to Power BI Desktop

1. Open Power BI Desktop, and sign in.

2. Select **Get data** > **More**.

3. On the **Get Data** page, select **Azure** > **Azure Data Lake Storage Gen2** > **Connect.**

4.  Enter the storage container name in the format<br>*https://accountname.dfs.core.windows.net/containername/*

5. Find the storage account name by going to **Azure** > **Storage accounts**, and then select the Data Lake Storage Gen2 account that's populated with the exported Common Data Services data.

6. Find the container name by going to **Storage Explorer (preview)** > **Containers**.

    ![Find the storage container name](media/find-container-name.png "Find the storage container name")

7. Select **CDM Folder View (Beta)**, and then select **OK**.

8. If prompted to sign in, do so, and then select **Access key** from the left side bar.

9. Find the access key by going back to the storage account setting and selecting **Access keys** from the left pane. Copy the first key.

    ![Copy the access key](media/copy-access-key.png "Copy the access key")

10. Expand **cdm**, select the **account** data, and then select **Load**.

    ![Load account data](media/load-account-data.png "Load account data")

## Create a Power BI report with account revenue by account owner

1. On the **Visualizations** menu, select **Pie Chart**.

    ![Pie chart](media/pie-chart.png "Pie chart")

2. On the **Fields** menu, search for and select the fields **ownerid** and **revenue**. The fields will appear on the **Visualizations** menu under **Legend** and **Values**, respectively.

    ![Search for and select the revenue field](media/select-fields.png "Search for and select the revenue field")

   A pie chart appears that separates each account owner by color and displays the total revenue of accounts.

    ![Colorful pie chart showing the total revenue and owner of ten individual accounts](media/account-data-pie-chart.png "Colorful pie chart showing the total revenue and owner of ten individual accounts")

### See also

[Export entity data to Azure Data Lake Storage Gen2](export-to-data-lake.md)