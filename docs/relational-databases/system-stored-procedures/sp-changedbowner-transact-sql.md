---
title: "sp_changedbowner (TRANSACT-SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_changedbowner
- sp_changedbowner_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_changedbowner
ms.assetid: 516ef311-e83b-45c9-b9cd-0e0641774c04
caps.latest.revision: "35"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Active
ms.openlocfilehash: 11b80fef363bd33f725a34e5cebd7fd8710be3b4
ms.sourcegitcommit: 9fbe5403e902eb996bab0b1285cdade281c1cb16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2017
---
# <a name="spchangedbowner-transact-sql"></a>sp_changedbowner (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  更改当前数据库的所有者。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]使用[ALTER AUTHORIZATION](../../t-sql/statements/alter-authorization-transact-sql.md)相反。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_changedbowner [ @loginame = ] 'login'  
     [ , [ @map = ] remap_alias_flag ]  
```  
  
## <a name="arguments"></a>参数  
 [ @loginame=] '*登录*  
 当前数据库的新所有者的登录 ID。 *登录名*是**sysname**，无默认值。 *登录名*必须已经存在[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]登录名或 Windows 用户。 *登录名*如果它已有权访问通过现有的用户安全帐户数据库中的数据库不能成为当前数据库的所有者。 为了避免发生上述情况，请首先删除当前数据库内的用户。  
  
 [ @map=] *remap_alias_flag*  
 *Remap_alias_flag*参数被弃用，因为已从删除登录名别名[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。 使用*remap_alias_flag*参数不会导致错误，但不起作用。  
  
## <a name="return-code-values"></a>返回代码值  
 0（成功）或 1（失败）  
  
## <a name="remarks"></a>注释  
 执行 sp_changedbowner 之后，新所有者称为数据库中的 dbo 用户。 dbo 拥有执行数据库中所有活动的暗示性权限。  
  
 不能更改 master、model 或 tempdb 系统数据库的所有者。  
  
 若要显示的有效列表*登录*值，执行 sp_helplogins 存储过程。  
  
 执行并且仅带有 sp_changedbowner*登录*参数更改数据库所有权转交到*登录*。  
  
 使用 ALTER AUTHORIZATION 语句可以更该任意安全对象的所用者。 有关详细信息，请参阅[ALTER AUTHORIZATION &#40;Transact SQL &#41;](../../t-sql/statements/alter-authorization-transact-sql.md).  
  
## <a name="permissions"></a>Permissions  
 要求具有对数据库的 TAKE OWNERSHIP 权限。 如果新所有者在数据库中具有对应的用户，则要求具有对登录名的 IMPERSONATE 权限，否则要求具有对服务器的 CONTROL SERVER 权限。  
  
## <a name="examples"></a>示例  
 以下示例将登录名 `Albert` 设为当前数据库的所有者。  
  
```  
EXEC sp_changedbowner 'Albert';  
```  
  
## <a name="see-also"></a>另请参阅  
 [安全存储过程 &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [CREATE DATABASE (SQL Server Transact-SQL)](../../t-sql/statements/create-database-sql-server-transact-sql.md)   
 [sp_dropalias &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-dropalias-transact-sql.md)   
 [sp_dropuser (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-dropuser-transact-sql.md)   
 [sp_helpdb &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-helpdb-transact-sql.md)   
 [sp_helplogins &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-helplogins-transact-sql.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  