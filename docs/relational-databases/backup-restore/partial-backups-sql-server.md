---
title: "部分备份 (SQL Server) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-backup-restore"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "完整备份 [SQL Server]"
  - "部分备份 [SQL Server]"
  - "READ_WRITE_FILEGROUPS 选项"
  - "数据库备份 [SQL Server], 关于备份数据库"
ms.assetid: fe6b6bb1-38d0-46c4-bab8-31df14e8999c
caps.latest.revision: 46
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 46
---
# 部分备份 (SQL Server)
  所有 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 恢复模式都支持部分备份，因此，本主题与所有 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 数据库相关。 但是，部分备份用于简单恢复模式中，旨在提高对非常大的数据库（包含一个或多个只读文件组）进行备份的灵活性。  
  
 部分备份在希望不包括只读文件组时非常有用。 “部分备份”  与完整数据库备份类似，但部分备份不包含所有文件组。 而对于读写数据库，部分备份包含主文件组、每个读写文件组以及（可选）一个或多个只读文件中的数据。 只读数据库的部分备份仅包含主文件组。  
  
> [!NOTE]  
>  如果部分备份后将只读数据库更改为读/写，则可能出现部分备份中所没有的读/写辅助文件组。 在这种情况下，如果尝试执行部分差异备份，则备份将失败。 在执行数据库的部分差异备份之前，必须先执行其他部分备份。 新的部分备份包含每个读/写辅助文件组，并可用作部分差异备份的基准。  
  
 只读文件组的文件备份可以与部分备份一起使用。 有关文件备份的信息，请参阅[完整文件备份 (SQL Server)](../../relational-databases/backup-restore/full-file-backups-sql-server.md)。  
  
 部分备份可用作部分差异备份的“差异基准”  。 有关详细信息，请参阅[差异备份 (SQL Server)](../../relational-databases/backup-restore/differential-backups-sql-server.md)。  
  
##  <a name="RelatedTasks"></a> 相关任务  
  
> [!NOTE]  
>  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 或维护计划向导不支持部分备份。  
  
 **创建部分备份**  
  
-   [BACKUP (Transact-SQL)](../../t-sql/statements/backup-transact-sql.md)（READ_WRITE_FILEGROUPS；FILEGROUP 选项，如果需要）  
  
 **在还原序列中使用部分备份**  
  
-   [示例：数据库的段落还原（简单恢复模式）](../../relational-databases/backup-restore/example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [示例：仅对某些文件组进行段落还原（简单恢复模式）](../../relational-databases/backup-restore/example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
## 另请参阅  
 [备份概述 (SQL Server)](../../relational-databases/backup-restore/backup-overview-sql-server.md)   
 [文件还原（简单恢复模式）](../../relational-databases/backup-restore/file-restores-simple-recovery-model.md)   
 [段落还原 (SQL Server)](../../relational-databases/backup-restore/piecemeal-restores-sql-server.md)  
  
  