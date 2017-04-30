---
title: "Invoke-ProcessASDatabase | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 66d5d154-88ce-4c2e-b1ef-e2d2f6fb1c44
caps.latest.revision: 11
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 11
---
# Invoke-ProcessASDatabase
  使用特定的 **ProcessType** 或 **RefreshType** 对指定的 **Database** 执行 **Process** 操作，具体取决于基础元数据类型。  
  
 将 **ProcessType** 用于具有多维元数据的数据库（这包括兼容级别为 1050、1100 或 1103 的表格数据库）。  
  
 将 **RefreshType** 用于兼容级别为 1200 或更高的表格数据库。  
  
## 语法  
 `Invoke-ProcessASDatabase [-DatabaseName] <string> [-RefreshType] <RefreshType> {Full | ClearValues | Calculate |     DataOnly | Automatic | Add | Defragment} [-Server <string>] [-Credential <pscredential>] [-WhatIf] [-Confirm]     [<CommonParameters>]`  
  
 `Invoke-ProcessASDatabase [-DatabaseName] <string> [-ProcessType] <ProcessType> {ProcessFull | ProcessAdd |     ProcessUpdate | ProcessIndexes | ProcessData | ProcessDefault | ProcessClear | ProcessStructure |     ProcessClearStructureOnly | ProcessScriptCache | ProcessRecalc | ProcessDefrag} [-Server <string>] [-Credential     <pscredential>] [-WhatIf] [-Confirm]  [<CommonParameters>]`  
  
## Description  
 **Invoke-ProcessASDatabase** cmdlet将数据集处理到指定的级别。 例如，对于兼容级别为 1200 的数据库，将 **RefreshType** 设置为 **Full** 会用全新的数据覆盖现有数据。  
  
 需要处理类型（多维）或刷新类型（表格），且可以在数据库和服务器参数之前或之后指定它们：  
  
-   有关多维的详细信息，请参阅[处理选项和设置 (Analysis Services)](../../analysis-services/multidimensional-models/processing-options-and-settings-analysis-services.md)。  
  
-   有关表格的详细信息，请参阅[处理数据库、表或分区 (Analysis Services)](../../analysis-services/tabular-models/process-database-table-or-partition-analysis-services.md)。  
  
## Parameters  
  
### -DatabaseName \<string>  
 指定要处理的表格或多维数据库。  
  
|||  
|-|-|  
|必需？|true|  
|位置？|0|  
|默认值||  
|接受管道输入？|false|  
|接受通配符？|false|  
  
### -Server\<Microsoft.AnalysisSevices.Server>  
 如果你未在使用上下文的 **SQLAS** 提供程序目录，则可以选择性地指定要连接到的服务器实例。  
  
|||  
|-|-|  
|必需？|false|  
|位置？|所指定位置|  
|默认值||  
|接受管道输入？|false|  
|接受通配符？|false|  
  
### -RefreshType \<Microsoft.AnalysisServices.RefreshType>  
 为兼容级别为 1200 的表格数据库指定处理类型。  有效值为 Full、ClearValues、Calculate、DataOnly、Automatic、Add 和 Defragment。 有关说明和指南，请参阅[处理数据库、表或分区 (Analysis Services)](../../analysis-services/tabular-models/process-database-table-or-partition-analysis-services.md)。  
  
|||  
|-|-|  
|必需？|true|  
|位置？|1|  
|默认值||  
|接受管道输入？|false|  
|接受通配符？|false|  
  
### -ProcessType \<Microsoft.AnalysisServices.ProcessType>  
 为兼容级别为 1050-1103 的多维数据库或表格数据库指定处理类型。 有效值包括 ProcessFull、ProcessAdd、ProcessUpdate、ProcessIndexes、ProcessData、ProcessDefault、ProcessClear、ProcessStructure、ProcessCelarStructureOnly、ProcessScriptCache 或 ProcessRecalc。 有关说明和指南，请参阅[处理选项和设置 (Analysis Services)](../../analysis-services/multidimensional-models/processing-options-and-settings-analysis-services.md)。  
  
|||  
|-|-|  
|必需？|true|  
|位置？|1|  
|默认值||  
|接受管道输入？|false|  
|接受通配符？|false|  
  
### -Credential  
 如果指定此参数，将使用传递的用户名和密码连接到 Analysis Services 实例。 如果未指定凭据，将使用正在运行该脚本的用户的默认 Windows 帐户。  
  
|||  
|-|-|  
|必需？|false|  
|位置？|所指定位置|  
|默认值||  
|接受管道输入？|false|  
|接受通配符？|false|  
  
## -Whatif  
 包括此参数以在操作执行前获取关于操作的影响的信息。  
  
|||  
|-|-|  
|必需？|false|  
|位置？|所指定位置|  
|默认值||  
|接受管道输入？|false|  
|接受通配符？|false|  
  
## -Confirm  
 包括此参数以在操作执行前用“是”或“否”响应来交互确认操作。  
  
|||  
|-|-|  
|必需？|false|  
|位置？||  
|默认值||  
|接受管道输入？||  
|接受通配符？|false|  
  
## 示例 1（SQLAS 提供程序）  
 此示例使用 **SQLAS** 提供程序在默认实例上将上下文设置为数据库的列表。  如果列出数据库目录的内容，将看到所有的数据库以及其进程状态和读写模式。  
  
 从数据库文件夹中，可运行仅指定数据库名称的 **Invoke-ProcessASDatabase**。  
  
```  
PS > import-module SQLPS -DisableNameChecking  
PS  SQL Server > cd sqlas\ssas-srv-01\default\databases  
PS SQLSERVER:\sqlas\ssas-srv-01\default\databases> dir  
. . . .  
PS SQLSERVER:\sqlas\ssas-srv-01\default\databases> Invoke-ProcessASDatabase "adventureworks"  
  
```  
  
 根据数据库的类型，系统将提示你指定 **RefreshType** 或 **ProcessType**。  
  
 处理证明是在 return 语句中存在影响对象：Microsoft.AnalysisServices.Tabular.ObjectImpact。  
  
 请注意，对象状态信息有时会被缓存，因此如果在处理成功后列出目录的内容，数据库状态将保留其原始的“未处理的”描述符。 这会令人误解，因为只要返回了 objectimact，那么数据库实际就已经处理了。  
  
 可以通过查看 Management Studio 中的数据库属性页、启动新的会话或（通过 [Microsoft.AnalysisServices.ProcessableMajorObject.LastProcessed](https://msdn.microsoft.com/library/microsoft.analysisservices.processablemajorobject.lastprocessed.aspx)）从数据库对象中返回处理状态来确认处理已成功。  
  
## 示例 2  
 此示例演示了仅使用 cmdlet 而不使用提供程序的相同操作。 需要其他参数以指定服务器和处理类型。  
  
```  
PS > import-module SQLPS -DisableNameChecking  
PS  SQL Server >  Invoke-ProcessASDatabase -databasename "AdventureWorks" -server '\\server-name\instancename' –ProcessType "ProcessFull"  
  
```  
  
## 另请参阅  
 [Analysis Services 中表格模型的兼容级别](../../analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md)  
  
  