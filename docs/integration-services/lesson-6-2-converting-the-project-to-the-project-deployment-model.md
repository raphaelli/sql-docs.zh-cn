---
title: 步骤 2：将项目转换为项目部署模型 | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.component: tutorial
ms.reviewer: ''
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- SQL Server 2016
ms.assetid: 80964293-f1f5-4da7-b1fb-00ab8c30c1c5
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: f7097d75078c8602172e2e16a26832ab4bb385a1
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="lesson-6-2---converting-the-project-to-the-project-deployment-model"></a>第 6-2 课 - 将项目转换为项目部署模型
在本任务中，你将使用 Integration Services 项目转换向导将项目转换为项目部署模型。  
  
### <a name="converting-the-project-to-the-project-deployment-model"></a>将项目转换为项目部署模型  
  
1.  在“项目”菜单上，单击“转换为项目部署模型”。  
  
2.  在 Integration Services 项目转换向导简介页面上，检查步骤，然后单击“下一步”。  
  
3.  在“选择包”页面上的“包”列表中，清除所有复选框（除了 Lesson 6.dtsx），然后单击“下一步”。  
  
4.  在“指定项目属性”页面上，单击“下一步”。  
  
5.  在“更新执行包任务”页面上，单击“下一步”。  
  
6.  在“选择配置”页面上，确保在“配置”列表中选择 Lesson 6.dtsx 包，然后单击“下一步”。  
  
7.  在“创建参数”页面上，确保在“配置属性”列表中选择 Lesson 6.dtsx 包，并且“范围”设置为“包”，然后单击“下一步”。  
  
8.  在“配置参数”页面上，对于变量和配置值验证“名称”和“值”的值是否为第 5 课中指定的相同名称和值，然后单击“下一步”。  
  
9. 在“检查”页面上的“摘要”窗格中，请注意向导使用了配置文件中的信息来设置“要转换的属性”。  
  
10. 单击“转换”。  
  
    转换完成时会显示一条消息，警告在 Visual Studio 中保存项目之前不会保存更改。 在警告对话框中单击“确定”。  
  
11. 在 Integration Services 项目转换向导上单击“关闭”。  
  
12. 在 SQL Server Data Tools 中，单击“文件”菜单，然后单击“保存”以保存转换的包。  
  
13. 单击“参数”选项卡，然后验证包现在是否包含用于 VarFolderName 的参数，以及值是否为第 5 课配置文件中为 New Sample Data 文件夹指定的相同路径。  
  
## <a name="next-task-in-lesson"></a>课程中的下一个任务  
[步骤 3：测试 Lesson 6 包](../integration-services/lesson-6-3-testing-the-lesson-6-package.md)  
  
  
  
