---
title: "大容量插入任务编辑器（“连接”页） | Microsoft Docs"
ms.custom: ""
ms.date: "03/04/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.bulkinserttask.connection.f1"
helpviewer_keywords: 
  - "大容量插入任务编辑器"
ms.assetid: 51252c20-8865-4ede-a3fd-bd73a968f47d
caps.latest.revision: 30
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 30
---
# 大容量插入任务编辑器（“连接”页）
  可以使用 **“大容量插入任务编辑器”** 对话框的 **“连接”** 页，指定大容量插入操作的源和目标以及使用的格式。  
  
 若要了解大容量插入，请参阅[大容量插入任务](../../integration-services/control-flow/bulk-insert-task.md)和[用来导入或导出数据的格式化文件 (SQL Server)](../../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md)。  
  
## 选项  
 **连接**  
 在列表中选择一个 OLE DB 连接管理器，或单击“\<新建连接…>”创建新的连接。  
  
 **相关主题：**[OLE DB 连接管理器](../../integration-services/connection-manager/ole-db-connection-manager.md)、[配置 OLE DB 连接管理器](../../integration-services/connection-manager/configure-ole-db-connection-manager.md)  
  
 **DestinationTable**  
 键入目标表或视图的名称，或在列表中选择表或视图。  
  
 **格式**  
 选择大容量插入任务的格式源。 此属性具有下表所列的选项。  
  
|“值”|Description|  
|-----------|-----------------|  
|**使用文件**|选择包含格式规范的文件。 选择此选项将显示动态选项 **FormatFile**。|  
|**指定**|指定格式。 选择此选项将显示动态选项 **RowDelimiter** 和 **ColumnDelimiter**。|  
  
 **文件**  
 在列表中选择一个文件或平面文件连接管理器，或单击“\<新建连接…>”创建新的连接。  
  
 文件位置与在此任务的连接管理器中指定的 SQL Server 数据库引擎有关。 该文本文件必须可被服务器本地硬盘上的 SQL Server 数据库引擎访问，或可通过 SQL Server 的共享驱动器或映射的驱动器访问。 SSIS 运行时不访问该文件。  
  
 如果通过使用平面文件连接管理器来访问源文件，则大容量插入任务不会使用在平面文件连接管理器中指定的格式。 相反，大容量插入任务将使用在格式化文件中指定的格式，或者使用该任务的 RowDelimite 和 ColumnDelimiter 属性的值。  
  
 **相关主题：**[文件连接管理器](../../integration-services/connection-manager/file-connection-manager.md)、[文件连接管理器编辑器](../../integration-services/connection-manager/file-connection-manager-editor.md)、[平面文件连接管理器](../../integration-services/connection-manager/flat-file-connection-manager.md)、[平面文件连接管理器编辑器（“常规”页）](../../integration-services/connection-manager/flat-file-connection-manager-editor-general-page.md)、[平面文件连接管理器编辑器（“列”页）](../../integration-services/connection-manager/flat-file-connection-manager-editor-columns-page.md)、[平面文件连接管理器编辑器（“高级”页）](../../integration-services/connection-manager/flat-file-connection-manager-editor-advanced-page.md)  
  
 **刷新表**  
 刷新表和视图的列表。  
  
## Format 动态选项  
  
### Format = 使用文件  
 **FormatFile**  
 键入格式化文件的路径，或单击省略号按钮 **(…)** 定位到该格式化文件。  
  
### Format = 指定  
 **RowDelimiter**  
 指定源文件中的行分隔符。 默认值为 **{CR}{LF}**。  
  
 **ColumnDelimiter**  
 指定源文件中的列分隔符。 默认值为 **“制表符”**。  
  
## 另请参阅  
 [Integration Services 错误和消息引用](../../integration-services/integration-services-error-and-message-reference.md)   
 [大容量插入任务编辑器（“常规”页）](../../integration-services/control-flow/bulk-insert-task-editor-general-page.md)   
 [大容量插入任务编辑器（“选项”页）](../../integration-services/control-flow/bulk-insert-task-editor-options-page.md)   
 [“表达式”页](../../integration-services/expressions/expressions-page.md)   
 [BULK INSERT (Transact-SQL)](../../t-sql/statements/bulk-insert-transact-sql.md)   
 [控制流](../../integration-services/control-flow/control-flow.md)  
  
  