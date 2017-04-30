---
title: "回退成员修订历史记录 (Master Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d39d3474-20e7-429f-9c8d-fcc4eb0854fc
caps.latest.revision: 5
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 5
---
# 回退成员修订历史记录 (Master Data Services)
  每当成员发生变化时，系统都会记录成员修订历史记录。 你可以将成员修订历史记录回退到旧版记录。  
  
## 先决条件  
  
-   你必须有权更新选定成员的至少一个属性。 当你回退修订历史记录时，可以更新的所有属性值都会回退到旧版值。  
  
-   仅当实体的事务日志类型是成员时，才会生成修订历史记录。  
  
 **回退成员修订历史记录**  
  
1.  在“主数据管理器”中，单击“资源管理器”。  
  
2.  选择要回退的实体和成员。  
  
3.  单击“查看历史记录”   
  
4.  选择要回退的修订，然后单击“回退” 。  
  
## 另请参阅  
 [成员修订历史记录 (Master Data Services)](../master-data-services/member-revision-history-master-data-services.md)   
 [更改实体事务日志类型 (Master Data Services)](../master-data-services/change-the-entity-transaction-log-type-master-data-services.md)  
  
  