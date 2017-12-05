---
title: "sp_syspolicy_delete_policy_execution_history (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/03/2017
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
- sp_syspolicy_delete_policy_execution_history
- sp_syspolicy_delete_policy_execution_history_TSQL
dev_langs: TSQL
helpviewer_keywords: sp_syspolicy_delete_policy_execution_history
ms.assetid: fe651af9-267e-45ec-b4e7-4b0698fb1be3
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 17fe4c1e46fe42228c058990473bfe3b34ace2b0
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="spsyspolicydeletepolicyexecutionhistory-transact-sql"></a>sp_syspolicy_delete_policy_execution_history (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  在基于策略的管理中删除策略的执行历史记录。 您可以使用此存储过程删除特定策略或所有策略的执行历史记录，也可以删除特定日期前的执行历史记录。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_syspolicy_delete_policy_execution_history [ @policy_id = ] policy_id ]  
    [ , [ @oldest_date = ] 'oldest_date' ]  
```  
  
## <a name="arguments"></a>参数  
 [  **@policy_id=** ] *policy_id*  
 您要删除其执行历史记录的策略的标识符。 *policy_id*是**int**，和是必需的。 可以为 NULL。  
  
 [  **@oldest_date=** ] *oldest_date*  
 要保留其策略执行历史记录的最早的日期。 先于此日期的所有执行历史记录都将被删除。 *oldest_date*是**datetime**，和是必需的。 可以为 NULL。  
  
## <a name="return-code-values"></a>返回代码值  
 **0** （成功） 或**1** （失败）  
  
## <a name="remarks"></a>注释  
 您必须在 msdb 系统数据库的上下文中运行 sp_syspolicy_delete_policy_execution_history。  
  
 若要获取的值*policy_id*，并且若要查看执行历史记录日期，你可以使用以下查询：  
  
```  
SELECT a.name AS N'policy_name', b.policy_id, b.start_date, b.end_date  
FROM msdb.dbo.syspolicy_policies AS a   
INNER JOIN msdb.dbo.syspolicy_policy_execution_history AS b  
ON a.policy_id = b.policy_id  
```  
  
 如果您为一个或两个值指定 NULL，则下面的行为适用：  
  
-   若要删除所有策略执行历史记录，则指定两个 NULL *policy_id*和*oldest_date*。  
  
-   若要删除的特定策略的所有策略执行历史记录，指定的策略标识符*policy_id*，并指定 NULL 作为*oldest_date*。  
  
-   若要在特定日期之前删除的所有策略的策略执行历史记录，则指定 NULL 为*policy_id*，并指定的日期*oldest_date*。  
  
 若要将策略执行历史记录存档，您可以在对象资源管理器中打开策略历史记录日志，然后将执行历史记录导出到某一文件中。 若要访问的策略历史记录日志，展开**管理**，右键单击**策略管理**，然后单击**查看历史记录**。  
  
## <a name="permissions"></a>Permissions  
 要求具有 PolicyAdministratorRole 固定数据库角色的成员身份。  
  
> [!IMPORTANT]  
>  可能的凭据提升：具有 PolicyAdministratorRole 角色的用户可以创建服务器触发器并计划策略执行，这可能会影响[!INCLUDE[ssDE](../../includes/ssde-md.md)]实例的正常运行。 例如，PolicyAdministratorRole 角色中的用户可以创建一个策略，它可能会禁止在[!INCLUDE[ssDE](../../includes/ssde-md.md)]中创建大多数对象。 由于凭据此可能提升，应仅向与控制的配置的受信任的用户授予 PolicyAdministratorRole 角色[!INCLUDE[ssDE](../../includes/ssde-md.md)]。  
  
## <a name="examples"></a>示例  
 下面的示例为 ID 为 7 的策略删除特定日期前的策略执行历史记录。  
  
```  
EXEC msdb.dbo.sp_syspolicy_delete_policy_execution_history @policy_id = 7  
, @oldest_date = '2009-02-16 16:00:00.000';  
  
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [基于策略的管理存储过程 &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/policy-based-management-stored-procedures-transact-sql.md)   
 [sp_syspolicy_set_config_history_retention &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-syspolicy-set-config-history-retention-transact-sql.md)   
 [sp_syspolicy_purge_history &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-syspolicy-purge-history-transact-sql.md)  
  
  