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
ms.openlocfilehash: d8d591c02bb621c16a1d1b46272b19573ea79785
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428450"
---
# <a name="mapi-idle-engine"></a><span data-ttu-id="cc37f-103">MAPI 空闲引擎</span><span class="sxs-lookup"><span data-stu-id="cc37f-103">MAPI Idle Engine</span></span>

  
  
<span data-ttu-id="cc37f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cc37f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cc37f-105">MAPI 提供了几个统称为空闲引擎的功能。</span><span class="sxs-lookup"><span data-stu-id="cc37f-105">MAPI provides several functions that are collectively known as the idle engine.</span></span> <span data-ttu-id="cc37f-106">这些函数允许客户端、通讯簿提供程序和邮件存储提供程序在会话速度较慢或响应速度较慢时执行各种任务。</span><span class="sxs-lookup"><span data-stu-id="cc37f-106">These functions allow clients, address book providers, and message store providers to perform various tasks during slow times in the session or in response to a slow time.</span></span> <span data-ttu-id="cc37f-107">例如, 客户端和服务提供程序可以推迟运行缓慢的操作, 或关闭在较长时间内仍未使用的文件。</span><span class="sxs-lookup"><span data-stu-id="cc37f-107">For example, clients and service providers can defer slow operations or close files that have remained unused for a lengthy period.</span></span> <span data-ttu-id="cc37f-108">传输提供程序通常不使用空闲引擎, 因为**IXPLogon:: idle**方法会替代它。</span><span class="sxs-lookup"><span data-stu-id="cc37f-108">Transport providers typically do not use the idle engine because the **IXPLogon::Idle** method takes its place.</span></span> <span data-ttu-id="cc37f-109">有关详细信息, 请参阅[IXPLogon:: Idle](ixplogon-idle.md)。</span><span class="sxs-lookup"><span data-stu-id="cc37f-109">For more information, see [IXPLogon::Idle](ixplogon-idle.md).</span></span>
  
<span data-ttu-id="cc37f-110">若要使用空闲引擎, 客户端和服务提供程序将创建一个回调函数, 其中包含当 MAPI 子系统处于空闲状态时应发生的任务。</span><span class="sxs-lookup"><span data-stu-id="cc37f-110">To use the idle engine, clients and service providers create a callback function that contains the tasks that should occur when the MAPI subsystem is idle.</span></span> <span data-ttu-id="cc37f-111">当 MAPI 检测到空闲时间时, 它会调用此回调函数。</span><span class="sxs-lookup"><span data-stu-id="cc37f-111">When MAPI detects idle time, it invokes this callback function.</span></span> <span data-ttu-id="cc37f-112">回调函数遵循**FNIDLE**原型, 定义如下:</span><span class="sxs-lookup"><span data-stu-id="cc37f-112">The callback function follows the **FNIDLE** prototype, defined as follows:</span></span> 
  
 `BOOL (STDAPICALLTYPE FNIDLE) (LPVOID lpvContext)`
  
<span data-ttu-id="cc37f-113">有关详细信息, 请参阅[FNIDLE](fnidle.md)。</span><span class="sxs-lookup"><span data-stu-id="cc37f-113">For more information, see [FNIDLE](fnidle.md).</span></span>
  
<span data-ttu-id="cc37f-114">组成空闲引擎的函数包括:</span><span class="sxs-lookup"><span data-stu-id="cc37f-114">The functions that make up the idle engine are:</span></span>
  
[<span data-ttu-id="cc37f-115">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="cc37f-115">ChangeIdleRoutine</span></span>](changeidleroutine.md)
  
[<span data-ttu-id="cc37f-116">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="cc37f-116">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md)
  
[<span data-ttu-id="cc37f-117">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="cc37f-117">EnableIdleRoutine</span></span>](enableidleroutine.md)
  
[<span data-ttu-id="cc37f-118">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="cc37f-118">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md)
  
[<span data-ttu-id="cc37f-119">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="cc37f-119">MAPIDeInitIdle</span></span>](mapideinitidle.md)
  
[<span data-ttu-id="cc37f-120">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="cc37f-120">MAPIInitIdle</span></span>](mapiinitidle.md)
  
<span data-ttu-id="cc37f-121">若要注册回调函数, 客户端和服务提供程序将调用**FtgRegisterIdleRoutine**函数。</span><span class="sxs-lookup"><span data-stu-id="cc37f-121">To register a callback function, clients and service providers call the **FtgRegisterIdleRoutine** function.</span></span> <span data-ttu-id="cc37f-122">输入参数包括一个可选的优先级、作为输入传递给回调函数的内存块、用于任何适当的方式的时间量以及一组选项标志。</span><span class="sxs-lookup"><span data-stu-id="cc37f-122">The input parameters include an optional priority, a block of memory that is passed to your callback function as input, an amount of time to be used in any way appropriate, and a set of option flags.</span></span> 
  
<span data-ttu-id="cc37f-123">客户端和服务提供程序可以在_priIdle_参数中指定一个优先级, 该参数控制 idle 函数的运行方式, 或指定零 (如果优先级不是问题)。</span><span class="sxs-lookup"><span data-stu-id="cc37f-123">Clients and service providers can specify a priority in the  _priIdle_ parameter that controls how the idle function runs or specify zero if priority is not an issue.</span></span> <span data-ttu-id="cc37f-124">由于负数表示的优先级高于正数或零, 因此应为压缩和搜索操作分配负数。</span><span class="sxs-lookup"><span data-stu-id="cc37f-124">Because negative numbers represent higher priorities than positive numbers or zero, compression and search operations should be assigned negative numbers.</span></span> <span data-ttu-id="cc37f-125">应为只发生一次的任务分配正数。</span><span class="sxs-lookup"><span data-stu-id="cc37f-125">Tasks that occur once should be assigned positive numbers.</span></span> 
  
<span data-ttu-id="cc37f-126">若要取消注册活动回调函数, 客户端和服务提供程序将调用**DeregisterIdleRoutine**函数。</span><span class="sxs-lookup"><span data-stu-id="cc37f-126">To deregister an active callback function, clients and service providers call the **DeregisterIdleRoutine** function.</span></span> <span data-ttu-id="cc37f-127">由于**DeregisterIdleRoutine**以异步方式运行, 因此可以在取消注册的过程中随时调用回调函数, 甚至可能在**DeregisterIdleRoutine**返回后调用。</span><span class="sxs-lookup"><span data-stu-id="cc37f-127">Because **DeregisterIdleRoutine** operates asynchronously, it is possible for the callback function to be invoked at any time during the deregister call and possibly even after **DeregisterIdleRoutine** has returned.</span></span> 
  
<span data-ttu-id="cc37f-128">若要修改回调函数的部分或全部特征, 客户端和服务提供程序将调用**ChangeIdleRoutine**函数。</span><span class="sxs-lookup"><span data-stu-id="cc37f-128">To modify some or all of the characteristics of a callback function, clients and service providers call the **ChangeIdleRoutine** function.</span></span> <span data-ttu-id="cc37f-129">**ChangeIdleRoutine**根据如何设置 flags 参数_ircIdle_来进行更改;**ChangeIdleRoutine**可以更改函数本身、其优先级、时间设置和输入参数。</span><span class="sxs-lookup"><span data-stu-id="cc37f-129">**ChangeIdleRoutine** makes changes according to how the flags parameter  _ircIdle_ is set; **ChangeIdleRoutine** can change the function itself, its priority, time setting, and input parameter.</span></span> 
  
<span data-ttu-id="cc37f-130">当操作系统有定义时, MAPI 将定义与操作系统相同的空闲。</span><span class="sxs-lookup"><span data-stu-id="cc37f-130">MAPI defines idle the same as the operating system, when the operating system has a definition.</span></span> <span data-ttu-id="cc37f-131">在 Win32 中, MAPI 将创建一个具有空闲类优先级的线程, 以安排空闲任务。</span><span class="sxs-lookup"><span data-stu-id="cc37f-131">On Win32, MAPI creates a thread with idle-class priority to schedule idle tasks.</span></span> <span data-ttu-id="cc37f-132">此线程跟踪时间, 并将邮件发送到在其执行到达时执行空闲任务的线程。</span><span class="sxs-lookup"><span data-stu-id="cc37f-132">This thread keeps track of the time and posts a message to the thread that is to execute the idle task when the time for its execution arrives.</span></span> <span data-ttu-id="cc37f-133">Win32 调度线程, 而不是进程。</span><span class="sxs-lookup"><span data-stu-id="cc37f-133">Win32 schedules threads, not processes.</span></span> <span data-ttu-id="cc37f-134">如果在工作站上发生优先级高于空闲优先级的任务, 则在任务完成之前, 空闲任务不应计划执行。</span><span class="sxs-lookup"><span data-stu-id="cc37f-134">If tasks that have a priority higher than the idle priority are occurring on the workstation, the idle task should not get scheduled for execution until the tasks have completed.</span></span> 
  
<span data-ttu-id="cc37f-135">所有空闲任务都在名为**MAPIInitIdle**的线程上运行。</span><span class="sxs-lookup"><span data-stu-id="cc37f-135">All idle tasks run on the thread that called **MAPIInitIdle**.</span></span> <span data-ttu-id="cc37f-136">MAPI 具有单独的调度线程, 但当空闲任务符合条件时, 它会将一条消息发送回初始化线程, 并在其中执行空闲任务。</span><span class="sxs-lookup"><span data-stu-id="cc37f-136">MAPI has a separate thread for scheduling, but when an idle task becomes eligible, it posts a message back over to the initialization thread and the idle task is executed there.</span></span> <span data-ttu-id="cc37f-137">不同类型的客户端的含义如下所示。</span><span class="sxs-lookup"><span data-stu-id="cc37f-137">The implications for different types of clients are as follows.</span></span>
  
|<span data-ttu-id="cc37f-138">**线程模型**</span><span class="sxs-lookup"><span data-stu-id="cc37f-138">**Threading model**</span></span>|<span data-ttu-id="cc37f-139">**含义**</span><span class="sxs-lookup"><span data-stu-id="cc37f-139">**Implication**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc37f-140">单线程</span><span class="sxs-lookup"><span data-stu-id="cc37f-140">Single-threaded</span></span>  <br/> |<span data-ttu-id="cc37f-141">没关系。</span><span class="sxs-lookup"><span data-stu-id="cc37f-141">No problem.</span></span> <span data-ttu-id="cc37f-142">Idle 函数在客户端的主线程上执行, 并通过消息循环进行序列化。</span><span class="sxs-lookup"><span data-stu-id="cc37f-142">Idle functions execute on your client's main thread and are serialized through the message loop.</span></span>  <br/> |
|<span data-ttu-id="cc37f-143">自由线程</span><span class="sxs-lookup"><span data-stu-id="cc37f-143">Free-threaded</span></span>  <br/> |<span data-ttu-id="cc37f-144">Idle 函数必须是线程安全的, 但您的客户端已经具有必要的基础结构。</span><span class="sxs-lookup"><span data-stu-id="cc37f-144">Idle functions must be thread-safe, but your client already has the necessary infrastructure.</span></span> <span data-ttu-id="cc37f-145">您的客户端可能根本不需要 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="cc37f-145">Your client might not need the MAPI idle engine at all.</span></span>  <br/> |
|<span data-ttu-id="cc37f-146">单元线程</span><span class="sxs-lookup"><span data-stu-id="cc37f-146">Apartment-threaded</span></span>  <br/> |<span data-ttu-id="cc37f-147">Idle 函数必须在注册它的同一线程上执行, 如果它要使用 MAPI、OLE 或任何其他 COM 接口。</span><span class="sxs-lookup"><span data-stu-id="cc37f-147">Idle function has to execute on the same thread that registered it if it wants to use MAPI, OLE, or any other COM interfaces.</span></span> <span data-ttu-id="cc37f-148">最简单的方法是使用 MAPI 注册 idle 函数, 以便将邮件发布到右侧线程, 并直接从该线程的邮件循环发送 "真实" 空闲函数。</span><span class="sxs-lookup"><span data-stu-id="cc37f-148">The most straightforward way is to register an idle function with MAPI that posts a message to the right thread and dispatch the "real" idle function directly from that thread's message loop.</span></span>  <br/> |
   

