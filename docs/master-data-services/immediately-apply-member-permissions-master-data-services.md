---
title: "立即应用成员权限 (Master Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "成员 [Master Data Services], 立即应用权限"
  - "权限 [Master Data Services], 立即应用成员权限"
ms.assetid: 5b16de66-5c39-49f5-992f-402a9eb319aa
caps.latest.revision: 6
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 6
---
# 立即应用成员权限 (Master Data Services)
  在 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]中，您可以立即应用成员权限，而不必等待定期应用的成员安全性。  
  
## 先决条件  
 若要执行此过程：  
  
-   您必须具有在 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 数据库中执行 mdm.udpSecurityMemberProcessRebuildModel 存储过程的权限。 有关详细信息，请参阅[数据库对象安全性 (Master Data Services)](../master-data-services/database-object-security-master-data-services.md)。  
  
### 立即应用层次结构成员权限  
  
1.  打开 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] 并连接到 [!INCLUDE[ssDE](../includes/ssde-md.md)] 数据库的 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 实例。  
  
2.  创建新查询。  
  
3.  键入以下文本，用数据库名称替换 database，用模型名称替换 Model_Name。  
  
    ```  
    USE [database];  
    GO  
  
    DECLARE @Model_ID INT;  
    SELECT @Model_ID = ID FROM mdm.tblModel WHERE [Name] = N'Model_Name';  
    EXEC [mdm].[udpSecurityMemberProcessRebuildModel] @Model_ID=@Model_ID, @ProcessNow=1;  
    GO  
    ```  
  
4.  运行查询。  
  
## 另请参阅  
 [分配层次结构成员权限 (Master Data Services)](../master-data-services/assign-hierarchy-member-permissions-master-data-services.md)   
 [层次结构成员权限 (Master Data Services)](../master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  