---
title: "管理 Oracle 表空间 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Oracle publishing [SQL Server replication], managing tablespaces
- tablespaces [SQL Server replication]
ms.assetid: b8ea6c3b-01d6-4efc-bbfb-03b264530bbd
caps.latest.revision: 33
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 6eaa6d1c6836cee6d8367e0c0893b3f8a73184f3
ms.lasthandoff: 04/11/2017

---
# <a name="manage-oracle-tablespaces"></a>管理 Oracle 表空间
  表空间是一个数据库存储单元，大致相当于 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]中的文件组。 表空间允许存储和管理各个组内的数据库对象。 有关详细信息，请参阅 Oracle 文档。  
  
 如果将表配置为 Oracle 发布的一部分，则可以选择指定在存储复制记录信息时使用现有的 Oracle 表空间。 如果未指定，则复制对象的表空间就是与配置发布服务器时配置的复制管理用户架构相关联的默认表空间。  
  
 **为项目记录表指定表空间**：  
  
-   在 **“项目属性”** 对话框中指定表空间。 有关访问此对话框的详细信息，请参阅 [View and Modify Publication Properties](../../../relational-databases/replication/publish/view-and-modify-publication-properties.md)。  
  
-   使用 [sp_changearticle (Transact-SQL)](../../../relational-databases/system-stored-procedures/sp-changearticle-transact-sql.md)。 若要使用 **sp_changearticle**，请指定下列内容：  
  
    -   为参数 **@publisher**中的文件组。  
  
    -   为参数 **@publication**中的文件组。  
  
    -   为参数 **@article**中的文件组。  
  
    -   为参数 **@property**中的文件组。  
  
    -   为参数 **@value**中的文件组。  
  
## <a name="see-also"></a>另请参阅  
 [配置 Oracle 发布服务器](../../../relational-databases/replication/non-sql/configure-an-oracle-publisher.md)   
 [Objects Created on the Oracle Publisher](../../../relational-databases/replication/non-sql/objects-created-on-the-oracle-publisher.md)  
  
  