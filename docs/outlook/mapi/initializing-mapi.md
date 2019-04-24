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
# <a name="initializing-mapi"></a><span data-ttu-id="eb2f9-103">初始化 MAPI</span><span class="sxs-lookup"><span data-stu-id="eb2f9-103">Initializing MAPI</span></span>

  
  
<span data-ttu-id="eb2f9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eb2f9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eb2f9-105">使用 MAPI 库的所有客户端应用程序都必须调用**MAPIInitialize**函数。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-105">All client applications that use the MAPI libraries must call the **MAPIInitialize** function.</span></span> <span data-ttu-id="eb2f9-106">有关详细信息, 请参阅[MAPIInitialize](mapiinitialize.md)。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-106">For more information, see [MAPIInitialize](mapiinitialize.md).</span></span> <span data-ttu-id="eb2f9-107">**MAPIInitialize**为会话初始化全局数据, 并准备 MAPI 库以接受呼叫。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-107">**MAPIInitialize** initializes global data for the session and prepares the MAPI libraries to accept calls.</span></span> <span data-ttu-id="eb2f9-108">在某些情况下, 有一些非常重要的标志需要进行设置:</span><span class="sxs-lookup"><span data-stu-id="eb2f9-108">There are a few flags that are important to set in some situations:</span></span> 
  
- <span data-ttu-id="eb2f9-109">MAPI_NT_SERVICE</span><span class="sxs-lookup"><span data-stu-id="eb2f9-109">MAPI_NT_SERVICE</span></span>
    
    <span data-ttu-id="eb2f9-110">如果您的客户端作为 Windows 服务实现, 则设置 MAPI_NT_SERVICE 标志。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-110">Set the MAPI_NT_SERVICE flag if your client is implemented as a Windows service.</span></span> <span data-ttu-id="eb2f9-111">如果你的客户端是 Windows 服务并且你不设置此标志, 则 MAPI 不会将其识别为服务。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-111">If your client is a Windows service and you do not set this flag, MAPI will not recognize it as a service.</span></span> 
    
- <span data-ttu-id="eb2f9-112">MAPI_MULTITHREAD_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="eb2f9-112">MAPI_MULTITHREAD_NOTIFICATIONS</span></span>
    
    <span data-ttu-id="eb2f9-113">MAPI_MULTITHREAD_NOTIFICATIONS 标志与 MAPI 管理通知的方式相关。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-113">The MAPI_MULTITHREAD_NOTIFICATIONS flag relates to how MAPI manages notifications.</span></span> <span data-ttu-id="eb2f9-114">MAPI 创建一个隐藏窗口, 该窗口在生成通知的对象发生更改时接收窗口消息。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-114">MAPI creates a hidden window that receives window messages when changes occur to an object generating notifications.</span></span> <span data-ttu-id="eb2f9-115">窗口消息在某一点进行处理, 从而导致发送通知并调用相应的[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-115">The window messages are processed at some point, causing the notifications to be sent and the appropriate [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) methods to be called.</span></span> 
    
- <span data-ttu-id="eb2f9-116">MAPI_NO_COINIT</span><span class="sxs-lookup"><span data-stu-id="eb2f9-116">MAPI_NO_COINIT</span></span>
    
    <span data-ttu-id="eb2f9-117">设置 MAPI_NO_COINT 标志, 以便**MAPIInitialize**不会尝试使用[CoInitialize](https://msdn.microsoft.com/library/ms886303.aspx)调用来初始化 COM。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-117">Set the MAPI_NO_COINT flag so that **MAPIInitialize** does not try to initialize COM with a call to [CoInitialize](https://msdn.microsoft.com/library/ms886303.aspx).</span></span> <span data-ttu-id="eb2f9-118">如果将**MAPIINIT_0**结构传递到_ulFlags_设置为 MAPI_NO_COINIT 的**MAPIInitialize**中, MAPI 将假定 COM 已初始化, 并绕过**CoInitialize**调用。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-118">If a **MAPIINIT_0** structure is passed into **MAPIInitialize** with  _ulFlags_ set to MAPI_NO_COINIT, MAPI will assume that COM has already been initialized and bypass the call to **CoInitialize**.</span></span>
    
<span data-ttu-id="eb2f9-119">如果未传递 MAPI_MULTITHREAD_NOTIFICATIONS 标志, MAPI 会在用于第一个**MAPIInitialize**呼叫的线程上创建通知窗口。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-119">If MAPI_MULTITHREAD_NOTIFICATIONS flag is not passed, MAPI creates the notification window on the thread that was used for your first **MAPIInitialize** call.</span></span> <span data-ttu-id="eb2f9-120">如果传递了 MAPI_MULTITHREAD_NOTIFICATIONS, MAPI 会在单独的线程上创建通知窗口, 这是一个专用于处理通知的线程。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-120">MAPI creates the notification window on a separate thread if MAPI_MULTITHREAD_NOTIFICATIONS is passed — a thread dedicated to handling notifications.</span></span> <span data-ttu-id="eb2f9-121">MAPI 要求用来创建隐藏的通知窗口的线程执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="eb2f9-121">MAPI expects the thread that is used to create the hidden notification window to:</span></span> 
  
- <span data-ttu-id="eb2f9-122">有一个消息循环。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-122">Have a message loop.</span></span>
    
- <span data-ttu-id="eb2f9-123">在会话生命周期内保持不被阻止。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-123">Remain unblocked throughout the life of the session.</span></span>
    
- <span data-ttu-id="eb2f9-124">生存期比客户端创建的任何其他线程的生存期更长。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-124">Have a longer lifetime than any other thread created by your client.</span></span> 
    
<span data-ttu-id="eb2f9-125">您可以通过在第一个**MAPIInitialize**调用中设置标志来选择要使用哪个线程。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-125">You can choose which thread is used by setting a flag in the first **MAPIInitialize** call.</span></span> <span data-ttu-id="eb2f9-126">允许其中一个线程处理通知的危险在于, 如果线程消失了, 通知窗口将被破坏, 并且通知无法再发送到任何其他线程。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-126">The danger in allowing one of your threads to handle the notifications is that if the thread disappears, the notification window is destroyed and notifications can no longer be sent to any of your other threads.</span></span> <span data-ttu-id="eb2f9-127">此外, 可能还需要进行特殊处理, 以控制发送到隐藏窗口的邮件队列的通知邮件的分派。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-127">Also, special processing might be needed to control the dispatching of the notification messages that are posted to the hidden window's message queue.</span></span> 
  
<span data-ttu-id="eb2f9-128">如果使用单独的窗口处理通知, 请确保通知将在适当的时间出现在适当的线程上。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-128">If you use a separate window to handle notifications, be assured that notifications will appear at the appropriate time on an appropriate thread.</span></span> <span data-ttu-id="eb2f9-129">不需要任何特殊代码即可检查和处理发布到通知窗口的 Windows 消息。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-129">You will not need any special code to check for and process the Windows messages that are posted to the notification window.</span></span> 
  
<span data-ttu-id="eb2f9-130">MAPI 建议以下类型的客户端应用程序使用单独的线程来创建用于通知支持的隐藏窗口:</span><span class="sxs-lookup"><span data-stu-id="eb2f9-130">MAPI recommends that the following types of client applications use a separate thread to create the hidden window for notification support:</span></span>
  
- <span data-ttu-id="eb2f9-131">所有多线程客户端。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-131">All multithreaded clients.</span></span>
    
- <span data-ttu-id="eb2f9-132">单线程 Windows 服务和 Win32 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-132">Single-threaded Windows services and Win32 console applications.</span></span>
    
- <span data-ttu-id="eb2f9-133">不需要使用其主线程进行通知的单线程客户端。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-133">Single-threaded clients that do not need to use their main thread for notification.</span></span>
    
<span data-ttu-id="eb2f9-134">若要使用单独的线程方法, 请在每个线程上调用**MAPIInitialize** , 设置 MAPI_MULTITHREAD_NOTIFICATIONS 标志。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-134">To use the separate thread approach, call **MAPIInitialize** on every thread, setting the MAPI_MULTITHREAD_NOTIFICATIONS flag.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="eb2f9-135">仅客户端对**MAPIInitialize**的第一次调用会导致创建隐藏窗口以支持通知。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-135">Only a client's first call to **MAPIInitialize** causes a hidden window to be created to support notifications.</span></span> <span data-ttu-id="eb2f9-136">后续调用只会导致引用计数递增。</span><span class="sxs-lookup"><span data-stu-id="eb2f9-136">Subsequent calls only cause a reference count to be incremented.</span></span> 
  

