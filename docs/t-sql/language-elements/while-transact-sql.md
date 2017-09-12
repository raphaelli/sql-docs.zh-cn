---
title: "时 (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- WHILE_TSQL
- WHILE
dev_langs:
- TSQL
helpviewer_keywords:
- statements [SQL Server], repeated executions
- statement blocks [SQL Server]
- repeated statement executions
- nested WHILE loops
- WHILE keyword
ms.assetid: 52dd29ab-25d7-4fd3-a960-ac55c30c9ea9
caps.latest.revision: 40
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 404365faed0bc7aa3a6d585565099f964cc915ce
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="while-transact-sql"></a>WHILE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  设置重复执行 SQL 语句或语句块的条件。 只要指定的条件为真，就重复执行语句。 可以使用 BREAK 和 CONTINUE 关键字在循环内部控制 WHILE 循环中语句的执行。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
WHILE Boolean_expression   
     { sql_statement | statement_block | BREAK | CONTINUE }  
  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
WHILE Boolean_expression   
     { sql_statement | statement_block | BREAK }  
  
```  
  
## <a name="arguments"></a>参数  
 *Boolean_expression*  
 是[表达式](../../t-sql/language-elements/expressions-transact-sql.md)返回**TRUE**或**FALSE**。 如果布尔表达式中含有 SELECT 语句，则必须用括号将 SELECT 语句括起来。  
  
 {*sql_statement* | *statement_block*}  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] 语句或用语句块定义的语句分组。 若要定义语句块，请使用控制流关键字 BEGIN 和 END。  
  
 BREAK  
 导致从最内层的 WHILE 循环中退出。 执行标记的末尾循环中，在结束关键字后显示的任何语句。  
  
 CONTINUE  
 使 WHILE 循环重新开始执行，忽略 CONTINUE 关键字后面的任何语句。  
  
## <a name="remarks"></a>注释  
 如果嵌套了两个或多个 WHILE 循环，则内层的 BREAK 将退出到下一个外层循环。 将首先运行内层循环结束之后的所有语句，然后重新开始下一个外层循环。  
  
## <a name="examples"></a>示例  
  
### <a name="a-using-break-and-continue-with-nested-ifelse-and-while"></a>A. 在嵌套的 IF...ELSE 和 WHILE 中使用 BREAK 和 CONTINUE  
 在以下示例中，如果产品的平均标价小于 `$300`，则 `WHILE` 循环将价格乘 2，然后选择最高价格。 如果最高价格小于或等于 `$500`，则 `WHILE` 循环重新开始，并再次将价格乘 2。 该循环不断地将价格乘 2，直到最高价格超过 `$500`，然后退出 `WHILE` 循环，并输出一条消息。  
  
```  
USE AdventureWorks2012;  
GO  
WHILE (SELECT AVG(ListPrice) FROM Production.Product) < $300  
BEGIN  
   UPDATE Production.Product  
      SET ListPrice = ListPrice * 2  
   SELECT MAX(ListPrice) FROM Production.Product  
   IF (SELECT MAX(ListPrice) FROM Production.Product) > $500  
      BREAK  
   ELSE  
      CONTINUE  
END  
PRINT 'Too much for the market to bear';  
```  
  
### <a name="b-using-while-in-a-cursor"></a>B. 在游标中使用 WHILE  
 以下示例使用 `@@FETCH_STATUS` 来控制 `WHILE` 循环中的游标活动。  
  
```  
DECLARE Employee_Cursor CURSOR FOR  
SELECT EmployeeID, Title   
FROM AdventureWorks2012.HumanResources.Employee  
WHERE JobTitle = 'Marketing Specialist';  
OPEN Employee_Cursor;  
FETCH NEXT FROM Employee_Cursor;  
WHILE @@FETCH_STATUS = 0  
   BEGIN  
      FETCH NEXT FROM Employee_Cursor;  
   END;  
CLOSE Employee_Cursor;  
DEALLOCATE Employee_Cursor;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>示例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]和[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="c-simple-while-loop"></a>C: While 循环简单的  
 在以下示例中，如果产品的平均标价小于 `$300`，则 `WHILE` 循环将价格乘 2，然后选择最高价格。 如果最高价格小于或等于 `$500`，则 `WHILE` 循环重新开始，并再次将价格乘 2。 此循环继续将价格加倍直到最高价格大于`$500`，，然后退出`WHILE`循环。  
  
```  
-- Uses AdventureWorks  
  
WHILE ( SELECT AVG(ListPrice) FROM dbo.DimProduct) < $300  
BEGIN  
    UPDATE dbo.DimProduct  
        SET ListPrice = ListPrice * 2;  
    SELECT MAX ( ListPrice) FROM dbo.DimProduct  
    IF ( SELECT MAX (ListPrice) FROM dbo.DimProduct) > $500  
        BREAK;  
END  
  
```  
  
## <a name="see-also"></a>另请参阅  
 [ALTER TRIGGER (Transact-SQL)](../../t-sql/statements/alter-trigger-transact-sql.md)   
 [控制流语言 &#40;Transact SQL &#41;](~/t-sql/language-elements/control-of-flow.md)   
 [CREATE TRIGGER (Transact-SQL)](../../t-sql/statements/create-trigger-transact-sql.md)   
 [游标 (Transact-SQL)](../../t-sql/language-elements/cursors-transact-sql.md)   
 [SELECT (Transact-SQL)](../../t-sql/queries/select-transact-sql.md)  
  
  


