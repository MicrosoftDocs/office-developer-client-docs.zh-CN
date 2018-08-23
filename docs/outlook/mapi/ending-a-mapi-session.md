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
# <a name="ending-a-mapi-session"></a><span data-ttu-id="0228e-103">结束 MAPI 会话</span><span class="sxs-lookup"><span data-stu-id="0228e-103">Ending a MAPI Session</span></span>

  
  
<span data-ttu-id="0228e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0228e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0228e-105">客户端可以响应用户的请求，其会话也立即或处理后所有出站邮件和结束时严重错误发生。</span><span class="sxs-lookup"><span data-stu-id="0228e-105">Clients can end their sessions in response to a user's request, either immediately or after all outbound messages have been processed, and when a critical error occurs.</span></span> <span data-ttu-id="0228e-106">某些客户端需要保持登录以便的待处理的出站邮件可达到传输提供程序和邮件系统的目标。</span><span class="sxs-lookup"><span data-stu-id="0228e-106">Some clients need to stay logged on so that pending outbound messages can reach the transport provider and the destination messaging system.</span></span> <span data-ttu-id="0228e-107">如果这样的客户端发送一条消息，并且立即注销，直到用户登录后，并保持登录要传输的消息的时间不够长消息可以保留在传出队列中。</span><span class="sxs-lookup"><span data-stu-id="0228e-107">If such a client sends a message and immediately logs off, the message may remain in the outgoing queue until a user logs back on and stays logged on long enough for the message to be transmitted.</span></span>
  
 <span data-ttu-id="0228e-108">**当您需要终止会话与 MAPI 子系统**</span><span class="sxs-lookup"><span data-stu-id="0228e-108">**When you need to terminate your session with the MAPI subsystem**</span></span>
  
1. <span data-ttu-id="0228e-109">通过调用每个已注册的对象的**Unadvise**方法取消所有通知注册。</span><span class="sxs-lookup"><span data-stu-id="0228e-109">Cancel the registrations for all notifications by calling the **Unadvise** method of every registered object.</span></span> 
    
2. <span data-ttu-id="0228e-110">通过调用其[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28VS.85%29.aspx)方法释放所有打开的对象。</span><span class="sxs-lookup"><span data-stu-id="0228e-110">Release all open objects by calling their [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28VS.85%29.aspx) methods.</span></span> <span data-ttu-id="0228e-111">打开的对象类型可以包括告知接收器、 状态表、 发件箱文件夹、 一个或多个邮件存储区和通讯簿。</span><span class="sxs-lookup"><span data-stu-id="0228e-111">The types of open objects can include advise sinks, the status table, the Outbox folder, one or more message stores, and the address book.</span></span> 
    
3. <span data-ttu-id="0228e-112">调用[MAPIFreeBuffer](mapifreebuffer.md)以释放任何缓存的条目标识符，如**PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)) 的内存。</span><span class="sxs-lookup"><span data-stu-id="0228e-112">Call [MAPIFreeBuffer](mapifreebuffer.md) to free the memory for any cached entry identifiers, such as **PR_IPM_SUBTREE_ENTRYID** ([PidTagIpmSubtreeEntryId](pidtagipmsubtreeentryid-canonical-property.md)).</span></span>
    
4. <span data-ttu-id="0228e-113">调用[IMAPISession::Logoff](imapisession-logoff.md)，如果您拥有当前共享的会话允许的用户界面和 MAPI_LOGOFF_SHARED 标志设置 MAPI_LOGOFF_UI 标志。</span><span class="sxs-lookup"><span data-stu-id="0228e-113">Call [IMAPISession::Logoff](imapisession-logoff.md), setting the MAPI_LOGOFF_UI flag if you allow a user interface and the MAPI_LOGOFF_SHARED flag if you own the current shared session.</span></span> <span data-ttu-id="0228e-114">**注销**通知其他使用他们应通过发送错误通知注销当前共享的会话的所有客户端。</span><span class="sxs-lookup"><span data-stu-id="0228e-114">**Logoff** notifies all other clients that are using the current shared session that they should log off by sending an error notification.</span></span> 
    
5. <span data-ttu-id="0228e-115">通过调用会话的**IUnknown::Release**方法释放会话指针。</span><span class="sxs-lookup"><span data-stu-id="0228e-115">Release the session pointer by calling the session's **IUnknown::Release** method.</span></span> 
    
6. <span data-ttu-id="0228e-116">如果您在初始化 OLE 库的会话启动期间调用[OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx) ，取消初始化它们现在通过调用[OleUninitialize](http://msdn.microsoft.com/en-us/library/ms691326%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0228e-116">If you called [OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx) during session startup to initialize the OLE libraries, uninitialize them now by calling [OleUninitialize](http://msdn.microsoft.com/en-us/library/ms691326%28VS.85%29.aspx).</span></span> <span data-ttu-id="0228e-117">只有以前呼叫过**OleInitialize**的客户端必须调用**OleUninitialize**。</span><span class="sxs-lookup"><span data-stu-id="0228e-117">Only clients that have called **OleInitialize** must call **OleUninitialize**.</span></span> 
    
7. <span data-ttu-id="0228e-118">通过调用[MAPIUninitialize](mapiuninitialize.md)取消初始化 MAPI 库。</span><span class="sxs-lookup"><span data-stu-id="0228e-118">Uninitialize the MAPI libraries by calling [MAPIUninitialize](mapiuninitialize.md).</span></span> <span data-ttu-id="0228e-119">如果您的某个时刻调用**OleInitialize** ，请确保**OleUninitialize**调用**MAPIUninitialize**到此调用前发生此事件。</span><span class="sxs-lookup"><span data-stu-id="0228e-119">If you called **OleInitialize** at some point, make sure that a call to **OleUninitialize** occurs before this call to **MAPIUninitialize**.</span></span> <span data-ttu-id="0228e-120">Timing 至关重要。</span><span class="sxs-lookup"><span data-stu-id="0228e-120">The timing is crucial.</span></span> <span data-ttu-id="0228e-121">如果调用**OleUninitialize**遵循**MAPIUninitialize**调用，您的客户端可能会丢弃终止。</span><span class="sxs-lookup"><span data-stu-id="0228e-121">If the call to **OleUninitialize** follows the call to **MAPIUninitialize**, your client might terminate ungracefully.</span></span> 
    
8. <span data-ttu-id="0228e-122">如果您在初始化 MAPI 实用程序库的会话启动期间调用[ScInitMapiUtil](scinitmapiutil.md) ，取消初始化它现在通过调用[DeinitMapiUtil](deinitmapiutil.md)。</span><span class="sxs-lookup"><span data-stu-id="0228e-122">If you called [ScInitMapiUtil](scinitmapiutil.md) during session startup to initialize the MAPI utility library, uninitialize it now by calling [DeinitMapiUtil](deinitmapiutil.md).</span></span> <span data-ttu-id="0228e-123">只有以前呼叫过**ScInitMapiUtil**的客户端必须调用**DeinitMapiUtil**。</span><span class="sxs-lookup"><span data-stu-id="0228e-123">Only clients that have called **ScInitMapiUtil** must call **DeinitMapiUtil**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0228e-124">**IMAPISession::Logoff**调用之前，必须释放所有打开的对象。</span><span class="sxs-lookup"><span data-stu-id="0228e-124">All open objects must be released before the call to **IMAPISession::Logoff**.</span></span> <span data-ttu-id="0228e-125">保持打开状态调用**注销**后的对象会变为无效;他们无法接受的所有呼叫，并可能永远不会被释放。</span><span class="sxs-lookup"><span data-stu-id="0228e-125">Objects that remain open after **Logoff** is called become invalid; they cannot accept any calls and might never be freed.</span></span> <span data-ttu-id="0228e-126">如果调用了其中一个对象，希望调用失败。</span><span class="sxs-lookup"><span data-stu-id="0228e-126">If a call is made to one of these objects, expect the call to fail.</span></span> 
  
 <span data-ttu-id="0228e-127">MAPI 具有会话关机过程删除 Dll 没有机制。</span><span class="sxs-lookup"><span data-stu-id="0228e-127">MAPI has no mechanism for deleting DLLs during the session shutdown process.</span></span> <span data-ttu-id="0228e-128">配置客户端，例如控制面板呼叫其消息服务入口点函数与 MSG_SERVICE_INSTALL 事件时，可以仅删除提供程序的 DLL 服务。</span><span class="sxs-lookup"><span data-stu-id="0228e-128">A service provider's DLL can only be deleted when a configuration client such as the Control Panel calls its message service entry point function with the MSG_SERVICE_INSTALL event.</span></span> 
  

