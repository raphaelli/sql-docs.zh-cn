---
title: getApplicationName 方法 (SQLServerDataSource) |Microsoft 文档
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
- SQLServerDataSource.getApplicationName
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: f71e501c-ccd7-4a1e-b6ea-4d47a81c18c6
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0239d7d251b4104000646a8f98a3cae0be656853
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="getapplicationname-method-sqlserverdatasource"></a>getApplicationName 方法 (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  返回应用程序名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
public java.lang.String getApplicationName()  
```  
  
## <a name="return-value"></a>返回值  
 A**字符串**包含应用程序的名称，或"[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]"如果未不设置任何值。  
  
## <a name="remarks"></a>注释  
 应用程序名称用于标识特定的应用程序在各种[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]事件探查和日志记录工具。 如果未设置的应用程序名称，则 getApplicationName 方法返回的非本地化的字符串"[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]"。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerDataSource 成员](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [SQLServerDataSource 类](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
