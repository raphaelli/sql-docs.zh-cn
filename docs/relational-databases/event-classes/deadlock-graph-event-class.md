---
title: "Deadlock Graph 事件类 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Deadlock Graph event class
ms.assetid: 20f92233-c912-4382-8993-8e2e23d03fbe
caps.latest.revision: 31
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 8dc88c1c1f2afb7f5cb79b7d18931c3cd2238722
ms.lasthandoff: 04/11/2017

---
# <a name="deadlock-graph-event-class"></a>Deadlock Graph 事件类
  **Deadlock Graph** 事件类提供了有关死锁的 XML 描述。 该类与 **Lock:Deadlock** 事件类同时发生。  
  
## <a name="deadlock-graph-event-class-data-columns"></a>Deadlock Graph 事件类的数据列  
  
|数据列名称|数据类型|说明|列 ID|可筛选|  
|----------------------|---------------|-----------------|---------------|----------------|  
|**EventClass**|**int**|事件类型 = 148。|27|是|  
|**EventSequence**|**int**|给定事件在请求中的顺序。|51|是|  
|**IsSystem**|**int**|指示事件是发生在系统进程中还是发生在用户进程中。 1 = 系统，0 = 用户。 对于此事件，该值始终为 1。|60|是|  
|**LoginName**|**nvarchar**|用户的登录名（ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安全登录名或 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 登录凭据，格式为“DOMAIN\username”）。 对于此事件，此值始终为系统用户。|11|是|  
|**LoginSid**|**image**|登录用户的安全标识号 (SID)。 您可以在 sys.server_principals 目录视图中找到此信息。 服务器中的每个登录名都具有唯一的 SID。 对于此事件，此值始终为系统用户的 SID。|41|是|  
|**ServerName**|**nvarchar**|所跟踪的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例的名称。|26|是|  
|**SessionLoginName**|**nvarchar**|发起会话的用户的登录名。 例如，如果您使用 Login1 连接到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ，再以 Login2 的身份执行语句，则 **SessionLoginName** 将显示 Login1，而 **LoginName** 将显示 Login2。 此列将同时显示 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登录名和 Windows 登录名。|64|是|  
|**SPID**|**int**|发生该事件的会话的 ID。|12|是|  
|**StartTime**|**datetime**|检测到死锁的时间。|14|是|  
|**TextData**|**ntext**|死锁的 XML 描述。|1|是|  
|**TransactionID**|**bigint**|未使用。|4|是|  
  
## <a name="see-also"></a>另请参阅  
 [sp_trace_setevent (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)   
 [Lock:Deadlock 事件类](../../relational-databases/event-classes/lock-deadlock-event-class.md)  
  
  