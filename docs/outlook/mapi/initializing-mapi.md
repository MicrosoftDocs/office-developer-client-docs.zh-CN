---
title: 初始化 MAPI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22ee8157-d74e-4a94-9c76-b9ac736d5211
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5fde3e7eda8d98eb5080fff360616649b1eb96a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309728"
---
# <a name="initializing-mapi"></a><span data-ttu-id="d9bcd-103">初始化 MAPI</span><span class="sxs-lookup"><span data-stu-id="d9bcd-103">Initializing MAPI</span></span>

  
  
<span data-ttu-id="d9bcd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9bcd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9bcd-105">所有使用 MAPI 库的客户端应用程序都必须调用 **MAPIInitialize** 函数。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-105">All client applications that use the MAPI libraries must call the **MAPIInitialize** function.</span></span> <span data-ttu-id="d9bcd-106">有关详细信息，请参阅 [MAPIInitialize](mapiinitialize.md)。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-106">For more information, see [MAPIInitialize](mapiinitialize.md).</span></span> <span data-ttu-id="d9bcd-107">**MAPIInitialize** 初始化会话的全局数据，并准备 MAPI 库以接受呼叫。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-107">**MAPIInitialize** initializes global data for the session and prepares the MAPI libraries to accept calls.</span></span> <span data-ttu-id="d9bcd-108">在某些情况下，有几个重要的标志需要设置：</span><span class="sxs-lookup"><span data-stu-id="d9bcd-108">There are a few flags that are important to set in some situations:</span></span> 
  
- <span data-ttu-id="d9bcd-109">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="d9bcd-109">MAPI_NT_SERVICE</span></span>
    
    <span data-ttu-id="d9bcd-110">如果客户端MAPI_NT_SERVICE服务实现，请设置 Windows 标志。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-110">Set the MAPI_NT_SERVICE flag if your client is implemented as a Windows service.</span></span> <span data-ttu-id="d9bcd-111">如果你的客户端是Windows服务，并且未设置此标志，MAPI 将不会将它识别为服务。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-111">If your client is a Windows service and you do not set this flag, MAPI will not recognize it as a service.</span></span> 
    
- <span data-ttu-id="d9bcd-112">MAPI_MULTITHREAD_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="d9bcd-112">MAPI_MULTITHREAD_NOTIFICATIONS</span></span>
    
    <span data-ttu-id="d9bcd-113">the MAPI_MULTITHREAD_NOTIFICATIONS flag relates to how MAPI manages notifications.</span><span class="sxs-lookup"><span data-stu-id="d9bcd-113">The MAPI_MULTITHREAD_NOTIFICATIONS flag relates to how MAPI manages notifications.</span></span> <span data-ttu-id="d9bcd-114">MAPI 创建一个隐藏窗口，该窗口在生成通知的对象发生更改时接收窗口消息。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-114">MAPI creates a hidden window that receives window messages when changes occur to an object generating notifications.</span></span> <span data-ttu-id="d9bcd-115">此时将处理窗口消息，从而发送通知并调用相应的 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-115">The window messages are processed at some point, causing the notifications to be sent and the appropriate [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) methods to be called.</span></span> 
    
- <span data-ttu-id="d9bcd-116">MAPI_NO_COINIT</span><span class="sxs-lookup"><span data-stu-id="d9bcd-116">MAPI_NO_COINIT</span></span>
    
    <span data-ttu-id="d9bcd-117">设置 MAPI_NO_COINT 标志，以便 **MAPIInitialize** 不会尝试使用对 [CoInitialize](https://msdn.microsoft.com/library/ms886303.aspx)的调用初始化 COM。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-117">Set the MAPI_NO_COINT flag so that **MAPIInitialize** does not try to initialize COM with a call to [CoInitialize](https://msdn.microsoft.com/library/ms886303.aspx).</span></span> <span data-ttu-id="d9bcd-118">如果将MAPIINIT_0传递到 **MAPIInitialize，** 并且 _ulFlags_ 设置为 MAPI_NO_COINIT，MAPI 将假定 COM 已初始化，并绕过对 **CoInitialize 的调用**。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-118">If a **MAPIINIT_0** structure is passed into **MAPIInitialize** with  _ulFlags_ set to MAPI_NO_COINIT, MAPI will assume that COM has already been initialized and bypass the call to **CoInitialize**.</span></span>
    
<span data-ttu-id="d9bcd-119">如果未MAPI_MULTITHREAD_NOTIFICATIONS，MAPI 在用于第一个 **MAPIInitialize** 调用的线程上创建通知窗口。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-119">If MAPI_MULTITHREAD_NOTIFICATIONS flag is not passed, MAPI creates the notification window on the thread that was used for your first **MAPIInitialize** call.</span></span> <span data-ttu-id="d9bcd-120">MAPI 在单独的线程上创建通知窗口（如果MAPI_MULTITHREAD_NOTIFICATIONS一个专用于处理通知的线程）。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-120">MAPI creates the notification window on a separate thread if MAPI_MULTITHREAD_NOTIFICATIONS is passed — a thread dedicated to handling notifications.</span></span> <span data-ttu-id="d9bcd-121">MAPI 期望用于创建隐藏通知窗口的线程：</span><span class="sxs-lookup"><span data-stu-id="d9bcd-121">MAPI expects the thread that is used to create the hidden notification window to:</span></span> 
  
- <span data-ttu-id="d9bcd-122">具有消息循环。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-122">Have a message loop.</span></span>
    
- <span data-ttu-id="d9bcd-123">在会话的整个生命周期中保持未阻止状态。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-123">Remain unblocked throughout the life of the session.</span></span>
    
- <span data-ttu-id="d9bcd-124">生存期比客户端创建的其他线程长。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-124">Have a longer lifetime than any other thread created by your client.</span></span> 
    
<span data-ttu-id="d9bcd-125">可以通过设置第一个 **MAPIInitialize** 调用中的标记来选择使用哪个线程。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-125">You can choose which thread is used by setting a flag in the first **MAPIInitialize** call.</span></span> <span data-ttu-id="d9bcd-126">允许其中一个线程处理通知有一个危险，即如果线程消失，通知窗口将被破坏，并且通知无法再发送到任何其他线程。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-126">The danger in allowing one of your threads to handle the notifications is that if the thread disappears, the notification window is destroyed and notifications can no longer be sent to any of your other threads.</span></span> <span data-ttu-id="d9bcd-127">此外，可能需要特殊处理来控制发送到隐藏窗口的邮件队列的通知邮件的调度。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-127">Also, special processing might be needed to control the dispatching of the notification messages that are posted to the hidden window's message queue.</span></span> 
  
<span data-ttu-id="d9bcd-128">如果使用单独的窗口来处理通知，则确保通知将在适当的时间显示在适当的线程上。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-128">If you use a separate window to handle notifications, be assured that notifications will appear at the appropriate time on an appropriate thread.</span></span> <span data-ttu-id="d9bcd-129">不需要任何特殊代码来检查并处理Windows通知窗口的邮件。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-129">You will not need any special code to check for and process the Windows messages that are posted to the notification window.</span></span> 
  
<span data-ttu-id="d9bcd-130">MAPI 建议以下类型的客户端应用程序使用单独的线程来创建隐藏的窗口，以用于通知支持：</span><span class="sxs-lookup"><span data-stu-id="d9bcd-130">MAPI recommends that the following types of client applications use a separate thread to create the hidden window for notification support:</span></span>
  
- <span data-ttu-id="d9bcd-131">所有多线程客户端。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-131">All multithreaded clients.</span></span>
    
- <span data-ttu-id="d9bcd-132">单线程管理Windows Win32 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-132">Single-threaded Windows services and Win32 console applications.</span></span>
    
- <span data-ttu-id="d9bcd-133">不需要使用主线程进行通知的单线程客户端。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-133">Single-threaded clients that do not need to use their main thread for notification.</span></span>
    
<span data-ttu-id="d9bcd-134">若要使用单独的线程方法，请调用每个线程上的 **MAPIInitialize，** 并设置MAPI_MULTITHREAD_NOTIFICATIONS标志。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-134">To use the separate thread approach, call **MAPIInitialize** on every thread, setting the MAPI_MULTITHREAD_NOTIFICATIONS flag.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d9bcd-135">只有客户端首次调用 **MAPIInitialize** 会导致创建隐藏窗口以支持通知。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-135">Only a client's first call to **MAPIInitialize** causes a hidden window to be created to support notifications.</span></span> <span data-ttu-id="d9bcd-136">后续调用仅会导致引用计数递增。</span><span class="sxs-lookup"><span data-stu-id="d9bcd-136">Subsequent calls only cause a reference count to be incremented.</span></span> 
  

