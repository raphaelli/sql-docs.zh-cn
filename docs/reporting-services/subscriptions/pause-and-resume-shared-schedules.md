---
title: "暂停和恢复共享计划 | Microsoft Docs"
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
  - "暂停计划"
  - "报表特定计划 [Reporting Services]"
  - "共享计划 [Reporting Services], 恢复"
  - "恢复计划"
  - "继续执行计划"
  - "计划 [Reporting Services], 恢复"
  - "计划 [Reporting Services], 暂停"
ms.assetid: e416be75-5234-4aa6-a3de-77f60f25169a
caps.latest.revision: 36
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
caps.handback.revision: 36
---
# 暂停和恢复共享计划
  您可以暂停和恢复正在使用的共享计划。 通过暂停共享计划，可以暂时冻结用于触发报表处理和订阅的计划。 您只能暂停和恢复共享计划。 不能暂停报表特定计划。  
  
 您不能暂停和恢复正在进行的报表处理。 您只能暂停和恢复处于 SQL Server 代理服务计划队列中的计划。 正在进行的作业不在计划引擎的管理范围内。 有关详细信息，请参阅[管理运行中的进程](../../reporting-services/subscriptions/manage-a-running-process.md)  
  
 暂停共享计划时，可以取消将要发生的任何操作。 恢复共享计划后，报表和订阅处理将使用服务器的本地时间，在计划的下一次执行时间进行。 假如未暂停计划，本机模式报表服务器或 SharePoint 服务应用程序不会虚构出一些本来将要发生的计划操作。  
  
 本主题内容：  
  
-   [暂停和恢复共享计划（本机模式）](#bkmk_native)  
  
-   [暂停和恢复共享计划（SharePoint 模式）](#bkmk_sharepoint)  
  
##  <a name="bkmk_native"></a> 暂停和恢复共享计划（本机模式）  
 要暂停和恢复共享计划，请使用报表管理器中的“计划”页。 您不能使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]；它没有提供用于暂停和恢复计划的选项。 有关详细信息，请参阅 [Create, Modify, and Delete Schedules](../../reporting-services/subscriptions/create-modify-and-delete-schedules.md)。  
  
#### 暂停或恢复共享计划  
  
1.  从报表管理器单击 **“站点设置”**。  
  
2.  单击 **“计划”**。  
  
3.  选择计划，在功能区中单击 **“暂停”** 或 **“恢复”** 。 如果计划当前已暂停， **“状态”** 列将包含 **“已暂停”**。  
  
##  <a name="bkmk_sharepoint"></a> 暂停和恢复共享计划（SharePoint 模式）  
 要暂停和恢复共享计划，请使用“站点设置”页或 PowerShell。 针对每个 SharePoint 站点管理计划。  
  
#### 暂停或恢复共享计划  
  
1.  单击 **“网站操作”**。  
  
2.  单击 **“网站设置”**。  
  
3.  在 Reporting Services 部分中，单击 **“管理共享计划”**。  
  
4.  选择计划，并单击 **“暂停所选计划”** 或 **“运行所选计划”**。 如果计划当前已暂停， **“状态”** 列将包含 **“已暂停”**。  
  
## 另请参阅  
 [计划](../../reporting-services/subscriptions/schedules.md)   
 [创建、修改和删除计划](../../reporting-services/subscriptions/create-modify-and-delete-schedules.md)   
 [更改报表服务器上的时区和时钟设置](../../reporting-services/subscriptions/change-time-zones-and-clock-settings-on-a-report-server.md)   
 [管理运行中的进程](../../reporting-services/subscriptions/manage-a-running-process.md)  
  
  