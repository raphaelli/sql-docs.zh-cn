---
title: "Customize the Parameters Pane in a Report (Report Builder) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4ce9e8d5-911a-4422-928f-a8d005b79fc6
caps.latest.revision: 8
author: "maggiesMSFT"
ms.author: "maggies"
manager: "erikre"
caps.handback.revision: 8
---
# Customize the Parameters Pane in a Report (Report Builder)
  使用报表生成器中的参数创建分页报表时，可以自定义参数窗格。 在报表设计视图中，可以将参数拖到参数窗格中的特定列和行。 你可以通过添加和删除列来更改窗格的布局。  
  
 将参数拖到窗格中的新列和新行时，“报表数据”窗格中的参数顺序也会发生变化。 更改“报表数据”窗格中参数顺序时，窗格中参数的位置会发生变化。 有关参数顺序的重要性的详细信息，请参阅[更改报表参数的顺序（报表生成器和 SSRS）](../../reporting-services/report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)。  
  
## 自定义参数窗格的步骤  
  
1.  在“视图”  选项卡上，选中“参数”  复选框以显示参数窗格。  
  
     ![Access parameters pane from View tab](../../reporting-services/report-design/media/ssrs-customparameter-accessparameterpanedesignmode.png "Access parameters pane from View tab")  
  
     窗格将显示在设计图面的顶部。  
  
2.  若要向窗格添加参数，请执行以下操作之一。  
  
    -   右键单击参数窗格中的空白单元格，然后单击“添加参数” 。  
  
         ![Add new parameter from parameters pane](../../reporting-services/report-design/media/ssrs-customizeparameter-addnewparameter.png "Add new parameter from parameters pane")  
  
    -   在“报表数据”窗格中，右键单击“参数”，然后单击“添加参数”。  
  
3.  若要将参数移动到参数窗格中的新位置，请将参数拖到窗格中的不同单元格。  
  
     更改窗格中参数的位置时，“报表数据”窗格的“参数”列表中的参数顺序将自动发生变化。 有关参数顺序的影响的详细信息，请参阅[更改报表参数的顺序（报表生成器和 SSRS）](../../reporting-services/report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)  
  
4.  若要访问参数的属性，请执行以下操作之一。  
  
    -   右键单击参数窗格中的参数，然后单击“参数属性” 。  
  
         ![Access parameter properties from the parameters pane](../../reporting-services/report-design/media/ssrs-customizeparameter-accessparameterproperties-composite.png "Access parameter properties from the parameters pane")  
  
    -   右键单击“报表数据”窗格中的参数，然后单击“参数属性”。  
  
5.  若要向窗格添加新的列和行，或删除现有的行和列，请右键单击参数窗格中的任意位置，然后单击所示菜单中的命令。  
  
     ![Add columns and rows to the parameters pane](../../reporting-services/report-design/media/ssrs-customparameter-addcolumnsrows.png "Add columns and rows to the parameters pane")  
  
    > [!IMPORTANT]  
    >  删除包含参数的列或行时，将从报表中删除这些参数。  
  
6.  若要从窗格和报表中删除参数，请执行以下操作之一。  
  
    -   右键单击参数窗格中的参数，然后单击“删除”  。  
  
         ![Delete parameters from the parameters pane](../../reporting-services/report-design/media/ssrs-customparameter-deleteparameter.png "Delete parameters from the parameters pane")  
  
    -   右键单击“报表数据”窗格中的参数，然后单击“删除”。  
  
## 另请参阅  
 [报表参数（报表生成器和报表设计器）](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)  
  
  