---
title: "生成镜像表和 CDC 捕获实例 | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mirTab"
ms.assetid: 260c1617-eecc-4007-a84d-3c5778ce46b6
caps.latest.revision: 5
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 5
---
# 生成镜像表和 CDC 捕获实例
  使用“生成镜像表”页可生成在 CDC 实例中包含的表的镜像表。  
  
 单击 **“运行”** 可创建镜像表。 将显示每个表的创建进度，并且将显示一条消息，通知您每个镜像表是成功完成还是存在错误。 如果出现任何错误，请单击 **“详细信息”** 以便查看含错误说明的对话框。  
  
 如果任何表无法创建，您可以选择是继续还是在继续前删除失败的表。 在向导运行完毕后，您可以决定是在 Oracle 源数据库中修复该表还是不在 CDC 实例中使用它。 如果您修复该表，则可以在 [Edit Tables](../../integration-services/change-data-capture/edit-tables.md)时添加该表。  
  
 单击 **“下一步”** 以便打开 [Finish](../../integration-services/change-data-capture/finish.md) 页。  
  
## 另请参阅  
 [如何创建 SQL Server 更改数据库实例](../../integration-services/change-data-capture/how-to-create-the-sql-server-change-database-instance.md)  
  
  