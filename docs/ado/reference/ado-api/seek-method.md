---
title: 查找方法 |Microsoft 文档
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
- Recordset21::Seek
- Recordset21::raw_Seek
helpviewer_keywords:
- Seek method [ADO]
ms.assetid: 129293d2-19d3-4940-bf64-483ee72fb4a1
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 59dcdd3426c39449b3d2348218aa7794a75c0474
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="seek-method"></a>查找方法
搜索的索引[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)快速找到的行与匹配的指定的值，并更改为该行的当前行位置。  
  
## <a name="syntax"></a>语法  
  
```  
  
recordset.Seek KeyValues, SeekOption  
```  
  
#### <a name="parameters"></a>Parameters  
 *KeyValues*  
 数组**Variant**值。 索引包含一个或多个列，该数组包含要针对每个相应的列进行比较的值。  
  
 *SeekOption*  
 A [SeekEnum](../../../ado/reference/ado-api/seekenum.md)值，该值指定要进行索引的列和相应之间的比较类型*KeyValues*。  
  
## <a name="remarks"></a>注释  
 使用**Seek**方法结合[索引](../../../ado/reference/ado-api/index-property.md)如果基础提供程序上支持索引属性**记录集**对象。 使用[支持](../../../ado/reference/ado-api/supports-method.md)**(adSeek)** 方法，以确定基础提供程序是否支持**Seek**，和**Supports(adIndex)** 若要确定此提供程序是否支持索引的方法。 (例如， [OLE DB Provider for Microsoft Jet](../../../ado/guide/appendixes/microsoft-ole-db-provider-for-microsoft-jet.md)支持**Seek**和**索引**。)  
  
 如果**Seek**功能不查找所需的行，没有错误发生，以及行是否定位在的结尾**记录集**。 设置**索引**为之前执行此方法所需索引的属性。  
  
 此方法仅支持服务器端游标。 查找时不支持**记录集**对象的[CursorLocation](../../../ado/reference/ado-api/cursorlocation-property-ado.md)属性值是**adUseClient**。  
  
 此方法只能时使用**记录集**对象使用打开[CommandTypeEnum](../../../ado/reference/ado-api/commandtypeenum.md)值**adCmdTableDirect**。  
  
## <a name="applies-to"></a>适用范围  
 [记录集对象 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>另请参阅  
 [查找方法和索引的属性示例 (VB)](../../../ado/reference/ado-api/seek-method-and-index-property-example-vb.md)   
 [查找方法和索引的属性示例 （VC + +）](../../../ado/reference/ado-api/seek-method-and-index-property-example-vc.md)   
 [Find 方法 (ADO)](../../../ado/reference/ado-api/find-method-ado.md)   
 [Index 属性](../../../ado/reference/ado-api/index-property.md)
