---
title: syscollector_execution_stats (TRANSACT-SQL) |Microsoft 文档
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- syscollector_execution_stats
- syscollector_execution_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- syscollector_execution_stats view
- data collector view
ms.assetid: 23e35ac5-fbbf-4922-970c-f4fac44c1263
caps.latest.revision: 17
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 74fef0f1da7d6ec8d1a66525e3b985c61fe52991
ms.sourcegitcommit: f1caaa156db2b16e817e0a3884394e7b30fb642f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="syscollectorexecutionstats-transact-sql"></a>syscollector_execution_stats (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  提供有关收集组或包的任务执行的信息。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**log_id**|**bigint**|标识收集组的每次执行。 用于将此视图与其他详细日志联接起来。 不可为 null。|  
|**task_name**|**nvarchar(128)**|该信息对应的收集组或包任务的名称。 不可为 null。|  
|**execution_row_count_in**|**int**|在数据流起始位置处理的行数。 可以为 Null。|  
|**execution_row_count_out**|**int**|在数据流结尾位置处理的行数。 可以为 Null。|  
|**execution_row_count_errors**|**int**|在数据流过程中失败的行数。 可以为 Null。|  
|**execution_time_ms**|**int**|完成任务所需的时间（单位为毫秒）。 可以为 Null。|  
|**log_time**|**datetime**|记录此信息的时间。 不可为 null。|  
  
## <a name="permissions"></a>权限  
 需要选择权限**dc_operator**。  
  
## <a name="see-also"></a>另请参阅  
 [数据收集器存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)   
 [数据收集器视图 (Transact-SQL)](../../relational-databases/system-catalog-views/data-collector-views-transact-sql.md)   
 [“数据收集”](../../relational-databases/data-collection/data-collection.md)  
  
  
