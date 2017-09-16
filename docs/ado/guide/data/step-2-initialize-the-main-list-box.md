---
title: "步骤 2： 初始化主列表框 |Microsoft 文档"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1454493-1c86-46c2-ada8-d3c6fcdaf3c1
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: c291da043764d9599311704af86952eec47578b6
ms.contentlocale: zh-cn
ms.lasthandoff: 09/09/2017

---
# <a name="step-2-initialize-the-main-list-box"></a>步骤 2： 初始化主列表框
若要声明全局记录和记录集对象，请将下面的代码插入 （常规） （声明） form1:  
  
```  
Option Explicit  
Dim grec As Record  
Dim grs As Recordset  
```  
  
 此代码声明将使用更高版本在此方案中的记录和记录集对象的全局对象引用。  
  
## <a name="to-connect-to-a-url-and-populate-lstmain"></a>若要连接到的 URL 并填充 lstMain  
 下面的代码 form1 插入窗体加载事件处理程序中：  
  
```  
Private Sub Form_Load()  
    Set grec = New Record  
    Set grs = New Recordset  
    grec.Open "", "URL=http://servername/foldername/", , _  
        adOpenIfExists Or adCreateCollection  
    Set grs = grec.GetChildren  
    While Not grs.EOF  
        lstMain.AddItem grs(0)  
        grs.MoveNext  
    Wend  
End Sub  
```  
  
 此代码实例化的全局的记录和记录集对象。 所记录的对象， `grec`，将打开，其中指定为 ActiveConnection 的 URL。 如果 URL 存在，则打开它;如果它尚不存在，则创建它。 请注意，应从你的环境中替换"http://servername/foldername/"与有效的 URL。  
  
 记录集对象， `grs`，在该记录的子级上打开`grec`。 然后`lstMain`用于发布到 URL 的资源的文件名称填充。  
  
## <a name="see-also"></a>另请参阅  
 [Internet 发布方案](../../../ado/guide/data/internet-publishing-scenario.md)   
 [步骤 1： 设置 Visual Basic 项目](../../../ado/guide/data/step-1-set-up-the-visual-basic-project.md)   
 [步骤 3： 在字段列表框中填充](../../../ado/guide/data/step-3-populate-the-fields-list-box.md)