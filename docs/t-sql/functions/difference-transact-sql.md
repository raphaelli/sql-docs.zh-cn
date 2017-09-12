---
title: "差异 (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DIFFERENCE
- DIFFERENCE_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- DIFFERENCE function
- comparing SOUNDEX values
- SOUNDEX values
ms.assetid: c58ca25d-d6ea-48fa-93bb-c9374b0b2a2b
caps.latest.revision: 27
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 3ea034f7217d031c21cf22f6b5aaff9bf16355a9
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="difference-transact-sql"></a>DIFFERENCE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  返回一个整数值，指示两个字符表达式的 SOUNDEX 值之间的差异。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
DIFFERENCE ( character_expression , character_expression )  
```  
  
## <a name="arguments"></a>参数  
 *character_expression*  
 是一个字母数字[表达式](../../t-sql/language-elements/expressions-transact-sql.md)的字符数据。 *character_expression*可以是常量、 变量或列。  
  
## <a name="return-types"></a>返回类型  
 **int**  
  
## <a name="remarks"></a>注释  
 返回的整数是 SOUNDEX 值中相同字符的个数。 返回的值从 0 到 4 不等：0 表示几乎不同或完全不同，4 表示几乎相同或完全相同。  
  
 DIFFERENCE 和 SOUNDEX 区分排序规则。  
  
## <a name="examples"></a>示例  
 在以下示例的第一部分，对两个非常相似的字符串的 `SOUNDEX` 值进行了比较。 对于 Latin1_General 排序规则`DIFFERENCE`返回的值`4`。 下面的示例中，第二部分`SOUNDEX`值进行比较两个非常不同的字符串，以及用于 Latin1_General 排序规则`DIFFERENCE`返回的值`0`。  
  
```  
-- Returns a DIFFERENCE value of 4, the least possible difference.  
SELECT SOUNDEX('Green'), SOUNDEX('Greene'), DIFFERENCE('Green','Greene');  
GO  
-- Returns a DIFFERENCE value of 0, the highest possible difference.  
SELECT SOUNDEX('Blotchet-Halls'), SOUNDEX('Greene'), DIFFERENCE('Blotchet-Halls', 'Greene');  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
----- ----- -----------   
G650  G650  4             
  
(1 row(s) affected)  
  
----- ----- -----------   
B432  G650  0             
  
(1 row(s) affected)  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>示例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]和[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 在以下示例的第一部分，对两个非常相似的字符串的 `SOUNDEX` 值进行了比较。 对于 Latin1_General 排序规则`DIFFERENCE`返回的值`4`。 下面的示例中，第二部分`SOUNDEX`值进行比较两个非常不同的字符串，以及用于 Latin1_General 排序规则`DIFFERENCE`返回的值`0`。  
  
```  
-- Returns a DIFFERENCE value of 4, the least possible difference.  
SELECT SOUNDEX('Green'), SOUNDEX('Greene'), DIFFERENCE('Green','Greene');  
GO  
-- Returns a DIFFERENCE value of 0, the highest possible difference.  
SELECT SOUNDEX('Blotchet-Halls'), SOUNDEX('Greene'), DIFFERENCE('Blotchet-Halls', 'Greene');  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
----- ----- -----------   
G650  G650  4             
  
(1 row(s) affected)  
  
----- ----- -----------   
B432  G650  0             
  
(1 row(s) affected)  
```  
  
## <a name="see-also"></a>另请参阅  
 [SOUNDEX &#40;Transact SQL &#41;](../../t-sql/functions/soundex-transact-sql.md)   
 [字符串函数 &#40;Transact SQL &#41;](../../t-sql/functions/string-functions-transact-sql.md)  
  
  

