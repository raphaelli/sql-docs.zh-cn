---
title: "字词查找转换编辑器（“字词查找”选项卡） | Microsoft Docs"
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
  - "sql13.dts.designer.termlookup.termlookup.f1"
helpviewer_keywords: 
  - "字词查找转换编辑器"
ms.assetid: 245d3466-d51f-4073-978a-694a8d9dfaec
caps.latest.revision: 26
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 26
---
# 字词查找转换编辑器（“字词查找”选项卡）
  可以使用 **“字词查找转换编辑器”** 对话框的 **“字词查找”** 选项卡，将输入列映射到引用表中的查找列，以及为每个输出列提供别名。  
  
 若要了解有关字词查找转换的详细信息，请参阅 [Term Lookup Transformation](../../../integration-services/data-flow/transformations/term-lookup-transformation.md)。  
  
## 选项  
 **可用输入列**  
 使用复选框选择要传递给未更改输出的输入列。 将输入列拖动到 **“可用引用列”** 列表可以将其映射到引用表中的查找列。 输入列和查找列必须具有支持的匹配数据类型（DT_NTEXT 或 DT_WSTR）。 选择一个映射行，再右键单击可在[创建关系](../../../integration-services/data-flow/transformations/create-relationships.md)对话框中编辑该映射。  
  
 **可用引用列**  
 查看引用表中可用的列。 选择包含要匹配的字词列表的列。  
  
 **传递列**  
 从可用输入列的列表中进行选择。 通过选中 **“可用输入列”** 表中的复选框来选择列。  
  
 **输出列别名**  
 为每个输出列键入一个别名。 默认值为列的名称；不过，您也可以任选一个唯一的描述性名称。  
  
 **配置错误输出**  
 使用[配置错误输出](../Topic/Configure%20Error%20Output.md)对话框可以为导致错误的行指定错误处理方式选项。  
  
## 另请参阅  
 [Integration Services 错误和消息引用](../../../integration-services/integration-services-error-and-message-reference.md)   
 [字词查找转换编辑器（“引用表”选项卡）](../../../integration-services/data-flow/transformations/term-lookup-transformation-editor-reference-table-tab.md)   
 [字词查找转换编辑器（“高级”选项卡）](../../../integration-services/data-flow/transformations/term-lookup-transformation-editor-advanced-tab.md)   
 [字词提取转换](../../../integration-services/data-flow/transformations/term-extraction-transformation.md)  
  
  