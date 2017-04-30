---
title: "从 Power Pivot 还原 | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/multidimensional-tabular"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql11.asvs.ssmsimbi.RestoreFromPP.f1"
ms.assetid: 232ac8ed-77fe-47d8-acd3-59bc2fdfdf48
caps.latest.revision: 8
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 8
---
# 从 Power Pivot 还原
  你可以使用 SQL Server Management Studio 中的“从 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 还原”功能针对 Analysis Services 实例（在表格模式下运行）创建新的表格模型数据库，或从 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 工作簿 (.xlsx) 还原到现有数据库。  
  
> [!NOTE]  
>  SQL Server Data Tools 中的“从 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 导入”项目模板提供了类似功能。 有关详细信息，请参阅[从 PowerPivot 导入（SSAS 表格）](../../analysis-services/tabular-models/import-from-power-pivot-ssas-tabular.md)。  
  
 使用“从 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)]还原”时，请注意下列问题：  
  
-   为了使用“从 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)]还原”，你必须以该 Analysis Services 实例上的服务器管理员角色的成员身份登录。  
  
-   该 Analysis Services 实例服务帐户必须对您要还原的工作簿文件具有读取权限。  
  
-   默认情况下，当你从 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)]还原数据库时，表格模型数据库的“数据源模拟信息”属性设置为“默认”，这会指定 Analysis Services 实例服务帐户。 建议在“数据库属性”中将模拟凭据更改为 Windows 用户帐户。 有关详细信息，请参阅[模拟（SSAS 表格）](../../analysis-services/tabular-models/impersonation-ssas-tabular.md)。  
  
-   [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 数据模型中的数据将复制到该 Analysis Services 实例上的现有或新的表格模型数据库中。 如果你的 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 工作簿包含链接表，则将以不带数据源的表形式来重新创建表，该表与使用“粘贴到新表中”创建的表类似。  
  
### 从 Power Pivot 还原  
  
1.  在 SSMS 中要还原到的 Active Directory 实例中，右键单击“数据库”，然后单击“从 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 还原”。  
  
2.  在“从 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 还原”对话框中“还原源”的“备份文件”中，单击“浏览”，然后选择要从其中还原的 .abf 或 .xslx 文件。  
  
3.  在 **“还原目标”**中的“ **还原数据库”**中，键入新数据库或现有数据库的名称。 如果不指定名称，则使用工作簿的名称。  
  
4.  在 **“存储位置”**中，单击 **“浏览”**，然后选择数据库的存储位置。  
  
5.  在 **“选项”**中，选中 **“包括安全信息”** 。 在从 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 工作簿还原时，此设置不适用。  
  
## 另请参阅  
 [表格模型数据库（SSAS 表格）](../../analysis-services/tabular-models/tabular-model-databases-ssas-tabular.md)   
 [从 PowerPivot 导入（SSAS 表格）](../../analysis-services/tabular-models/import-from-power-pivot-ssas-tabular.md)  
  
  