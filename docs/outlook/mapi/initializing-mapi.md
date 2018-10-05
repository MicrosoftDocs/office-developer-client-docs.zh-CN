---
title: 初始化 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22ee8157-d74e-4a94-9c76-b9ac736d5211
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5fde3e7eda8d98eb5080fff360616649b1eb96a5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399037"
---
# <a name="initializing-mapi"></a><span data-ttu-id="c21bd-103">初始化 MAPI</span><span class="sxs-lookup"><span data-stu-id="c21bd-103">Initializing MAPI</span></span>

  
  
<span data-ttu-id="c21bd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c21bd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c21bd-105">使用 MAPI 库的所有客户端应用程序必须调用**MAPIInitialize**函数。</span><span class="sxs-lookup"><span data-stu-id="c21bd-105">All client applications that use the MAPI libraries must call the **MAPIInitialize** function.</span></span> <span data-ttu-id="c21bd-106">有关详细信息，请参阅[MAPIInitialize](mapiinitialize.md)。</span><span class="sxs-lookup"><span data-stu-id="c21bd-106">For more information, see [MAPIInitialize](mapiinitialize.md).</span></span> <span data-ttu-id="c21bd-107">**MAPIInitialize**会话初始化全局数据，并准备要接受呼叫的 MAPI 库。</span><span class="sxs-lookup"><span data-stu-id="c21bd-107">**MAPIInitialize** initializes global data for the session and prepares the MAPI libraries to accept calls.</span></span> <span data-ttu-id="c21bd-108">有几个重要在某些情况下设置的标记：</span><span class="sxs-lookup"><span data-stu-id="c21bd-108">There are a few flags that are important to set in some situations:</span></span> 
  
- <span data-ttu-id="c21bd-109">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="c21bd-109">MAPI_NT_SERVICE</span></span>
    
    <span data-ttu-id="c21bd-110">如果您的客户端实现作为 Windows 服务，请设置 MAPI_NT_SERVICE 标志。</span><span class="sxs-lookup"><span data-stu-id="c21bd-110">Set the MAPI_NT_SERVICE flag if your client is implemented as a Windows service.</span></span> <span data-ttu-id="c21bd-111">如果您的客户端是一项 Windows 服务，并且未设置此标志，则 MAPI 不就将其视为服务。</span><span class="sxs-lookup"><span data-stu-id="c21bd-111">If your client is a Windows service and you do not set this flag, MAPI will not recognize it as a service.</span></span> 
    
- <span data-ttu-id="c21bd-112">MAPI_MULTITHREAD_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="c21bd-112">MAPI_MULTITHREAD_NOTIFICATIONS</span></span>
    
    <span data-ttu-id="c21bd-113">MAPI 管理通知的方式与 MAPI_MULTITHREAD_NOTIFICATIONS 标志。</span><span class="sxs-lookup"><span data-stu-id="c21bd-113">The MAPI_MULTITHREAD_NOTIFICATIONS flag relates to how MAPI manages notifications.</span></span> <span data-ttu-id="c21bd-114">MAPI 创建生成通知对象发生变化时收到窗口消息隐藏的窗口。</span><span class="sxs-lookup"><span data-stu-id="c21bd-114">MAPI creates a hidden window that receives window messages when changes occur to an object generating notifications.</span></span> <span data-ttu-id="c21bd-115">此时，导致将通知发送和相应的[IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md)方法，调用处理窗口消息。</span><span class="sxs-lookup"><span data-stu-id="c21bd-115">The window messages are processed at some point, causing the notifications to be sent and the appropriate [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) methods to be called.</span></span> 
    
- <span data-ttu-id="c21bd-116">MAPI_NO_COINIT</span><span class="sxs-lookup"><span data-stu-id="c21bd-116">MAPI_NO_COINIT</span></span>
    
    <span data-ttu-id="c21bd-117">设置 MAPI_NO_COINT 标志，以便不会尝试通过调用[CoInitialize](https://msdn.microsoft.com/library/ms886303.aspx)初始化 COM **MAPIInitialize** 。</span><span class="sxs-lookup"><span data-stu-id="c21bd-117">Set the MAPI_NO_COINT flag so that **MAPIInitialize** does not try to initialize COM with a call to [CoInitialize](https://msdn.microsoft.com/library/ms886303.aspx).</span></span> <span data-ttu-id="c21bd-118">如果**MAPIINIT_0**结构与_ulFlags_设置为 MAPI_NO_COINIT 一起传递到**MAPIInitialize** ，MAPI 将假定 COM 已初始化和绕过**CoInitialize**调用。</span><span class="sxs-lookup"><span data-stu-id="c21bd-118">If a **MAPIINIT_0** structure is passed into **MAPIInitialize** with  _ulFlags_ set to MAPI_NO_COINIT, MAPI will assume that COM has already been initialized and bypass the call to **CoInitialize**.</span></span>
    
<span data-ttu-id="c21bd-119">MAPI 不传递 MAPI_MULTITHREAD_NOTIFICATIONS 标志，如果使用的线程上创建通知窗口的第一个**MAPIInitialize**呼叫。</span><span class="sxs-lookup"><span data-stu-id="c21bd-119">If MAPI_MULTITHREAD_NOTIFICATIONS flag is not passed, MAPI creates the notification window on the thread that was used for your first **MAPIInitialize** call.</span></span> <span data-ttu-id="c21bd-120">MAPI 在如果传递 MAPI_MULTITHREAD_NOTIFICATIONS 单独的线程上创建通知窗口 — 线程专门处理通知。</span><span class="sxs-lookup"><span data-stu-id="c21bd-120">MAPI creates the notification window on a separate thread if MAPI_MULTITHREAD_NOTIFICATIONS is passed — a thread dedicated to handling notifications.</span></span> <span data-ttu-id="c21bd-121">MAPI 期望用于创建隐藏的通知窗口的主题：</span><span class="sxs-lookup"><span data-stu-id="c21bd-121">MAPI expects the thread that is used to create the hidden notification window to:</span></span> 
  
- <span data-ttu-id="c21bd-122">具有邮件循环。</span><span class="sxs-lookup"><span data-stu-id="c21bd-122">Have a message loop.</span></span>
    
- <span data-ttu-id="c21bd-123">保持取消整个生命周期中的会话。</span><span class="sxs-lookup"><span data-stu-id="c21bd-123">Remain unblocked throughout the life of the session.</span></span>
    
- <span data-ttu-id="c21bd-124">具有比由您的客户端创建的任何其他线程较长的生存期。</span><span class="sxs-lookup"><span data-stu-id="c21bd-124">Have a longer lifetime than any other thread created by your client.</span></span> 
    
<span data-ttu-id="c21bd-125">您可以选择使用哪个线程设置第一个**MAPIInitialize**调用中的标志。</span><span class="sxs-lookup"><span data-stu-id="c21bd-125">You can choose which thread is used by setting a flag in the first **MAPIInitialize** call.</span></span> <span data-ttu-id="c21bd-126">在允许您线程处理通知之一危险是，如果线程消失，就会蒙受通知窗口，不再将通知发送给任何其他线程。</span><span class="sxs-lookup"><span data-stu-id="c21bd-126">The danger in allowing one of your threads to handle the notifications is that if the thread disappears, the notification window is destroyed and notifications can no longer be sent to any of your other threads.</span></span> <span data-ttu-id="c21bd-127">此外，可能需要特殊处理来控制发布到隐藏的窗口的消息队列的通知消息调度。</span><span class="sxs-lookup"><span data-stu-id="c21bd-127">Also, special processing might be needed to control the dispatching of the notification messages that are posted to the hidden window's message queue.</span></span> 
  
<span data-ttu-id="c21bd-128">如果您使用一个单独的窗口来处理通知，保证通知将显示在相应的线程上适当的时间。</span><span class="sxs-lookup"><span data-stu-id="c21bd-128">If you use a separate window to handle notifications, be assured that notifications will appear at the appropriate time on an appropriate thread.</span></span> <span data-ttu-id="c21bd-129">您无需任何特殊代码以检查和处理发布到通知窗口 Windows 消息。</span><span class="sxs-lookup"><span data-stu-id="c21bd-129">You will not need any special code to check for and process the Windows messages that are posted to the notification window.</span></span> 
  
<span data-ttu-id="c21bd-130">MAPI 建议以下类型的客户端应用程序使用单独的线程创建通知支持隐藏窗口：</span><span class="sxs-lookup"><span data-stu-id="c21bd-130">MAPI recommends that the following types of client applications use a separate thread to create the hidden window for notification support:</span></span>
  
- <span data-ttu-id="c21bd-131">多线程的所有客户端。</span><span class="sxs-lookup"><span data-stu-id="c21bd-131">All multithreaded clients.</span></span>
    
- <span data-ttu-id="c21bd-132">单线程 Windows 服务和 Win32 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="c21bd-132">Single-threaded Windows services and Win32 console applications.</span></span>
    
- <span data-ttu-id="c21bd-133">单线程的客户端不需要其主线程用于通知。</span><span class="sxs-lookup"><span data-stu-id="c21bd-133">Single-threaded clients that do not need to use their main thread for notification.</span></span>
    
<span data-ttu-id="c21bd-134">若要使用单独的线程方法，请对每个线程，设置 MAPI_MULTITHREAD_NOTIFICATIONS 标志调用**MAPIInitialize** 。</span><span class="sxs-lookup"><span data-stu-id="c21bd-134">To use the separate thread approach, call **MAPIInitialize** on every thread, setting the MAPI_MULTITHREAD_NOTIFICATIONS flag.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c21bd-135">仅客户端的第一次调用**MAPIInitialize**会创建支持通知隐藏的窗口。</span><span class="sxs-lookup"><span data-stu-id="c21bd-135">Only a client's first call to **MAPIInitialize** causes a hidden window to be created to support notifications.</span></span> <span data-ttu-id="c21bd-136">后续调用仅原因引用计数递增。</span><span class="sxs-lookup"><span data-stu-id="c21bd-136">Subsequent calls only cause a reference count to be incremented.</span></span> 
  

