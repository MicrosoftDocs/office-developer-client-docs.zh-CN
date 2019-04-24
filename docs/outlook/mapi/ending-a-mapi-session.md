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
  
客户端可以结束其会话以响应用户的请求, 无论是在处理完所有出站邮件, 还是在发生严重错误时。 某些客户端需要保持登录状态, 以便挂起的出站邮件可以到达传输提供程序和目标邮件系统。 如果这样的客户端发送邮件, 并立即注销, 则该邮件可能会保留在传出队列中, 直到用户重新登录并保持登录状态足够长, 以便发送邮件。
  
 **当您需要使用 MAPI 子系统终止会话时**
  
1. 通过调用每个已注册对象的**Unadvise**方法来取消所有通知的注册。 
    
2. 通过调用其[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx)方法释放所有打开的对象。 打开的对象的类型可以包括 "建议接收器"、"状态" 表、"发件箱" 文件夹、一个或多个邮件存储和通讯簿。 
    
3. 调用[MAPIFreeBuffer](mapifreebuffer.md)以释放任何缓存的条目标识符 (如**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))) 的内存。
    
4. 如果您拥有当前共享会话, 请调用[IMAPISession:: 注销](imapisession-logoff.md), 并设置 MAPI_LOGOFF_UI 标志 (如果允许用户界面和 MAPI_LOGOFF_SHARED 标志)。 **注销**会通知所有其他使用当前共享会话的客户端, 这些客户端应通过发送错误通知注销。 
    
5. 通过调用会话的**IUnknown:: release**方法来释放会话指针。 
    
6. 如果在会话启动过程中调用[OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx)以初始化 OLE 库, 请通过调用[OleUninitialize](https://msdn.microsoft.com/library/ms691326%28VS.85%29.aspx)立即取消对它们的初始化。 只有已调用**OleInitialize**的客户端才必须调用**OleUninitialize**。 
    
7. 通过调用[MAPIUninitialize](mapiuninitialize.md)取消对 MAPI 库的初始化。 如果您在某个时刻调用了**OleInitialize** , 请确保在对**MAPIUninitialize**的此调用之前发生对**OleUninitialize**的调用。 计时是至关重要的。 如果调用**OleUninitialize**后调用**MAPIUninitialize**, 则客户端可能会终止 ungracefully。 
    
8. 如果在会话启动过程中调用[ScInitMapiUtil](scinitmapiutil.md)以初始化 MAPI 实用工具库, 现在通过调用[DeinitMapiUtil](deinitmapiutil.md)取消对它的初始化。 只有已调用**ScInitMapiUtil**的客户端才必须调用**DeinitMapiUtil**。
    
> [!NOTE]
> 在调用**IMAPISession:: 注销**之前, 必须释放所有打开的对象。 **注销**后仍处于打开状态的对象将被称为无效。它们无法接受任何呼叫, 并且可能永远无法释放。 如果对其中一个对象进行了调用, 则预期呼叫将失败。 
  
 MAPI 没有在会话关闭过程中删除 dll 的机制。 仅当配置客户端 (如 "控制面板") 使用 MSG_SERVICE_INSTALL 事件调用其邮件服务入口点函数时, 才能删除服务提供程序的 DLL。 
  

