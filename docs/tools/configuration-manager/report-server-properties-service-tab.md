---
title: 报表服务器属性 （服务选项卡） |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.suite: sql
ms.technology: configuration
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 2a2e1dbf-02b9-4893-aaf0-c0e4a2c9b4f9
caps.latest.revision: 22
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: e69f6b4cbe72ccb635f573fb01bc84508a18de78
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MTE
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="report-server-properties-service-tab"></a>报表服务器属性（“服务”选项卡）
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]
  此服务为 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 报表服务器服务。 如果属性值呈浅灰色，则不能使用此应用程序更改。  
  
## <a name="options"></a>“常规”  
 **二进制路径**  
 显示此服务所使用的程序文件的位置。  
  
 **错误控制**  
 1 指示“SERVICE_ERROR_NORMAL”。 如果在计算机启动过程中无法启动该服务，则启动程序会记录该错误并显示一个弹出消息框，但仍会继续执行启动操作。 此值不能更改。  
  
 **退出代码**  
 当发生错误时，错误号显示在此信息框中。 您可以通过在 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 知识库中搜索该号码获取相关信息来排除故障，或将该错误号提供给技术支持人员以获得帮助。  
  
 **Host Name**  
 显示运行全文搜索的计算机或群集的名称。  
  
 **名称**  
 指示该服务的显示名称。  
  
 **进程 ID**  
 显示 [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 进程 ID。  
  
 **SQL 服务类型**  
 用于调用进程的服务的类型。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安装有多种服务。  
  
 **启动模式**  
 对此服务设置以下选项：  
  
-   手动：计算机启动时，此服务不自动启动。 您必须使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 配置管理器或其他工具来启动该服务。  
  
-   自动：计算机启动时，此服务将尝试启动。  
  
-   已禁用：此服务无法启动。  
  
 **State**  
 指示此服务是正在运行、已停止还是已禁用。  
  
## <a name="see-also"></a>另请参阅  
 [SQL Server 服务](../../tools/configuration-manager/sql-server-services.md)  
  
  
