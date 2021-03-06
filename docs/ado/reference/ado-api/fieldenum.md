---
title: FieldEnum |Microsoft 文档
ms.prod: sql
ms.prod_service: connectivity
ms.component: ado
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- FieldEnum
helpviewer_keywords:
- FieldEnum enumeration [ADO]
ms.assetid: be4eda13-d4e4-4d6b-bb0d-3310b0a96fc2
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: e2d38463ec703335530e33017f77b46cf91c68f0
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="fieldenum"></a>FieldEnum
指定在中引用的特殊字段[记录](../../../ado/reference/ado-api/record-object-ado.md)对象的[字段](../../../ado/reference/ado-api/fields-collection-ado.md)集合。  
  
## <a name="remarks"></a>注释  
 这些常量提供访问与关联的特殊字段的"快捷方式"**记录**。 检索[字段](../../../ado/reference/ado-api/field-object.md)对象**字段**集合，然后获取其内容与**字段**对象的[值](../../../ado/reference/ado-api/value-property-ado.md)属性。  
  
|常量|“值”|Description|  
|--------------|-----------|-----------------|  
|**adDefaultStream**|-1|引用包含默认值的字段[流](../../../ado/reference/ado-api/stream-object-ado.md)与关联的对象**记录**。|  
|**adRecordURL**|-2|引用包含当前的绝对 URL 字符串的字段**记录**。|
