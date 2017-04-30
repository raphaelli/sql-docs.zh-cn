---
title: "传输主存储过程任务编辑器（“存储过程”页） | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.transferstoredprocedurestask.storedprocedures.f1"
helpviewer_keywords: 
  - "传输存储过程任务编辑器"
ms.assetid: 5fcf171e-cc0b-4c24-8eb5-3a4b4775e64a
caps.latest.revision: 20
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 20
---
# 传输主存储过程任务编辑器（“存储过程”页）
  可以使用“传输主存储过程任务编辑器”对话框的“存储过程”页，指定用于将一个或多个用户定义存储过程从一个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例中的 **master** 数据库复制到另一个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例中的 **master** 数据库的属性。 有关此任务的详细信息，请参阅 [Transfer Master Stored Procedures Task](../../integration-services/control-flow/transfer-master-stored-procedures-task.md)。  
  
> [!NOTE]  
>  此任务只将 **dbo** 拥有的用户定义存储过程从源服务器上的 **master** 数据库传递到目标服务器上的 **master** 数据库。 若要在目标服务器上创建存储过程，必须在目标服务器上的 **master** 数据库中授予用户 CREATE PROCEDURE 权限，或者用户必须为目标服务器上 **sysadmin** 固定服务器角色的成员。  
  
## 选项  
 **SourceConnection**  
 从列表中选择一个 SMO 连接管理器，或单击“\<新建连接...>”创建与源服务器的新连接。  
  
 **DestinationConnection**  
 从列表中选择一个 SMO 连接管理器，或单击“\<新建连接...>”创建与目标服务器的新连接。  
  
 **IfObjectExists**  
 选择该任务应如何处理目标服务器上的 **master** 数据库中已经存在的同名用户定义存储过程。  
  
 此属性具有下表所列的选项：  
  
|“值”|Description|  
|-----------|-----------------|  
|**FailTask**|如果目标服务器上的 **master** 数据库中已存在同名的存储过程，则任务失败。|  
|**Overwrite**|任务将覆盖目标服务器上的 **master** 数据库中的同名存储过程。|  
|**Skip**|任务将跳过目标服务器上的 **master** 数据库中存在的同名存储过程。|  
  
 **TransferAllStoredProcedures**  
 选择是否应将源服务器上 **master** 数据库中的所有用户定义存储过程复制到目标服务器。  
  
|“值”|Description|  
|-----------|-----------------|  
|**True**|复制 **master** 数据库中的所有用户定义存储过程。|  
|**False**|仅复制指定的存储过程。|  
  
 **StoredProceduresList**  
 选择应将源服务器上 **master** 数据库中的哪些用户定义存储过程复制到目标 **master** 数据库。 只有在 **TransferAllStoredProcedures** 设置为 **False**时，此选项才可用。  
  
## 另请参阅  
 [Integration Services 错误和消息引用](../../integration-services/integration-services-error-and-message-reference.md)   
 [Integration Services 任务](../../integration-services/control-flow/integration-services-tasks.md)   
 [传输主存储过程任务编辑器（“常规”页）](../../integration-services/control-flow/transfer-master-stored-procedures-task-editor-general-page.md)   
 [“表达式”页](../../integration-services/expressions/expressions-page.md)   
 [SMO 连接管理器](../../integration-services/connection-manager/smo-connection-manager.md)  
  
  