---
title: "getDate 方法 （int、 java.util.Calendar） (SQLServerResultSet) |Microsoft 文档"
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
- SQLServerResultSet.getDate (int, java.util.Calendar)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 150411f7-2a73-4380-b921-9698acd5d1f9
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 5fbf5aec492a9fe711e7b6caaf5959b2d1a7bc81
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="getdate-method-int-javautilcalendar-sqlserverresultset"></a>getDate 方法 （int、 java.util.Calendar） (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索此当前行中指定的列索引的值[SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)作为 Java 编程语言，使用给定的日历对象中的 java.sql.Date 对象的对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
public java.sql.Date getDate(int columnIndex,  
                             java.util.Calendar cal)  
```  
  
#### <a name="parameters"></a>Parameters  
 *列索引*  
  
 **Int** ，该值指示的列索引。  
  
 *cal*  
  
 日历对象中。  
  
## <a name="return-value"></a>返回值  
 Date 对象。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 GetDate 方法 java.sql.ResultSet 界面中指定此 getDate 方法。  
  
 此方法返回的有效日期部分的[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]datetime 或 smalldatetime 数据类型，其设置为 00:00 （午夜） 提供的日历的时区中的 Java 时间基线的时间部分。  
  
## <a name="see-also"></a>另请参阅  
 [getDate 方法 &#40;SQLServerResultSet &#41;](../../../connect/jdbc/reference/getdate-method-sqlserverresultset.md)   
 [SQLServerResultSet 成员](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 类](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  