---
title: "OBJECT_NAME (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- OBJECT_NAME
- OBJECT_NAME_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- OBJECT_NAME function
- viewing database object names
- objects [SQL Server], names
- database objects [SQL Server], names
- displaying database object names
- database objects [SQL Server]
- names [SQL Server], database objects
ms.assetid: 7d5b923f-0c3e-4af9-b39b-132807a6d5b3
caps.latest.revision: 45
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 9960fb31a6f2805424797da5b25db2d391523b2e
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="objectname-transact-sql"></a>OBJECT_NAME (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  返回架构范围内对象的数据库对象名称。 架构范围的对象的列表，请参阅[sys.objects &#40;Transact SQL &#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
OBJECT_NAME ( object_id [, database_id ] )  
```  
  
## <a name="arguments"></a>参数  
 *object_id*  
 要使用的对象的 ID。 *object_id*是**int** ，假定在指定的数据库中，或在当前数据库上下文中为架构范围的对象。  
  
 *database_id*  
 要在其中查找对象的数据库的 ID。 *database_id*是**int**。  
  
## <a name="return-types"></a>返回类型  
 **sysname**  
  
## <a name="exceptions"></a>异常  
 出现错误时或调用方没有查看对象的权限时，将返回 NULL。 如果目标数据库的 AUTO_CLOSE 选项设置为 ON，则此函数将打开此数据库。  
  
 用户只能查看符合如下条件的安全对象的元数据：该安全对象为该用户所有，或已授予该用户对该安全对象的权限。 也就是说，如果用户对该对象没有任何权限，则那些会生成元数据的内置函数（如 OBJECT_NAME）可能返回 NULL。 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
## <a name="permissions"></a>Permissions  
 需要对对象拥有 ANY 权限。 若要指定数据库 ID，还需要对数据库拥有 CONNECT 权限，或者必须启用 guest 帐户。  
  
## <a name="remarks"></a>注释  
 在选择列表中，在 WHERE 子句中，可以使用系统函数和允许的表达式的任意位置。 有关详细信息，请参阅[表达式](../../t-sql/language-elements/expressions-transact-sql.md)和[其中](../../t-sql/queries/where-transact-sql.md)。  
  
 由此系统函数返回的值使用当前数据库的排序规则。  
  
 默认情况下，[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]假定*object_id*位于当前数据库上下文中。 引用的查询*object_id*另一个数据库中返回 NULL 或错误的结果。 例如，以下查询中当前数据库上下文是 [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)]。 [!INCLUDE[ssDE](../../includes/ssde-md.md)]将尝试返回在该数据库（而非查询的 FROM 子句中指定的数据库）中指定的对象 ID 的对象名称。 因此，会返回不正确的信息。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT DISTINCT OBJECT_NAME(object_id)  
FROM master.sys.objects;  
GO  
```  
  
 您可以通过指定数据库 ID 在其他数据库的上下文中解析对象名。 以下示例在 `master` 函数中指定 `OBJECT_SCHEMA_NAME` 数据库的数据库 ID，并返回正确的结果。  
  
```  
USE AdventureWorks2012;  
GO  
SELECT DISTINCT OBJECT_SCHEMA_NAME(object_id, 1) AS schema_name  
FROM master.sys.objects;  
GO  
```  
  
## <a name="examples"></a>示例  
  
### <a name="a-using-objectname-in-a-where-clause"></a>A. 在 WHERE 子句中使用 OBJECT_NAME  
 以下示例将返回来自对象的 `sys.objects` 目录视图的列，该对象是通过 `OBJECT_NAME` 在 `WHERE` 语句的 `SELECT` 子句中指定的。  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @MyID int;  
SET @MyID = (SELECT OBJECT_ID('AdventureWorks2012.Production.Product',  
    'U'));  
SELECT name, object_id, type_desc  
FROM sys.objects  
WHERE name = OBJECT_NAME(@MyID);  
GO  
```  
  
### <a name="b-returning-the-object-schema-name-and-object-name"></a>B. 返回对象架构名称和对象名称  
 以下示例返回所有缓存查询计划（为非临时语句或预定义语句）的对象架构名称、对象名称和 SQL 文本。  
  
```  
SELECT DB_NAME(st.dbid) AS database_name,   
    OBJECT_SCHEMA_NAME(st.objectid, st.dbid) AS schema_name,  
    OBJECT_NAME(st.objectid, st.dbid) AS object_name,   
    st.text AS query_text  
FROM sys.dm_exec_query_stats AS qs  
CROSS APPLY sys.dm_exec_sql_text(qs.sql_handle) AS st  
WHERE st.objectid IS NOT NULL;  
GO  
```  
  
### <a name="c-returning-three-part-object-names"></a>C. 返回由三部分组成的对象名称  
 以下示例返回所有数据库中所有对象的数据库名称、架构名称和对象名称，同时返回 `sys.dm_db_index_operational_stats` 动态管理视图中的其他所有列。  
  
```  
SELECT QUOTENAME(DB_NAME(database_id))   
    + N'.'   
    + QUOTENAME(OBJECT_SCHEMA_NAME(object_id, database_id))   
    + N'.'   
    + QUOTENAME(OBJECT_NAME(object_id, database_id))  
    , *   
FROM sys.dm_db_index_operational_stats(null, null, null, null);  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>示例：[!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)]和[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="d-using-objectname-in-a-where-clause"></a>D. 在 WHERE 子句中使用 OBJECT_NAME  
 以下示例将返回来自对象的 `sys.objects` 目录视图的列，该对象是通过 `OBJECT_NAME` 在 `WHERE` 语句的 `SELECT` 子句中指定的。 （你对象编号 (在下面的示例 274100017) 将不同。  若要测试此示例中，查找有效的对象数通过执行`SELECT name, object_id FROM sys.objects;`数据库中。)  
  
```  
SELECT name, object_id, type_desc  
FROM sys.objects  
WHERE name = OBJECT_NAME(274100017);  
```  
  
## <a name="see-also"></a>另请参阅  
 [元数据函数 &#40;Transact SQL &#41;](../../t-sql/functions/metadata-functions-transact-sql.md)   
 [OBJECT_DEFINITION (Transact-SQL)](../../t-sql/functions/object-definition-transact-sql.md)   
 [OBJECT_ID (Transact-SQL)](../../t-sql/functions/object-id-transact-sql.md)  
  
  

