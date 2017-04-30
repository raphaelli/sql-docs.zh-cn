---
title: "计划 SQL Server 安装 | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 03/08/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- setup-install
ms.tgt_pltfrm: 
ms.topic: get-started-article
helpviewer_keywords:
- installing SQL Server, planning
ms.assetid: b1d56f2f-603f-48f2-b902-c715f14a6db9
caps.latest.revision: 36
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 72117bfd62b37633e2b815fb1c8014b48c63d2ab
ms.lasthandoff: 04/11/2017

---
# <a name="planning-a-sql-server-installation"></a>计划 SQL Server 安装
  若要安装 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]，请按下列步骤操作：  
  
-   查看 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安装的安装要求、系统配置检查和安全注意事项。  
  
-   运行 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安装程序以安装或升级到更高版本。 在升级前，请查看 [Upgrade to SQL Server 2016](../../database-engine/install-windows/upgrade-sql-server.md)。  
  
-   使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 实用工具配置 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。  
  
 无论使用哪种安装方法，您都需要作为个人或代表实体确认接受软件许可条款，除非您对于软件的使用受单独的协议（如 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 批量许可协议或与 ISV 或 OEM 之间的第三方协议）管辖。  
  
 将在安装程序用户界面中显示许可条款，供您审核审阅和接受。 使用 /Q 或 /QS 参数进行无人参与安装时，必须包含 /IAcceptSQLServerLicenseTerms 参数。 可以通过 [Microsoft Software License Terms](http://go.microsoft.com/fwlink/?LinkID=148209)（Microsoft 软件许可条款）单独查看许可条款。  
  
> [!NOTE]  
>  根据您接收软件的方式（例如，通过 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 批量许可），您对软件的使用可能受其他条款和条件约束。  
  
## <a name="in-this-section"></a>本节内容  
 [SQL Server 安装中的新增功能](../../sql-server/install/what-s-new-in-sql-server-installation.md)  
 本主题介绍有关这一版本的 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]中新增或改进的安装功能的详细信息。  
  
 [安装 SQL Server 2016 的硬件和软件要求](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)  
 本主题列出了安装和运行 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]安装的最低硬件和软件要求。  
  
 [安装 SQL Server 的安全注意事项](../../sql-server/install/security-considerations-for-a-sql-server-installation.md)  
 本主题介绍安装 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 前和安装 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]之后应考虑采用的一些最佳安全做法。  
  
 [配置 Windows 服务帐户和权限](../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md)  
 本主题介绍此 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]版本中服务的默认配置，以及可以在 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安装过程中以及安装之后设置的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 服务的配置选项。  
  
 [网络协议和网络库](../../sql-server/install/network-protocols-and-network-libraries.md)  
 本主题介绍这一版本的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]中网络协议的默认配置，以及可用的配置选项。  
  
 [使用 SQL Server 的多个版本和实例](../../sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md)  
 本主题介绍安装 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]的多个版本和实例时的注意事项。  
  
 [SQL Server 中的本地语言版本](../../sql-server/install/local-language-versions-in-sql-server.md)  
 本主题介绍了 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]的本地化版本。  
  
## <a name="related-sections"></a>相关章节  
 [安装 SQL Server 2016](../../database-engine/install-windows/install-sql-server.md)  
 本节概要介绍用于安装 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]的不同安装选项。  
  
 [安装 SQL Server 2016 商业智能功能](../../sql-server/install/install-sql-server-business-intelligence-features.md)  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安装文档中的本节说明如何安装属于 Microsoft BI 平台一部分的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 功能。  
  
 [Upgrade to SQL Server 2016](../../database-engine/install-windows/upgrade-sql-server.md)  
 本节概要说明如何将以前的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 版本的实例升级到 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]。  
  
 [卸载 SQL Server 2016](../../sql-server/install/uninstall-sql-server.md)  
 参照本节可以完全卸载 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 的现有实例，并且对系统进行准备以便您可以重新安装 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]。  
  
 [SQL Server 故障转移群集安装](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md)  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 安装文档中的本节介绍了如何安装和配置 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 故障转移群集。  
  
## <a name="see-also"></a>另请参阅  
 [从命令提示符安装 SQL Server 2016](../../database-engine/install-windows/install-sql-server-2016-from-the-command-prompt.md)   
 [高可用性解决方案 (SQL Server)](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md)   
 [安装故障转移群集前的准备工作](../../sql-server/failover-clusters/install/before-installing-failover-clustering.md)   
 [使用安装向导（安装程序）升级到 SQL Server 2016](../../database-engine/install-windows/upgrade-sql-server-using-the-installation-wizard-setup.md)  
  
  
