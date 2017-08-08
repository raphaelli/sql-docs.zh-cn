---
title: "（除）(DMX) |Microsoft 文档"
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- DMX
helpviewer_keywords:
- / (divide)
- divide operator (/)
ms.assetid: 7afc06cd-054b-48c3-9c3c-9a0c17d15e63
caps.latest.revision: 14
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 8485c6e5cb68fcfd07f1ee812ba4c9a7035b1931
ms.contentlocale: zh-cn
ms.lasthandoff: 08/02/2017

---
# <a name="divide-dmx"></a>（除）(DMX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  执行算术运算，将一个数除以另一个数。  
  
## <a name="syntax"></a>語法  
  
```  
  
Dividend / Divisor  
```  
  
#### <a name="parameters"></a>Parameters  
 *被除数*  
 一个返回数值的有效数据挖掘扩展 (DMX) 表达式。  
  
 *除数*  
 一个返回数值的有效 DMX 表达式。  
  
## <a name="return-value"></a>返回值  
 与优先级较高的参数具有相同数据类型的值。  
  
## <a name="remarks"></a>注释  
 此运算符返回的值即为用第一个表达式除以第二个表达式所得的商。  
  
 两个表达式必须具有相同的数据类型，或者其中一个表达式必须能够隐式转换为另一个表达式的数据类型。 如果除数的计算结果为 Null 值，则该运算符将产生错误。 如果除数和被除数的计算结果均为 Null 值，则该运算符将返回 Null 值。  
  
## <a name="see-also"></a>另请参阅  
 [算术运算符 &#40; DMX &#41;](../dmx/operators-arithmetic.md)   
 [数据挖掘扩展插件 &#40; DMX &#41;运算符参考](../dmx/data-mining-extensions-dmx-operator-reference.md)   
 [运算符 &#40; DMX &#41;](../dmx/operators-dmx.md)   
 [除 &#40;SSIS 表达式 &#41;](../integration-services/expressions/divide-ssis-expression.md)   
 [&#40; 除 &#41;&#40;Transact SQL &#41;](../t-sql/language-elements/divide-transact-sql.md)  
  
  
