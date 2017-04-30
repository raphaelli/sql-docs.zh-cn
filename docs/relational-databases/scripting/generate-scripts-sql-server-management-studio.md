---
title: "生成脚本 (SQL Server Management Studio) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9711c617-3c68-4e5a-aea3-befc64d51524
caps.latest.revision: 6
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 1bf73031c7e2e302d6174e6f21a005c3106f4cb2
ms.lasthandoff: 04/11/2017

---
# <a name="generate-scripts-sql-server-management-studio"></a>生成脚本 (SQL Server Management Studio)
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 提供了两种机制，用于生成 [!INCLUDE[tsql](../../includes/tsql-md.md)] 脚本。 可以使用 **“生成和发布脚本向导”**为多个对象创建脚本。 还可以通过使用 **“对象资源管理器”** 中的 **“编写脚本为”**菜单为单个对象或多个对象生成脚本。  
  
1.  **Choose a method:**  [Generate and Publish Scripts Wizard](#GenPubScriptWiz), [Object Explorer Script As Menu](#OEScriptAsMenu)  
  
2.  **To use the Script As menu:**  [Script a Single Object](#ScriptSingleObject), [Script Two Objects Using Object Explorer](#ScriptTwoObjectsOE), [Script Two Objects Using Object Explorer Details](#ScriptTwoObjectsOED)  
  
## <a name="before-you-begin"></a>开始之前  
 选择最能满足您的需求的机制。  
  
###  <a name="GenPubScriptWiz"></a> 生成和发布脚本向导  
 使用 **“生成和发布脚本向导”** 可为多个对象创建 [!INCLUDE[tsql](../../includes/tsql-md.md)] 脚本。 此向导为数据库中的所有对象或所选对象子集生成脚本。 该向导具有许多用于您的脚本的选项，例如是否包括权限、排序规则和约束等。 有关使用向导的说明，请参阅 [Generate and Publish Scripts Wizard](../../relational-databases/scripting/generate-and-publish-scripts-wizard.md).  
  
###  <a name="OEScriptAsMenu"></a> 对象资源管理器“编写脚本为”菜单  
 可以使用对象资源管理器 **“编写脚本为”** 菜单编写单个对象的脚本、编写多个对象的脚本或为单个对象编写多条脚本语句。 您可以选择多种脚本类型之一；例如，创建、更改或删除对象。 您可以将脚本保存到查询编辑器窗口、文件或剪贴板。 脚本以 Unicode 格式创建。  
  
##  <a name="ScriptSingleObject"></a> 生成单个对象的脚本  
 **编写单个对象的脚本**  
  
1.  在对象资源管理器中，连接到 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 的实例，然后展开该实例。  
  
2.  展开 **“数据库”**，然后展开包含要对其编写脚本的对象的数据库。  
  
3.  展开该对象的类别。 例如，展开 **“表”** 或 **“视图”** 节点。  
  
4.  右键单击该对象，指向“编写 \<对象类型> 脚本为”，例如，指向“编写表脚本为”。  
  
5.  指向脚本类型，如 **“创建到”** 或 **“更改到”**。  
  
6.  选择要保存该脚本的位置，如 **“新查询编辑器窗口”** 或 **“剪贴板”**。  
  
##  <a name="ScriptTwoObjectsOE"></a> 使用对象资源管理器为两个对象生成一个脚本  
 **使用对象资源管理器为两个对象编写脚本**  
  
 有时您可能需要使用具有多个选项的脚本，如删除一个过程后再创建一个过程，或者创建一个表后再更改一个表。 如果您需要创建引用不同类型的对象（如表、视图和存储过程）的脚本，下面的用于为多个对象生成脚本的过程也适用。  
  
1.  在对象资源管理器中，连接到 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 的实例，然后展开该实例。  
  
2.  展开 **“数据库”**，然后展开包含要对其编写脚本的对象的数据库。  
  
3.  右键单击要为其编写脚本的第一个对象，指向“编写 \<对象类型> 脚本为”，然后在“另存为”选项中选择“新查询编辑器窗口”作为输出目标。  
  
4.  导航到第二个要编写脚本的对象。  
  
5.  右键单击该对象，指向“编写 \<对象类型> 脚本为”，然后在“另存为”选项中选择“剪贴板”作为输出目标。  
  
6.  在“查询编辑器”窗口中打开第一个对象，然后从剪贴板中粘贴第二个对象的脚本。  
  
##  <a name="ScriptTwoObjectsOED"></a> 使用“对象资源管理器详细信息”为两个对象生成一个脚本  
 **使用“对象资源管理器详细信息”为两个对象编写脚本**  
  
 可以使用 **“对象资源管理器详细信息”** 窗格为相同类别的多个对象生成一个脚本。  
  
1.  在对象资源管理器中，连接到 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 的实例，然后展开该实例。  
  
2.  展开 **“数据库”**，然后展开包含要对其编写脚本的对象的数据库。  
  
3.  展开要编写脚本的对象类型的类别节点，如 **“表”** 节点。  
  
4.  可通过选中 **F7** 或打开 **“视图”**菜单并选择 **“对象资源管理器详细信息”** 来打开 **“对象资源管理器详细信息”**窗格。  
  
5.  左键单击要编写脚本的对象之一。  
  
6.  然后，按住 Ctrl 并左键单击第二个要编写脚本的对象。  
  
7.  右键单击所选对象之一，然后选择“编写 \<对象类型> 脚本为”。  
  
  