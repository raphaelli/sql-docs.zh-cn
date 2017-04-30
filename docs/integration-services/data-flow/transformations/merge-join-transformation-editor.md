---
title: "合并联接转换编辑器 | Microsoft Docs"
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
  - "sql13.dts.designer.mergejointransformation.f1"
helpviewer_keywords: 
  - "合并联接转换编辑器"
ms.assetid: ac06f419-30b3-42aa-8b34-42000bec4285
caps.latest.revision: 31
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 31
---
# 合并联接转换编辑器
  可以使用 **“合并联接转换编辑器”** 对话框指定联接类型、联接列和输出列，以合并通过联接组合的两个输入。  
  
> [!IMPORTANT]  
>  合并联接转换要求输入已排序的数据。 有关此重要要求的详细信息，请参阅[为合并转换和合并联接转换排序数据](../../../integration-services/data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md)。  
  
 若要了解有关合并联接转换的详细信息，请参阅 [Merge Join Transformation](../../../integration-services/data-flow/transformations/merge-join-transformation.md)。  
  
## 选项  
 **联接类型**  
 指定要使用内部联接、左外部联接还是完全联接。  
  
 **交换输入**  
 通过使用“交换输入”按钮来交换输入的顺序。 对于左外部联接选项，此选项可能有用。  
  
 **输入**  
 对于要在合并的输出中包含的每个列，请首先从可用输入列表中相应地进行选择。  
  
 输入显示在两个单独的表中。 请选择要包含在输出中的列。 通过拖动列可以在表之间创建联接。 若要删除某个联接，请选定该联接，再按 Delete 键。  
  
 **输入列**  
 从所选输入的可用列的列表中选择要包含在合并的输出中的列。  
  
 **输出别名**  
 为每个输出列键入一个别名。 默认值为输入列的名称；不过，您也可以任选一个唯一的描述性名称。  
  
## 另请参阅  
 [Integration Services 错误和消息引用](../../../integration-services/integration-services-error-and-message-reference.md)   
 [为合并转换和合并联接转换排序数据](../../../integration-services/data-flow/transformations/sort-data-for-the-merge-and-merge-join-transformations.md)   
 [使用合并联接转换扩展数据集](../../../integration-services/data-flow/transformations/extend-a-dataset-by-using-the-merge-join-transformation.md)   
 [合并转换](../../../integration-services/data-flow/transformations/merge-transformation.md)   
 [Union All 转换](../../../integration-services/data-flow/transformations/union-all-transformation.md)  
  
  