---
title: InstanceName 属性 （ClientSettingsGeneralFlag 类） |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: wmi
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- InstanceName Property (ClientSettingsGeneralFlag Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- InstanceName property
ms.assetid: 7de3c043-6c5a-4663-b960-a80492444a99
caps.latest.revision: 14
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: 7fd5fc8217fcddb82ea316b929cb0b063f0448b8
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="instancename-property-clientsettingsgeneralflag-class"></a>InstanceName 属性（ClientSettingsGeneralFlag 类）
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
  获取 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 客户端实例的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
object.InstanceName [= value]  
```  
  
## <a name="parts"></a>组成部分  
 *对象*  
 一个表示服务器设置的常规标志的 [ClientSettingsGeneralFlag 类](../../../relational-databases/wmi-provider-configuration-classes/clientsettingsgeneralflag-class/clientsettingsgeneralflag-class.md) 对象。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 一个指定 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 客户端实例的名称的字符串值。  
  
## <a name="remarks"></a>注释  
  
## <a name="see-also"></a>另请参阅  
 [配置客户端协议](http://technet.microsoft.com/library/ms181035.aspx)  
  
  
