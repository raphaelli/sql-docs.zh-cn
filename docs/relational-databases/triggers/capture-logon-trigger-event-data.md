---
title: "捕获登录触发器事件数据 | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e05b1ab4-c10b-402a-9591-f6ec1e3db8c0
caps.latest.revision: 5
author: BYHAM
ms.author: rickbyh
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 790a086c90eeeeb606a86056f239853d805cb091
ms.lasthandoff: 04/11/2017

---
# <a name="capture-logon-trigger-event-data"></a>捕获登录触发器事件数据
  若要捕获有关 LOGON 事件的 XML 数据以在登录触发器内部使用，请使用 [EVENTDATA](../../t-sql/functions/eventdata-transact-sql.md) 函数。 LOGON 事件将返回以下事件数据架构：  
  
 `<EVENT_INSTANCE>`  
  
 `<EventType>event_type</EventType>`  
  
 `<PostTime>post_time</PostTime>`  
  
 `<SPID>spid</SPID>`  
  
 `<ServerName>server_name</ServerName>`  
  
 `<LoginName>login_name</LoginName>`  
  
 `<LoginType>login_type</LoginType>`  
  
 `<SID>sid</SID>`  
  
 `<ClientHost>client_host</ClientHost>`  
  
 `<IsPooled>is_pooled</IsPooled>`  
  
 `</EVENT_INSTANCE>`  
  
 `<EventType>`  
 包含 `LOGON`。  
  
 `<PostTime>`  
 包含请求建立会话时的时间。  
  
 `<SID>`  
 包含指定登录名的安全标识号 (SID) 的 Base 64 编码二进制流。  
  
 `<ClientHost>`  
 包含建立连接的客户端的主机名。 如果客户端和服务器名称相同，则此值为“`<local_machine>`”。 否则，此值为客户端的 IP 地址。  
  
 `<IsPooled>`  
 如果通过使用连接池重用连接，则此值为 `1` 。 否则，此值为 `0`。  
  
  