---
title: "sysmergepartitioninfoview (Transact SQL) |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-views
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- sysmergepartitioninfoview
- sysmergepartitioninfoview_TSQL
dev_langs: TSQL
helpviewer_keywords: sysmergepartitioninfoview view
ms.assetid: 714e2935-1bc7-4901-aea2-64b1bbda03d6
caps.latest.revision: "16"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4a6c4dab4fd8f840d4c646bb1b9ec07a38da275a
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="sysmergepartitioninfoview-transact-sql"></a>sysmergepartitioninfoview (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **Sysmergepartitioninfoview**视图将显示分区的表项目的信息。 此视图存储在发布服务器的发布数据库以及订阅服务器的订阅数据库中。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**名称**|**sysname**|项目的名称。|  
|**type**|**tinyint**|指示项目类型，可以为下列类型之一：<br /><br /> **0x0a** = 表。<br /><br /> **0x20** = 仅限过程架构。<br /><br /> **0x40** = 仅限视图架构或仅限索引的视图架构。<br /><br /> **0x80** = 仅限函数架构。|  
|**objid**|**int**|已发布对象的标识符。|  
|**sync_objid**|**int**|表示同步数据集的视图的对象 ID。|  
|**view_type**|**tinyint**|视图类型：<br /><br /> **0** = 不是视图; 使用所有基对象。<br /><br /> **1** = 永久视图。<br /><br /> **2** = 临时视图。|  
|**artid**|**uniqueidentifier**|给定项目的唯一标识号。|  
|**说明**|**nvarchar(255)**|项目的简要说明。|  
|**pre_creation_command**|**tinyint**|在订阅数据库中创建项目时将执行的默认操作：<br /><br /> **0** = none-如果订阅服务器上已存在表，不执行任何操作。<br /><br /> **1** = drop-将表放置在重新创建它。<br /><br /> **2** = delete-删除基于子集筛选器中的 WHERE 子句的问题。<br /><br /> **3** = Truncate-2，但删除页，而不是行相同。 不过，不要使用 WHERE 子句。|  
|**pubid**|**uniqueidentifier**|当前项目所属发布的 ID。|  
|**别名**|**int**|项目标识的别名映射。|  
|**column_tracking**|**int**|指示是否为项目执行列跟踪。|  
|**status**|**tinyint**|指示项目的状态，可以为下列状态之一：<br /><br /> **1** = Unsynced-用于发布的表的初始处理脚本将运行的下次运行快照代理。<br /><br /> **2** = 活动-用于发布的表的初始处理脚本已运行。|  
|**conflict_table**|**sysname**|包含当前项目冲突记录的本地表的名称。 该表仅用于提供信息，其内容可以由自定义冲突解决例程修改或删除，或直接由系统管理员修改或删除。|  
|**creation_script**|**nvarchar(255)**|此项目的创建脚本。|  
|**conflict_script**|**nvarchar(255)**|此项目的冲突脚本。|  
|**article_resolver**|**nvarchar(255)**|该项目的冲突解决程序。|  
|**ins_conflict_proc**|**sysname**|用于向冲突表写入冲突信息的过程。|  
|**insert_proc**|**sysname**|用于在同步过程中插入行的过程。|  
|**update_proc**|**sysname**|用于在同步过程中更新行的过程。|  
|**select_proc**|**sysname**|自动生成的存储过程的名称，合并代理使用该存储过程完成锁定并查找项目的行和列。|  
|**metadata_select_proc**|**sysname**|自动生成的存储过程的名称，该存储过程用于访问合并复制系统表中的元数据。|  
|**delete_proc**|**sysname**|用于在同步过程中删除行的过程。|  
|**schema_option**|**binary （8)**|对于指定的项目的架构生成选项的位图。 有关支持*schema_option*值，请参阅[sp_addmergearticle &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql.md).|  
|**destination_object**|**sysname**|在订阅服务器上创建的表的名称。|  
|**destination_owner**|**sysname**|目标对象的所有者的名称。|  
|**resolver_clsid**|**nvarchar(50)**|自定义冲突解决程序的 ID。 对于业务逻辑处理程序，该值为 NULL。|  
|**subset_filterclause**|**nvarchar(1000)**|此项目的筛选子句。|  
|**missing_col_count**|**int**|项目中缺少的已发布列数。|  
|**missing_cols**|**varbinary(128)**|用于说明项目中的缺少列的位图。|  
|**excluded_cols**|**varbinary(128)**|已从项目中排除的列的位图。|  
|**excluded_col_count**|**int**|从项目中排除的列数。|  
|**列**|**varbinary(128)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**deleted_cols**|**varbinary(128)**|用于说明从项目中删除的列的位图。|  
|**resolver_info**|**nvarchar(255)**|存储自定义冲突解决程序所需的其他信息。|  
|**view_sel_proc**|**nvarchar(290)**|存储过程的名称，合并代理使用该存储过程初始填充动态筛选发布中的项目，并枚举在任何筛选发布中的已更改行。|  
|**gen_cur**|**bigint**|生成项目基表的本地更改数。|  
|**vertical_partition**|**int**|指定是否对表项目启用列筛选。 **0**指示没有垂直筛选并发布所有列。|  
|**identity_support**|**int**|指定是否启用自动标识范围处理。 **1**意味着处理标识范围是否启用了，和**0**意味着没有任何标识范围支持。|  
|**before_image_objid**|**int**|跟踪表对象 ID。 当已对发布启用分区更改优化时，跟踪表将包含某些键列值。|  
|**before_view_objid**|**int**|视图表的对象 ID。 视图所在的表用于在删除或更新行之前跟踪行是否属于特定的订阅服务器。 仅当对发布启用了分区更改优化时才适用。|  
|**verify_resolver_signature**|**int**|指定在合并复制中使用冲突解决程序之前是否验证数字签名：<br /><br /> **0** = 不验证签名。<br /><br /> **1** = 验证签名以确定它是否来自可靠来源。|  
|**allow_interactive_resolver**|**bit**|指定是否对项目启用交互式冲突解决程序。 **1**意味着，可以在文章上使用交互式冲突解决程序。|  
|**fast_multicol_updateproc**|**bit**|指定是否已启用合并代理来使用一条 UPDATE 语句在同一行的多个列中应用更改。<br /><br /> **0** = 每个列的独立更新更改的问题。<br /><br /> **1** = 颁发 on UPDATE 语句，这会导致更新发生在一个语句中的多个列。|  
|**check_permissions**|**int**|将表级权限的位图验证合并代理将更改应用到发布服务器的时。 *check_permissions*可以具有这些值之一：<br /><br /> **0x00** = 则不检查权限。<br /><br /> **0x10** = 可以上载发布服务器之前进行插入时，在订阅服务器上的权限的检查。<br /><br /> **0x20** = 检查发布服务器上的权限，可以上载订阅服务器上所做的更新之前。<br /><br /> **0x40** = 检查发布服务器上的权限，可以上载订阅服务器上的 delete 操作之前。|  
|**maxversion_at_cleanup**|**int**|合并代理下次运行时清除的最大生成。|  
|**processing_order**|**int**|指示合并发布; 中的项目的处理顺序其中的一个值**0**指示文章是无序的并且从最低到最高值的顺序处理项目。 如果两个项目具有相同值，将对其进行并发处理。 有关详细信息，请参阅[指定合并项目的处理顺序](../../relational-databases/replication/merge/specify-the-processing-order-of-merge-articles.md)。|  
|**upload_options**|**tinyint**|定义是否可以在订阅服务器上进行更改或从订阅服务器上载更改，可以为下列值之一：<br /><br /> **0** = 没有在订阅服务器上所做的更新限制; 所有的更改上载到发布服务器。<br /><br /> **1** = 更改允许在订阅服务器上，但不是会上载到发布服务器。<br /><br /> **2** = 订阅服务器上不允许更改。|  
|**published_in_tran_pub**|**bit**|指示合并发布中的项目也将在事务发布中发布。<br /><br /> **0** = 事务文章中未发布的文章。<br /><br /> **1** = 文章也发布事务文章中。|  
|**轻型**|**bit**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**procname_postfix**|**nchar(32)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**well_partitioned_lightweight**|**bit**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**before_upd_view_objid**|**int**|更新前表视图的 ID。|  
|**delete_tracking**|**bit**|指示是否复制删除。<br /><br /> **0** = 删除不会复制。<br /><br /> **1** = 删除复制，这是合并复制的默认行为。<br /><br /> 时的值*delete_tracking*是**0**、 必须在发布服务器，手动删除订阅服务器上删除的行和删除发布服务器上的行都必须在订阅服务器上手动删除。<br /><br /> 注意： 一个的值的**0**导致非收敛。|  
|**是 compensate_for_errors**|**bit**|指示在同步期间遇到错误时是否采取补救措施。<br /><br /> **0** = Compensating 操作已被禁用。<br /><br /> **1** = 不在订阅服务器或发布服务器始终前导能应用于补偿操作要撤消这些更改，这是合并复制的默认行为的更改。<br /><br /> 注意： 一个的值的**0**导致非收敛。|  
|**pub_range**|**bigint**|发布服务器标识范围大小。|  
|**范围**|**bigint**|将分配到调整中订阅服务器的连续标识值的大小。|  
|**阈值**|**int**|标识范围阈值百分比。|  
|**stream_blob_columns**|**bit**|指示是否使用针对二进制大型对象列的流式优化。 **1**意味着尝试优化。|  
|**preserve_rowguidcol**|**bit**|指示复制是否使用现有 rowguid 列。 值为**1**表示将使用现有的 ROWGUIDCOL 列。 **0**意味着复制添加 ROWGUIDCOL 列。|  
|**partition_view_id**|**int**|标识定义订阅服务器分区的视图。|  
|**repl_view_id**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**partition_deleted_view_rule**|**sysname**|在合并复制触发器内部使用的语句，用于根据其旧列值检索每个已删除或已更新行的分区 ID。|  
|**partition_inserted_view_rule**|**Sysname**|在合并复制触发器内部使用的语句，用于根据其新列值检索每个已插入或已更新行的分区 ID。|  
|**membership_eval_proc_name**|**sysname**|中的行的当前分区 Id 的计算结果的过程的名称[MSmerge_contents &#40;Transact SQL &#41;](../../relational-databases/system-tables/msmerge-contents-transact-sql.md).|  
|**column_list**|**sysname**|在项目中发布的列的逗号分隔列表。|  
|**column_list_blob**|**sysname**|在项目中发布的列（包括二进制大型对象列）的逗号分隔列表。|  
|**expand_proc**|**sysname**|重新分区 Id 为的新插入的父行的所有子行和已进行分区更改或已被删除的父行的评估过程的名称。|  
|**logical_record_parent_nickname**|**int**|逻辑记录中指定项目的顶级父项目的别名。|  
|**logical_record_view**|**int**|一个视图，用于输出与各子项目 rowguid 相对应的顶级父项目 rowguid。|  
|**logical_record_deleted_view_rule**|**sysname**|类似于**logical_record_view**，只不过它显示为"已删除"表中的子行更新和删除触发器。|  
|**logical_record_level_conflict_detection**|**bit**|指示应在逻辑记录级还是行级或列级检测冲突。<br /><br /> **0** = 行或列级别使用冲突检测。<br /><br /> **1** = 逻辑记录冲突检测时，在发布服务器上的行中的更改和更改在单独的行的同一逻辑订阅服务器上的记录会被视为冲突。<br /><br /> 当该值为 1 时，只能使用逻辑记录级别的冲突解决。|  
|**logical_record_level_conflict_resolution**|**bit**|指示是否应在逻辑记录级别或在行级或列级解决冲突。<br /><br /> **0** = 行或列级别使用解析。<br /><br /> **1** = 以防中入选方的整个逻辑记录的冲突时，将覆盖落选方上的整个逻辑记录。<br /><br /> 值 1 既可用于逻辑记录级别的检测，也可用于行或列级别的检测。|  
|**partition_options**|**tinyint**|定义项目数据的分区方式，当所有行只属于一个分区或只属于一个订阅时，这将可以实现性能优化。 *Partition_options*可以是以下值之一。<br /><br /> **0** = 筛选的项目是静态的也不会生成唯一的每个分区的数据子集，即"重叠"分区。<br /><br /> **1** = 分区重叠，并且订阅服务器上所做的 DML 更新不能更改行属于哪个分区。<br /><br /> **2** = 筛选文章生成不重叠分区，但多个订阅服务器可以接收相同的分区。<br /><br /> **3** = 筛选的项目生成对每个订阅都是唯一的不重叠分区。|  
|**名称**|**sysname**|分区的名称。|  
  
## <a name="see-also"></a>另请参阅  
 [为参数化筛选器与合并发布管理分区](../../relational-databases/replication/publish/manage-partitions-for-a-merge-publication-with-parameterized-filters.md)   
 [复制表 &#40;Transact SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [复制视图 &#40;Transact SQL &#41;](../../relational-databases/system-views/replication-views-transact-sql.md)   
 [sp_addmergepartition &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-addmergepartition-transact-sql.md)   
 [sp_helpmergepartition &#40;Transact SQL &#41;](../../relational-databases/system-stored-procedures/sp-helpmergepartition-transact-sql.md)  
  
  