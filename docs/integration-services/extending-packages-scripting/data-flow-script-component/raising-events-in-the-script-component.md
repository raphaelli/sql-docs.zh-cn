---
title: "在脚本组件中引发事件 |Microsoft 文档"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- Script component [Integration Services], raising events
ms.assetid: bb389073-e1d0-4794-8d29-c8b293b6a5e3
caps.latest.revision: 16
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 505855e82b683fc15ca00073f58e1f9cb348f830
ms.contentlocale: zh-cn
ms.lasthandoff: 08/03/2017

---
# <a name="raising-events-in-the-script-component"></a>在脚本组件中引发事件
  事件提供向包含包报告错误、警告和其他信息（如任务进度或状态）的方式。 包为管理事件通知提供事件处理程序。 脚本组件可以通过在调用方法来引发事件<xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A>属性**ScriptMain**类。 详细了解如何[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]包处理事件，请参阅[Integration Services &#40;SSIS &#41;事件处理程序](../../../integration-services/integration-services-ssis-event-handlers.md)。  
  
 事件可以记录到包中已启用的任何日志提供程序中。 日志提供程序在数据存储区中存储有关事件的信息。 脚本组件还可以使用 <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> 方法将信息记录到日志提供程序中而不引发事件。 有关如何使用 <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> 方法的详细信息，请参阅以下内容。  
  
 为了引发事件，脚本任务将调用由 <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> 属性公开的 <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> 接口的以下方法之一：  
  
|事件|Description|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>|引发包中用户定义的自定义事件。|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A>|将错误情况通知包。|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A>|为用户提供信息。|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireProgress%2A>|将组件的进度通知包。|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A>|向包发出通知：组件处于有必要发出用户通知，但不是错误条件的状态。|  
  
 下面是一个简单的引发错误事件的示例：  
  
 `Dim myMetadata as IDTSComponentMetaData100`  
  
 `myMetaData = Me.ComponentMetaData`  
  
 `myMetaData.FireError(...)`  
  
## <a name="see-also"></a>另请参阅  
 [Integration Services &#40;SSIS &#41;事件处理程序](../../../integration-services/integration-services-ssis-event-handlers.md)   
 [将事件处理程序添加到包](http://msdn.microsoft.com/library/5e56885d-8658-480a-bed9-3f2f8003fd78)  
  
  