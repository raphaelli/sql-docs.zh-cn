---
title: "订阅，发布服务器到分发服务器的历史记录（事务订阅）| Microsoft Docs"
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
- sql13.rep.monitor.subscription.pubtodist.tran.f1
ms.assetid: d5a4c697-1342-49fd-8b7b-b059af32556a
caps.latest.revision: 20
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 2d6d5ad351cd6e89952f70b37d1a62fd3250127e
ms.lasthandoff: 04/11/2017

---
# <a name="subscription-publisher-to-distributor-history-transactional-subscription"></a>订阅，发布服务器到分发服务器的历史记录（事务订阅）
  **“发布服务器到分发服务器的历史记录”** 选项卡显示日志读取器代理的相关详细信息，包括状态、历史记录、信息性消息和所有错误消息。  
  
## <a name="options"></a>选项  
 从 **“视图”** 菜单中选择要查看的日志读取器代理会话，然后在标记为 **“日志读取器代理的会话”**的网格中选择特定的会话。 有关此会话的详细信息显示在标记为 **“所选会话中的操作”**的网格中。 如果所选会话由于出错而结束，则还将显示一个标记为 **“所选会话的错误详细信息或消息”** 的文本区域。  
  
 **“视图”**  
 选择要查看的日志读取器代理会话。 日志读取器代理通常连续运行，因此可能只有一个可供查看的会话。  
  
 **状态**  
 日志读取器代理的状态。 下面列出了可能的状态值：  
  
-   错误  
  
-   已完成  
  
-   正在重试  
  
-   正在运行  
  
 **Start Time**  
 会话的开始时间。  
  
 **结束时间**  
 会话的结束时间。 如果代理尚未停止，此字段为空。  
  
 **Duration**  
 日志读取器代理已在此会话中运行的时间。 如果代理当前正在运行，该时间表示已用时间；如果代理会话已经结束，则该时间表示会话的总时间。  
  
 **错误消息**  
 如果会话由于出错而结束，此字段将显示日志读取器代理记录的上一条错误消息。 如果某会话未因出错而结束，此字段为空白。  
  
 **操作消息**  
 日志读取器代理在所选会话期间记录的所有信息性消息和错误消息。  
  
 **操作时间**  
 执行 **“操作消息”** 列中所述操作的时间。  
  
 **“所选会话的错误详细信息或消息”**  
 只有当所选会话在 **“状态”** 列中显示 **“错误”** 值时，才会显示此项。 此文本区域显示详细错误信息以及出错时尝试执行的命令。 另外，还包括指向与该错误相关的其他内容的链接。  
  
## <a name="see-also"></a>另请参阅  
 [启动复制监视器](../../relational-databases/replication/monitor/start-the-replication-monitor.md)   
 [查看与订阅关联的代理的信息和执行其任务（复制监视器）](../../relational-databases/replication/monitor/view-information-and-perform-tasks-for-subscription-agents.md)   
 [监视复制](../../relational-databases/replication/monitor/monitoring-replication-overview.md)   
 [Replication Agents Overview](../../relational-databases/replication/agents/replication-agents-overview.md)  
  
  