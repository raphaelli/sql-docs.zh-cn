---
title: "传输错误消息任务编辑器（“消息”页） | Microsoft Docs"
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
  - "sql13.dts.designer.transfererrormessagestask.errormessages.F1"
helpviewer_keywords: 
  - "传输错误消息任务编辑器"
ms.assetid: cb2226a0-3037-4fdf-966f-81eabc0da9cf
caps.latest.revision: 22
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 22
---
# 传输错误消息任务编辑器（“消息”页）
  可以使用“传输错误消息任务编辑器”对话框的“消息”页指定属性，以将一个或多个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 用户定义错误消息从一个 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实例复制到另一个实例。 有关此任务的详细信息，请参阅 [Transfer Error Messages Task](../../integration-services/control-flow/transfer-error-messages-task.md)。  
  
## 选项  
 **SourceConnection**  
 从列表中选择一个 SMO 连接管理器，或单击“\<新建连接...>”创建与源服务器的新连接。  
  
 **DestinationConnection**  
 从列表中选择一个 SMO 连接管理器，或单击“\<新建连接...>”创建与目标服务器的新连接。  
  
 **IfObjectExists**  
 选择在目标服务器上已存在同名的错误消息时，该任务是应该覆盖现有的用户定义错误消息还是跳过现有消息，或是失败。  
  
 **TransferAllErrorMessages**  
 选择该任务应将全部用户定义消息还是只有指定的用户定义消息从源服务器复制到目标服务器。  
  
 此属性具有下表所列的选项：  
  
|“值”|Description|  
|-----------|-----------------|  
|**True**|复制所有用户定义消息。|  
|**False**|仅复制指定的用户定义消息。|  
  
 **ErrorMessagesList**  
 单击浏览按钮 **(…)** 可选择要复制的错误消息。  
  
> [!NOTE]  
>  必须先指定 **SourceConnection**，然后才能选择要复制的错误消息。  
  
 **ErrorMessageLanguagesList**  
 单击浏览按钮 **(…)** 可选择要将哪些语言的用户定义错误消息复制到目标服务器。 在目标服务器上必须存在 us_english（代码页 1033）版本的消息，才能将其他语言版本的消息传输到目标服务器。  
  
> [!NOTE]  
>  必须先指定 **SourceConnection**，然后才能选择要复制的错误消息。  
  
## 另请参阅  
 [Integration Services 错误和消息引用](../../integration-services/integration-services-error-and-message-reference.md)   
 [Integration Services 任务](../../integration-services/control-flow/integration-services-tasks.md)   
 [传输错误消息任务编辑器（“常规”页）](../../integration-services/control-flow/transfer-error-messages-task-editor-general-page.md)   
 [SMO 连接管理器](../../integration-services/connection-manager/smo-connection-manager.md)   
 [传输错误消息任务编辑器（“常规”页）](../../integration-services/control-flow/transfer-error-messages-task-editor-general-page.md)   
 [SMO 连接管理器](../../integration-services/connection-manager/smo-connection-manager.md)  
  
  