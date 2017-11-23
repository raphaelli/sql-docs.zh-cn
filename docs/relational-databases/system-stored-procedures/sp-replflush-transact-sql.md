---
title: "sp_replflush (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- sp_replflush
- sp_replflush_TSQL
helpviewer_keywords: sp_replflush
ms.assetid: 20809f5f-941d-427f-8f0c-de7a6c487584
caps.latest.revision: "17"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3626c4662c2c18722ac5f657ca9c3a5ee4356455
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="spreplflush-transact-sql"></a>sp_replflush (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  刷新项目缓存。 在发布服务器的发布数据库上执行此存储的过程。  
  
> [!IMPORTANT]  
>  用户不应手动执行此过程。 **sp_replflush**应仅可用于故障排除复制由有经验的复制支持专业人员的指引。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_replflush  
```  
  
## <a name="return-code-values"></a>返回代码值  
 **0** （成功） 或**1** （失败）  
  
## <a name="remarks"></a>注释  
 **sp_replflush**事务复制中使用。  
  
 为提高效率，项目定义存储在缓存中。 **sp_replflush**其他复制存储过程修改或删除项目定义时使用。  
  
 只有一个客户端连接有权访问给定数据库的日志读取器。 如果客户端具有对数据库的日志读取器访问，则执行**sp_replflush**导致客户端版本的访问权限。 其他客户端然后可以扫描事务日志使用**sp_replcmds**或**sp_replshowcmds**。  
  
## <a name="permissions"></a>Permissions  
 只有的成员**sysadmin**固定的服务器角色或**db_owner**固定的数据库角色可以执行**sp_replflush**。  
  
## <a name="see-also"></a>另请参阅  
 [sp_replcmds (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-replcmds-transact-sql.md)   
 [sp_repldone &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-repldone-transact-sql.md)   
 [sp_repltrans &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-repltrans-transact-sql.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  