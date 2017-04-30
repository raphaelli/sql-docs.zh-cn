---
title: "向更改跟踪组添加属性 (Master Data Services) | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "更改跟踪组 [Master Data Services]"
  - "属性 [Master Data Services]，更改跟踪组"
  - "更改跟踪组 [Master Data Services]，添加属性"
ms.assetid: e153eb5f-70ca-4c6f-89d8-1f937ed3917d
caps.latest.revision: 7
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 7
---
# 向更改跟踪组添加属性 (Master Data Services)
  在 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]中，在您想要跟踪对属性值的更改时向更改跟踪组添加属性。  
  
> [!NOTE]  
>  在您向更改跟踪组添加属性后，在属性值发生更改时，该属性在 [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] 数据库中将标记为“已更改”。 创建业务规则以便基于更改执行操作。  
  
## 先决条件  
 若要执行此过程：  
  
-   您必须有权访问 **“系统管理”** 功能区域。  
  
-   您必须是模型管理员。 有关详细信息，请参阅[管理员 (Master Data Services)](../master-data-services/administrators-master-data-services.md)。  
  
-   要添加到更改跟踪组的属性必须存在。 有关详细信息，请参阅[创建文本属性 (Master Data Services)](../master-data-services/create-a-text-attribute-master-data-services.md)。  
  
### 向更改跟踪组添加属性  
  
1.  在 [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]中，单击 **“系统管理”**。  
  
2.  在“管理模型”  页上，从网格中选择一个模型，然后单击“实体” 。  
  
3.  在“管理实体”  页上，选择要为其创建属性的实体所在的行。  
  
4.  单击 **“属性”**。  
  
5.  在“管理属性”  页上，执行下列操作之一。  
  
    -   如果是叶成员的属性，请从“成员类型”  列表框中选择“叶”  。  
  
    -   如果属性是针对合并成员，则从“成员类型”  列表框中选择“合并”  。  
  
    -   如果是集合的属性，请从“成员类型”  列表框中选择“集合”  。  
  
6.  选择要编辑的属性所在的行，然后单击“编辑” 。  
  
7.  选中 **“启用更改跟踪”** 复选框。  
  
8.  在 **“更改跟踪组”** 框中，键入该组的编号。  
  
9. 单击 **“保存属性”**。  
  
     对于已编辑的属性，网格中的“启用更改跟踪组”列会变成“是(组: 输入的组号)”。  
  
10. 对于您要在组中包括的所有属性重复此过程。 对于该组中的每个属性，使用相同的更改跟踪组编号。  
  
## 后续步骤  
  
-   [基于属性值更改启动操作 (Master Data Services)](../master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)  
  
## 另请参阅  
 [创建文本属性 (Master Data Services)](../master-data-services/create-a-text-attribute-master-data-services.md)   
 [创建基于域的属性 (Master Data Services)](../master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  