---
title: Power BI Integration Component and Architecture Overview for Business Central| Microsoft Docs
description: Learn about the different aspects of Power BI integration with Business Central.
author: jswymer
ms.topic: overview
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'account schedule, analysis, reporting, financial report, business intelligence, KPI'
ms.reviewer: edupont
ms.date: 04/01/2021
ms.author: jswymer
---
# <a name="power-bi-integration-component-and-architecture-overview-for-includeprodshortincludesprodshortmd" />Power BI Integration Component and Architecture Overview for [!INCLUDE[prod_short](includes/prod_short.md)]

In this article, you'll learn about the different aspects of Power BI integration with [!INCLUDE[prod_short](includes/prod_short.md)] to help you understand its implementation and use.

## <a name="components" />Components

The following table describes the major components involved with Power BI integration.

|Component|Description|
|---------|-----------|
|Power BI|A cloud-based report hosting and management service.|
|Power BI Desktop|An authoring tool for building reports and dashboards, and allows you to run reports. It's available as a free download on Microsoft Store and is installed locally.|
|[!INCLUDE[prod_short](includes/prod_short.md)]|Online or on-premises solution with connectors exposed to Power BI and the ability to embed a Power BI part.|

## <a name="whats-available-from-the-start" />What's available from the start

The following table describes available features.

|Feature|[!INCLUDE[prod_short](includes/prod_short.md)] online or on-premises support|
|-------|---------------------|
|Power BI connectors|Both. Different connectors for online and on-premises. Same connector used for Power BI Desktop and Power BI Service |
|Embedded experience for viewing a given report inside a FactBox in [!INCLUDE[prod_short](includes/prod_short.md)]|Both. Requires configuration to display reports for on-premises.|
|Power BI report management from [!INCLUDE[prod_short](includes/prod_short.md)]|Online|
|Default Power BI reports on role centres deployed to Power BI|Online|
|Power BI Apps on Microsoft AppSource|Online|

## <a name="architecture" />Architecture

[!INCLUDE[prod_short](includes/prod_short.md)] integrates with Power BI through a connector using OData. The data source for Power BI reports is exposed as API pages and OData web services.

:::image type="content" source="./media/power-bi-architecture.png" alt-text="Image alt text." lightbox="./media/power-bi-architecture.png":::

Starting in February 2022, Power BI reports for [!INCLUDE[prod_short](includes/prod_short.md)] online are sourced from a secondary, read-only database replica. The database replica is part of the [read scale-out](/dynamics365/business-central/dev-itpro/administration/database-read-scale-out-overview) capability in [!INCLUDE[prod_short](includes/prod_short.md)] online. This configuration frees up the main database for transactions, which enhances performance of the system. Connecting to the read-only database replica is an integral part of the Business Central online connector, and requires no extra setup on your part. All new reports will connect to the read-only database replica by default. Old reports will still use the main database. For more information, see [Business Central 2021 Release Wave 2 Plan](/dynamics365-release-plan/2021wave2/smb/dynamics365-business-central/use-secondary-read-only-database-power-bi-reporting).

## <a name="general-flow" />General Flow

The following diagram illustrates the basic workflow for users when connecting [!INCLUDE[prod_short](includes/prod_short.md)] to Power BI.

![Power BI workflow  for integration with Business Central.](./media/power-bi-flow.png)

1. User signs up for a Power BI account.
2. User connects to Power BI from [!INCLUDE[prod_short](includes/prod_short.md)].
3. [!INCLUDE[prod_short](includes/prod_short.md)] verifies the licence.
4. [!INCLUDE[prod_short](includes/prod_short.md)] deploys default reports to the Power BI service. This step only happens for [!INCLUDE[prod_short](includes/prod_short.md)] online.
5. [!INCLUDE[prod_short](includes/prod_short.md)] makes reports in Power BI available for selection in [!INCLUDE[prod_short](includes/prod_short.md)]. Default reports are automatically displayed in Power BI parts.
6. User creates a report in Power BI Desktop.
7. User publishes the report to the Power BI service. The reports are then available for selection in [!INCLUDE[prod_short](includes/prod_short.md)].

## <a name="see-related-microsoft-trainingtrainingmodulesconfigure-powerbi-excel-dynamics-365-business-centralindex" />See related [Microsoft training](/training/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## <a name="see-also" />See Also

[Business Central and Power BI](admin-powerbi.md)  
[Power BI for consumers](/power-bi/consumer/end-user-consumer)  
[The 'new look' of the Power BI service](/power-bi/service-new-look)  
[Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Power BI documentation](/power-bi/)  
[Business Intelligence](bi.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as a Power BI Data Source](across-how-use-financials-data-source-powerbi.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as a Power Apps Data Source](across-how-use-financials-data-source-powerapps.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] in Power Automate](across-how-use-financials-data-source-flow.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
