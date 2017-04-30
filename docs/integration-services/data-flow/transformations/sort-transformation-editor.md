---
title: "排序转换编辑器 | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.sorttransformation.f1"
helpviewer_keywords: 
  - "排序转换编辑器"
ms.assetid: 8ae23970-49a9-4d6d-9f15-c7074783347c
caps.latest.revision: 25
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 25
---
# 排序转换编辑器
  可以使用 **“排序转换编辑器”** 对话框，选择要排序的列，设置排序顺序以及指定是否删除重复项。  
  
 若要了解有关排序转换的详细信息，请参阅 [Sort Transformation](../../../integration-services/data-flow/transformations/sort-transformation.md)。  
  
## 选项  
 **可用输入列**  
 使用此复选框可以指定要排序的列。  
  
 **名称**  
 查看每个可用输入列的名称。  
  
 **传递**  
 指示是否在排序输出中包含相应列。  
  
 **输入列**  
 从每行的可用输入列的列表中选择。 通过选中 **“可用输入列”** 表中的复选框来选择列。  
  
 **输出别名**  
 为每个输出列键入一个别名。 默认值为输入列的名称；不过，您也可以任选一个唯一的描述性名称。  
  
 **排序类型**  
 指示按升序还是按降序排序。  
  
 **排序顺序**  
 指示列的排序顺序。 必须对每列手动设置此选项。  
  
 **比较标志**  
 有关字符串比较选项的信息，请参阅[比较字符串数据](../../../integration-services/data-flow/comparing-string-data.md)。  
  
 **删除具有重复排序值的行**  
 根据指定的字符串比较选项，指示转换是将重复行复制到转换输出，还是为所有重复项创建单个条目。  
  
## 另请参阅  
 [Integration Services 错误和消息引用](../../../integration-services/integration-services-error-and-message-reference.md)  
  
  