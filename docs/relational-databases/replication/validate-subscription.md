---
title: "验证单个订阅 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.validate.validateandresynch.f1
helpviewer_keywords:
- Validate Subscription dialog box
ms.assetid: 74bdf5e1-b886-4284-b5fb-332bf79ae083
caps.latest.revision: 19
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 1ec35a68110b658b505cb47324118af557b95d6c
ms.lasthandoff: 04/11/2017

---
# <a name="validate-subscription"></a>验证单个订阅
  可以使用 **“验证单个订阅”** 对话框，指定在下次运行订阅的合并代理时应对针对合并发布的订阅进行验证。 验证的结果显示在复制监视器中。 有关详细信息，请参阅 [Validate Data at the Subscriber](../../relational-databases/replication/validate-data-at-the-subscriber.md)。  
  
 也可以在 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 中右键单击某个发布，并单击 **“验证所有订阅”**来验证对合并发布的所有订阅。  
  
## <a name="options"></a>选项  
 **上次尝试验证的日期**  
 最后一个包含订阅验证（无论验证是否成功）的合并代理会话的日期。  
  
 **上次成功验证的日期**  
 最后一个包含成功订阅验证的合并代理会话的日期。  
  
 **验证此订阅**  
 选择此选项可验证订阅。  
  
 **选项**  
 单击此项可访问 **“订阅验证选项”** 对话框，使用此对话框可以指定是使用行计数验证还是使用二进制校验和验证。  
  
## <a name="see-also"></a>另请参阅  
 [验证已复制的数据](../../relational-databases/replication/validate-replicated-data.md)  
  
  