---
title: "收集饼图上的小切片（报表生成器和 SSRS） | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 21c2b8cb-b9ca-4bc0-bf49-50ba432562f6
caps.latest.revision: 10
author: "maggiesMSFT"
ms.author: "maggies"
manager: "erikre"
caps.handback.revision: 8
---
# 收集饼图上的小切片（报表生成器和 SSRS）
  饼图显示太多数据点时，这些数据点会显得混乱。 若要解决此问题，可以将低于特定值的所有数据显示为饼图的一个切片。  
  
 若要将若干小切片收集到一个切片中，请先确定用于收集小切片的阈值以饼图的百分比度量或为固定值。 然后设置 CollectedThreshold 和 CollectedThresholdUsePercent 属性。将 CollectedThreshold 属性设置为某个值必须低至可以进行收集的图表百分比，或者设置为用于收集的实际阈值数据值。 将 CollectedThresholdUsePercent 属性设置为 **True** 以使用百分比，或者设置为 **False** 以使用实际值。  
  
 还可以将小切片收集到第一个饼图的收集切片标注的辅助饼图中。 该辅助饼图绘制在原始饼图的右侧。  
  
 不能将漏斗图或棱锥图的切片组合到一个切片。  
  
 此图表的示例可用于示例报表。 有关下载此示例报表和其他内容的详细信息，请参阅 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][报表生成器和报表设计器示例报表](http://go.microsoft.com/fwlink/?LinkId=198283)。  
  
### 将小切片收集到饼图上的一个切片中  
  
1.  打开“属性”窗格。  
  
2.  在设计图面上，单击饼图的任一切片。 序列的属性将显示在“属性”窗格中。  
  
3.  在 **“常规”** 部分，展开 **CustomAttributes** 节点。  
  
4.  将 CollectedStyle 属性设置为 **SingleSlice**。  
  
5.  设置收集的阈值和阈值的类型。 以下示例是收集阈值的常见设置方法。  
  
    -   **按百分比。** 例如，若要将饼图上少于 10% 的切片收集到一个切片：  
  
         将 CollectedThresholdUsePercent 属性设置为 **True**。  
  
         将 CollectedThreshold 属性设置为 **10**。  
  
        > [!NOTE]  
        >  如果你将 CollectedStyle 设置为 **SingleSlice**，将 CollectedThreshold 设置为大于 **100** 的值，并且 CollectedThresholdUsePercent 为 **True**，则图表将引发异常，因为它无法计算百分比。 若要解决此问题，请将 CollectedThreshold 设置为小于 **100** 的值。  
  
    -   **按数据值。** 例如，若要将饼图上少于 5000 的切片收集到一个切片：  
  
         将 CollectedThresholdUsePercent 属性设置为 **False**。  
  
         将 CollectedThreshold 属性设置为 **5000**。  
  
6.  将 CollectedLabel 属性设置为字符串，该字符串表示将在收集的切片上显示的文本标签。  
  
7.  （可选）设置 CollectedSliceExploded、CollectedColor、CollectedLegendText 和 CollectedToolTip 属性。 这些属性可更改一个切片的外观、颜色、标签文本、图例文本和工具提示方面。  
  
### 将小切片收集到辅助标注饼图中  
  
1.  请执行以上 1 - 3 步骤。  
  
2.  将 CollectedStyle 属性设置为 **CollectedPie**。  
  
3.  将 CollectedThreshold 属性设置为一个值，该值表示将小切片收集成一个切片的阈值。 当 CollectedStyle 属性设置为 **CollectedPie** 时，CollectedThresholdUsePercent 属性始终设置为 **True**，收集阈值也始终以百分比度量。  
  
4.  （可选）设置 CollectedColor、CollectedLabel、CollectedLegendText 和 CollectedToolTip 属性。 所有名为“Collected”的其他属性都不适用于收集的切片。  
  
> [!NOTE]  
>  辅助饼图是根据您数据中的小切片计算的，因此将仅在“预览”中显示。 它不显示在设计图面上。  
  
> [!NOTE]  
>  您不能设置辅助饼图的格式。 因此，强烈建议使用第一种方法收集饼图切片。  
  
## 另请参阅  
 [饼图&#40;报表生成器和 SSRS&#41;](../../reporting-services/report-design/pie-charts-report-builder-and-ssrs.md)   
 [设置图表上数据点的格式&#40;报表生成器和 SSRS&#41;](../../reporting-services/report-design/formatting-data-points-on-a-chart-report-builder-and-ssrs.md)   
 [在饼图外显示数据点标签&#40;报表生成器和 SSRS&#41;](../../reporting-services/report-design/display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md)   
 [在饼图上显示百分比值&#40;报表生成器和 SSRS&#41;](../../reporting-services/report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md)   
 [向图表添加三维效果&#40;报表生成器和 SSRS&#41;](../../reporting-services/report-design/add-3d-effects-to-a-chart-report-builder-and-ssrs.md)  
  
  