---
title: Session Events Data Columns |Microsoft 文档
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 6e3a0287edc3081273f2a3c3075f355e9b2b2493
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="session-events-data-columns"></a>会话事件数据列
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  “会话事件”事件类别具有以下事件类：  
  
|**事件 ID**|**事件名称**|**事件说明**|  
|------------------|--------------------|---------------------------|  
|41|Existing Connection|现有用户连接。|  
|42|现有会话|现有会话。|  
|43|会话初始化|会话初始化。|  
  
 下表列出了此事件类的数据列。  
  
## <a name="existing-connection"></a>Existing Connection  
  
|**列名**|**列 ID**|**列类型**|**列说明**|  
|---------------------|-------------------|---------------------|----------------------------|  
|CurrentTime|2|5|事件开始的时间（如果可用）。 为了便于筛选，采用的格式为“YYYY-MM-DD”和“YYYY-MM-DD HH:MM:SS”。|  
|StartTime|3|5|事件开始的时间（如果可用）。 为了便于筛选，采用的格式为“YYYY-MM-DD”和“YYYY-MM-DD HH:MM:SS”。|  
|ConnectionID|25|1|唯一的连接 ID。|  
|NTUserName|32|8|Windows 用户名。|  
|NTDomainName|33|8|用户所属的 Windows 域。|  
|ClientHostName|35|8|正在运行客户端的计算机的名称。 如果客户端提供了主机名，则填充此数据列。|  
|ClientProcessID|36|1|客户端应用程序的进程 ID。|  
|ApplicationName|37|8|创建了到服务器连接的客户端应用程序的名称。 此列由应用程序传递的值填充，而不是由所显示的程序名填充。|  
|SPID|41|1|服务器进程 ID。 该 ID 将唯一标识一个用户会话， 并且直接于 XML/A 使用的会话 GUID 相对应。|  
|ServerName|43|8|生成事件的服务器的名称。|  
  
## <a name="existing-session"></a>现有会话  
  
|**列名**|**列 ID**|**列类型**|**列说明**|  
|---------------------|-------------------|---------------------|----------------------------|  
|CurrentTime|2|5|事件开始的时间（如果可用）。 为了便于筛选，采用的格式为“YYYY-MM-DD”和“YYYY-MM-DD HH:MM:SS”。|  
|StartTime|3|5|事件开始的时间（如果可用）。 为了便于筛选，采用的格式为“YYYY-MM-DD”和“YYYY-MM-DD HH:MM:SS”。|  
|Duration|5|2|事件占用的时间（毫秒）。|  
|CPUTime|6|2|事件所用的 CPU 时间（毫秒）。|  
|ConnectionID|25|1|唯一的连接 ID。|  
|DatabaseName|28|8|正在运行用户语句的数据库的名称。|  
|NTUserName|32|8|Windows 用户名。|  
|NTDomainName|33|8|用户所属的 Windows 域。|  
|ClientHostName|35|8|正在运行客户端的计算机的名称。 如果客户端提供了主机名，则填充此数据列。|  
|ClientProcessID|36|1|客户端应用程序的进程 ID。|  
|ApplicationName|37|8|创建了到服务器连接的客户端应用程序的名称。 此列由应用程序传递的值填充，而不是由所显示的程序名填充。|  
|NTCanonicalUserName|40|8|采用规范格式的用户名。 例如，engineering.microsoft.com/software/someone。|  
|SPID|41|1|服务器进程 ID。 该 ID 将唯一标识一个用户会话， 并且直接于 XML/A 使用的会话 GUID 相对应。|  
|TextData|42|9|与事件关联的文本数据。|  
|ServerName|43|8|生成事件的服务器的名称。|  
|RequestProperties|45|9|XMLA 请求属性。|  
  
## <a name="session-initialize"></a>会话初始化  
  
|||||  
|-|-|-|-|  
|**列名**|**列 ID**|**列类型**|**列说明**|  
|CurrentTime|2|5|事件开始的时间（如果可用）。 为了便于筛选，采用的格式为“YYYY-MM-DD”和“YYYY-MM-DD HH:MM:SS”。|  
|StartTime|3|5|事件开始的时间（如果可用）。 为了便于筛选，采用的格式为“YYYY-MM-DD”和“YYYY-MM-DD HH:MM:SS”。|  
|ConnectionID|25|1|唯一的连接 ID。|  
|DatabaseName|28|8|正在运行用户语句的数据库的名称。|  
|NTUserName|32|8|Windows 用户名。|  
|NTDomainName|33|8|用户所属的 Windows 域。|  
|ClientHostName|35|8|正在运行客户端的计算机的名称。 如果客户端提供了主机名，则填充此数据列。|  
|ClientProcessID|36|1|客户端应用程序的进程 ID。|  
|ApplicationName|37|8|创建了到服务器连接的客户端应用程序的名称。 此列由应用程序传递的值填充，而不是由所显示的程序名填充。|  
|NTCanonicalUserName|40|8|采用规范格式的用户名。 例如，engineering.microsoft.com/software/someone。|  
|SPID|41|1|服务器进程 ID。 该 ID 将唯一标识一个用户会话， 并且直接于 XML/A 使用的会话 GUID 相对应。|  
|TextData|42|9|与事件关联的文本数据。|  
|ServerName|43|8|生成事件的服务器的名称。|  
|RequestProperties|45|9|XMLA 请求属性。|  
  
## <a name="see-also"></a>另请参阅  
 [“安全审核”事件类别](../../analysis-services/trace-events/security-audit-event-category.md)  
  
  
