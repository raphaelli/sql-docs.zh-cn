---
title: 处理 TOM API (Analysis Services AMO-TOM) 中的错误 |Microsoft 文档
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tabular-models
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: b2483d4d6d443a21f43cf11e5271bb11041f1c53
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="handling-errors-in-the-tom-api-analysis-services-amo-tom"></a>处理 TOM API (Analysis Services AMO-TOM) 中的错误
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
托管库如 Analysis Services 管理对象 (AMO) 表格对象模型 (TOM) 的常见做法是使用作为向用户报告错误条件的机制的异常。  

在 AMO TOM 中检测到错误时，除了引发几个标准.NET 异常喜欢**ArgumentException**和**InvalidOperationException**，TOM 还可引发多个特定于 TOM 的异常。  

TOM 异常派生自[AmoException 类](http://msdn.microsoft.com/library/microsoft.analysisservices.amoexception.aspx)，涵盖这两种 AMO 和 TOM 特定异常。 

若要说明 TOM 中的异常处理，让我们查看的更常见的异常，这是一个[OperationException 类](http://msdn.microsoft.com/library/microsoft.analysisservices.operationexception.aspx)。

**OperationException**用户启动 Analysis Services 服务器上的操作，并且服务器无法执行操作，因为操作非法操作，或由于其他内部或外部错误时引发。 

当引发，* * OperationException * * 对象将包含 XMLA 返回的错误的服务器列表。 

请注意，服务器将不接受无效的更改。 如果发生这种情况，恢复**模型**回最后一个已知的良好状态使用树[UndoLocalChanges 方法](http://msdn.microsoft.com/library/microsoft.analysisservices.tabular.model.undolocalchanges.aspx)，请更正模型，然后重新提交。 

## <a name="code-example-handle-exceptions"></a>代码示例： 句柄异常 
 
```
 try 
 { 
  // Change the Model, for example create a table. 
  // … 
   model.saveChanges(); 
 } 
  catch(operationException ex) 
 { 
  foreach(XmlaError err in ex.Results.OfType<XmlaError>().cast<XmlaError>()) 
  { 
   Console.WriteLine(“Error returned from the server:” + err.Messsage ); 
  } 
 } 
```

## <a name="next-steps"></a>后续步骤

其他相关的异常如下所示：

- [TomInternalException 类](http://msdn.microsoft.com/library/microsoft.analysisservices.tabular.tominternalexception.aspx)
- [TomValidationException 类](http://msdn.microsoft.com/library/microsoft.analysisservices.tabular.tomvalidationexception.aspx)
- [JsonSerializationException 类](http://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_JsonSerializationException.htm)
