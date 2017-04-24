---
title: "如何：使用 ConcurrentBag 创建目标池 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "对象池，在 .NET Framework 中"
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# 如何：使用 ConcurrentBag 创建目标池
本示例演示如何使用并发包来实现对象池。  在您需要某个类的多个实例并且创建或销毁该类的成本很高的情况下，对象池可以改进应用程序性能。  当客户端程序请求新对象时，对象池先尝试提供一个已创建并返回该池的对象。  仅在没有可用对象时，才会创建一个新对象。  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601> 用于存储对象，因为它支持快速插入和移除，特别是在同一线程既添加又移除项时。  可将此示例进一步扩大，以围绕包数据结构实现的 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 来生成，与 <xref:System.Collections.Concurrent.ConcurrentQueue%601> 和 <xref:System.Collections.Concurrent.ConcurrentStack%601> 相似。  
  
## 示例  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## 请参阅  
 [线程安全集合](../../../../docs/standard/collections/thread-safe/index.md)