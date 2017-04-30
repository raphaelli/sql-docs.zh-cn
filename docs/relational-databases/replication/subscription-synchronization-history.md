---
title: "订阅，同步历史记录 | Microsoft Docs"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.monitor.subscription.synchhistory.f1
ms.assetid: 85f666f6-14ee-4f19-b385-e5cc508aabe4
caps.latest.revision: 20
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 4da555ce4d256a6f4990831c6c7f3a2c2db5997a
ms.lasthandoff: 04/11/2017

---
# <a name="subscription-synchronization-history"></a>订阅，同步历史记录
  **“同步历史记录”** 选项卡显示有关合并代理的详细信息，包括状态、项目统计信息、历史记录、信息性消息和所有错误信息。  
  
## <a name="options"></a>选项  
 从 **“视图”** 菜单中选择要查看的合并代理会话，然后在标记为 **“合并代理的会话”**的网格中选择特定的会话。 有关此会话的详细信息显示在标记为 **“所选会话中已处理的项目”**的网格中。  
  
 **“视图”**  
 选择要查看的合并代理会话。  
  
 **状态**  
 会话结束时合并代理的状态。 下面列出了可能的状态值：  
  
-   错误  
  
-   已完成  
  
-   正在重试  
  
-   正在运行  
  
 **Start Time**  
 会话的开始时间。  
  
 **结束时间**  
 会话的结束时间。 如果代理尚未停止，此字段为空。  
  
 **Duration**  
 合并代理已在会话中运行的时间。 如果代理当前正在运行，该时间表示已用时间；如果代理已在之前运行完毕，则该时间表示总时间。  
  
 **已上载的命令**  
 合并代理会话过程中上载的行数。  
  
 **已下载的命令**  
 合并代理会话过程中下载的行数。  
  
 **错误消息**  
 如果某会话由于出错而结束，此字段将会显示合并代理记录的上一条错误消息。 如果某会话未因出错而结束，此字段为空白。  
  
 **项目**  
 发布中各个项目的名称以及在整个发布中所处的处理阶段：  
  
-   **初始化**。 这是指启动合并代理；其过程不同于初始化订阅，后者涉及应用快照。  
  
-   **架构更改和大容量插入**。  
  
-   **上载对发布服务器的更改**。  
  
-   **下载对订阅服务器的更改**。  
  
 包含这些阶段后，网格就可以显示各个阶段在所选会话中所占用的时间以及占总时间的百分比。  
  
 **占总时间的百分比**  
 在所选的会话中每个阶段占总处理时间的百分比。  
  
 **Duration**  
 每个处理阶段所用的时间。 如果合并代理当前正在为会话运行，该时间表示已用时间；如果合并代理之前已经运行完毕，该时间则表示运行所用的总时间。  
  
 **Inserts**  
 在所选会话的此阶段中插入的行数。  
  
 **Updates**  
 在所选会话的此阶段中更新的行数。  
  
 **Deletes**  
 在所选会话的此阶段中删除的行数。  
  
 **冲突**  
 所选会话中的冲突数。  
  
 **架构更改**  
 所选会话中的架构更改数。 架构更改可能由于以下原因而发生：从发布数据库中复制架构更改；添加或删除项目；更改项目或发布属性。  
  
 **所选会话的上一条消息**  
 此文本区显示所选会话中的最后消息。 如果发生错误，该区域会显示详细的错误信息以及出错时所尝试的命令。 另外，还包括指向与该错误相关的其他内容的链接。  
  
## <a name="see-also"></a>另请参阅  
 [启动复制监视器](../../relational-databases/replication/monitor/start-the-replication-monitor.md)   
 [查看与订阅关联的代理的信息和执行其任务（复制监视器）](../../relational-databases/replication/monitor/view-information-and-perform-tasks-for-subscription-agents.md)   
 [监视复制](../../relational-databases/replication/monitor/monitoring-replication-overview.md)   
 [Replication Agents Overview](../../relational-databases/replication/agents/replication-agents-overview.md)  
  
  