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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344826"
---
# <a name="threading-in-mapi"></a>MAPI 中的线程

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
线程是操作系统为其分配 CPU 时间的基本实体。 线程具有自己的寄存器、堆栈、优先级和存储, 但会共享地址空间和处理资源 (如访问令牌)。 线程也共享内存, 其中一个线程读取另一个线程已写入的内容。
  
MAPI 客户端使用以下通用线程模型。
  
|**线程模型**|**Description**|
|:-----|:-----|
|单线程模型  <br/> |在单个线程上使用所有对象。  <br/> |
|单元线程模型  <br/> |只能在创建对象的线程上使用该对象。  <br/> |
|自由线程或线程方模型  <br/> |可以在任何线程上使用对象。  <br/> |
   
MAPI 使用自由线程模型, 支持可在任何时候在任何线程上使用的线程安全对象。 OLE 使用单元线程模型。 单元线程模型支持当不是创建对象的线程需要使用该对象时, 必须显式转移的对象。
  
OLE 用来将对象从一个线程传输到另一个线程的机制称为封送。 封送处理涉及一个存根对象和一个代理对象。 这些特殊对象打包要封送的对象中接口的参数, 将这些参数转移到另一个线程, 并在到达时将其解开。 当使用 OLE "轻型" 远程过程调用或 LRPC 将自由线程的 MAPI 对象发送到另一个进程时, 会出现两个多线程模型之间的冲突。 LRPC 通过 interposing 存根和代理接口将对象的语义从自由线程处理更改为单元线程, 在对象与其调用方之间具有单元线程行为。 对 MAPI 中导致此冲突的情况的感知可帮助客户端和服务提供商防止出现问题。
  
可以访问 MAPI 对象:
  
- 通过使用服务提供程序返回的接口指针或链接到客户端进程的 MAPI (如从[MAPILogonEx](mapilogonex.md)返回的 session 对象) 直接调用其方法。
    
- 通过使用任何服务提供程序返回的接口指针间接调用其方法, 如从[IMAPIFolder:: CopyFolder](imapifolder-copyfolder.md)中的另一个文件夹复制的 folder 对象。
    
- 通过回调函数 (如[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法) 传递给服务提供程序或**通知**调用中的 MAPI, 或者可以显示长操作进度的方法。 
    

