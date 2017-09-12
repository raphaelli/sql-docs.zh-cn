---
title: "密钥元素 (XMLA) |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Key Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#Key
- urn:schemas-microsoft-com:xml-analysis#Key
- microsoft.xml.analysis.key
helpviewer_keywords:
- Key element
ms.assetid: 09d3cd48-49f7-4b58-b8bb-ca75b81bb02f
caps.latest.revision: 12
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 00c7e159e919afe608a9d55c70485592c4b7003d
ms.contentlocale: zh-cn
ms.lasthandoff: 09/01/2017

---
# <a name="key-element-xmla"></a>Key 元素 (XMLA)
  包含属性成员的成员键值。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<Keys>  
   ...  
   <Key>...</Key>  
   ...  
</Keys>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|说明|  
|--------------------|-----------------|  
|数据类型和长度|Any|  
|默认值|无|  
|基数|0-n：可多次出现的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[密钥](../../../analysis-services/xmla/xml-elements-properties/keys-element-xmla.md)|  
|子元素|无|  
  
## <a name="remarks"></a>注释  
 此元素使用的数据类型应与指定属性的相应键列的数据类型相匹配。 如果**密钥**元素未指定父**属性**元素， **AttributeName**和**名称**中指定的元素父**属性**元素用于标识要修改的属性成员。  
  
## <a name="see-also"></a>另请参阅  
 [Attribute 元素 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/attribute-element-xmla.md)   
 [AttributeName 元素 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/attributename-element-xmla.md)   
 [删除元素 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/drop-element-xmla.md)   
 [插入元素 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md)   
 [KeyColumn 元素 &#40;ASSL &#41;](../../../analysis-services/scripting/objects/keycolumn-element-assl.md)   
 [更新元素 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md)   
 [其中元素 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/where-element-xmla.md)   
 [属性 &#40;XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  