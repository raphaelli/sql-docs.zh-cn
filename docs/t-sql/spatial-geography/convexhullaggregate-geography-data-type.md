---
title: "ConvexHullAggregate (geography 数据类型) |Microsoft 文档"
ms.custom: 
ms.date: 07/30/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ConvexHullAggregate_TSQL
- ConvexHullAggregate
dev_langs:
- TSQL
helpviewer_keywords:
- ConvexHullAggregate method (geography)
ms.assetid: 21784c66-2725-471b-9e2d-a8c2e3695197
caps.latest.revision: 11
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5a2f112e58838c754b946bdf3870fea31125a813
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="convexhullaggregate-geography-data-type"></a>ConvexHullAggregate（geography 数据类型）
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

返回一组给定的凸包**geography**对象。
  
## <a name="syntax"></a>语法  
  
```  
  
ConvexHullAggregate ( geography_operand )  
```  
  
## <a name="arguments"></a>参数  
 *geography_operand*  
 是**geography**类型表示的一组表列**geography**对象。  
  
## <a name="return-types"></a>返回类型  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]返回类型：**地理位置**  
  
## <a name="exception"></a>异常  
 在输入值无效时引发 `FormatException`。 请参阅[STIsValid &#40; geography 数据类型 &#41;](../../t-sql/spatial-geography/stisvalid-geography-data-type.md)  
  
## <a name="remarks"></a>注释  
 方法返回**null**时输入为空或输入具有不同 Srid。 请参阅[空间引用标识符 &#40;Srid &#41;](../../relational-databases/spatial/spatial-reference-identifiers-srids.md)  
  
 方法将忽略**null**输入。  
  
> [!NOTE]  
>  方法返回**null**如果所有输入的值为**null**。  
  
## <a name="examples"></a>示例  
 下面的示例返回的一套凸包**geography**对象。  
  
 `USE AdventureWorks2012`  
  
 `GO`  
  
 `SELECT geography::ConvexHullAggregate(SpatialLocation).ToString() AS SpatialLocation`  
  
 `FROM Person.Address`  
  
 `WHERE City LIKE ('Bothell')`  
  
## <a name="see-also"></a>另请参阅  
 [扩展静态 Geography 方法](../../t-sql/spatial-geography/extended-static-geography-methods.md)  
  
  
