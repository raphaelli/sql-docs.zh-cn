---
title: "编辑现有记录 |Microsoft 文档"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editing data [ADO], existing records
ms.assetid: 17ce1263-5897-452a-9ea5-c7f96b33df65
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 03e720476c8056737e2735ac96c97a7caf190de4
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="editing-existing-records"></a>编辑现有记录
若要编辑现有记录，移动到你想要编辑和更改的行**值**你想要更改的字段的属性。 有关详细信息**字段**对象的**值**属性，请参阅[检查数据](../../../ado/guide/data/examining-data.md)。 根据你的光标类型，你将使用**更新**或**UpdateBatch**若要将更改发送回数据源。 有关详细信息，请参阅[更新和保持数据](../../../ado/guide/data/updating-and-persisting-data.md)。  
  
 它是用于存储的过程的一个命令对象执行更新，以及执行其他操作，因为存储的过程不需要创建游标通常更高效。 有关游标的详细信息，请参阅[了解游标和锁定](../../../ado/guide/data/understanding-cursors-and-locks.md)。