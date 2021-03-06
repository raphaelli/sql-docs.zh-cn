---
title: 使用数据类型 (JDBC) |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: b39f44d0-3710-4bc6-880c-35bd8c10a734
caps.latest.revision: 18
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 73be4e0bc7a20a8a592493badf95a123ad6ade84
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="working-with-data-types-jdbc"></a>使用数据类型 (JDBC)
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  主要功能的[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]是允许 Java 开发人员能够访问数据中包含[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]数据库。 若要实现此目的，JDBC 驱动程序调解之间的转换[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]数据类型和 Java 语言类型和对象。  
  
> [!NOTE]  
>  有关详细的讨论[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]和 JDBC 驱动程序数据类型，包括它们之间的差异和如何将它们转换为 Java 语言数据类型，请参阅[了解 JDBC 驱动程序数据类型](../../connect/jdbc/understanding-the-jdbc-driver-data-types.md)。  
  
 若要使用 SQL Server 数据类型，JDBC 驱动程序提供 get\<类型 > 并将设置\<类型 > 方法[SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)和[SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md)类，并提供 get\<类型 > 和更新\<类型 > 方法[SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md)类。 要使用哪个方法取决于所使用的数据类型以及是否要使用结果集和查询。  
  
 本部分中的主题介绍如何使用 JDBC 驱动程序数据类型来访问[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]Java 应用程序中的数据。  
  
## <a name="in-this-section"></a>本節內容  
  
|主题|Description|  
|-----------|-----------------|  
|[基本数据类型示例](../../connect/jdbc/basic-data-types-sample.md)|描述如何使用结果集 getter 方法来检索基本[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]数据类型值，以及如何使用结果集更新方法以更新这些值。|  
|[SQLXML 数据类型示例](../../connect/jdbc/sqlxml-data-type-sample.md)|描述如何将 XML 数据存储在关系数据库、 如何从数据库中，检索 XML 数据以及如何分析 XML 数据与**SQLXML** Java 数据类型。|  
  
## <a name="see-also"></a>另请参阅  
 [示例 JDBC 驱动程序应用程序](../../connect/jdbc/sample-jdbc-driver-applications.md)  
  
  
