---
title: "网络属性 | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "LingerTimeout 属性"
  - "EnableNagleAlgorithm 属性"
  - "MinPendingAcceptExCount 属性"
  - "MaxPendingSendCount 属性"
  - "EnableBinaryXML 属性"
  - "MinPendingReceiveCount 属性"
  - "MaxCompletedReceiveCount 属性"
  - "DisableNonblockingMode 属性"
  - "RequestSizeThreshold 属性"
  - "CompressionLevel 属性"
  - "ReceiveBufferSize 属性"
  - "EnableCompression 属性"
  - "ServerSendTimeout 属性"
  - "IPV4Support 属性"
  - "MaxPendingReceiveCount 属性"
  - "MaxPendingAcceptExCount 属性"
  - "IPV6Support 属性"
  - "MaxAllowedRequestSize 属性"
  - "ServerReceiveTimeout 属性"
  - "EnableLingerOnClose 属性"
  - "InitialConnectTimeout 属性"
  - "SendBufferSize 属性"
  - "ScatterReceiveMultiplier 属性"
  - "网络属性 [Analysis Services]"
ms.assetid: ef4251e2-abe5-4c5b-9868-7549782d0244
caps.latest.revision: 15
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 15
---
# 网络属性
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 支持下表中列出的服务器属性。 有关更多服务器属性以及如何设置这些属性的详细信息，请参阅 [Analysis Services 中的服务器属性](../../analysis-services/server-properties/server-properties-in-analysis-services.md)。  
  
 **适用于：** 多维和表格服务器模式  
  
## 常规  
 **ListenOnlyOnLocalConnections**  
 一个布尔值属性，指定是否仅侦听本地连接（例如 localhost）。  
  
## 侦听器  
 **IPV4Support**  
 有符号 32 位整数属性，用于定义 IPv4 协议支持。 此属性具有下表所列的值之一：  
  
|“值”|说明|  
|-----------|-----------------|  
|*0*|禁用 IPv4；客户端无法连接。|  
|*1*|（默认值）要求使用 IPv4；如果服务器无法侦听 IPv4，则不启动服务器。|  
|*2*|IPv4 为可选项；服务器将尝试侦听 IPv4，但即使无法侦听，也会启动服务器。|  
  
 **IPV6Support**  
 有符号 32 位整数属性，用于定义 IPv6 协议支持。 此属性具有下表所列的值之一：  
  
|“值”|说明|  
|-----------|-----------------|  
|*0*|禁用 IPv6；客户端无法连接。|  
|*1*|（默认值）要求使用 IPv6；如果服务器无法侦听 IPv6，则不启动服务器。|  
|*2*|IPv6 为可选项；服务器将尝试侦听 IPv6，但即使无法侦听，也会启动服务器。|  
  
 **MaxAllowedRequestSize**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **RequestSizeThreshold**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **ServerReceiveTimeout**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **ServerSendTimeout**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
## 请求  
 **EnableBinaryXML**  
 布尔值属性，指定服务器是否识别二进制 xml 格式请求。  
  
 **EnableCompression**  
 布尔值属性，指定是否对请求启用压缩。  
  
## 响应  
 **CompressionLevel**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **EnableBinaryXML**  
 布尔值属性，指定是否启用服务器的二进制 xml 响应。  
  
 **EnableCompression**  
 布尔值属性，指定是否对客户端请求的响应启用压缩。  
  
## TCP  
 **InitialConnectTimeout**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **MaxCompletedReceiveCount**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **MaxPendingAcceptExCount**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **MaxPendingReceiveCount**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **MaxPendingSendCount**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **MinPendingAcceptExCount**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **MinPendingReceiveCount**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **ScatterReceiveMultiplier**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **SocketOptions\ DisableNonblockingMode**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **SocketOptions\ EnableLingerOnClose**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **SocketOptions\EnableNagleAlgorithm**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **SocketOptions\ LingerTimeout**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **SocketOptions\ ReceiveBufferSize**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
 **SocketOptions\ SendBufferSize**  
 这是一项高级属性，除非有 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 技术支持的指导，否则不应更改此属性。  
  
## 另请参阅  
 [Analysis Services 中的服务器属性](../../analysis-services/server-properties/server-properties-in-analysis-services.md)   
 [确定 Analysis Services 实例的服务器模式](../../analysis-services/instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  