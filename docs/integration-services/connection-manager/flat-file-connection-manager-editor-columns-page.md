---
title: "平面文件连接管理器编辑器（“列”页） | Microsoft Docs"
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
  - "sql13.dts.designer.ffileconnection.columns.f1"
helpviewer_keywords: 
  - "平面文件连接管理器编辑器"
ms.assetid: 40ce7537-abd0-4973-97fd-6ccb90fddfa0
caps.latest.revision: 21
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 21
---
# 平面文件连接管理器编辑器（“列”页）
  可以使用 **“平面文件连接管理器编辑器”** 对话框的 **“列”** 页，指定行和列的信息以及预览相应的文件。  
  
 若要了解有关平面文件连接管理器的详细信息，请参阅 [Flat File Connection Manager](../../integration-services/connection-manager/flat-file-connection-manager.md)。  
  
## 静态选项  
 **连接管理器名称**  
 为工作流中的平面文件连接提供唯一的名称。 所提供的名称将在 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器中显示。  
  
 **Description**  
 描述此连接。 最好按照连接的用途对其进行说明，使包的说明一目了然，且更便于维护。  
  
## 平面文件格式动态选项  
  
### 格式 = 带分隔符  
 **行分隔符**  
 从可用行分隔符的列表中选择，或输入分隔符文本。  
  
|“值”|Description|  
|-----------|-----------------|  
|**{CR}{LF}**|行由回车符和换行符的组合分隔。|  
|**{CR}**|行由回车符分隔。|  
|**{LF}**|行由换行符分隔。|  
|**分号 {;}**|行由分号分隔。|  
|**冒号 {:}**|行由冒号分隔。|  
|**逗号 {,}**|行由逗号分隔。|  
|**制表符 {t}**|行由制表符分隔。|  
|**竖线 {|}。**|行由竖线分隔。|  
  
 **列分隔符**  
 从可用列分隔符的列表中选择，或输入分隔符文本。  
  
|“值”|Description|  
|-----------|-----------------|  
|**{CR}{LF}**|列由回车符和换行符的组合分隔。|  
|**{CR}**|列由回车符分隔。|  
|**{LF}**|列由换行符分隔。|  
|**分号 {;}**|列由分号分隔。|  
|**冒号 {:}**|列由冒号分隔。|  
|**逗号 {,}**|列由逗号分隔。|  
|**制表符 {t}**|列由制表符分隔。|  
|**竖线 {|}。**|列由竖线分隔。|  
  
 **刷新**  
 通过单击“刷新”查看更改要跳过的分隔符后的效果。 只有在更改其他连接选项之后，此按钮才可见。  
  
 **预览行**  
 查看平面文件中的示例数据，这些数据已按所选的选项划分为列和行。  
  
 **重置列**  
 通过单击“重置列”可以删除除原始列之外的所有列。  
  
### 格式 = 固定宽度  
 **字体**  
 选择用于显示预览数据的字体。  
  
 **源数据列**  
 通过滑动垂直的红色行标记可以调整行宽，通过单击预览窗口顶部的标尺可以调整列宽。  
  
 **行宽**  
 为各列添加分隔符之前，先指定行的长度。 或者，拖动预览窗口中的垂直红线，以标记行尾。 行宽值将自动更新。  
  
 **重置列**  
 通过单击“重置列”可以删除除原始列之外的所有列。  
  
### 格式 = 右边未对齐  
  
> [!NOTE]  
>  在右边未对齐的文件中，除最后一列之外的每一列的宽度都固定。 它由行分隔符分隔。  
  
 **字体**  
 选择用于显示预览数据的字体。  
  
 **源数据列**  
 通过滑动垂直的红色行标记可以调整行宽，通过单击预览窗口顶部的标尺可以调整列宽。  
  
 **行分隔符**  
 从可用行分隔符的列表中选择，或输入分隔符文本。  
  
|“值”|Description|  
|-----------|-----------------|  
|**{CR}{LF}**|行由回车符和换行符的组合分隔。|  
|**{CR}**|行由回车符分隔。|  
|**{LF}**|行由换行符分隔。|  
|**分号 {;}**|行由分号分隔。|  
|**冒号 {:}**|行由冒号分隔。|  
|**逗号 {,}**|行由逗号分隔。|  
|**制表符 {t}**|行由制表符分隔。|  
|**竖线 {|}。**|行由竖线分隔。|  
  
 **重置列**  
 通过单击“重置列”可以删除除原始列之外的所有列。  
  
## 另请参阅  
 [Integration Services 错误和消息引用](../../integration-services/integration-services-error-and-message-reference.md)   
 [平面文件连接管理器编辑器（“常规”页）](../../integration-services/connection-manager/flat-file-connection-manager-editor-general-page.md)   
 [平面文件连接管理器编辑器（“高级”页）](../../integration-services/connection-manager/flat-file-connection-manager-editor-advanced-page.md)   
 [平面文件连接管理器编辑器（“预览”页）](../../integration-services/connection-manager/flat-file-connection-manager-editor-preview-page.md)  
  
  