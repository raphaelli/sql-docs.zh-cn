---
title: 使用参数元数据 |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: db2c1957-91c6-4989-a07b-9f8be6d2033a
caps.latest.revision: 17
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c2ff7d2646c0a3838b8a0dc72249b73e64227dd7
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="using-parameter-metadata"></a>使用参数元数据
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  查询[SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)或[SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)它们包含的参数对象[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]实现[SQLServerParameterMetaData](../../connect/jdbc/reference/sqlserverparametermetadata-class.md)类。 该类包含很多以单个值的格式返回信息的字段和方法。  
  
 若要创建 SQLServerParameterMetaData 对象，可以使用[getParameterMetaData](../../connect/jdbc/reference/getparametermetadata-method-sqlserverpreparedstatement.md) SQLServerPreparedStatement 和 SQLServerCallableStatement 类的方法。  
  
 在下面的示例中，与的开放连接[!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal_md.md)]示例数据库中传递给函数，SQLServerCallableStatement 类的 getParameterMetaData 方法用于返回 SQLServerParameterMetaData 对象，然后各种SQLServerParameterMetaData 对象的方法用于显示有关类型和 HumanResources.uspUpdateEmployeeHireInfo 存储过程中包含的参数的模式的信息。  
  
 [!code[JDBC#UsingParamMetaData1](../../connect/jdbc/codesnippet/Java/using-parameter-metadata_1.java)]  
    
> [!NOTE]  
已准备的语句中使用 SQLServerParameterMetaData 类时，有一些限制。 
**与 Microsoft JDBC Driver 6.0 （或更高版本） for SQL Server**： 在使用 SQL Server 2008 或 2008 R2，JDBC 驱动程序支持选择、 DELETE、 INSERT 和 UPDATE 语句，只要这些语句不包含子查询和/或联接。  

合并也不支持查询 SQLServerParameterMetaData 类时使用的 SQL Server 2008 或 2008 R2。 对于 SQL Server 2012 和较高版本，支持带有复杂查询的参数元数据。  

不支持的加密列的参数元数据的检索。 **与 Microsoft JDBC Driver 4.1 或 SQL Server 的 4.2**: JDBC 驱动程序还支持选择、 DELETE、 INSERT 和 UPDATE 语句，只要这些语句不包含子查询和/或联接。 此外 SQLServerParameterMetaData 类不支持合并查询。  
  
  
