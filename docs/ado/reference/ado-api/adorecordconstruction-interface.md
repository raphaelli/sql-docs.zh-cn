---
title: ADORecordConstruction 接口 |Microsoft 文档
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
- ADORecordConstruction
helpviewer_keywords:
- ADORecordConstruction interface [ADO]
ms.assetid: 52a5429e-5829-455e-be3b-31f05cbecf2d
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 76a13ea05920d1a479734b26bdc57bedfe2d6817
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="adorecordconstruction-interface"></a>ADORecordConstruction 接口
**ADORecordConstruction**接口用于构造 ADO**记录**从 OLE DB 对象**行**C/c + + 应用程序中的对象。  
  
 此接口支持下列属性：  
  
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|[ParentRow](../../../ado/reference/ado-api/parentrow-property-ado.md)|只写。<br />设置 OLE DB 的容器**行**上此 ADO 对象**记录**对象。|  
|[行](../../../ado/reference/ado-api/row-property-ado.md)|读/写。<br />获取/设置 OLE DB**行**对象从/上此 ADO**记录**对象。|  
  
## <a name="methods"></a>方法  
 无。  
  
## <a name="events"></a>事件  
 无。  
  
## <a name="remarks"></a>注释  
 提供 OLE DB**行**对象 (`pRow`)，构造的 ADO**记录**对象 (`adoR`)，都可对以下三个基本操作：  
  
1.  创建 ADO**记录**对象：  
  
    ```  
    _RecordPtr adoR;  
    adoRs.CreateInstance(__uuidof(_Record));  
    ```  
  
2.  查询**IADORecordConstruction**接口**记录**对象：  
  
    ```  
    adoRecordConstructionPtr adoRConstruct=NULL;  
    adoR->QueryInterface(__uuidof(ADORecordConstruction),  
                        (void**)&adoRConstruct);  
    ```  
  
3.  调用**IADORecordConstruction::put_Row**属性方法以设置 OLE DB**行**上 ADO 对象**记录**对象：  
  
    ```  
    IUnknown *pUnk=NULL;  
    pRow->QueryInterface(IID_IUnknown, (void**)&pUnk);  
    adoRConstruct->put_Row(pUnk);  
    ```  
  
 所产生的**adoR**对象现在表示 ADO**记录**构造从 OLE DB 对象**行**对象。  
  
 ADO**记录**还可从 OLE DB 的容器构造对象**行**对象。  
  
## <a name="requirements"></a>需求  
 **版本：** ADO 2.0 及更高版本  
  
 **库：** msado15.dll  
  
 **UUID:** 00000567-0000-0010-8000-00AA006D2EA4
