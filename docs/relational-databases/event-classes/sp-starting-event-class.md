---
title: "SP:Starting 事件类 | Microsoft Docs"
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
- SP:Starting event class
ms.assetid: ef55e579-080d-4650-a7fc-4dd03ed8e391
caps.latest.revision: 33
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 5c5aed4070cc1d0c3477f2ce31a55add8ca89e0f
ms.lasthandoff: 04/11/2017

---
# <a name="spstarting-event-class"></a>SP:Starting 事件类
  SP:Starting 事件类指示存储过程将要开始执行。  
  
## <a name="spstarting-event-class-data-columns"></a>SP:Starting 事件类的数据列  
  
|数据列名称|数据类型|说明|列 ID|可筛选|  
|----------------------|---------------|-----------------|---------------|----------------|  
|ApplicationName|**nvarchar**|客户端应用程序的名称，该客户端应用程序创建了指向 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]实例的连接。 此列由应用程序传递的值填充，而不是由所显示的程序名填充。|10|是|  
|ClientProcessID|**int**|主机为运行该客户端应用程序的进程分配的 ID。 如果客户端提供了客户端进程 ID，则填充此数据列。|9|是|  
|DatabaseID|**int**|正在运行存储过程的数据库的 ID。 可使用 DB_ID 函数来确定数据库的值。|3|是|  
|DatabaseName|**nvarchar**|正在运行存储过程的数据库的名称。|35|是|  
|EventClass|**int**|事件类型 = 42。|27|是|  
|EventSequence|**int**|给定事件在请求中的顺序。|51|是|  
|GroupID|**int**|在其中激发 SQL 跟踪事件的工作负荷组的 ID。|66|是|  
|HostName|**nvarchar**|正在运行客户端的计算机的名称。 如果客户端提供了主机名，则填充此数据列。 若要确定主机名，请使用 HOST_NAME 函数。|8|是|  
|IsSystem|**int**|指示事件是发生在系统进程中还是发生在用户进程中。 1 = 系统，0 = 用户。|60|是|  
|LineNumber|**int**|显示调用此存储过程的 execute 语句的行号。|5|是|  
|LoginName|**nvarchar**|用户的登录名（ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安全登录名或 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 登录凭据，格式为“DOMAIN\username”）。|11|是|  
|LoginSid|**image**|登录用户的安全标识号 (SID)。 您可以在 sys.server_principals 目录视图中找到此信息。 服务器中的每个登录名都具有唯一的 SID。|41|是|  
|NestLevel|**int**|存储过程的嵌套级别。|29|是|  
|NTDomainName|**nvarchar**|用户所属的 Windows 域。|7|是|  
|NTUserName|**nvarchar**|Windows 用户名。|6|是|  
|ObjectID|**int**|系统分配的存储过程 ID。|22|是|  
|ObjectName|**nvarchar**|将要开始的存储过程的名称。|34|是|  
|ObjectType|**int**|将要开始的存储过程的类型。 此值对应于 sys.objects 目录视图中的类型列。 有关值的信息，请参阅 [ObjectType 跟踪事件列](../../relational-databases/event-classes/objecttype-trace-event-column.md)。|28|是|  
|RequestID|**int**|包含该语句的请求的 ID。|49|是|  
|ServerName|**nvarchar**|所跟踪的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例的名称。|26|是|  
|SessionLoginName|**nvarchar**|发起会话的用户的登录名。 例如，如果您使用 Login1 连接到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ，再以 Login2 的身份执行语句，则 SessionLoginName 将显示 Login1，而 LoginName 将显示 Login2。 此列将同时显示 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 登录名和 Windows 登录名。|64|是|  
|SourceDatabaseID|**int**|对象所在数据库的 ID。|62|是|  
|SPID|**int**|发生该事件的会话的 ID。|12|是|  
|StartTime|**datetime**|该事件（如果存在）的启动时间。|14|是|  
|TextData|**ntext**|过程调用的文本。|1|是|  
|TransactionID|**bigint**|系统分配的事务 ID。|4|是|  
|XactSequence|**bigint**|用于说明当前事务的标记。|50|是|  
  
## <a name="see-also"></a>另请参阅  
 [扩展事件](../../relational-databases/extended-events/extended-events.md)   
 [sp_trace_setevent (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql.md)  
  
  