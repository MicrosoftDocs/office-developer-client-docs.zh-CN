---
title: 结束 MAPI 会话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ca153737-75dc-426a-a410-7a7ab3264f23
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 74c2a7247df02570761247a9e4a6fae378f37312
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287151"
---
# <a name="ending-a-mapi-session"></a>结束 MAPI 会话

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
客户端可以立即或处理完所有出站邮件后，以及发生严重错误时，结束其会话以响应用户的请求。 某些客户端需要保持登录状态，以便挂起的出站邮件可以到达传输提供程序和目标邮件系统。 如果此类客户端发送邮件并立即注销，则邮件可能一直保留在传出队列中，直到用户重新登录并保持登录的时间足够长，以传输邮件。
  
 **当你需要终止与 MAPI 子系统的会话时**
  
1. 通过调用每个已注册对象的 **Unadvise** 方法取消所有通知的注册。 
    
2. 通过调用其 [IUnknown：：Release 方法释放所有打开](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) 的对象。 打开的对象类型可以包括通知接收器、状态表、发件箱文件夹、一个或多个邮件存储以及通讯簿。 
    
3. 调用[MAPIFreeBuffer](mapifreebuffer.md)以释放任何缓存条目标识符的内存，例如 PR_IPM_SUBTREE_ENTRYID  ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 。
    
4. 调用 [IMAPISession：：Logoff](imapisession-logoff.md)，如果允许用户界面和 MAPI_LOGOFF_SHARED 标志，则设置 MAPI_LOGOFF_UI 标志（如果你拥有当前共享会话）。 **注销** 会通过发送错误通知来通知使用当前共享会话的所有其他客户端应注销。 
    
5. 通过调用会话的 **IUnknown：：Release** 方法释放会话指针。 
    
6. 如果在会话启动 [期间调用 OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx) 以初始化 OLE 库，则现在通过调用 [OleUninitialize 取消初始化它们](https://msdn.microsoft.com/library/ms691326%28VS.85%29.aspx)。 只有调用 **OleInitialize** 的客户端必须调用 **OleUninitialize**。 
    
7. 通过调用 [MAPIUninitialize](mapiuninitialize.md)来取消初始化 MAPI 库。 如果在某些时候调用 **了 OleInitialize，** 请确保在调用 **MAPIUninitialize 之前调用 OleUninitialize。**  时间至关重要。 如果 **对 OleUninitialize** 的调用遵循 **对 MAPIUninitialize** 的调用，则客户端可能会非正常终止。 
    
8. 如果在会话启动 [期间调用 ScInitMapiUtil](scinitmapiutil.md) 以初始化 MAPI 实用工具库，则现在通过调用 [DeinitMapiUtil](deinitmapiutil.md)来取消初始化它。 只有调用 **ScInitMapiUtil** 的客户端必须调用 **DeinitMapiUtil**。
    
> [!NOTE]
> 在调用 **IMAPISession：：Logoff** 之前，必须释放所有打开的对象。 调用注销后 **保持打开状态** 的对象将变为无效;他们无法接受任何呼叫，并且可能永远不会获得释放。 如果调用这些对象之一，预期调用将失败。 
  
 MAPI 没有在会话关闭过程中删除 DLL 的机制。 只有在配置客户端（如控制面板）使用 MSG_SERVICE_INSTALL 事件调用其消息服务入口点函数时，才能删除服务提供商的 DLL。 
  

