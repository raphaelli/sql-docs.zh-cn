---
title: isFirst 方法 (SQLServerResultSet) |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerResultSet.isFirst
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 2ff94b95-32ad-4378-8bb1-970030527bb2
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 2c2cabb7a4fbc20d284d93a018a6d88e1486e885
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="isfirst-method-sqlserverresultset"></a>isFirst 方法 (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索光标所在的第一行是否[SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
public boolean isFirst()  
```  
  
## <a name="return-value"></a>返回值  
 **true**如果光标位于第一行。 **false**如果光标位于任何其他位置或结果集不包含任何行。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.ResultSet 接口中的 isFirst 方法指定此 isFirst 方法。  
  
 如果将此方法用于前进游标和动态游标，则将引发异常。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerResultSet 成员](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 类](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
