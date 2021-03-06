---
title: 连接到 SQL Server (MySQLToSQL) |Microsoft 文档
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssma-mysql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: d73abd3a-80df-4293-b973-1723069db049
caps.latest.revision: 3
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: f8baef39a5687fc7c1231252139aba2a41d45267
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="connect-to-sql-server-mysqltosql"></a>连接到 SQL Server (MySQLToSQL)
使用**连接到 SQL Server**对话框中，连接到的实例[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]你想要迁移到。 访问**连接到 SQL Server**对话框中，在**文件**菜单上，单击**连接到 SQL Server**。  
  
## <a name="options"></a>选项  
**服务器名称**  
输入或选择要连接到的 SQL Server 实例。 默认情况下，显示最近连接到的实例。  
  
-   如果你要连接到本地计算机上的默认实例，可以输入**localhost**或句点 (**。**)。  
  
-   如果你要连接到另一台计算机上的默认实例，输入的计算机的名称。  
  
-   如果你要连接到另一台计算机上的命名实例，输入计算机名称、 反斜杠和实例名称，例如*MyServer*\\*MyInstance*。  
  
**服务器端口**  
如果你的实例[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]未配置为接受默认值上的连接端口 (1433)，输入端口号。 否则，将此值留空。  
  
**数据库**  
指定要迁移对象和数据迁移到的数据库。 此选项不可用，当重新连接到[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。  
  
**身份验证**  
选择用于连接到的身份验证方法[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。 若要使用您当前的 Windows 帐户，选择 Windows 身份验证。 若要指定[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]登录名和密码，选择[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]身份验证。  
  
**用户名**  
如果你使用[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]身份验证，该实例的输入的登录名[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。 如果使用 Windows 身份验证，则此选项不可用。  
  
**密码**  
如果你使用[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]身份验证，在该实例上输入该登录名的密码[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]。 如果使用 Windows 身份验证，则此选项不可用。  
  
**加密连接**  
如果你想要安全地连接到 SQL Server，请通过检查使用的加密连接**加密连接**复选框。  
  
**信任服务器证书**  
如果你想要使用此选项，选择**信任服务器证书**复选框。  
  
> [!NOTE]  
> 若要启用**信任服务器证书**，必须将"加密"设置为**True**。  
  
