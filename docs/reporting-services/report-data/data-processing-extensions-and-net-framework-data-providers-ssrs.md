---
title: "数据处理扩展插件和 .NET Framework 数据访问接口 (SSRS) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "报表 [Reporting Services]，数据"
  - "数据处理扩展插件 [Reporting Services]"
  - "数据访问接口 [Reporting Services]"
  - "数据检索 [Reporting Services]"
  - "Reporting Services，数据源"
  - "报表数据 [报表生成器], 访问"
ms.assetid: 42a5afb5-f4c8-4957-b1fd-77bf39afa5be
caps.latest.revision: 19
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
caps.handback.revision: 19
---
# 数据处理扩展插件和 .NET Framework 数据访问接口 (SSRS)
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 数据处理扩展插件是随 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]安装的组件，用于从特定类型的数据源检索数据，并提供支持报表设计和报表处理的额外功能。 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 数据提供程序是 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 或支持 <xref:System.Data> 接口（可让你检索并修改特定类型的源数据中的数据）的第三方源代码中提供的一个组件。  
  
## 了解数据处理扩展插件  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 数据处理扩展插件支持 <xref:System.Data> 接口的子集。 数据处理扩展插件要求对数据源进行只读访问，因此不实现写入接口和更新接口。 每个数据处理扩展插件都可提供自定义功能，以支持报表处理。 例如，数据处理扩展插件可能会支持下列功能类型：  
  
-   在连接字符串之外单独管理凭据  
  
-   支持多值参数  
  
-   检索对数据源计算的服务器聚合  
  
-   从数据源检索数据属性和数据值  
  
## 了解数据访问接口  
 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 数据提供程序（有时称为驱动程序）支持一组用于在数据源读取、写入和更新数据的标准 <xref:System.Data> 接口。 对于特定类型的数据源，如果没有可用的数据处理扩展插件，则可以使用数据访问接口。 有许多第三方标准 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 数据访问接口可用。  
  
 因为 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 具有一个可扩展的数据访问接口体系结构，所以您可以创建自定义数据处理扩展插件以包含 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 数据处理扩展插件提供的额外功能。 有关详细信息，请参阅 [Implementing a Data Processing Extension](../../reporting-services/extensions/data-processing/implementing-a-data-processing-extension.md)。 有关第三方数据处理扩展插件的信息，请参阅第三方数据处理扩展插件的随附文档。  
  
> [!NOTE]  
>  [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 数据访问接口或自定义数据处理扩展插件必须先行安装并注册，然后才能用于访问数据源中的数据。 必须同时在报表客户端和报表服务器安装并注册数据处理扩展插件，以便创作报表和查看已发布的报表。 不是所有数据访问接口都设计为在服务器环境中工作。 有关详细信息，请参阅[注册标准 .NET Framework 数据提供程序 (SSRS)](../../reporting-services/report-data/register-a-standard-net-framework-data-provider-ssrs.md) 和[部署数据处理扩展插件](../../reporting-services/extensions/data-processing/deploying-a-data-processing-extension.md)。  
  
## 另请参阅  
 [数据处理扩展插件概述](../../reporting-services/extensions/data-processing/data-processing-extensions-overview.md)   
 [报表的嵌入数据集和共享数据集（报表生成器和 SSRS）](../../reporting-services/report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  