---
title: 呈现和执行方法 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.component: report-server-web-service
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- rendered reports [Reporting Services]
- reports [Reporting Services], execution options
- methods [Reporting Services], execution options
- methods [Reporting Services], rendering
ms.assetid: 12626aad-f0be-4653-87d0-60eb3a3fff78
caps.latest.revision: 36
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 1d4da662ed770c6b104e53e9397321a56d4b065b
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="rendering-and-execution-methods"></a>呈现和执行方法
  可以使用这些方法来管理项执行和缓存以及报表呈现。  
  
|方法|操作|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.FlushCache%2A>|使项的缓存无效。|  
|<xref:ReportService2010.ReportingService2010.GetCacheOptions%2A>|返回项的缓存配置以及说明项的缓存副本何时到期的设置。|  
|<xref:ReportService2010.ReportingService2010.GetExecutionOptions%2A>|返回单个项的执行选项和相关设置。|  
|<xref:ReportService2010.ReportingService2010.ListExecutionSettings%2A>|返回支持的执行设置的列表。|  
|<xref:ReportExecution2005.ReportExecutionService.Render%2A>|处理指定报表并以指定格式呈现报表。|  
|<xref:ReportService2010.ReportingService2010.SetCacheOptions%2A>|配置要缓存的项并提供指定项的缓存副本何时到期的设置。|  
|<xref:ReportService2010.ReportingService2010.SetExecutionOptions%2A>|为指定的项设置执行选项和相关的执行属性。|  
|<xref:ReportService2010.ReportingService2010.UpdateItemExecutionSnapshot%2A>|生成指定项的项执行快照。|  
  
## <a name="see-also"></a>另请参阅  
 [使用 Web 服务和 .NET Framework 生成应用程序](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [报表服务器 Web 服务](../../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [报表服务器 Web 服务方法](../../../reporting-services/report-server-web-service/methods/report-server-web-service-methods.md)   
 [技术参考 (SSRS)](../../../reporting-services/technical-reference-ssrs.md)  
  
  
