---
title: "executeUpdate 方法 (SQLServerStatement) |Microsoft 文档"
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
- SQLServerStatement.executeUpdate
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 10ae662a-ce3c-4b24-875c-5c2df319d93b
caps.latest.revision: 16
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 09479ee3af274d06564427c4ca60f3cc15f36644
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="executeupdate-method-sqlserverstatement"></a>executeUpdate 方法 (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  运行给定的 SQL 语句，可以是 INSERT、UPDATE 或 DELETE 语句；或不返回任何内容的 SQL 语句，例如 SQL DDL 语句。 从[!INCLUDE[msCoName](../../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] JDBC Driver 3.0 executeUpdate 将返回正确的在合并操作中更新的行数。  
  
## <a name="overload-list"></a>重载列表  
  
|Name|Description|  
|----------|-----------------|  
|[executeUpdate (java.lang.String)](../../../connect/jdbc/reference/executeupdate-method-java-lang-string-sqlserverstatement.md)|运行给定的 SQL 语句，可以是 INSERT、UPDATE、DELETE 或 MERGE 语句；或不返回任何内容的 SQL 语句，例如 SQL DDL 语句。|  
|[executeUpdate （java.lang.String，int）](../../../connect/jdbc/reference/executeupdate-method-java-lang-string-int.md)|运行给定的 SQL 语句和信号[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]给定标志是否自动生成的键生成由此[SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)对象应变为可供检索。|  
|[executeUpdate （java.lang.String、 int 和 #91; 和 #93;）](../../../connect/jdbc/reference/executeupdate-method-java-lang-string.md)|运行给定的 SQL 语句，并向 JDBC 驱动程序发出信号，指示给定数组中指示的自动生成的键应对检索可用。|  
|[executeUpdate （java.lang.String、 java.lang.String 和 #91; 和 #93;）](../../../connect/jdbc/reference/executeupdate-method-java-lang-string-java-lang-string.md)|运行给定的 SQL 语句，并向 JDBC 驱动程序发出信号，指示给定数组中指示的自动生成的键应对检索可用。|  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerStatement 成员](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 类](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  