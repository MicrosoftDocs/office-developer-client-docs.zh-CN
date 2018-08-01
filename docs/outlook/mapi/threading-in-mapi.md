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
ms.openlocfilehash: 15fb6113e9c3428cff3865307736592fd6e2b2f7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778974"
---
# <a name="threading-in-mapi"></a>MAPI 中的线程

  
  
**适用于**： Outlook 
  
线程是操作系统向其分配 CPU 时间的基本实体。 线程都有其自己的 register、 堆栈、 优先级和存储，但共享地址空间和处理资源如访问令牌。 线程还与另一个线程具有写入中读取的一个线程共享内存。
  
MAPI 客户端使用的以下泛型线程模型。
  
|**线程模型**|**说明**|
|:-----|:-----|
|单线程模型  <br/> |在单个线程中使用的所有对象。  <br/> |
|单元线程模型  <br/> |对象仅用于创建它的线程。  <br/> |
|自由线程，或线程方模型  <br/> |可在任何线程上一个对象。  <br/> |
   
MAPI 使用自由线程模型中，支持随时都可以在任何线程上使用的线程安全对象。 OLE 使用单元线程模型。 单元线程模型支持之外创建对象的线程需要使用该对象时必须明确转接的对象。
  
OLE 用来将对象从一个线程传输到另一个机制称为封送处理。 封送涉及存根对象和代理对象。 这些特殊对象打包对象封送，转接到其他线程，这些参数并将它们时到达解包中的接口的参数。 发送到另一个进程使用 OLE"轻型"远程过程调用，或 LRPC 自由线程 MAPI 对象时，则会发生两个线程模型之间的冲突。 LRPC 从到单元线程通过单元线程对象和其呼叫者之间的行为与在仅存根和代理接口的自由线程更改对象的语义。 认知度的 MAPI 中在此冲突导致的情况下可帮助客户端和服务提供商防止出现问题。
  
可访问 MAPI 对象：
  
- 通过直接调用使用界面及其方法返回的服务提供商或 MAPI 指针链接到客户端的过程，如从[MAPILogonEx](mapilogonex.md)返回会话对象。
    
- 通过间接调用其方法使用返回的任何服务提供商，如 folder 对象的接口指针从另一个文件夹复制[IMAPIFolder::CopyFolder](imapifolder-copyfolder.md)中。
    
- 通过如**Advise**呼叫或可以显示在冗长的操作的进度的方法中传递到服务提供商或 MAPI [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法的回调函数。 
    

