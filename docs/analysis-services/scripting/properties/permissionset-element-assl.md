---
title: PermissionSet 元素 (ASSL) |Microsoft 文档
ms.date: 5/8/2018
ms.prod: sql
ms.custom: assl
ms.reviewer: owend
ms.technology: analysis-services
ms.topic: reference
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2299f76822ae24eb2fee1085fc49836704ba275a
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="permissionset-element-assl"></a>PermissionSet 元素 (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  标识与关联的权限集[!INCLUDE[msCoName](../../../includes/msconame-md.md)].NET Framework 程序集。  
  
## <a name="syntax"></a>语法  
  
```xml  
  
<ClrAssembly>  
   ...  
   <PermissionSet>...</PermissionSet>  
  
</ClrAssembly>  
```  
  
## <a name="element-characteristics"></a>元素特征  
  
|特征|说明|  
|--------------------|-----------------|  
|数据类型和长度|String（枚举）|  
|默认值|*Safe*|  
|基数|0-1：可出现一次且仅出现一次的可选元素。|  
  
## <a name="element-relationships"></a>元素关系  
  
|关系|元素|  
|------------------|-------------|  
|父元素|[ClrAssembly](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md)|  
|子元素|无|  
  
## <a name="remarks"></a>備註  
 此元素的值限定为下表中列出的字符串之一。  
  
|值|Description|  
|-----------|-----------------|  
|*Safe*|只允许内部计算和本地数据访问。 *安全*是限制性最强的权限集。 程序集执行代码*安全*权限无法访问外部系统资源，例如文件、 网络、 环境变量或注册表。|  
|*外部访问*|*安全*，与访问外部系统资源，如文件、 网络、 环境变量和注册表的附加功能。|  
|*不受限制*|不受限制允许程序集不受限制地访问资源，在内部和外部[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。 代码中执行*不受限制的*程序集可以调用非托管的代码。|  
  
 对应于的允许值为枚举**PermissionSet**在分析管理对象 (AMO) 对象模型并<xref:Microsoft.AnalysisServices.PermissionSet>。  
  
## <a name="see-also"></a>另请参阅  
 [ComAssembly 数据类型 & #40;ASSL & #41;](../../../analysis-services/scripting/data-type/comassembly-data-type-assl.md)   
 [Assemblies 元素&#40;ASSL&#41;](../../../analysis-services/scripting/collections/assemblies-element-assl.md)   
 [数据库元素&#40;ASSL&#41;](../../../analysis-services/scripting/objects/database-element-assl.md)   
 [服务器元素 & #40;ASSL & #41;](../../../analysis-services/scripting/objects/server-element-assl.md)   
 [属性 & #40;ASSL & #41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
