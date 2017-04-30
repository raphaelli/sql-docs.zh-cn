---
title: "查看或配置 backup compression default 服务器配置选项 | Microsoft Docs"
ms.custom: ""
ms.date: "03/02/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SQL Server Management Studio [SQL Server], 备份压缩默认选项"
  - "备份压缩 [SQL Server], 备份压缩默认选项"
ms.assetid: 23029395-3e93-4c29-b7d6-e5a47a3526ff
caps.latest.revision: 30
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 30
---
# 查看或配置 backup compression default 服务器配置选项
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  本主题说明如何使用 **或** 在 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 中查看或配置 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] backup compression default [!INCLUDE[tsql](../../includes/tsql-md.md)]服务器配置选项。 **backup compression default** 选项确定默认情况下服务器实例是否创建压缩的备份。 当安装 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 时， **backup compression default** 选项关闭。  
  
 **本主题内容**  
  
-   **开始之前：**  
  
     [限制和局限](#Restrictions)  
  
     [建议](#Recommendations)  
  
     [安全性](#Security)  
  
-   **查看或配置 backup compression default 选项，使用：**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
-   **跟进：**[在配置备份压缩默认选项之后](#FollowUp)  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Restrictions"></a> 限制和局限  
  
-   在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的所有版本中不提供备份压缩功能。 有关详细信息，请参阅 [SQL Server 2016 各个版本支持的功能](../Topic/Features%20Supported%20by%20the%20Editions%20of%20SQL%20Server%202016.md)。  
  
-   默认情况下，压缩会显著增加 CPU 的使用，并且压缩进程所消耗的额外 CPU 可能会对并发操作产生不利影响。 因此，你可能需要在会话中创建低优先级的压缩备份，其 CPU 使用率受[资源调控器](../../relational-databases/resource-governor/resource-governor.md)限制。 有关详细信息，请参阅[使用资源调控器限制备份压缩的 CPU 使用率 (Transact-SQL)](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)。  
  
###  <a name="Recommendations"></a> 建议  
  
-   创建单个备份、配置日志传送配置或创建维护计划时，可以覆盖服务器级默认设置。  
  
-   磁盘备份设备和磁带备份设备都支持备份压缩。  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> 权限  
 默认情况下，所有用户都具备不带参数或仅带第一个参数的 **sp_configure** 的执行权限。 若要执行带两个参数的 **sp_configure** 以更改配置选项或运行 RECONFIGURE 语句，则用户必须具备 ALTER SETTINGS 服务器级别的权限。 ALTER SETTINGS 权限由 **sysadmin** 和 **serveradmin** 固定服务器角色隐式持有。  
  
##  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
  
#### 查看或配置备份压缩默认值选项  
  
1.  在对象资源管理器中，右键单击“服务器”并选择“属性”。  
  
2.  单击 **“数据库设置”** 节点。  
  
3.  在“备份和还原” 下，“压缩备份”  显示了 **backup compression default** 选项的当前设置。 该设置确定压缩备份的服务器级默认设置，如下所示：  
  
    -   如果未选中 **“压缩备份”** 框，在默认情况下将不压缩新备份。  
  
    -   如果 **“压缩备份”** 框已选中，则默认情况下将压缩新备份。  
  
     如果你是 **sysadmin** 或 **serveradmin** 固定服务器角色的成员，还可以通过单击“压缩备份”  框来更改默认设置。  
  
##  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
  
#### 查看 backup compression default 选项  
  
1.  连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)]。  
  
2.  在标准菜单栏上，单击 **“新建查询”**。  
  
3.  将以下示例复制并粘贴到查询窗口中，然后单击 **“执行”**。 此示例查询 [sys.configurations](../../relational-databases/system-catalog-views/sys-configurations-transact-sql.md) 目录视图以确定 `backup compression default`的值。 值为 0 表示禁用备份压缩功能，值为 1 表示启用备份压缩功能。  
  
```tsql  
SELECT value   
FROM sys.configurations   
WHERE name = 'backup compression default' ;  
GO  
```  
  
#### 配置 backup compression default 选项  
  
1.  连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)]。  
  
2.  在标准菜单栏上，单击 **“新建查询”**。  
  
3.  将以下示例复制并粘贴到查询窗口中，然后单击 **“执行”**。 此示例说明了如何使用 [sp_configure](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md) 将服务器实例配置为在默认情况下创建压缩备份。  
  
```tsql  
EXEC sp_configure 'backup compression default', 1 ;  
RECONFIGURE WITH OVERRIDE ;  
GO 
```  
  
 有关详细信息，请参阅[服务器配置选项 (SQL Server)](../../database-engine/configure-windows/server-configuration-options-sql-server.md)。  
  
##  <a name="FollowUp"></a> 跟进：在配置 backup compression default 选项之后  
 该设置将立即生效，无需重新启动服务器。  
  
## 另请参阅  
 [BACKUP (Transact-SQL)](../../t-sql/statements/backup-transact-sql.md)   
 [服务器配置选项 (SQL Server)](../../database-engine/configure-windows/server-configuration-options-sql-server.md)   
 [RECONFIGURE (Transact-SQL)](../../t-sql/language-elements/reconfigure-transact-sql.md)   
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [备份概述 (SQL Server)](../../relational-databases/backup-restore/backup-overview-sql-server.md)  
  
  