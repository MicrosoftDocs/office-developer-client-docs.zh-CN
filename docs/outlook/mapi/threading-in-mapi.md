---
title: MAPI 中的线程
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 259297d2-acd7-4bc5-9a77-0df92cbfa33e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5d94aeaa75ede85983a678f448b05ad90c1e458a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405539"
---
# <a name="threading-in-mapi"></a>MAPI 中的线程

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
线程是操作系统为其分配 CPU 时间的基本实体。 线程具有其自己的注册、堆栈、优先级和存储，但共享地址空间并处理访问令牌等资源。 线程还共享内存，一个线程读取另一个线程写入了哪些内容。
  
MAPI 客户端使用以下通用线程模型。
  
|**线程模型**|**说明**|
|:-----|:-----|
|单线程模型  <br/> |所有对象都用于单个线程。  <br/> |
|单元线程模型  <br/> |对象只能在创建该对象的线程上使用。  <br/> |
|自由线程或线程方模型  <br/> |对象可在任何线程上使用。  <br/> |
   
MAPI 使用自由线程模型，支持随时可在任何线程中使用的线程安全对象。 OLE 使用单元线程模型。 单元线程模型支持当创建对象的线程外的其他线程需要使用该对象时必须显式传输的对象。
  
OLE 用于将对象从一个线程转移到另一个线程的机制称为封送。 封送涉及存根对象和代理对象。 这些特殊对象打包要封送的对象中的接口参数，将这些参数传输给另一个线程，在到达时将其解包。 当使用 OLE"轻型"远程过程调用或 LRPC 将自由线程 MAPI 对象发送到另一个进程时，两个多线程模型之间会出现冲突。 LRPC 通过将存根和代理接口与对象及其调用方之间的单元线程行为进行互置，将对象的语义从自由线程更改到单元线程。 了解 MAPI 中导致此冲突的情况可帮助客户端和服务提供商防止出现问题。
  
可以访问 MAPI 对象：
  
- 通过使用服务提供商返回的接口指针或链接到客户端进程的 MAPI（如 [MAPILogonEx](mapilogonex.md)返回的会话对象）直接调用其方法。
    
- 通过使用由任何服务提供商返回的接口指针（例如从 [IMAPIFolder：：CopyFolder](imapifolder-copyfolder.md)中的另一个文件夹复制的文件夹对象）间接调用其方法。
    
- 通过回调函数（如 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法传递到服务提供商或 **Advise** 调用中的 MAPI）或可以显示长时间操作进度的方法。 
    

