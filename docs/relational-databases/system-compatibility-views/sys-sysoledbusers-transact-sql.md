---
title: sys.sysoledbusers (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-compatibility-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sys.sysoledbusers
- sys.sysoledbusers_TSQL
- sysoledbusers
- sysoledbusers_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysoledbusers system table
- sys.sysoledbusers compatibility view
ms.assetid: fe924c17-9cad-4b2b-8124-1e0fd82931e3
caps.latest.revision: 34
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 9bed55c42d7d656f53e24acb1d859658666ce901
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="syssysoledbusers-transact-sql"></a>sys.sysoledbusers (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

    
> [!IMPORTANT]  
>  [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] 中包括此 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 系统表只为了向后兼容。 我们建议你使用[目录视图](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)相反。  
  
 指定的链接服务器的每个用户和密码映射在表中对应一行。 **sysoledbusers**存储在**master**数据库。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**rmtsrvid**|**int**|服务器的安全标识号 (SID)。|  
|**rmtloginame**|**nvarchar(** 128 **)**|远程登录名， **loginsid**链接映射到**rmtservid**。|  
|**rmtpassword**|**nvarchar(** 128 **)**|返回 NULL。|  
|**loginsid**|**varbinary(** 85 **)**|要映射的本地登录 SID。|  
|**status**|**int**|如果为 1，则映射应使用用户凭据。|  
|**changedate**|**datetime**|最近更改映射信息的日期。|  
  
## <a name="see-also"></a>另请参阅  
 [目录视图 (Transact-SQL)](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [兼容性视图 (Transact SQL)](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
