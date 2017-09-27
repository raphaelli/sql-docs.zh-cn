---
title: "catalog.executions （SSISDB 数据库） |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- executions view [Integration Services]
- catalog.executions view [Integration Services]
ms.assetid: 879f13b0-331d-4dee-a079-edfaca11ae5b
caps.latest.revision: 32
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 5e60664352054cd8f62250cc7c6b8082e84f607f
ms.contentlocale: zh-cn
ms.lasthandoff: 09/26/2017

---
# <a name="catalogexecutions-ssisdb-database"></a>catalog.executions（SSISDB 数据库）
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  在 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] 目录中显示包执行的实例。 通过“执行包”任务执行的包在同一个执行实例中作为父包运行。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|execution_id|**bigint**|唯一标识符 (ID) 的实例的执行。|  
|folder_name|**sysname(nvarchar(128))**|包含项目的文件夹的名称。|  
|文件的内容|**sysname(nvarchar(128))**|项目的名称。|  
|package_name|**nvarchar(260)**|在执行过程中启动的第一个包的名称。|  
|reference_id|**bigint**|执行实例引用的环境。|  
|reference_type|**char （1)**|指示环境是可以位于与项目相同的文件夹中（相对引用），还是位于其他文件夹中（绝对引用）中。 如果值为 `R`，则通过使用相对引用定位环境。 如果值为 `A`，则通过使用绝对引用定位环境。|  
|environment_folder_name|**nvarchar （128)**|包含环境的文件夹的名称。|  
|environment_name|**nvarchar （128)**|在执行过程中引用的环境的名称。|  
|project_lsn|**bigint**|与执行实例对应的项目版本。 此数字不保证是按顺序排列的。|  
|executed_as_sid|**varbinary(85)**|启动执行实例的用户的 SID。|  
|executed_as_name|**nvarchar （128)**|用于启动执行实例的数据库主体的名称。|  
|use32bitruntime|**bit**|指示是否应使用 32 位运行时在 64 位操作系统上运行包。 当值是`1`，默认情况下，执行与 32 位运行时。 如果值为 `0`，则使用 64 位运行库来运行执行过程。|  
|object_type|**int**|对象的类型。 该对象可能是一个项目 (`20`) 或包 (`30`)。|  
|object_id|**bigint**|操作影响的对象的 ID。|  
|status|**int**|操作的状态。 可能的值是已创建 (`1`)、正在运行 (`2`)、已取消 (`3`)、失败 (`4`)、挂起 (`5`)、意外结束 (`6`)、已成功 (`7`)、停止 (`8`) 和已完成 (`9`)。|  
|start_time|**datetimeoffset**|启动执行实例的时间。|  
|end_time|**datetimeoffsset**|结束执行实例的时间。|  
|caller_sid|**varbinary(85)**|如果是使用 Windows 身份验证进行登录的，则为用户的安全 ID (SID)。|  
|呼叫|**nvarchar （128)**|执行备份操作的帐户的名称。|  
|process_id|**int**|外部进程的进程 ID（如果适用）。|  
|stopped_by_sid|**varbinary(85)**|停止执行实例的用户的安全 ID (SID)。|  
|stopped_by_name|**nvarchar （128)**|停止执行实例的用户名。|  
|total_physical_memory_kb|**bigint**|开始执行时服务器上物理内存的总量 (MB)。|  
|available_physical_memory_kb|**bigint**|开始执行时服务器上可用的物理内存 (MB)。|  
|total_page_file_kb|**bigint**|开始执行时服务器上页内存的总量 (MB)。|  
|available_page_file_kb|**bigint**|开始执行时服务器上可用的页内存 (MB)。|  
|cpu_count|**int**|开始执行时服务器上逻辑 CPU 的数量。|  
|server_name|**nvarchar （128)**|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 指定实例的 Windows 服务器和实例信息。|  
|machine_name|**nvarchar （128)**|运行服务器实例的计算机名称。|  
|dump_id|**uniqueidentifier**|执行转储的 ID。|  
  
## <a name="remarks"></a>注释  
 此视图对于目录中的每个执行实例显示一行。  
  
## <a name="permissions"></a>Permissions  
 此视图需要下列权限之一：  
  
-   针对执行实例的 READ 权限  
  
-   成员资格**ssis_admin**数据库角色  
  
-   成员资格**sysadmin**服务器角色  
  
> [!NOTE]  
>  将实施行级安全性；只显示您有权查看的行。  
  
  