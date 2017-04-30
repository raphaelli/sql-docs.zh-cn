---
title: "指定第一个和最后一个触发器 | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-dml
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- first triggers [SQL Server]
- last triggers
- DML triggers, first or last triggers
- INSTEAD OF triggers
- AFTER triggers
ms.assetid: 9e6c7684-3dd3-46bb-b7be-523b33fae4d5
caps.latest.revision: 24
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 99935796043bf8ea14c32a2f98867ca2c7612a2d
ms.lasthandoff: 04/11/2017

---
# <a name="specify-first-and-last-triggers"></a>指定第一个和最后一个触发器
  可将与表关联的 AFTER 触发器之一指定为执行每个 INSERT、DELETE 和 UPDATE 触发操作时激发的第一个或最后一个 AFTER 触发器。 在第一个和最后一个触发器之间激发的 AFTER 触发器将按未定义的顺序执行。  
  
 若要指定 AFTER 触发器的顺序，请使用 **sp_settriggerorder** 存储过程。 **sp_settriggerorder** 有下列选项。  
  
|选项|说明|  
|------------|-----------------|  
|**第一个**|指定 DML 触发器是执行触发操作时激发的第一个 AFTER 触发器。|  
|**上一次**|指定 DML 触发器是执行触发操作时激发的最后一个 AFTER 触发器。|  
|**无**|指定不按特定的顺序激发 DML 触发器。 主要用于将某个触发器重置为第一个或最后一个触发器。|  
  
 以下示例说明如何使用 **sp_settriggerorder**：  
  
```  
sp_settriggerorder @triggername = 'MyTrigger', @order = 'first', @stmttype = 'UPDATE'  
```  
  
> [!IMPORTANT]  
>  第一个和最后一个触发器必须是两个不同的 DML 触发器。  
  
 可以同时为表定义 INSERT、UPDATE 和 DELETE 触发器。 每个语句类型都可以有其自己的第一个和最后一个触发器，但它们不能是相同的触发器。  
  
 如果为某个表定义的第一个或最后一个触发器不包括触发操作，如 FOR UPDATE、FOR DELETE 或 FOR INSERT，则缺少的操作将没有第一个或最后一个触发器。  
  
 不能将 INSTEAD OF 触发器指定为第一个或最后一个触发器。 在对基础表进行更新前激发 INSTEAD OF 触发器。 如果由 INSTEAD OF 触发器对基础表进行更新，这些更新将在激发为表定义的任何 AFTER 触发器之前发生。 例如，如果视图上的一个 INSTEAD OF INSERT 触发器将数据插入某个基表，而基表本身包含一个 INSTEAD OF INSERT 触发器和三个 AFTER INSERT 触发器，则会激发基表上的 INSTEAD OF INSERT 触发器而不发生插入操作，而基表上 AFTER 触发器将在执行所有插入操作后激发。 有关详细信息，请参阅 [DML Triggers](../../relational-databases/triggers/dml-triggers.md)。  
  
 如果 ALTER TRIGGER 语句更改了第一个或最后一个触发器，则会删除 **First** 或 **Last** 属性并将顺序值设置为 **None**。 必须使用 **sp_settriggerorder**来重置顺序。  
  
 OBJECTPROPERTY 函数使用属性 **ExecIsFirstTrigger** 和 **ExecIsLastTrigger**来报告某个触发器是第一个还是最后一个触发器。  
  
 复制将为包含在立即更新订阅或排队更新订阅中的任意表自动生成第一个触发器。 复制要求其触发器为第一个触发器。 在尝试将带有第一个触发器的表包含在立即更新订阅或排队更新订阅中时，复制将引发错误。 如果在表已经包含在订阅中之后尝试使某个触发器成为第一个触发器， **sp_settriggerorder** 将返回错误。 如果在复制触发器上使用 ALTER，或使用 **sp_settriggerorder** 将复制触发器更改为最后一个触发器或无触发器，订阅将无法正常工作。  
  
## <a name="see-also"></a>另请参阅  
 [OBJECTPROPERTY (Transact-SQL)](../../t-sql/functions/objectproperty-transact-sql.md)   
 [sp_settriggerorder (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-settriggerorder-transact-sql.md)  
  
  