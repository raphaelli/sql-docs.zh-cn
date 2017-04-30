---
title: "数据质量匹配列（用于 Excel 的 MDS 外接程序） | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f683fdc6-0d4c-4793-8143-567616cb2094
caps.latest.revision: 9
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 9
---
# 数据质量匹配列（用于 Excel 的 MDS 外接程序）
  在 [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] 中，匹配数据后，在功能区上的“数据质量”组中，可单击“显示详细信息”以便显示提供匹配详细信息的列。  
  
 下表显示匹配数据时显示的列。  
  
|名称|Description|  
|----------|-----------------|  
|**CLUSTER_ID**|用于对相似记录进行分组的唯一标识符。 所有相似的行都具有相同的 **CLUSTER_ID**。 如果没有为某一行显示 **CLUSTER_ID**，则找不到相似的记录。|  
|**RECORD_ID**|用于标识记录的唯一标识符。 与在 MDS 存储库中存储的代码值相似，它是用于标识记录的值。 每次出现匹配时都将自动生成该值。|  
|**PIVOT_MARK**|其他记录与其进行比较的任意记录；它不具有得分值。|  
|**SCORE**|表示组中的记录与透视记录的相似程度。 该得分是由 DQS 确定的。 如果没有显示任何得分，则该记录是其他记录的透视记录，或者找不到匹配项。|  
  
## 另请参阅  
 [用于 Excel 的 MDS 外接程序中的数据质量匹配](../../master-data-services/microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md)   
 [匹配相似数据（用于 Excel 的 MDS 外接程序）](../../master-data-services/microsoft-excel-add-in/match-similar-data-mds-add-in-for-excel.md)   
 [数据匹配](../../data-quality-services/data-matching.md)  
  
  