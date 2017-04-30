---
title: "查看时序模型的公式（数据挖掘） | Microsoft Docs"
ms.custom: ""
ms.date: "03/02/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "数据挖掘 [Analysis Services], 操作指南主题"
  - "ARTXP"
  - "时序算法 [Analysis Services]"
  - "ARIMA"
  - "时序 [Analysis Services]"
  - "时序查看器 [Analysis Services]"
ms.assetid: 825ef719-2f44-4979-be01-5a81f54e1a53
caps.latest.revision: 14
author: "Minewiskan"
ms.author: "owend"
manager: "jhubbard"
caps.handback.revision: 14
---
# 查看时序模型的公式（数据挖掘）
  如果已使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 数据挖掘创建时序模型，查看模型的回归公式的最简单方法是使用 [Microsoft 时序查看器](../../analysis-services/data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md)中的**挖掘图例**，该图例将以可读格式显示所有常量。  
  
### 查看时序模型的 ARTXP 回归公式  
  
1.  在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中，选择要查看的时序模型，然后单击 **“浏览”**。  
  
     --或者--  
  
     在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]中，选择该时序模型，然后单击 **“挖掘模型查看器”** 选项卡。  
  
2.  单击 **“模型”** 选项卡。  
  
3.  如果模型包含多个树，请从“树”下拉列表中选择一个树。  
  
    > [!NOTE]  
    >  您有多个数据序列时，模型将始终包含多个树。 但是，您在 **“时序查看器”** 中看到的树的数目却不像在 [Microsoft 一般内容树查看器](../Topic/Microsoft%20Generic%20Content%20Tree%20Viewer%20\(Data%20Mining\).md)中所看到的那么多。 这是因为时序查看器会将每个数据序列的 ARIMA 和 ARTXP 信息结合到单个表示形式中。  
  
4.  单击树中的任一叶节点。  
  
     标记为 **“数据序列”** 的节点始终为叶节点并且可包含公式。 如果“(全部)”节点没有子节点，则它也可包含一个公式。  
  
5.  如果未显示“挖掘图例”，请右键单击该节点，然后选择“显示图例”。  
  
     ARTXP 公式将在 **“挖掘图例”**的前半部分显示为 **“树节点公式”**。  
  
     ![viewing the time series formula in the legend](../../analysis-services/data-mining/media/ssdm-timeserieslegend.png "viewing the time series formula in the legend")  
  
### 查看时序模型的 ARIMA 公式  
  
1.  在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中，选择要查看的时序模型，然后单击 **“浏览”**。  
  
     --或者--  
  
     在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]中，选择该时序模型，然后单击 **“挖掘模型查看器”** 选项卡。  
  
2.  单击 **“模型”** 选项卡。  
  
3.  如果模型包含多个树，请从“树”下拉列表中选择一个树。  
  
    > [!NOTE]  
    >  当有多个数据序列时，模型将始终包含多个树。  
  
4.  单击树中的任一叶节点。  
  
     ARIMA 公式将在 **“挖掘图例”**的后半部分显示为 **“ARIMA 公式”**。  
  
5.  如果未显示“挖掘图例”，请右键单击该节点，然后选择“显示图例”。  
  
### 获取公式的系数和术语  
  
1.  还可以通过对模型内容创建**内容查询**时序模型的回归公式的术语和系数。  
  
     有关详细信息，请参阅[时序模型查询示例](../../analysis-services/data-mining/time-series-model-query-examples.md)  
  
2.  此外，也可以浏览时序模型，然后使用 [Microsoft 一般内容树查看器](../Topic/Microsoft%20Generic%20Content%20Tree%20Viewer%20\(Data%20Mining\).md)来查找术语和系数。  
  
     有关详细信息，请参阅[时序模型的挖掘模型内容](../../analysis-services/data-mining/mining-model-content-for-time-series-models-analysis-services-data-mining.md)。  
  
    > [!NOTE]  
    >  如果浏览使用 ARIMA 模型和 ARTXP 模型的混合模型内容，则在单独的树中的这两个模型将在表示该模型的根节点处联接。 即使为了方便起见将 ARIMA 模型和 ARTXP 模型显示在同一查看器中，但由于公式不同，模型结构也具有很大不同，因此不能对其进行合并或比较。 ARTXP 树更像是决策树，而 ARIMA 树则是一系列移动平均线。  
  
## 另请参阅  
 [挖掘模型查看器任务和操作指南](../../analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md)   
 [使用 Microsoft 时序查看器浏览模型](../../analysis-services/data-mining/browse-a-model-using-the-microsoft-time-series-viewer.md)  
  
  