---
title: "选择源表和源视图（SQL Server 导入和导出向导） | Microsoft Docs"
ms.custom: ""
ms.date: "03/16/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.impexpwizard.selectsourcetablesandviews.f1"
ms.assetid: f60e1a19-2ea6-403c-89ab-3e60ac533ea0
caps.latest.revision: 96
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 88
---
# 选择源表和源视图（SQL Server 导入和导出向导）
  指定要复制整个表或提供查询之后，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 导入和导出向导会显示“选择源表和源视图”。 在此页上，选择想要复制的现有表和视图。 然后将源表映射到新的或现有的目标表。 或者，还可查看单个列的映射并预览示例数据。

> [!TIP] 如果必须复制多个数据库或数据库对象（而非表和视图），请使用复制数据库向导，而不是使用导入和导出向导。 有关详细信息，请参阅[使用复制数据库向导](../../relational-databases/databases/use-the-copy-database-wizard.md)。  
  
## <a name="screen-shot---what-you-see-if-youre-going-to-copy-tables"></a>屏幕截图 - 复制表后将看到的内容  
 以下屏幕截图显示之前在“指定表复制或查询”页上选择“复制一个或多个表或视图的数据”选项时，向导的“选择源表和源视图”页。 在列表中，可以看到数据源中可用的所有表和视图。
 
在此示例中，用户要将 **Sales.Customer** 表从源复制到目标上的新 **Sales.CustomerNew** 表。 
   
 ![Select tables page of the Import and Export Wizard](../../integration-services/import-export-data/media/select-tables1.png "Select tables page of the Import and Export Wizard")
  
## <a name="screen-shot---what-you-see-if-you-provided-a-query"></a>屏幕截图 - 提供查询后将看到的内容  
 以下屏幕截图显示之前在“指定表复制或查询”页上选择“编写查询以指定要传输的数据”选项，然后在“提供源查询”页提供查询时，呈现的向导的“选择源表和源视图”页。 在列表中，只会看到单个行，其中“源”列中的项表示你所提供的查询。
 
在此示例中，用户要将查询结果从源复制到目标上的 **Sales.CustomerNew** 表。  
    
 ![Select tables page of the Import and Export Wizard](../../integration-services/import-export-data/media/select-tables2.png "Select tables page of the Import and Export Wizard")  

## <a name="select-source-and-destination-tables"></a>选择源表和目标表 
**源**  
使用这些复选框，可以从可用表和视图的列表中进行选择，以复制到目标。 默认情况下，可在不更改的情况下复制数据源中的数据。 如果创建新的目标表，也可在不更改的情况下从数据源复制架构。

如果要提供查询，则列表只包含一个名为“查询”\[\]的项。 

**目标**  
 从列表中为每个源表或查询选择目标表，或输入希望向导创建的新表的名称。 如果选择现有目标表，则该表必须具有与源数据兼容的数据类型的列。  

> [!NOTE] 如果此时在向导中暂停操作以使用外部工具（如 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]）在目标数据库中手动创建新表，则新表不会立即出现在可用目标表的列表中。 若要刷新目标表的列表，请退回到“选择目标”页，重新选择目标数据库以刷新可用表和视图的列表，然后再次前进到“选择源表和源视图”页。  

## <a name="select-source-and-destination-tables-for-excel"></a>选择 Excel 的源表和目标表

### <a name="excel-source-tables"></a>Excel 源表
Excel 数据源的源表和视图的列表包括两种类型的 Excel 对象。
-   **工作表**。 工作表名称后跟美元符号 ($) ，例如，**“Sheet1$”**。
-   **命名区域。** 命名区域（如有）按名称列出。

如果想要加载来自特定的、未命名的单元格区域的数据（或将数据加载到其中）- 例如，来自或加载到 **[Sheet1$ A1: B4]**，则必须编写查询。 后退到“指定表复制或查询”页，选择“编写查询以指定要传输的数据”。

无论是否将工作表或区域指定为源表，该驱动程序都将读取从工作表或区域左上角第一个非空单元开始的连续单元块。 因此，源数据中不能有空行。 例如，列标题和数据行之间不能有空行。 如果工作表顶部数据上面的标题后跟有空行，则无法查询该工作表。 在 Excel 中，必须为区域内的数据分配名称，并查询命名区域而非工作表。

### <a name="excel-destination-tables"></a>Excel 目标表
如果将数据导出到 Excel，可以通过以下三种方式之一来指定目标。
-   **工作表。** 若要指定工作表，请将 $ 字符附加到表名称的末尾，并用分隔符包围字符串 - 例如，**[Sheet1$]**。
-   **命名区域。** 若要指定命名区域，只需使用区域名称 - 例如，**MyDataRange**。
-   **未命名区域。** 若要指定未命名的单元格区域，请将 $ 字符附加到表名称的末尾，添加区域说明，并用分隔符包围字符串 - 例如，**[Sheet1$ A1: B4]**。

## <a name="special-considerations-for-excel-sources-and-destinations"></a>Excel 源和目标的特殊注意事项
使用 Excel 作为源或目标时，最好单击“编辑映射”并在“列映射”页查看数据类型映射。 

**Excel 工作簿中的数据类型**。 Excel 不是一个典型的数据库。 它的列不具有固定的数据类型。 向导仅能识别 Excel 中一组有限的数据类型 - 数字、货币、布尔值，日期/时间、字符串（最多 255 个字符）和备注（255 个字符以上）。 向导读取 Excel 数据源中一定数量的行（默认情况下为 8 行）以推测每列的数据类型。

当向导必须执行从 Excel 加载或加载到 Excel 的显式数据类型转换时，它通常会显示“查看数据类型映射”页，你可以在其中查看这些转换。 这些转换可能包括以下内容。
-   双精度 Excel 数值列与其他类型的数值列之间的转换。
-   Unicode Excel 字符串列与具有特定代码页的非 Unicode 字符串列之间的转换。
-   在 255 个字符的 Excel 字符串列和不同长度的字符串列之间转换。

### <a name="special-considerations-for-excel-sources"></a>Excel 源的特殊注意事项
**导入的数据中的 null 值或缺少值**。 当 Excel 列似乎包含混合数据类型时（例如，向导采样的前 8 行中与文本值混合的数值），向导会提取大多数数据类型作为列的数据类型，并为包含其他类型数据的单元格返回 null 值。 无法更改向导的此行为。

**导入的数据中截断的字符串**。 向导在确定 Excel 列是否包含文本数据时，它将基于前 8 行中采样的最长值来选择列的数据类型（字符串或备注）。 如果向导没有在其采样的行中发现任何长于 255 个字符的值，那么它会将该列视为 255 个字符的字符串的列而不是备注列，并截断长于 255 个字符的值。 若要从备注列导入数据而无需截断，则必须确保备注列前 8 行中至少包含一个超过 255 个字符的值。

### <a name="special-considerations-for-excel-destinations"></a>Excel 目标的特殊注意事项
**指定现有范围**。 当指定现有范围为目标时，如果范围不够宽（即，如果它具有的列比源数据少），则将收到错误。 但是，如果指定的范围不够长（即，如果它具有的行比源数据少），则向导将继续写入行并扩展范围定义以匹配新的行数。

**保存备注 (ntext) 数据**。 若要将大于 255 个字符的字符串成功地保存到 Excel 列中，向导必须将该目标列的数据类型识别为 **memo**，而不是 **string**。
-   如果目标表中已存在数据行，则由向导抽样的前 8 行的备注列中必须至少包含一个长度大于 255 个字符的值的行。
-   如果目标表由向导创建，则相应的 **CREATE TABLE** 语句必须使用 **LONGTEXT**（或其同义词之一）作为备注列的数据类型。 单击“列映射”页上“创建目标表”选项旁边的“编辑 SQL”，修订 **CREATE TABLE** 语句。

## <a name="optionally-edit-column-mappings-and-preview-sample-data"></a>（可选）编辑列映射和预览示例数据
**编辑映射**   
（可选）对所选表单击“编辑映射”以显示“列映射”对话框。 使用“列映射”对话框可执行以下操作，
-   查看单个列在源与目标之间的映射。
-   通过对不想复制的列选择“忽略”，可以仅复制列的子集。

有关详细信息，请参阅[列映射](../../integration-services/import-export-data/column-mappings-sql-server-import-and-export-wizard.md)。  

**预览**  
（可选）单击“预览”以在“预览数据”对话框中预览最多 200 行的示例数据。 这会确认向导将复制你想要复制的数据。 有关详细信息，请参阅[预览数据](../../integration-services/import-export-data/preview-data-dialog-box-sql-server-import-and-export-wizard.md)。  
  
预览数据后，你可能想更改之前在向导页面中选择的选项。 若要进行这些更改，请返回到“选择源表和源视图”页，单击“后退”返回到前面可以更改选项的页面。  

## <a name="whats-next"></a>下一步是什么？  
 选择现有表和视图以进行复制并将它们映射到其目标之后，下一页是“保存并运行包”。 在此页上，你可以指定是否要立即运行复制操作。 根据你的配置，或许还可以保存向导创建的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 包，以便对其进行自定义并在以后重新使用。 有关详细信息，请参阅[保存并运行包](../../integration-services/import-export-data/save-and-run-package-sql-server-import-and-export-wizard.md)。  