---
title: "对 INSERT 和 UPDATE 语句禁用 CHECK 约束 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-tables"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CHECK 约束, 禁用"
  - "约束 [SQL Server], 禁用"
  - "禁用约束"
  - "约束 [SQL Server], 检查"
ms.assetid: c7287ad1-50d2-4e80-bc0c-b5570f7e5f69
caps.latest.revision: 17
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 17
---
# 对 INSERT 和 UPDATE 语句禁用 CHECK 约束
[!INCLUDE[tsql-appliesto-ss2016-all_md](../../includes/tsql-appliesto-ss2016-all-md.md)]

  您可以通过使用 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 或 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ，在 [!INCLUDE[tsql](../../includes/tsql-md.md)]中禁用针对 INSERT 和 UPDATE 事务的 CHECK 约束。 在禁用该 CHECK 约束后，在将来插入或更新列时，将不会根据约束条件进行验证。 如果您知道新数据将与现有约束冲突或者如果约束仅适用于数据库中已有的数据，则可选择此选项。  
  
 **本主题内容**  
  
-   **开始之前：**  
  
     [安全性](#Security)  
  
-   **使用以下工具为 INSERT 和 UPDATE 语句禁用 CHECK 约束：**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> 开始之前  
  
###  <a name="Security"></a> 安全性  
  
####  <a name="Permissions"></a> 权限  
 需要对表的 ALTER 权限。  
  
##  <a name="SSMSProcedure"></a> 使用 SQL Server Management Studio  
  
#### 为 INSERT 和 UPDATE 语句禁用 CHECK 约束  
  
1.  在 **“对象资源管理器”**中，展开具有约束的表，再展开 **“约束”** 文件夹。  
  
2.  右键单击该约束，再选择“修改”。  
  
3.  在“表设计器”下的网格中，单击“强制用于 INSERT 和 UPDATE”，然后从下拉菜单中选择“否”。  
  
4.  单击 **“关闭”**。  
  
##  <a name="TsqlProcedure"></a> 使用 Transact-SQL  
  
#### 为 INSERT 和 UPDATE 语句禁用 CHECK 约束  
  
1.  在 **“对象资源管理器”**中，连接到 [!INCLUDE[ssDE](../../includes/ssde-md.md)]的实例。  
  
2.  在标准菜单栏上，单击 **“新建查询”**。  
  
3.  将以下示例复制并粘贴到查询窗口中，然后单击 **“执行”**。  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT CK_PurchaseOrderHeader_Freight;   
    GO  
    ```  
  
 有关详细信息，请参阅 [ALTER TABLE (Transact-SQL)](../../t-sql/statements/alter-table-transact-sql.md)。  
  
###  <a name="TsqlExample"></a>  