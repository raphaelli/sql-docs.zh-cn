---
title: "复制代理概述 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "分发代理"
  - "代理 [SQL Server 复制]"
  - "队列读取器代理, 关于队列读取器代理"
  - "队列读取器代理"
  - "合并代理, 关于合并代理"
  - "日志读取器代理, 关于日志读取器代理"
  - "复制 [SQL Server], 代理和配置文件"
  - "日志读取器代理"
  - "分发代理, 关于分发代理"
  - "代理 [SQL Server 复制], 关于代理"
  - "合并代理"
  - "快照代理, 关于快照代理"
  - "快照代理"
ms.assetid: a35ecd7d-f130-483c-87e3-ddc8927bb91b
caps.latest.revision: 42
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 42
---
# 复制代理概述
  复制使用许多称为“代理”的独立程序执行与跟踪更改和分发数据关联的任务。 默认情况下，复制代理作为 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 代理安排的作业运行，必须运行 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 代理，这些作业才能运行。 复制代理还可以从命令行以及由使用复制管理对象 (RMO) 的应用程序运行。 可以从 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 复制监视器和 [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]对复制代理进行管理。  
  
## SQL Server 代理  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 代理保存并安排复制中使用的代理，并提供运行复制代理的简便方法。 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 代理还控制和监视复制之外的操作。 有关详细信息，请参阅 [Configure SQL Server Agent](../../../ssms/agent/configure-sql-server-agent.md)。  
  
> [!IMPORTANT]  
>  默认情况下，安装完 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 之后， [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 代理服务处于禁用状态，除非在安装过程中明确选择自动启动该服务。 有关启动的详细信息 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 代理服务，请参阅 [启动、 停止或暂停 SQL Server 代理服务](../../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)。  
  
## 快照代理  
 快照代理通常与各种类型的复制一起使用。 快照代理准备已发布表的架构和初始数据文件以及其他对象、存储快照文件并记录分发数据库中的同步信息。 快照代理在分发服务器上运行。 有关详细信息，请参阅 [Replication Snapshot Agent](../../../relational-databases/replication/agents/replication-snapshot-agent.md)。  
  
## 日志读取器代理  
 日志读取器代理与事务复制一起使用。 它将发布服务器上的事务日志中标记为复制的事务移至分发数据库中。 使用事务复制发布的每个数据库都有自己的日志读取器代理，该代理运行于分发服务器上并与发布服务器连接（分发服务器与发布服务器可以是同一台计算机）。 有关详细信息，请参阅 [Replication Log Reader Agent](../../../relational-databases/replication/agents/replication-log-reader-agent.md)。  
  
## 分发代理  
 分发代理与快照复制和事务复制一起使用。 它将初始快照应用于订阅服务器，并将分发数据库中保存的事务移至订阅服务器。 分发代理既可以运行于分发服务器（对于推送订阅），也可运行于订阅服务器（对于请求订阅）。 有关详细信息，请参阅 [Replication Distribution Agent](../../../relational-databases/replication/agents/replication-distribution-agent.md)。  
  
## 合并代理  
 合并代理与合并复制一起使用。 它将初始快照应用于订阅服务器，并移动和协调所发生的增量数据更改。 每个合并订阅都有自己的合并代理，该代理同时连接到发布服务器和订阅服务器并对它们进行更新。 合并代理既可以运行于分发服务器（对于推送订阅），也可以运行于订阅服务器（对于请求订阅）。 默认情况下，合并代理将订阅服务器上的更改上载到发布服务器，然后将发布服务器上的更改下载到订阅服务器。 有关详细信息，请参阅 [Replication Merge Agent](../../../relational-databases/replication/agents/replication-merge-agent.md)。  
  
## 队列读取器代理  
 队列读取器代理与包含排队更新选项的事务复制一起使用。 该代理运行于分发服务器，并将订阅服务器上所做更改移回至发布服务器。 与分发代理和合并代理不同，只有一个队列读取器代理的实例为给定分发数据库的所有发布服务器和发布提供服务。 有关队列读取器代理的详细信息，请参阅 [Replication Queue Reader Agent](../../../relational-databases/replication/agents/replication-queue-reader-agent.md)。 有关可更新订阅的详细信息，请参阅 [Updatable Subscriptions for Transactional Replication](../../../relational-databases/replication/transactional/updatable-subscriptions-for-transactional-replication.md)。  
  
## 复制维护作业  
 复制包含许多执行计划维护和按需维护的维护作业。 有关详细信息，请参阅 [复制代理管理](../../../relational-databases/replication/agents/replication-agent-administration.md)。  
  
## 另请参阅  
 [启动和停止复制代理 & #40;SQL Server Management Studio & #41;](../../../relational-databases/replication/agents/start-and-stop-a-replication-agent-sql-server-management-studio.md)   
 [运行复制维护作业 （&） #40;SQL Server Management Studio & #41;](../../../relational-databases/replication/administration/run-replication-maintenance-jobs-sql-server-management-studio.md)   
 [复制代理可执行文件概念](../../../relational-databases/replication/concepts/replication-agent-executables-concepts.md)   
 [复制代理管理](../../../relational-databases/replication/agents/replication-agent-administration.md)  
  
  