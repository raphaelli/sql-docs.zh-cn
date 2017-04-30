---
title: "OLE DB 连接管理器 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "OLE DB 连接管理器"
  - "数据源 [Integration Services], 连接"
  - "连接管理器 [Integration Services], OLE DB"
  - "连接 [Integration Services], OLE DB"
ms.assetid: 91e3622e-4b1a-439a-80c7-a00b90d66979
caps.latest.revision: 59
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 59
---
# OLE DB 连接管理器
  OLE DB 连接管理器使包能够用 OLE DB 访问接口连接到数据源。 例如，连接到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的 OLE DB 连接管理器可以使用 [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。    
    
> [!NOTE]    
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 OLEDB 提供程序不支持用于多子网故障转移群集的新连接字符串关键字 (MultiSubnetFailover=True)。 有关详细信息，请参阅 [SQL Server 发行说明](http://go.microsoft.com/fwlink/?LinkId=247824)以及 www.mattmasson.com 上博客文章 [AlwaysOn 多子网故障转移和 SSIS](http://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/)。    
    
> [!NOTE]    
>  如果数据源是 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office Excel 2007 或 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office Access 2007，则数据源需要不同于早期版本 Excel 或 Access 的数据访问接口。 有关详细信息，请参阅[连接到 Excel 工作簿](../../integration-services/connection-manager/connect-to-an-excel-workbook.md)和[连接到 Access 数据库](../../integration-services/connection-manager/connect-to-an-access-database.md)。    
    
 有若干 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 任务和数据流组件使用 OLE DB 连接管理器。 例如，OLE DB 源和 OLE DB 目标使用这种连接管理器来提取和加载数据，而执行 SQL 任务可以使用这种连接管理器来连接到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 数据库以运行查询。    
    
 OLE DB 连接管理器还用于在以使用 C++ 等语言的非托管代码编写的自定义任务中访问 OLE DB 数据源。    
    
 将 OLE DB 连接管理器添加到包时，[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 会创建将在运行时决定 OLE DB 连接的连接管理器，设置该连接管理器的属性，并将该连接管理器添加到包上的“连接”集合。    
    
 该连接管理器的 **ConnectionManagerType** 属性设置为 **OLEDB**。    
    
 可以按下列方式配置 OLE DB 连接管理器：    
    
-   提供配置为满足选定访问接口要求的特定连接字符串。    
    
-   包括要连接到的数据源的名称（取决于访问接口）。    
    
-   为选定的访问接口提供相应的安全凭据。    
    
-   指示是否在运行时保留从连接管理器中创建的连接。    
    
## 日志记录    
 可以记录 OLE DB 连接管理器对外部数据访问接口所做的调用。 使用此日志记录功能，可以对 OLE DB 连接管理器与外部数据源的连接进行故障排除。 若要记录 OLE DB 连接管理器对外部数据访问接口所做的调用，请在包级别启用包日志记录并选择 **“诊断”** 事件。 有关详细信息，请参阅[包执行的疑难解答工具](../../integration-services/troubleshooting/troubleshooting-tools-for-package-execution.md)。    
    
## OLEDB 连接管理器的配置    
 可以通过 [!INCLUDE[ssIS](../../includes/ssis-md.md)] 设计器或以编程方式来设置属性。 有关可以在 [!INCLUDE[ssIS](../../includes/ssis-md.md)]设计器中设置的属性的详细信息，请参阅[配置 OLE DB 连接管理器](../../integration-services/connection-manager/configure-ole-db-connection-manager.md)。 有关以编程方式配置连接管理器的信息，请参阅开发人员指南中针对 **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** 类的文档。    
    
## 相关内容    
    
-   social.technet.microsoft.com 上的 Wiki 文章 [SSIS 与 Oracle 连接器](http://go.microsoft.com/fwlink/?LinkId=220670) 。    
    
-   carlprothman.net 上的技术文章 [Connection Strings for OLE DB Providers](http://go.microsoft.com/fwlink/?LinkId=220744)（OLE DB 访问接口的连接字符串）。    
    
## 另请参阅    
 [OLE DB 源](../../integration-services/data-flow/ole-db-source.md)     
 [OLE DB 目标](../../integration-services/data-flow/ole-db-destination.md)     
 [执行 SQL 任务](../../integration-services/control-flow/execute-sql-task.md)     
 [Integration Services (SSIS) 连接](../../integration-services/connection-manager/integration-services-ssis-connections.md)    
    
  