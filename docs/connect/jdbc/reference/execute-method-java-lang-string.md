---
title: "执行方法 (java.lang.String) |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerPreparedStatement.execute (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: a871917e-d286-46c3-96cf-2e8e8b22111c
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 219d4ff6ff793b244e30ca43582f4d194e7e6a5d
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="execute-method-javalangstring"></a>execute 方法 (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  运行可返回多个结果的给定的 SQL 语句。  
  
## <a name="syntax"></a>语法  
  
```  
  
public final boolean execute(java.lang.String sql)  
```  
  
#### <a name="parameters"></a>Parameters  
 *sql*  
  
 A**字符串**包含 SQL 语句。  
  
## <a name="return-value"></a>返回值  
 **true**如果语句返回的结果集。 **false**如果它返回更新计数或任何结果。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.Statement 接口中的 execute 方法指定此 execute 方法。  
  
 此方法将替代[执行](../../../connect/jdbc/reference/execute-method-sqlserverstatement.md)中找到的方法[SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)类。  
  
 由于在创建对象时指定 SQLServerPreparedStatement 对象的 SQL 语句，则将调用此方法将导致异常。  
  
## <a name="see-also"></a>另请参阅  
 [执行方法 &#40;SQLServerPreparedStatement &#41;](../../../connect/jdbc/reference/execute-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement 成员](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)   
 [SQLServerPreparedStatement 类](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)  
  
  