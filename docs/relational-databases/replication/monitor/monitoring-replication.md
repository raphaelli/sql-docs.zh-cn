---
title: "监视（复制）| Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring performance [SQL Server replication], about monitoring replication
- transactional replication, monitoring
- monitoring [SQL Server replication]
- merge replication monitoring [SQL Server replication]
- snapshot replication [SQL Server], monitoring
- replication [SQL Server], monitoring
- administering replication, monitoring
ms.assetid: f182f43a-6af8-45bc-a708-08d5f7a6984a
caps.latest.revision: 39
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 8b38dc87277d0b3de4a528b8db807cfe0a6245c0
ms.lasthandoff: 04/11/2017

---
# <a name="monitoring-replication"></a>监视（复制）
  监视复制拓扑是部署复制的一个重要方面。 因为复制活动是分布式的，所以跟踪复制过程中涉及的所有计算机的活动和状态非常有必要。 以下工具可用于监视复制：  
  
-   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor  
  
     复制监视器是监视复制最重要的工具，它可以显示以发布服务器为中心的所有复制活动视图。 有关详细信息，请参阅 [Monitoring Replication](../../../relational-databases/replication/monitor/monitoring-replication-overview.md)。  
  
-   [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]  
  
     [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] 提供对复制监视器的访问。 它还允许您查看当前状态以及下列代理所记录的最后一条消息，还允许您启动和停止每个代理：日志读取器代理、快照代理、合并代理和分发代理。 有关详细信息，请参阅 [Monitor Replication Agents](../../../relational-databases/replication/monitor/monitor-replication-agents.md)。  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)] 和复制管理对象 (RMO)  
  
     两个界面都可用于监视分发服务器上的所有复制类型。 合并复制还提供从发布服务器监视复制的功能。  
  
-   复制代理事件的警报  
  
     复制提供了许多复制代理事件的预定义警报，如果有必要，您还可以创建其他警报。 警报用于触发对某个事件的自动响应和/或用于通知管理员。 有关详细信息，请参阅[对复制代理事件使用警报](../../../relational-databases/replication/agents/use-alerts-for-replication-agent-events.md)。  
  
-   系统监视器  
  
     系统监视器对性能监视很有用，它可为复制提供多个计数器。 有关详细信息，请参阅 [Monitoring Replication with System Monitor](../../../relational-databases/replication/monitor/monitoring-replication-with-system-monitor.md)。  
  
## <a name="see-also"></a>另请参阅  
 [管理（复制）](../../../relational-databases/replication/administration/administration-replication.md)   
 [Best Practices for Replication Administration](../../../relational-databases/replication/administration/best-practices-for-replication-administration.md)   
 [监视复制](../../../relational-databases/replication/monitor/monitoring-replication-overview.md)  
  
  