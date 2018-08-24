---
title: MAPI 空闲引擎
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 755d096a-2a61-44d2-a765-5d464a857756
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9fdc254053c2d35c83866bd8a076279fd383db02
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583034"
---
# <a name="mapi-idle-engine"></a><span data-ttu-id="2f4ab-103">MAPI 空闲引擎</span><span class="sxs-lookup"><span data-stu-id="2f4ab-103">MAPI Idle Engine</span></span>

  
  
<span data-ttu-id="2f4ab-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f4ab-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f4ab-105">MAPI 提供了几个统称为空闲引擎的功能。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-105">MAPI provides several functions that are collectively known as the idle engine.</span></span> <span data-ttu-id="2f4ab-106">这些功能允许客户端、 通讯簿提供程序和消息存储提供程序在慢速时间内或响应慢时间会话中执行各种任务。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-106">These functions allow clients, address book providers, and message store providers to perform various tasks during slow times in the session or in response to a slow time.</span></span> <span data-ttu-id="2f4ab-107">例如，客户端和服务提供商可以推迟速度慢的操作或关闭一长段仍保留未使用的文件。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-107">For example, clients and service providers can defer slow operations or close files that have remained unused for a lengthy period.</span></span> <span data-ttu-id="2f4ab-108">通常传输提供程序不使用空闲引擎，因为该**IXPLogon::Idle**方法采用其位置。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-108">Transport providers typically do not use the idle engine because the **IXPLogon::Idle** method takes its place.</span></span> <span data-ttu-id="2f4ab-109">有关详细信息，请参阅[IXPLogon::Idle](ixplogon-idle.md)。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-109">For more information, see [IXPLogon::Idle](ixplogon-idle.md).</span></span>
  
<span data-ttu-id="2f4ab-110">若要使用空闲引擎，客户端和服务提供商创建一个包含应 MAPI 子系统空闲时进行的任务的回调函数。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-110">To use the idle engine, clients and service providers create a callback function that contains the tasks that should occur when the MAPI subsystem is idle.</span></span> <span data-ttu-id="2f4ab-111">MAPI 检测到空闲时间后，它会调用此回调函数。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-111">When MAPI detects idle time, it invokes this callback function.</span></span> <span data-ttu-id="2f4ab-112">回调函数遵循**FNIDLE**原型，定义如下：</span><span class="sxs-lookup"><span data-stu-id="2f4ab-112">The callback function follows the **FNIDLE** prototype, defined as follows:</span></span> 
  
 `BOOL (STDAPICALLTYPE FNIDLE) (LPVOID lpvContext)`
  
<span data-ttu-id="2f4ab-113">有关详细信息，请参阅[FNIDLE](fnidle.md)。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-113">For more information, see [FNIDLE](fnidle.md).</span></span>
  
<span data-ttu-id="2f4ab-114">构成空闲引擎的功能是：</span><span class="sxs-lookup"><span data-stu-id="2f4ab-114">The functions that make up the idle engine are:</span></span>
  
[<span data-ttu-id="2f4ab-115">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="2f4ab-115">ChangeIdleRoutine</span></span>](changeidleroutine.md)
  
[<span data-ttu-id="2f4ab-116">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="2f4ab-116">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md)
  
[<span data-ttu-id="2f4ab-117">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="2f4ab-117">EnableIdleRoutine</span></span>](enableidleroutine.md)
  
[<span data-ttu-id="2f4ab-118">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="2f4ab-118">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md)
  
[<span data-ttu-id="2f4ab-119">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="2f4ab-119">MAPIDeInitIdle</span></span>](mapideinitidle.md)
  
[<span data-ttu-id="2f4ab-120">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="2f4ab-120">MAPIInitIdle</span></span>](mapiinitidle.md)
  
<span data-ttu-id="2f4ab-121">若要注册回调函数，客户端和服务提供商，请调用**FtgRegisterIdleRoutine**函数。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-121">To register a callback function, clients and service providers call the **FtgRegisterIdleRoutine** function.</span></span> <span data-ttu-id="2f4ab-122">输入的参数包含可选的优先级，传递给回调函数中作为输入，一段时间以任何方式相应，要使用的内存块和一选项的标志。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-122">The input parameters include an optional priority, a block of memory that is passed to your callback function as input, an amount of time to be used in any way appropriate, and a set of option flags.</span></span> 
  
<span data-ttu-id="2f4ab-123">客户端和服务提供商可以控制空闲函数的运行方式_priIdle_参数中指定的优先级，或指定零，如果优先级不是问题。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-123">Clients and service providers can specify a priority in the  _priIdle_ parameter that controls how the idle function runs or specify zero if priority is not an issue.</span></span> <span data-ttu-id="2f4ab-124">由于负数表示比正数或 0 更高的优先级，压缩和搜索操作应分配给负数。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-124">Because negative numbers represent higher priorities than positive numbers or zero, compression and search operations should be assigned negative numbers.</span></span> <span data-ttu-id="2f4ab-125">应将出现一次的任务分配正数。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-125">Tasks that occur once should be assigned positive numbers.</span></span> 
  
<span data-ttu-id="2f4ab-126">若要取消注册的活动的回调函数，客户端和服务提供商，请调用**DeregisterIdleRoutine**函数。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-126">To deregister an active callback function, clients and service providers call the **DeregisterIdleRoutine** function.</span></span> <span data-ttu-id="2f4ab-127">因为**DeregisterIdleRoutine**异步操作，很可能随时取消注册呼叫过程中调用的回调函数和甚至可能返回了**DeregisterIdleRoutine**之后。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-127">Because **DeregisterIdleRoutine** operates asynchronously, it is possible for the callback function to be invoked at any time during the deregister call and possibly even after **DeregisterIdleRoutine** has returned.</span></span> 
  
<span data-ttu-id="2f4ab-128">若要修改的特征的回调函数的部分或全部，客户端和服务提供商，请调用**ChangeIdleRoutine**函数。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-128">To modify some or all of the characteristics of a callback function, clients and service providers call the **ChangeIdleRoutine** function.</span></span> <span data-ttu-id="2f4ab-129">**ChangeIdleRoutine**进行根据如何设置 flags 参数_ircIdle_ ; 更改**ChangeIdleRoutine**可以更改函数本身、 其优先级、 时间设置和输入的参数。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-129">**ChangeIdleRoutine** makes changes according to how the flags parameter  _ircIdle_ is set; **ChangeIdleRoutine** can change the function itself, its priority, time setting, and input parameter.</span></span> 
  
<span data-ttu-id="2f4ab-130">MAPI 定义空闲时操作系统都有一个定义操作系统相同。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-130">MAPI defines idle the same as the operating system, when the operating system has a definition.</span></span> <span data-ttu-id="2f4ab-131">在 Win32，MAPI 空闲类优先级来安排空闲任务创建一个线程。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-131">On Win32, MAPI creates a thread with idle-class priority to schedule idle tasks.</span></span> <span data-ttu-id="2f4ab-132">此线程跟踪时间并发布到线程的执行空闲任务时执行的时间到达一条消息。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-132">This thread keeps track of the time and posts a message to the thread that is to execute the idle task when the time for its execution arrives.</span></span> <span data-ttu-id="2f4ab-133">Win32 安排线程，不处理。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-133">Win32 schedules threads, not processes.</span></span> <span data-ttu-id="2f4ab-134">如果在工作站上出现高于空闲优先级的优先级的任务，空闲任务应不获取之前计划执行任务已完成。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-134">If tasks that have a priority higher than the idle priority are occurring on the workstation, the idle task should not get scheduled for execution until the tasks have completed.</span></span> 
  
<span data-ttu-id="2f4ab-135">在调用**MAPIInitIdle**线程上运行所有空闲的任务。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-135">All idle tasks run on the thread that called **MAPIInitIdle**.</span></span> <span data-ttu-id="2f4ab-136">MAPI 有单独的线程对于安排，但合格空闲任务时，发布一条消息后通过初始化线程并那里执行空闲的任务。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-136">MAPI has a separate thread for scheduling, but when an idle task becomes eligible, it posts a message back over to the initialization thread and the idle task is executed there.</span></span> <span data-ttu-id="2f4ab-137">不同类型的客户端的含义如下所示。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-137">The implications for different types of clients are as follows.</span></span>
  
|<span data-ttu-id="2f4ab-138">**线程模型**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-138">**Threading model**</span></span>|<span data-ttu-id="2f4ab-139">**暗示**</span><span class="sxs-lookup"><span data-stu-id="2f4ab-139">**Implication**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2f4ab-140">单线程</span><span class="sxs-lookup"><span data-stu-id="2f4ab-140">Single-threaded</span></span>  <br/> |<span data-ttu-id="2f4ab-141">没关系。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-141">No problem.</span></span> <span data-ttu-id="2f4ab-142">空闲函数在客户端的主线程上执行，并通过消息循环序列。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-142">Idle functions execute on your client's main thread and are serialized through the message loop.</span></span>  <br/> |
|<span data-ttu-id="2f4ab-143">自由线程</span><span class="sxs-lookup"><span data-stu-id="2f4ab-143">Free-threaded</span></span>  <br/> |<span data-ttu-id="2f4ab-144">空闲函数必须线程安全的但您的客户端已具有必需的基础结构。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-144">Idle functions must be thread-safe, but your client already has the necessary infrastructure.</span></span> <span data-ttu-id="2f4ab-145">您的客户端不可能根本需要 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-145">Your client might not need the MAPI idle engine at all.</span></span>  <br/> |
|<span data-ttu-id="2f4ab-146">单元线程</span><span class="sxs-lookup"><span data-stu-id="2f4ab-146">Apartment-threaded</span></span>  <br/> |<span data-ttu-id="2f4ab-147">空闲函数具有相同注册它，如果要使用 MAPI、 OLE 或任何其他 COM 接口的线程上执行。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-147">Idle function has to execute on the same thread that registered it if it wants to use MAPI, OLE, or any other COM interfaces.</span></span> <span data-ttu-id="2f4ab-148">最简单的方法是使用发布到右的线程一条消息的 MAPI 注册的空闲函数并调度直接从该线程消息循环"实际"空闲函数。</span><span class="sxs-lookup"><span data-stu-id="2f4ab-148">The most straightforward way is to register an idle function with MAPI that posts a message to the right thread and dispatch the "real" idle function directly from that thread's message loop.</span></span>  <br/> |
   

