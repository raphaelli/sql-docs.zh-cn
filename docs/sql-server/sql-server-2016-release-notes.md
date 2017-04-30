---
title: "SQL Server 2016 发行说明 | Microsoft Docs"
ms.date: 11/28/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- server-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- build notes
- release issues
ms.assetid: c64077a2-bec8-4c87-9def-3dbfb1ea1fb6
caps.latest.revision: 276
author: craigg-msft
ms.author: craigg
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 0447dd94774287a71028252723508ebc5e2e50f8
ms.lasthandoff: 04/11/2017

---
# <a name="sql-server-2016-release-notes"></a>SQL Server 2016 发行说明
  本主题介绍 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] 的限制和问题。    
    
 **进行试用：**    
   
[![从评估中心下载](../analysis-services/media/download.png)](https://www.microsoft.com/en-us/evalcenter/evaluate-sql-server-2016)从**[评估中心](https://www.microsoft.com/en-us/evalcenter/evaluate-sql-server-2016)下载 SQL Server 2016**    
    
[![Azure 虚拟机小](../analysis-services/media/azure-virtual-machine-small.png)](https://azure.microsoft.com/en-us/marketplace/partners/microsoft/sqlserver2016sp1standardwindowsserver2016/) 是否拥有 Azure 帐户？  然后转到 **[此处](https://azure.microsoft.com/en-us/marketplace/partners/microsoft/sqlserver2016sp1standardwindowsserver2016/)** ，启动装有 SQL Server 2016 SP1 的虚拟机。
    
[![Download SSMS](../analysis-services/media/download.png)](https://msdn.microsoft.com/library/mt238290.aspx) **SSMS:** To get the latest version of SQL Server Management Studio, see **[Download SQL Server Management Studio (SSMS)](https://msdn.microsoft.com/library/mt238290.aspx)**.   
    
 有关新增功能的信息，请参阅 [《What's New in SQL Server 2016》](http://msdn.microsoft.com/library/8223c19b-4b0d-4b1d-a042-9a726c18e708)（SQL Server 2016 的新增功能）。
    
##  <a name="bkmk_top"></a> Sections In this topic:    

-   [SQL Server 2016 Service Pack 1 (SP1) 可用](#bkmk_2016sp1)    
-   [SQL Server 2016 正式发布版 (GA)](#bkmk_2016_ga) 
-   [SQL Server 2016 候选发布版 3 (RC3)](#bkmk_2016_rc3)     

## <a name="bkmk_2016sp1"></a>SQL Server 2016 Service Pack 1 (SP1) 可用
![info_tip](../sql-server/media/info-tip.png) SQL Server 2016 SP1 会将 SQL Server 2016 所有版本和服务级别升级到 SQL Server 2016 SP1。 除了本文中列出的修补程序，SQL Server 2016 SP1 还包括 SQL Server 2016 累积更新 1 (CU1) 到 SQL Server 2016 CU3 中的修补程序。
    
- [SQL Server 2016 SP1 下载页](https://www.microsoft.com/en-us/download/details.aspx?id=54276)
- [SQL Server 2016 Service Pack 1 release information](https://support.microsoft.com/en-us/kb/3182545) （SQL Server 2016 Service Pack 1 发布信息） 列出了 SP1 中修复或更改的单个 bug #s 和问题。
 - ![info_tip](../sql-server/media/info-tip.png) 有关所有受支持版本的链接和信息（包括 [的 Service Pack），请参阅](https://msdn.microsoft.com/library/ff803383.aspx) SQL Server 更新中心 [!INCLUDE[ssNoVersion_md](../includes/ssnoversion-md.md)] 
    
    
##  <a name="bkmk_2016_ga"></a> SQL Server 2016 Release - General Availability (GA)
-   [数据库引擎 (GA)](#bkmk_ga_instalpatch) 

-   [Stretch Database (GA)](#bkmk_ga_stretch)

-   [查询存储 (GA)](#bkmk_ga_query_store)

-   [产品文档 (GA)](#bkmk_ga_docs)
 
### ![repl_icon_warn](../database-engine/availability-groups/windows/media/repl-icon-warn.gif) <a name="bkmk_ga_instalpatch"></a> Install Patch Requirement (GA) 
**问题及对用户的影响：** Microsoft 已发现影响 Microsoft VC++ 2013 运行时二进制文件的一个问题，这些二进制文件是作为 SQL Server 2016 系统必备进行安装的。 现在有可用的更新来修复该问题。 如果未安装适用于该 VC 运行时二进制文件的更新，则在某些情况下 SQL Server 2016 可能会遇到稳定性问题。 在安装 SQL Server 2016 之前，请检查计算机是否需要 [KB 3164398](http://support.microsoft.com/kb/3164398)中所述的修补程序。 此修补程序也包含在 [SQL Server 2016 RTM 的累积更新包 1 (CU1)](https://www.microsoft.com/en-us/download/details.aspx?id=53338)中。 

**解决方法：** 请执行下列操作之一：

- 安装 [KB 3138367 - Visual C++ 2013 和 Visual C++ 可再发行包的更新](http://support.microsoft.com/kb/3138367)。 这是首选的解决方法。 可以在安装 SQL Server 2016 之前或之后安装此更新。 

    如果已安装 SQL Server 2016，请按顺序执行以下步骤：

    1.  下载合适的 *vcredist_\*exe*。
    1.  停止数据库引擎的所有实例的 SQL Server 服务。
    1.  安装 **KB 3138367**。
    1.  重新启动计算机。
 

 - 安装  [KB 3164398 - 适用于 SQL Server 2016 MSVCRT 系统必备的关键更新](http://support.microsoft.com/kb/3164398)。  
 
    如果使用 **KB 3164398**，可以在 SQL Server 安装过程中、通过 Microsoft 更新或从 Microsoft 下载中心进行安装。 

    - **在 SQL Server 2016 安装过程中：** 如果运行 SQL Server 安装程序的计算机具有 Internet 访问权限，那么 SQL Server 安装程序将检查该更新，并将其作为整个 SQL Server 安装的一部分。 如果接受更新，安装程序将下载并在安装过程中更新二进制文件。

    - **Microsoft 更新：** 该更新作为 SQL Server 2016 的重要的非安全更新，可从 Microsoft 更新获取。 在安装 SQL Server 2016 后通过 Microsoft 更新安装，更新后需要重新启动服务器。 

    - **下载中心：** 最后，可从 Microsoft 下载中心获取该更新。 可以在安装 SQL Server 2016 之后下载更新软件并安装在服务器上。 


### <a name="bkmk_ga_stretch"></a>Stretch Database

#### <a name="problem-with-a-specific-character-in-a-database-or-table-name"></a>与数据库或表名称中的特定字符有关的问题

**问题和对用户的影响：** 在将对象名称从小写转换为大写时，如果名称中有一个字符被视为不一样的字符，那么尝试对数据库或表启用 Stretch Database 将失败并显示错误。 导致此问题的字符的一个示例是字符“ƒ”（通过键入 ALT + 159 得到）。

**解决方法：** 如果想要对数据库或表启用 Stretch Database，唯一的方法是重命名对象并删除问题字符。

#### <a name="problem-with-an-index-that-uses-the-include-keyword"></a>与使用 INCLUDE 关键字的索引有关的问题

**问题和对用户的影响：** 如果表的一个索引使用 INCLUDE 关键字以包含索引中的其他列，那么尝试对该表启用 Stretch Database 将失败并显示错误。

**解决方法：** 删除使用 INCLUDE 关键字的索引，对表启用 Stretch Database，然后重新创建索引。 如果这样做，请务必遵从组织的维护实践和策略，以确保对受影响的表的用户的影响最小或没有影响。

### <a name="bkmk_ga_query_store"></a>Query Store

#### <a name="problem-with-automatic-data-cleanup-on-editions-other-than-enterprise-and-developer"></a>与版本的自动数据清理有关的问题（不包括企业版和开发人员版）

 **问题和对用户的影响：** 对版本的自动数据清理失败（不包括企业版和开发人员版）。 因此，如果不手动清除数据，查询存储使用的空间将不断增长直至达到配置的限制。 如果该问题未得到修复，那么还将填满为错误日志分配的磁盘空间，因为每次尝试执行清理都将生成一个转储文件。 清理激活期限取决于工作负荷频率，但不会超过 15 分钟。

 **解决方法：** 如果计划对企业版和开发人员版以外的版本使用查询存储，则需要显式关闭清理策略。 可通过 SQL Server Management Studio（数据库属性页）或 Transact-SQL 脚本来完成该操作：

```ALTER DATABASE <database name> SET QUERY_STORE (OPERATION_MODE = READ_WRITE, CLEANUP_POLICY = (STALE_QUERY_THRESHOLD_DAYS = 0), SIZE_BASED_CLEANUP_MODE = OFF)```

此外，可以考虑手动清除以防止查询存储转变为只读模式。 例如，运行以下查询以定期清除整个数据空间：

```ALTER DATABASE <database name> SET QUERY_STORE CLEAR```

此外，定期执行下面的查询存储的存储过程，以清理运行时统计信息、特定查询或计划：

-    ```sp_query_store_reset_exec_stats```

-    ```sp_query_store_remove_plan```

-    ```sp_query_store_remove_query```


###  <a name="bkmk_ga_docs"></a> 产品文档 (GA) 
 **问题及其对客户的影响：** 尚未提供可下载的 SQL Server 2016 文档版本。 当你尝试使用帮助库管理器 **联机安装内容**时，你将看到 SQL Server 2012 和 SQL Sever 2014 文档，但没有 SQL Server 2016 文档的选项。    
    
 **解决方法：** 使用以下方法之一：    
    
 ![管理 SQL Server 的帮助设置](../sql-server/media/docs-sql2016-managehelpsettings.png "管理 SQL Server 的帮助设置")    
    
-   使用选项“选择联机或本地帮助”，然后配置“我想要使用联机帮助”对应的帮助选项。     
    
-   使用选项“联机安装内容”并下载 SQL Server 2014 Content。     
    
 **F1 帮助：** 按照设计，在 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]中按 F1 时，将在浏览器中显示 F1 帮助主题的联机版本。 即使已安装本地帮助也是如此。    
     
**更新内容：**    
在 SQL Server Management Studio 和 Visual Studio 中，在添加文档的过程中帮助查看器应用程序可能冻结（挂起）。 若要解决此问题，请执行以下操作。 有关此问题的详细信息，请参阅 [《Visual Studio 帮助查看器冻结》](https://msdn.microsoft.com/library/mt654096.aspx)。    
    
* 在记事本中打开 %LOCALAPPDATA%\Microsoft\HelpViewer2.2\HlpViewer_SSMS16_en-US.settings |HlpViewer_VisualStudio14_en US.settings 文件，并将下面代码中的日期更改为在将来的某个日期。    
    
     
```    
     Cache LastRefreshed="12/31/2017 00:00:00"    
``` 
![horizontal_bar](../sql-server/media/horizontal-bar.png "horizontal_bar")  
##  <a name="bkmk_2016_rc3"></a> SQL Server 2016 候选发布版 3 (RC3)    
-   [产品文档 (RC2)](#bkmk_rc3_docs)    
-   [PolyBase (RC3)](#bkmk_rc3_polybase) 

    
###  <a name="bkmk_rc3_docs"></a> Product Documentation (RC3)    
 **问题及其对客户的影响：** 尚未提供可下载的 SQL Server 2016 文档版本。 当你尝试使用帮助库管理器 **联机安装内容**时，你将看到 SQL Server 2012 和 SQL Sever 2014 文档，但没有 SQL Server 2016 文档的选项。    
    
 **解决方法：** 使用以下方法之一：    
    
 ![管理 SQL Server 的帮助设置](../sql-server/media/docs-sql2016-managehelpsettings.png "管理 SQL Server 的帮助设置")    
    
-   使用选项“选择联机或本地帮助”，然后配置“我想要使用联机帮助”对应的帮助选项。     
    
-   使用选项“联机安装内容”并下载 SQL Server 2014 Content。     
    
 **F1 帮助：** 按照设计，在 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]中按 F1 时，将在浏览器中显示 F1 帮助主题的联机版本。 即使已安装本地帮助也是如此。    
     
**更新内容：**    
在 SQL Server Management Studio 和 Visual Studio 中，在添加文档的过程中帮助查看器应用程序可能冻结（挂起）。 若要解决此问题，请执行以下操作。 有关此问题的详细信息，请参阅 [《Visual Studio 帮助查看器冻结》](https://msdn.microsoft.com/library/mt654096.aspx)。    
    
* 在记事本中打开 %LOCALAPPDATA%\Microsoft\HelpViewer2.2\HlpViewer_SSMS16_en-US.settings |HlpViewer_VisualStudio14_en US.settings 文件，并将下面代码中的日期更改为在将来的某个日期。    
    
     
```    
     Cache LastRefreshed="12/31/2017 00:00:00"    
```    
    
###  <a name="bkmk_rc3_polybase"></a> PolyBase (RC3)        
 从 RC1 或早期版本升级后 PolyBase Queries 可能会失败。    
    
 **问题和对用户的影响**：从 SQL Server 2016 RC1 或以前的版本升级后，PolyBase Queries、导入和导出可能会失败并出现以下错误：“内部查询处理器错误: 查询处理器在处理远程查询阶段的过程中遇到意外错误。”    
    
 **解决方法**    
    
-   卸载 PolyBase。 在“控制面板”中，依次单击“卸载程序”、“Microsoft SQL Server 2016”、“删除”。 在“删除 SQL Server 2016”向导中，选择其 PolyBase 安装失败的实例，然后单击“下一步”。 在“功能”中，单击“针对外部数据的 PolyBase 查询服务”。  不需要删除已成功安装的其他功能。 完成删除 SQL Server 2016 的步骤。    
    
-   重新安装 PolyBase。 运行安装程序，并在相同的 SQL Server 实例上添加 PolyBase 功能。    
    
 **适用于**：SQL Server 2016 RC3（从 RC1 或早期版本升级时）。    
 
## <a name="additional-information"></a>其他信息
- [安装 SQL Server 2016](../database-engine/install-windows/installation-for-sql-server-2016.md)
    
 ![MS_Logo_X-Small](../sql-server/media/ms-logo-x-small.png "MS_Logo_X-Small")    
    
  
