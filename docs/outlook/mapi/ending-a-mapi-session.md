---
title: 结束 MAPI 会话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ca153737-75dc-426a-a410-7a7ab3264f23
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e8fa8df4e1439db3f1bc688d282e5ebdd3503024
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575502"
---
# <a name="ending-a-mapi-session"></a>结束 MAPI 会话

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
客户端可以响应用户的请求，其会话也立即或处理后所有出站邮件和结束时严重错误发生。 某些客户端需要保持登录以便的待处理的出站邮件可达到传输提供程序和邮件系统的目标。 如果这样的客户端发送一条消息，并且立即注销，直到用户登录后，并保持登录要传输的消息的时间不够长消息可以保留在传出队列中。
  
 **当您需要终止会话与 MAPI 子系统**
  
1. 通过调用每个已注册的对象的**Unadvise**方法取消所有通知注册。 
    
2. 通过调用其[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28VS.85%29.aspx)方法释放所有打开的对象。 打开的对象类型可以包括告知接收器、 状态表、 发件箱文件夹、 一个或多个邮件存储区和通讯簿。 
    
3. 调用[MAPIFreeBuffer](mapifreebuffer.md)以释放任何缓存的条目标识符，如**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 的内存。
    
4. 调用[IMAPISession::Logoff](imapisession-logoff.md)，如果您拥有当前共享的会话允许的用户界面和 MAPI_LOGOFF_SHARED 标志设置 MAPI_LOGOFF_UI 标志。 **注销**通知其他使用他们应通过发送错误通知注销当前共享的会话的所有客户端。 
    
5. 通过调用会话的**IUnknown::Release**方法释放会话指针。 
    
6. 如果您在初始化 OLE 库的会话启动期间调用[OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx) ，取消初始化它们现在通过调用[OleUninitialize](http://msdn.microsoft.com/en-us/library/ms691326%28VS.85%29.aspx)。 只有以前呼叫过**OleInitialize**的客户端必须调用**OleUninitialize**。 
    
7. 通过调用[MAPIUninitialize](mapiuninitialize.md)取消初始化 MAPI 库。 如果您的某个时刻调用**OleInitialize** ，请确保**OleUninitialize**调用**MAPIUninitialize**到此调用前发生此事件。 Timing 至关重要。 如果调用**OleUninitialize**遵循**MAPIUninitialize**调用，您的客户端可能会丢弃终止。 
    
8. 如果您在初始化 MAPI 实用程序库的会话启动期间调用[ScInitMapiUtil](scinitmapiutil.md) ，取消初始化它现在通过调用[DeinitMapiUtil](deinitmapiutil.md)。 只有以前呼叫过**ScInitMapiUtil**的客户端必须调用**DeinitMapiUtil**。
    
> [!NOTE]
> **IMAPISession::Logoff**调用之前，必须释放所有打开的对象。 保持打开状态调用**注销**后的对象会变为无效;他们无法接受的所有呼叫，并可能永远不会被释放。 如果调用了其中一个对象，希望调用失败。 
  
 MAPI 具有会话关机过程删除 Dll 没有机制。 配置客户端，例如控制面板呼叫其消息服务入口点函数与 MSG_SERVICE_INSTALL 事件时，可以仅删除提供程序的 DLL 服务。 
  

