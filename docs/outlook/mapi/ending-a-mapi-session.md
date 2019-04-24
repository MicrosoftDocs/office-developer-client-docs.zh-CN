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
# <a name="ending-a-mapi-session"></a><span data-ttu-id="e8d89-103">结束 MAPI 会话</span><span class="sxs-lookup"><span data-stu-id="e8d89-103">Ending a MAPI Session</span></span>

  
  
<span data-ttu-id="e8d89-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8d89-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e8d89-105">客户端可以结束其会话以响应用户的请求, 无论是在处理完所有出站邮件, 还是在发生严重错误时。</span><span class="sxs-lookup"><span data-stu-id="e8d89-105">Clients can end their sessions in response to a user's request, either immediately or after all outbound messages have been processed, and when a critical error occurs.</span></span> <span data-ttu-id="e8d89-106">某些客户端需要保持登录状态, 以便挂起的出站邮件可以到达传输提供程序和目标邮件系统。</span><span class="sxs-lookup"><span data-stu-id="e8d89-106">Some clients need to stay logged on so that pending outbound messages can reach the transport provider and the destination messaging system.</span></span> <span data-ttu-id="e8d89-107">如果这样的客户端发送邮件, 并立即注销, 则该邮件可能会保留在传出队列中, 直到用户重新登录并保持登录状态足够长, 以便发送邮件。</span><span class="sxs-lookup"><span data-stu-id="e8d89-107">If such a client sends a message and immediately logs off, the message may remain in the outgoing queue until a user logs back on and stays logged on long enough for the message to be transmitted.</span></span>
  
 <span data-ttu-id="e8d89-108">**当您需要使用 MAPI 子系统终止会话时**</span><span class="sxs-lookup"><span data-stu-id="e8d89-108">**When you need to terminate your session with the MAPI subsystem**</span></span>
  
1. <span data-ttu-id="e8d89-109">通过调用每个已注册对象的**Unadvise**方法来取消所有通知的注册。</span><span class="sxs-lookup"><span data-stu-id="e8d89-109">Cancel the registrations for all notifications by calling the **Unadvise** method of every registered object.</span></span> 
    
2. <span data-ttu-id="e8d89-110">通过调用其[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx)方法释放所有打开的对象。</span><span class="sxs-lookup"><span data-stu-id="e8d89-110">Release all open objects by calling their [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) methods.</span></span> <span data-ttu-id="e8d89-111">打开的对象的类型可以包括 "建议接收器"、"状态" 表、"发件箱" 文件夹、一个或多个邮件存储和通讯簿。</span><span class="sxs-lookup"><span data-stu-id="e8d89-111">The types of open objects can include advise sinks, the status table, the Outbox folder, one or more message stores, and the address book.</span></span> 
    
3. <span data-ttu-id="e8d89-112">调用[MAPIFreeBuffer](mapifreebuffer.md)以释放任何缓存的条目标识符 (如**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md))) 的内存。</span><span class="sxs-lookup"><span data-stu-id="e8d89-112">Call [MAPIFreeBuffer](mapifreebuffer.md) to free the memory for any cached entry identifiers, such as **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)).</span></span>
    
4. <span data-ttu-id="e8d89-113">如果您拥有当前共享会话, 请调用[IMAPISession:: 注销](imapisession-logoff.md), 并设置 MAPI_LOGOFF_UI 标志 (如果允许用户界面和 MAPI_LOGOFF_SHARED 标志)。</span><span class="sxs-lookup"><span data-stu-id="e8d89-113">Call [IMAPISession::Logoff](imapisession-logoff.md), setting the MAPI_LOGOFF_UI flag if you allow a user interface and the MAPI_LOGOFF_SHARED flag if you own the current shared session.</span></span> <span data-ttu-id="e8d89-114">**注销**会通知所有其他使用当前共享会话的客户端, 这些客户端应通过发送错误通知注销。</span><span class="sxs-lookup"><span data-stu-id="e8d89-114">**Logoff** notifies all other clients that are using the current shared session that they should log off by sending an error notification.</span></span> 
    
5. <span data-ttu-id="e8d89-115">通过调用会话的**IUnknown:: release**方法来释放会话指针。</span><span class="sxs-lookup"><span data-stu-id="e8d89-115">Release the session pointer by calling the session's **IUnknown::Release** method.</span></span> 
    
6. <span data-ttu-id="e8d89-116">如果在会话启动过程中调用[OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx)以初始化 OLE 库, 请通过调用[OleUninitialize](https://msdn.microsoft.com/library/ms691326%28VS.85%29.aspx)立即取消对它们的初始化。</span><span class="sxs-lookup"><span data-stu-id="e8d89-116">If you called [OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx) during session startup to initialize the OLE libraries, uninitialize them now by calling [OleUninitialize](https://msdn.microsoft.com/library/ms691326%28VS.85%29.aspx).</span></span> <span data-ttu-id="e8d89-117">只有已调用**OleInitialize**的客户端才必须调用**OleUninitialize**。</span><span class="sxs-lookup"><span data-stu-id="e8d89-117">Only clients that have called **OleInitialize** must call **OleUninitialize**.</span></span> 
    
7. <span data-ttu-id="e8d89-118">通过调用[MAPIUninitialize](mapiuninitialize.md)取消对 MAPI 库的初始化。</span><span class="sxs-lookup"><span data-stu-id="e8d89-118">Uninitialize the MAPI libraries by calling [MAPIUninitialize](mapiuninitialize.md).</span></span> <span data-ttu-id="e8d89-119">如果您在某个时刻调用了**OleInitialize** , 请确保在对**MAPIUninitialize**的此调用之前发生对**OleUninitialize**的调用。</span><span class="sxs-lookup"><span data-stu-id="e8d89-119">If you called **OleInitialize** at some point, make sure that a call to **OleUninitialize** occurs before this call to **MAPIUninitialize**.</span></span> <span data-ttu-id="e8d89-120">计时是至关重要的。</span><span class="sxs-lookup"><span data-stu-id="e8d89-120">The timing is crucial.</span></span> <span data-ttu-id="e8d89-121">如果调用**OleUninitialize**后调用**MAPIUninitialize**, 则客户端可能会终止 ungracefully。</span><span class="sxs-lookup"><span data-stu-id="e8d89-121">If the call to **OleUninitialize** follows the call to **MAPIUninitialize**, your client might terminate ungracefully.</span></span> 
    
8. <span data-ttu-id="e8d89-122">如果在会话启动过程中调用[ScInitMapiUtil](scinitmapiutil.md)以初始化 MAPI 实用工具库, 现在通过调用[DeinitMapiUtil](deinitmapiutil.md)取消对它的初始化。</span><span class="sxs-lookup"><span data-stu-id="e8d89-122">If you called [ScInitMapiUtil](scinitmapiutil.md) during session startup to initialize the MAPI utility library, uninitialize it now by calling [DeinitMapiUtil](deinitmapiutil.md).</span></span> <span data-ttu-id="e8d89-123">只有已调用**ScInitMapiUtil**的客户端才必须调用**DeinitMapiUtil**。</span><span class="sxs-lookup"><span data-stu-id="e8d89-123">Only clients that have called **ScInitMapiUtil** must call **DeinitMapiUtil**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e8d89-124">在调用**IMAPISession:: 注销**之前, 必须释放所有打开的对象。</span><span class="sxs-lookup"><span data-stu-id="e8d89-124">All open objects must be released before the call to **IMAPISession::Logoff**.</span></span> <span data-ttu-id="e8d89-125">**注销**后仍处于打开状态的对象将被称为无效。它们无法接受任何呼叫, 并且可能永远无法释放。</span><span class="sxs-lookup"><span data-stu-id="e8d89-125">Objects that remain open after **Logoff** is called become invalid; they cannot accept any calls and might never be freed.</span></span> <span data-ttu-id="e8d89-126">如果对其中一个对象进行了调用, 则预期呼叫将失败。</span><span class="sxs-lookup"><span data-stu-id="e8d89-126">If a call is made to one of these objects, expect the call to fail.</span></span> 
  
 <span data-ttu-id="e8d89-127">MAPI 没有在会话关闭过程中删除 dll 的机制。</span><span class="sxs-lookup"><span data-stu-id="e8d89-127">MAPI has no mechanism for deleting DLLs during the session shutdown process.</span></span> <span data-ttu-id="e8d89-128">仅当配置客户端 (如 "控制面板") 使用 MSG_SERVICE_INSTALL 事件调用其邮件服务入口点函数时, 才能删除服务提供程序的 DLL。</span><span class="sxs-lookup"><span data-stu-id="e8d89-128">A service provider's DLL can only be deleted when a configuration client such as the Control Panel calls its message service entry point function with the MSG_SERVICE_INSTALL event.</span></span> 
  

