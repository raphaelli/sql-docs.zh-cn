---
title: "HEX（SSIS 表达式） | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "十六进制数据"
  - "HEX 函数"
ms.assetid: f5d471ee-aeef-421c-b6e1-55b9676c3842
caps.latest.revision: 36
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 36
---
# HEX（SSIS 表达式）
  返回一个表示整数的十六进制值的字符串。  
  
## 语法  
  
```  
  
HEX(integer_expression)  
```  
  
## 参数  
 *integer_expression*  
 有符号或无符号整数。  
  
## 结果类型  
 DT_WSTR  
  
## 注释  
 如果 integer_expression 为 Null，则 HEX 返回 Null。  
  
 integer_expression 参数的计算结果必须为整数。 有关详细信息，请参阅 [Integration Services Data Types](../../integration-services/data-flow/integration-services-data-types.md)。  
  
 返回结果不包含限定符，如 0x 前缀。 若要包含前缀，请使用 +（连接）运算符。 有关详细信息，请参阅 [+（连接）（SSIS 表达式）](../../integration-services/expressions/concatenate-ssis-expression.md)。  
  
 HEX 计数法中的字符 A – F 显示为大写字符。  
  
 产生的整数数据类型的字符串的长度如下所示：  
  
-   DT_I1 和 DT_UI1 返回最大长度为 2 的字符串。  
  
-   DT_I2 和 DT_UI2 返回最大长度为 4 的字符串。  
  
-   DT_I4 和 DT_UI4 返回最大长度为 8 的字符串。  
  
-   DT_I8 和 DT_UI8 返回最大长度为 16 的字符串。  
  
## 表达式示例  
 以下示例使用了一个数值。 该函数将返回值 190。  
  
```  
HEX(400)   
```  
  
 以下示例使用了 **ReorderPoint** 列。 列数据类型为 **smallint**。 如果 **ReorderPoint** 为 750，则函数返回 2EE。  
  
```  
HEX(ReorderPoint)   
```  
  
 以下示例使用了系统变量 **LocaleID**。 如果 **LocaleID** 为 1033，则函数返回 409。  
  
```  
HEX(@LocaleID)  
```  
  
## 另请参阅  
 [函数（SSIS 表达式）](../../integration-services/expressions/functions-ssis-expression.md)  
  
  