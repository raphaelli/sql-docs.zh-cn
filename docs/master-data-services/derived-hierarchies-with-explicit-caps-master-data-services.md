---
title: "具有显式顶端的派生层次结构 (Master Data Services) | Microsoft Docs"
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
  - "层次结构 [Master Data Services], 具有显式顶端的派生层次结构"
  - "显式层次结构, 具有显式顶端的派生层次结构"
  - "派生层次结构, 具有显式顶端的派生层次结构"
ms.assetid: 6a82ff66-c137-4757-99bb-787d189b4295
caps.latest.revision: 7
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 7
---
# 具有显式顶端的派生层次结构 (Master Data Services)
  在 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]中，当来自显式层次结构的级别用作派生层次结构的顶级时，该级别称作具有显式顶端的派生层次结构。  
  
 此显式层次结构必须基于与派生层次结构顶部的实体相同的实体。  
  
 在[!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]用户界面 (UI) 中，通过将显式层次结构拖到派生层次结构的顶部来创建此类型的层次结构。  
  
 ![mds_conc_explicit_cap_UI_structure](../master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")  
  
## 具有显式顶端的派生层次结构示例  
 在此示例中，该显式层次结构中的成员来自 Subcategory 实体。 在派生层次结构中，顶级成员也来自 Subcategory 实体。  
  
 ![mds_conc_explicit_cap_UI_example](../master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")  
  
 通过在某一派生层次结构的顶部使用显式层次结构，该派生层次结构将成为不规则层次结构。  
  
## 规则  
  
-   不能在具有显式顶端的派生层次结构中具有多个显式层次结构。  
  
-   可以将相同的显式层次结构用作多个派生层次结构的顶端。  
  
-   不能将层次结构成员权限分配给具有显式顶端的派生层次结构。 如果您单独将权限分配给显式层次结构或派生层次结构，则这些权限将影响这两种层次结构。  
  
## 相关任务  
  
|任务说明|主题|  
|----------------------|-----------|  
|创建派生层次结构。|[创建派生层次结构 (Master Data Services)](../master-data-services/create-a-derived-hierarchy-master-data-services.md)|  
|创建显式层次结构。|[创建显式层次结构 (Master Data Services)](../master-data-services/create-an-explicit-hierarchy-master-data-services.md)|  
|删除现有派生层次结构。|[删除派生层次结构 (Master Data Services)](../master-data-services/delete-a-derived-hierarchy-master-data-services.md)|  
|||  
  
## 相关内容  
  
-   [派生层次结构 (Master Data Services)](../master-data-services/derived-hierarchies-master-data-services.md)  
  
-   [显式层次结构 (Master Data Services)](../master-data-services/explicit-hierarchies-master-data-services.md)  
  
  