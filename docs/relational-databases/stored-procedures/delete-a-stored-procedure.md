---
title: "删除存储过程 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-stored-Procs
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- removing stored procedures
- stored procedures [SQL Server], deleting
- deleting stored procedures
ms.assetid: 232dbf4d-392a-406f-af3a-579518cd8e46
caps.latest.revision: 26
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: d9f9d65d2521299d34188897fbbf5675b5c9eea4
ms.lasthandoff: 04/11/2017

---
# <a name="delete-a-stored-procedure"></a>删除存储过程
    
##  <a name="Top"></a> 本主题介绍了如何使用 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 或 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 在 [!INCLUDE[tsql](../../includes/tsql-md.md)]中删除存储过程。  
  
-   **准备工作：**[限制和局限](#Restrictions)、[安全性](#Security)  
  
-   **要删除过程，请使用：**[SQL Server Management Studio](#SSMSProcedure)、[Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Restrictions"></a> 限制和局限  
 如果依赖对象和脚本尚未更新以反映过程的删除，则删除过程可能会导致这些对象和脚本失败。 但是，如果创建了具有相同名称和参数的新过程来替换已被删除的过程，那么引用该过程的其他对象仍能成功处理。 有关详细信息，请参阅 [查看存储过程的依赖关系](../../relational-databases/stored-procedures/view-the-dependencies-of-a-stored-procedure.md)。  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> 权限  
 需要拥有对该过程所属架构的 ALTER 权限，或对该过程的 CONTROL 权限。  
  
##  <a name="Procedures"></a> 如何删除存储过程  
 您可以使用以下项之一：  
  
-   [SQL Server Management Studio](#SSMSProcedure)  
  
-   [Transact-SQL](#TsqlProcedure)  
  
###  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
 **在对象资源管理器中删除过程**  
  
1.  在对象资源管理器中，连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 的实例，然后展开该实例。  
  
2.  展开 **“数据库”**、过程所属的数据库以及 **“可编程性”**。  
  
3.  展开“存储过程”，右键单击要删除的过程，再单击“删除”。  
  
4.  若要查看依赖于过程的对象，请单击 **“显示依赖关系”**。  
  
5.  确认选择了正确的过程，再单击 **“确定”**。  
  
6.  从所有依赖对象和脚本中删除对该过程的引用。  
  
###  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
 **在查询编辑器中删除过程**  
  
1.  在 **“对象资源管理器”**中，连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)] 的实例，然后展开该实例。  
  
2.  展开 **“数据库”**、过程所属的数据库，或者从工具栏，从可用数据库列表选择该数据库。  
  
3.  在“文件”菜单上，单击 **“新建查询”**。  
  
4.  获取要在当前数据库中删除的存储过程的名称。 从对象资源管理器，展开 **“可编程性”** ，再展开 **“存储过程”**。 或者，在查询编辑器中，运行以下语句：  
  
    ```tsql  
    SELECT name AS procedure_name   
        ,SCHEMA_NAME(schema_id) AS schema_name  
        ,type_desc  
        ,create_date  
        ,modify_date  
    FROM sys.procedures;  
    ```  
  
5.  将以下示例复制并粘贴到查询编辑器，然后插入要从当前数据库中删除的存储过程名称。  
  
    ```tsql  
    DROP PROCEDURE <stored procedure name>;  
    GO  
    ```  
  
6.  从所有依赖对象和脚本中删除对该过程的引用。  
  
## <a name="see-also"></a>另请参阅  
 [创建存储过程](../../relational-databases/stored-procedures/create-a-stored-procedure.md)   
 [修改存储过程](../../relational-databases/stored-procedures/modify-a-stored-procedure.md)   
 [重命名存储过程](../../relational-databases/stored-procedures/rename-a-stored-procedure.md)   
 [查看存储过程的定义](../../relational-databases/stored-procedures/view-the-definition-of-a-stored-procedure.md)   
 [查看存储过程的依赖关系](../../relational-databases/stored-procedures/view-the-dependencies-of-a-stored-procedure.md)   
 [DROP PROCEDURE (Transact-SQL)](../../t-sql/statements/drop-procedure-transact-sql.md)  
  
  