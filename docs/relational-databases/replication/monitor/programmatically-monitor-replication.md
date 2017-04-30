---
title: "以编程方式监视复制 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- TSQL
helpviewer_keywords:
- sp_replmonitorhelppublisher
- sp_replmonitorhelpmergesessiondetail
- monitoring performance [SQL Server replication], publication status
- sp_replmonitorhelpmergesession
- sp_replmonitorhelppublicationthresholds
- monitoring performance [SQL Server replication], subscription status
- monitoring performance [SQL Server replication], Transact-SQL programming
- sp_replmonitorsubscriptionpendingcmds
- sp_replmonitorchangepublicationthreshold
- transactional replication, monitoring
- sp_replmonitorhelppublication
- sp_replmonitorhelpsubscription
- monitoring performance [SQL Server replication], thresholds and warnings
- merge replication monitoring [SQL Server replication]
- snapshot replication [SQL Server], monitoring
ms.assetid: e8bf8850-8da5-4a4f-a399-64232b4e476d
caps.latest.revision: 34
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: b05b9c5af4ff9ed8626773fc6714c2c05f1605b2
ms.lasthandoff: 04/11/2017

---
# <a name="programmatically-monitor-replication"></a>以编程方式监视复制
  复制监视器是一种可用于监视复制拓扑的图形化工具。 可以使用 [!INCLUDE[tsql](../../../includes/tsql-md.md)] 复制存储过程或复制管理对象 (RMO) 以编程方式访问相同的监视数据。 您可以利用这些对象对以下任务进行编程：  
  
-   监视发布服务器、发布和订阅的状态。  
  
-   监视一个或多个订阅服务器上的合并代理会话。  
  
-   监视等待在一个或多个订阅服务器上应用的事务处理命令。  
  
-   定义用于确定发布何时需要干预的阈值标准。  
  
-   监视跟踪令牌的状态。  
  
 **本主题内容：**  
  
 [Transact-SQL](#Tsql)  
  
 [复制管理对象 (RMO)](#RMO)  
  
##  <a name="Tsql"></a> Transact-SQL  
  
#### <a name="to-monitor-publishers-publications-and-subscriptions-from-the-distributor"></a>从分发服务器监视发布服务器、发布和订阅  
  
1.  在分发服务器上，对分发数据库执行 [sp_replmonitorhelppublisher](../../../relational-databases/system-stored-procedures/sp-replmonitorhelppublisher-transact-sql.md)。 这将返回使用此分发服务器的所有发布服务器的监视信息。 若要将结果集限制在单个发布服务器范围之内，请指定 **@publisher**。  
  
2.  在分发服务器上，对分发数据库执行 [sp_replmonitorhelppublication](../../../relational-databases/system-stored-procedures/sp-replmonitorhelppublication-transact-sql.md). 这将返回使用此分发服务器的所有发布的监视信息。 若要将结果集限制在单个发布服务器、发布或已发布数据库的范围之内，请分别指定 **@publisher**、 **@publication**或 **@publisher_db**。  
  
3.  在分发服务器上，对分发数据库执行 [sp_replmonitorhelpsubscription](../../../relational-databases/system-stored-procedures/sp-replmonitorhelpsubscription-transact-sql.md)。 这将返回使用此分发服务器的所有订阅的监视信息。 若要将结果集限制在属于单个发布服务器、发布或已发布数据库的订阅范围之内，请分别指定 **@publisher**、 **@publication**或 **@publisher_db**。  
  
#### <a name="to-monitor-transactional-commands-waiting-to-be-applied-at-the-subscriber"></a>监视等待在订阅服务器上应用的事务处理命令  
  
1.  在分发服务器上，对分发数据库执行 [sp_replmonitorsubscriptionpendingcmds](../../../relational-databases/system-stored-procedures/sp-replmonitorsubscriptionpendingcmds-transact-sql.md)。 这将返回为使用此分发服务器的所有订阅挂起的所有命令的监视信息。 若要将结果集限制在为属于单个发布服务器、订阅服务器、发布或已发布数据库的订阅挂起的命令范围之内，请分别指定 **@publisher**、 **@subscriber**、 **@publication**或 **@publisher_db**。  
  
#### <a name="to-monitor-merge-changes-waiting-to-be-uploaded-or-downloaded"></a>监视等待上载或下载的合并更改  
  
1.  在发布服务器上，对发布数据库执行 [sp_showpendingchanges](../../../relational-databases/system-stored-procedures/sp-showpendingchanges-transact-sql.md)。 这将返回一个结果集，其中显示了有关等待复制到订阅服务器的更改的信息。 若要将结果集限制在属于单个发布或项目的更改范围之内，请分别指定 **@publication** 或 **@article**。  
  
2.  在订阅服务器上，对订阅数据库执行 [sp_showpendingchanges](../../../relational-databases/system-stored-procedures/sp-showpendingchanges-transact-sql.md)。 这将返回一个结果集，其中显示了有关等待复制到发布服务器的更改的信息。 若要将结果集限制在属于单个发布或项目的更改范围之内，请分别指定 **@publication** 或 **@article**。  
  
#### <a name="to-monitor-merge-agent-sessions"></a>监视合并代理会话  
  
1.  在分发服务器上，对分发数据库执行 [sp_replmonitorhelpmergesession](../../../relational-databases/system-stored-procedures/sp-replmonitorhelpmergesession-transact-sql.md)。 这将为所有使用此分发服务器的订阅返回有关所有合并代理会话的监视信息（包括 **Session_id**）。 还可以提供查询 **MSmerge_sessions** 系统表来获得 [Session_id](../../../relational-databases/system-tables/msmerge-sessions-transact-sql.md) 。  
  
2.  在分发服务器上，对分发数据库执行 [sp_replmonitorhelpmergesessiondetail](../../../relational-databases/system-stored-procedures/sp-replmonitorhelpmergesessiondetail-transact-sql.md)。 为 **Session_id** 指定步骤 1 中的 **@session_id**。 这将显示有关该会话的详细监视信息。  
  
3.  为每个相关会话重复步骤 2。  
  
#### <a name="to-monitor-merge-agent-sessions-for-pull-subscriptions-from-the-subscriber"></a>从订阅服务器监视请求订阅的合并代理会话  
  
1.  在订阅服务器上，对订阅数据库执行 [sp_replmonitorhelpmergesession](../../../relational-databases/system-stored-procedures/sp-replmonitorhelpmergesession-transact-sql.md)。 针对给定订阅指定 **@publisher**、 **@publication**，并为 **@publisher_db**。 这将为此订阅的最后五个合并代理会话返回监视信息。 请记下结果集中相关会话的 **Session_id** 值。  
  
2.  在订阅服务器上，对订阅数据库执行 [sp_replmonitorhelpmergesessiondetail](../../../relational-databases/system-stored-procedures/sp-replmonitorhelpmergesessiondetail-transact-sql.md)。 为 **Session_id** 指定步骤 1 中的 **@session_id**。 这将显示有关该会话的详细监视信息。  
  
3.  为每个相关会话重复步骤 2。  
  
#### <a name="to-view-and-modify-the-monitor-threshold-metrics-for-a-publication"></a>查看和修改发布的监视阈值标准  
  
1.  在分发服务器上，对分发数据库执行 [sp_replmonitorhelppublicationthresholds](../../../relational-databases/system-stored-procedures/sp-replmonitorhelppublicationthresholds-transact-sql.md)。 这将返回为使用此分发服务器的所有发布设置的监视阈值。 若要将结果集限制在属于单个发布服务器或已发布数据库的发布或者单个发布的监视阈值范围之内，请分别指定 **@publisher**、 **@publisher_db**或 **@publication**。 请记下任何必须更改的阈值的 **Metric_id** 值。 有关详细信息，请参阅 [Set Thresholds and Warnings in Replication Monitor](../../../relational-databases/replication/monitor/set-thresholds-and-warnings-in-replication-monitor.md)。  
  
2.  在分发服务器上，对分发数据库执行 [sp_replmonitorchangepublicationthreshold](../../../relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql.md)。 根据需要指定下列参数：  
  
    -   为 **Metric_id** 指定在步骤 1 中获得 **@metric_id**。  
  
    -   为 **@value**。  
  
    -   将 **@shouldalert** 的值指定为 **@shouldalert** 以在达到此阈值时记录警报；如果不需要警报，则指定为 **0** 。  
  
    -   将 **@shouldalert** 的值指定为 **@mode** 以启用监视阈值指标，或指定为 **2** 以禁用它。  
  
##  <a name="RMO"></a> 复制管理对象 (RMO)  
  
#### <a name="to-monitor-a-subscription-to-a-merge-publication-at-the-subscriber"></a>监视对订阅服务器上的合并发布的订阅  
  
1.  使用 <xref:Microsoft.SqlServer.Management.Common.ServerConnection> 类创建与订阅服务器的连接。  
  
2.  创建 <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor> 类的实例，设置订阅的 <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.Publisher%2A>、<xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.Publication%2A>、<xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.PublisherDB%2A> 和 <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.SubscriberDB%2A> 属性，并将 <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> 属性设置为步骤 1 中创建的 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>。  
  
3.  调用以下方法之一返回有关该订阅的合并代理会话的信息：  
  
    -   <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.GetSessionsSummary%2A> - 返回 <xref:Microsoft.SqlServer.Replication.MergeSessionSummary> 对象的数组，其中包含有关最后最多五个“合并代理”会话的信息。 请注意任何相关会话的 <xref:Microsoft.SqlServer.Replication.MergeSessionSummary.SessionId%2A> 值。  
  
    -   <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.GetSessionsSummary%2A> - 返回 <xref:Microsoft.SqlServer.Replication.MergeSessionSummary> 对象的数组，其中包含有关在最后几个小时内，作为 *hours* 参数传入的“合并代理”会话（最后最多五个会话）的信息。 请注意任何相关会话的 <xref:Microsoft.SqlServer.Replication.MergeSessionSummary.SessionId%2A> 值。  
  
    -   <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.GetLastSessionSummary%2A> - 返回 <xref:Microsoft.SqlServer.Replication.MergeSessionSummary> 对象，其中包含有关最后一个“合并代理”会话的信息。 请注意此会话的 <xref:Microsoft.SqlServer.Replication.MergeSessionSummary.SessionId%2A> 值。  
  
    -   <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.GetSessionsSummaryDataSet%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关最后最多五个“合并代理”会话的信息，每行返回一个会话的信息。 请注意任何相关会话的 **Session_id** 列的值。  
  
    -   <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.GetLastSessionSummaryDataRow%2A> - 返回 <xref:System.Data.DataRow> 对象，其中包含有关最后一个“合并代理”会话的信息。 请注意此会话的 **Session_id** 列的值。  
  
4.  （可选）调用 <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.RefreshSessionSummary%2A> 刷新作为 *mss* 传递的 <xref:Microsoft.SqlServer.Replication.MergeSessionSummary> 对象的数据，或者调用 <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.RefreshSessionSummary%2A> 刷新作为 *drRefresh* 传递的 <xref:System.Data.DataRow> 对象中的数据。  
  
5.  使用步骤 3 中获取的会话 ID 调用以下方法之一，以返回有关特定会话的详细信息：  
  
    -   <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.GetSessionDetails%2A> - 返回提供的 *SessionId* 的 <xref:Microsoft.SqlServer.Replication.MergeSessionDetail> 对象的数组。  
  
    -   <xref:Microsoft.SqlServer.Replication.MergeSubscriberMonitor.GetSessionDetailsDataSet%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含指定的 *SessionId* 的信息。  
  
#### <a name="to-monitor-replication-properties-for-all-publications-at-a-distributor"></a>监视分发服务器上所有发布的复制属性  
  
1.  使用 <xref:Microsoft.SqlServer.Management.Common.ServerConnection> 类创建与分发服务器的连接。  
  
2.  创建 <xref:Microsoft.SqlServer.Replication.ReplicationMonitor> 类的实例。  
  
3.  将 <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> 属性设置为步骤 1 中创建的 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>。  
  
4.  调用 <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> 方法获取该对象的属性。  
  
5.  执行以下一种或多种方法返回使用该分发服务器的所有发布服务器的复制信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumDistributionAgents%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关此分发服务器中所有分发代理的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumErrorRecords%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关分发服务器中存储的错误的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumLogReaderAgents%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关分发服务器中所有日志读取器代理的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumMergeAgents%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关分发服务器中所有合并代理的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumMiscellaneousAgents%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关分发服务器中其他所有复制代理的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumPublishers%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关此分发服务器中所有发布服务器的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumPublishers2%2A> - 返回 <xref:System.Data.DataSet> 对象，该对象返回使用此分发服务器的发布服务器。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumQueueReaderAgents%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关分发服务器中所有队列读取器代理的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumQueueReaderAgentSessionDetails%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关指定的队列读取器代理和会话的详细信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumQueueReaderAgentSessions%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关指定的队列读取器代理的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.EnumSnapshotAgents%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关分发服务器中所有快照代理的信息。  
  
#### <a name="to-monitor-publication-properties-for-a-specific-publisher-at-the-distributor"></a>监视分发服务器上特定发布服务器的发布属性  
  
1.  使用 <xref:Microsoft.SqlServer.Management.Common.ServerConnection> 类创建与分发服务器的连接。  
  
2.  通过以下方法之一获取 <xref:Microsoft.SqlServer.Replication.PublisherMonitor> 对象。  
  
    -   创建 <xref:Microsoft.SqlServer.Replication.PublisherMonitor> 类的实例。 设置发布服务器的 <xref:Microsoft.SqlServer.Replication.PublisherMonitor.Name%2A> 属性，并将 <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> 属性设置为步骤 1 中创建的 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>。 调用 <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> 方法获取该对象的属性。 如果该方法返回 **false**，则表示发布服务器名称定义不正确或表示该发布不存在。  
  
    -   从通过现有 <xref:Microsoft.SqlServer.Replication.ReplicationMonitor> 对象的 <xref:Microsoft.SqlServer.Replication.ReplicationMonitor.PublisherMonitors%2A> 属性访问的 <xref:Microsoft.SqlServer.Replication.PublisherMonitorCollection> 中获取。  
  
3.  执行以下一种或多种方法返回有关属于该发布服务器的所有发布的复制信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumDistributionAgentSessionDetails%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关指定的分发代理和会话的详细信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumDistributionAgentSessions%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关指定的分发代理的会话信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumErrorRecords%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关指定的错误的错误记录信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumLogReaderAgentSessionDetails%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含指定的日志读取器代理和会话的详细信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumLogReaderAgentSessions%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含指定的日志读取器代理的会话信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumMergeAgentSessionDetails%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关指定的合并代理和会话的详细信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumMergeAgentSessionDetails2%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关指定的合并代理和会话的其他详细信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumMergeAgentSessions%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含指定的合并代理的会话信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumMergeAgentSessions2%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含指定的合并代理的其他会话信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumPublications%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关此分发服务器中所有发布内容的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumPublications2%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关此分发服务器中所有发布内容的其他信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumSnapshotAgentSessionDetails%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关指定的快照代理和会话的详细信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumSnapshotAgentSessions%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含指定的快照代理的会话信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublisherMonitor.EnumSubscriptions%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关此分发服务器中所有发布订阅的信息。  
  
#### <a name="to-monitor-properties-for-a-specific-publication-at-the-distributor"></a>监视分发服务器上的特定发布的属性  
  
1.  使用 <xref:Microsoft.SqlServer.Management.Common.ServerConnection> 类创建与分发服务器的连接。  
  
2.  通过以下方法之一获取 <xref:Microsoft.SqlServer.Replication.PublicationMonitor> 对象。  
  
    -   创建 <xref:Microsoft.SqlServer.Replication.PublicationMonitor> 类的实例。 设置发布内容的 <xref:Microsoft.SqlServer.Replication.PublicationMonitor.DistributionDBName%2A>、<xref:Microsoft.SqlServer.Replication.PublicationMonitor.PublisherName%2A>、<xref:Microsoft.SqlServer.Replication.PublicationMonitor.PublicationDBName%2A> 和 <xref:Microsoft.SqlServer.Replication.PublicationMonitor.Name%2A> 属性，并将 <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> 属性设置为步骤 1 中创建的 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>。 调用 <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> 方法获取该对象的属性。 如果该方法返回 **false**，则表示发布属性定义不正确，或表示该发布不存在。  
  
    -   从通过现有 <xref:Microsoft.SqlServer.Replication.PublisherMonitor> 对象的 <xref:Microsoft.SqlServer.Replication.PublisherMonitor.PublicationMonitors%2A> 属性访问的 <xref:Microsoft.SqlServer.Replication.PublicationMonitorCollection> 中获取。  
  
3.  执行以下一种或多种方法返回有关此发布的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublicationMonitor.EnumErrorRecords%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关指定的错误的错误记录。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublicationMonitor.EnumLogReaderAgent%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关此发布内容的日志读取器代理的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublicationMonitor.EnumMonitorThresholds%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关针对此发布内容设置的监视警告阈值的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublicationMonitor.EnumQueueReaderAgent%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关此发布内容使用的队列读取器代理的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublicationMonitor.EnumSnapshotAgent%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关此发布内容的快照代理的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.Publication.EnumSubscriptions%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关此发布内容的订阅的信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublicationMonitor.EnumSubscriptions2%2A> - 返回 <xref:System.Data.DataSet> 对象，其中根据提供的 <xref:Microsoft.SqlServer.Replication.SubscriptionResultOption> 包含有关此发布内容的订阅的其他信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublicationMonitor.EnumTracerTokenHistory%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含指定的跟踪令牌的延迟信息。  
  
    -   <xref:Microsoft.SqlServer.Replication.PublicationMonitor.EnumTracerTokens%2A> - 返回 <xref:System.Data.DataSet> 对象，其中包含有关已插入此发布内容的所有跟踪令牌的信息。  
  
#### <a name="to-monitor-transactional-commands-that-are-waiting-to-be-applied-at-the-subscriber"></a>监视正等待在订阅服务器上应用的事务处理命令  
  
1.  使用 <xref:Microsoft.SqlServer.Management.Common.ServerConnection> 类创建与分发服务器的连接。  
  
2.  通过以下方法之一获取 <xref:Microsoft.SqlServer.Replication.PublicationMonitor> 对象。  
  
    -   创建 <xref:Microsoft.SqlServer.Replication.PublicationMonitor> 类的实例。 设置发布内容的 <xref:Microsoft.SqlServer.Replication.PublicationMonitor.DistributionDBName%2A>、<xref:Microsoft.SqlServer.Replication.PublicationMonitor.PublisherName%2A>、<xref:Microsoft.SqlServer.Replication.PublicationMonitor.PublicationDBName%2A> 和 <xref:Microsoft.SqlServer.Replication.PublicationMonitor.Name%2A> 属性，并将 <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> 属性设置为步骤 1 中创建的 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>。 调用 <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> 方法获取该对象的属性。 如果该方法返回 **false**，则表示发布属性定义不正确，或表示该发布不存在。  
  
    -   从通过现有 <xref:Microsoft.SqlServer.Replication.PublisherMonitor> 对象的 <xref:Microsoft.SqlServer.Replication.PublisherMonitor.PublicationMonitors%2A> 属性访问的 <xref:Microsoft.SqlServer.Replication.PublicationMonitorCollection> 中获取。  
  
3.  执行返回 <xref:Microsoft.SqlServer.Replication.PendingCommandInfo> 对象的 <xref:Microsoft.SqlServer.Replication.PublicationMonitor.TransPendingCommandInfo%2A> 方法。  
  
4.  使用此 <xref:Microsoft.SqlServer.Replication.PendingCommandInfo> 对象的属性可估算挂起命令的数目以及完成这些命令的传递所需的时间。  
  
#### <a name="to-set-the-monitor-warning-thresholds-for-a-publication"></a>为发布设置监视器警告阈值  
  
1.  使用 <xref:Microsoft.SqlServer.Management.Common.ServerConnection> 类创建与分发服务器的连接。  
  
2.  通过以下方法之一获取 <xref:Microsoft.SqlServer.Replication.PublicationMonitor> 对象。  
  
    -   创建 <xref:Microsoft.SqlServer.Replication.PublicationMonitor> 类的实例。 设置发布内容的 <xref:Microsoft.SqlServer.Replication.PublicationMonitor.DistributionDBName%2A>、<xref:Microsoft.SqlServer.Replication.PublicationMonitor.PublisherName%2A>、<xref:Microsoft.SqlServer.Replication.PublicationMonitor.PublicationDBName%2A> 和 <xref:Microsoft.SqlServer.Replication.PublicationMonitor.Name%2A> 属性，并将 <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> 属性设置为步骤 1 中创建的 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>。 调用 <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> 方法获取该对象的属性。 如果该方法返回 **false**，则表示发布属性定义不正确，或表示该发布不存在。  
  
    -   从通过现有 <xref:Microsoft.SqlServer.Replication.PublisherMonitor> 对象的 <xref:Microsoft.SqlServer.Replication.PublisherMonitor.PublicationMonitors%2A> 属性访问的 <xref:Microsoft.SqlServer.Replication.PublicationMonitorCollection> 中获取。  
  
3.  执行 <xref:Microsoft.SqlServer.Replication.PublicationMonitor.EnumMonitorThresholds%2A> 方法。 请注意返回的 <xref:Microsoft.SqlServer.Replication.MonitorThreshold> 对象 <xref:System.Collections.ArrayList> 中的当前阈值设置。  
  
4.  执行 <xref:Microsoft.SqlServer.Replication.PublicationMonitor.ChangeMonitorThreshold%2A> 方法。 传递以下参数：  
  
    -   *metricID* - 一个 <xref:System.Int32> 值，表示下表中的监视阈值指标：  
  
        |“值”|说明|  
        |-----------|-----------------|  
        |@shouldalert|**expiration** - 监视对事务发布的订阅是否即将过期。|  
        |2|**latency** - 监视对事务发布的订阅的性能。|  
        |4|**mergeexpiration** - 监视对合并发布的订阅是否即将过期。|  
        |5|**mergeslowrunduration** - 监视通过低带宽（拨号）连接进行的合并同步的持续时间。|  
        |6|**mergefastrunduration** - 监视通过高带宽 (LAN) 连接进行的合并同步的持续时间。|  
        |7|**mergefastrunspeed** - 监视通过高带宽 (LAN) 连接进行的合并同步的同步速率。|  
        |8|**mergeslowrunspeed** - 监视通过低带宽（拨号）连接进行的合并同步的同步速率。|  
  
    -   *enable* - 用于指示是否为发布启用指标的 <xref:System.Boolean> 值。  
  
    -   *thresholdValue* - 用于设置阈值的整数值。  
  
    -   *shouldAlert* - 用于指示在此阈值是否应生成警报的整数。  
  
  