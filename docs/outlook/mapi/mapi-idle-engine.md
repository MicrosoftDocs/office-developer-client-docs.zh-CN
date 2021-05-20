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
# <a name="mapi-idle-engine"></a><span data-ttu-id="19749-103">MAPI 空闲引擎</span><span class="sxs-lookup"><span data-stu-id="19749-103">MAPI Idle Engine</span></span>

  
  
<span data-ttu-id="19749-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="19749-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="19749-105">MAPI 提供了多个统称为空闲引擎的函数。</span><span class="sxs-lookup"><span data-stu-id="19749-105">MAPI provides several functions that are collectively known as the idle engine.</span></span> <span data-ttu-id="19749-106">这些函数允许客户端、通讯簿提供程序和邮件存储提供程序在会话的较慢时间或为响应较慢的时间执行各种任务。</span><span class="sxs-lookup"><span data-stu-id="19749-106">These functions allow clients, address book providers, and message store providers to perform various tasks during slow times in the session or in response to a slow time.</span></span> <span data-ttu-id="19749-107">例如，客户端和服务提供商可以延迟较慢的操作或关闭长时间未使用的文件。</span><span class="sxs-lookup"><span data-stu-id="19749-107">For example, clients and service providers can defer slow operations or close files that have remained unused for a lengthy period.</span></span> <span data-ttu-id="19749-108">传输提供程序通常不使用空闲引擎，因为 **IXPLogon：：Idle** 方法将处于其位置。</span><span class="sxs-lookup"><span data-stu-id="19749-108">Transport providers typically do not use the idle engine because the **IXPLogon::Idle** method takes its place.</span></span> <span data-ttu-id="19749-109">有关详细信息，请参阅 [IXPLogon：：Idle](ixplogon-idle.md)。</span><span class="sxs-lookup"><span data-stu-id="19749-109">For more information, see [IXPLogon::Idle](ixplogon-idle.md).</span></span>
  
<span data-ttu-id="19749-110">若要使用空闲引擎，客户端和服务提供商会创建一个回调函数，其中包含 MAPI 子系统处于空闲状态时应执行的任务。</span><span class="sxs-lookup"><span data-stu-id="19749-110">To use the idle engine, clients and service providers create a callback function that contains the tasks that should occur when the MAPI subsystem is idle.</span></span> <span data-ttu-id="19749-111">当 MAPI 检测到空闲时间时，它将调用此回调函数。</span><span class="sxs-lookup"><span data-stu-id="19749-111">When MAPI detects idle time, it invokes this callback function.</span></span> <span data-ttu-id="19749-112">回调函数遵循 **FNIDLE** 原型，定义如下：</span><span class="sxs-lookup"><span data-stu-id="19749-112">The callback function follows the **FNIDLE** prototype, defined as follows:</span></span> 
  
 `BOOL (STDAPICALLTYPE FNIDLE) (LPVOID lpvContext)`
  
<span data-ttu-id="19749-113">有关详细信息，请参阅 [FNIDLE](fnidle.md)。</span><span class="sxs-lookup"><span data-stu-id="19749-113">For more information, see [FNIDLE](fnidle.md).</span></span>
  
<span data-ttu-id="19749-114">作为空闲引擎的一些功能包括：</span><span class="sxs-lookup"><span data-stu-id="19749-114">The functions that make up the idle engine are:</span></span>
  
[<span data-ttu-id="19749-115">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="19749-115">ChangeIdleRoutine</span></span>](changeidleroutine.md)
  
[<span data-ttu-id="19749-116">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="19749-116">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md)
  
[<span data-ttu-id="19749-117">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="19749-117">EnableIdleRoutine</span></span>](enableidleroutine.md)
  
[<span data-ttu-id="19749-118">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="19749-118">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md)
  
[<span data-ttu-id="19749-119">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="19749-119">MAPIDeInitIdle</span></span>](mapideinitidle.md)
  
[<span data-ttu-id="19749-120">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="19749-120">MAPIInitIdle</span></span>](mapiinitidle.md)
  
<span data-ttu-id="19749-121">为了注册回调函数，客户端和服务提供商调用 **FtgRegisterIdleRoutine** 函数。</span><span class="sxs-lookup"><span data-stu-id="19749-121">To register a callback function, clients and service providers call the **FtgRegisterIdleRoutine** function.</span></span> <span data-ttu-id="19749-122">输入参数包括可选优先级、作为输入传递给回调函数的内存块、以任何适当方式使用的时间量以及一组选项标志。</span><span class="sxs-lookup"><span data-stu-id="19749-122">The input parameters include an optional priority, a block of memory that is passed to your callback function as input, an amount of time to be used in any way appropriate, and a set of option flags.</span></span> 
  
<span data-ttu-id="19749-123">客户端和服务提供商可以在  _priIdle_ 参数中指定一个优先级，该优先级控制空闲函数的运行方式;如果优先级不是问题，则指定零。</span><span class="sxs-lookup"><span data-stu-id="19749-123">Clients and service providers can specify a priority in the  _priIdle_ parameter that controls how the idle function runs or specify zero if priority is not an issue.</span></span> <span data-ttu-id="19749-124">由于负数表示的优先级高于正数或零，因此压缩和搜索操作应分配负数。</span><span class="sxs-lookup"><span data-stu-id="19749-124">Because negative numbers represent higher priorities than positive numbers or zero, compression and search operations should be assigned negative numbers.</span></span> <span data-ttu-id="19749-125">应为一次发生的任务分配正数。</span><span class="sxs-lookup"><span data-stu-id="19749-125">Tasks that occur once should be assigned positive numbers.</span></span> 
  
<span data-ttu-id="19749-126">若要取消注册活动回调函数，客户端和服务提供商将调用 **DeregisterIdleRoutine** 函数。</span><span class="sxs-lookup"><span data-stu-id="19749-126">To deregister an active callback function, clients and service providers call the **DeregisterIdleRoutine** function.</span></span> <span data-ttu-id="19749-127">由于 **DeregisterIdleRoutine** 以异步方式运行，因此在取消注册调用期间，或者即使在 **DeregisterIdleRoutine** 返回后，也随时可能调用回调函数。</span><span class="sxs-lookup"><span data-stu-id="19749-127">Because **DeregisterIdleRoutine** operates asynchronously, it is possible for the callback function to be invoked at any time during the deregister call and possibly even after **DeregisterIdleRoutine** has returned.</span></span> 
  
<span data-ttu-id="19749-128">为了修改回调函数的一些或所有特征，客户端和服务提供商调用 **ChangeIdleRoutine** 函数。</span><span class="sxs-lookup"><span data-stu-id="19749-128">To modify some or all of the characteristics of a callback function, clients and service providers call the **ChangeIdleRoutine** function.</span></span> <span data-ttu-id="19749-129">**ChangeIdleRoutine** 根据 flags 参数  _ircIdle_ 的设置方法进行更改; **ChangeIdleRoutine** 可以更改函数本身、其优先级、时间设置和输入参数。</span><span class="sxs-lookup"><span data-stu-id="19749-129">**ChangeIdleRoutine** makes changes according to how the flags parameter  _ircIdle_ is set; **ChangeIdleRoutine** can change the function itself, its priority, time setting, and input parameter.</span></span> 
  
<span data-ttu-id="19749-130">当操作系统具有定义时，MAPI 定义与操作系统相同的空闲。</span><span class="sxs-lookup"><span data-stu-id="19749-130">MAPI defines idle the same as the operating system, when the operating system has a definition.</span></span> <span data-ttu-id="19749-131">在 Win32 上，MAPI 创建具有空闲类优先级的线程来计划空闲任务。</span><span class="sxs-lookup"><span data-stu-id="19749-131">On Win32, MAPI creates a thread with idle-class priority to schedule idle tasks.</span></span> <span data-ttu-id="19749-132">此线程跟踪时间，并在其执行时间到达时向线程发布消息以执行空闲任务。</span><span class="sxs-lookup"><span data-stu-id="19749-132">This thread keeps track of the time and posts a message to the thread that is to execute the idle task when the time for its execution arrives.</span></span> <span data-ttu-id="19749-133">Win32 计划线程，而不是进程。</span><span class="sxs-lookup"><span data-stu-id="19749-133">Win32 schedules threads, not processes.</span></span> <span data-ttu-id="19749-134">如果工作站上发生优先级高于空闲优先级的任务，则空闲任务不应在任务完成之前计划执行。</span><span class="sxs-lookup"><span data-stu-id="19749-134">If tasks that have a priority higher than the idle priority are occurring on the workstation, the idle task should not get scheduled for execution until the tasks have completed.</span></span> 
  
<span data-ttu-id="19749-135">所有空闲任务在名为 **MAPIInitIdle 的线程上运行**。</span><span class="sxs-lookup"><span data-stu-id="19749-135">All idle tasks run on the thread that called **MAPIInitIdle**.</span></span> <span data-ttu-id="19749-136">MAPI 具有单独的计划线程，但当空闲任务符合条件时，它会将消息发回到初始化线程，并在那里执行空闲任务。</span><span class="sxs-lookup"><span data-stu-id="19749-136">MAPI has a separate thread for scheduling, but when an idle task becomes eligible, it posts a message back over to the initialization thread and the idle task is executed there.</span></span> <span data-ttu-id="19749-137">不同类型的客户端的含义如下所示。</span><span class="sxs-lookup"><span data-stu-id="19749-137">The implications for different types of clients are as follows.</span></span>
  
|<span data-ttu-id="19749-138">**线程模型**</span><span class="sxs-lookup"><span data-stu-id="19749-138">**Threading model**</span></span>|<span data-ttu-id="19749-139">**含义**</span><span class="sxs-lookup"><span data-stu-id="19749-139">**Implication**</span></span>|
|:-----|:-----|
|<span data-ttu-id="19749-140">单线程</span><span class="sxs-lookup"><span data-stu-id="19749-140">Single-threaded</span></span>  <br/> |<span data-ttu-id="19749-141">没问题。</span><span class="sxs-lookup"><span data-stu-id="19749-141">No problem.</span></span> <span data-ttu-id="19749-142">空闲函数在客户端的主线程上执行，并通过消息循环进行序列化。</span><span class="sxs-lookup"><span data-stu-id="19749-142">Idle functions execute on your client's main thread and are serialized through the message loop.</span></span>  <br/> |
|<span data-ttu-id="19749-143">自由线程</span><span class="sxs-lookup"><span data-stu-id="19749-143">Free-threaded</span></span>  <br/> |<span data-ttu-id="19749-144">空闲函数必须是线程安全的，但客户端已具有必要的基础结构。</span><span class="sxs-lookup"><span data-stu-id="19749-144">Idle functions must be thread-safe, but your client already has the necessary infrastructure.</span></span> <span data-ttu-id="19749-145">客户端可能完全不需要 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="19749-145">Your client might not need the MAPI idle engine at all.</span></span>  <br/> |
|<span data-ttu-id="19749-146">单元线程</span><span class="sxs-lookup"><span data-stu-id="19749-146">Apartment-threaded</span></span>  <br/> |<span data-ttu-id="19749-147">如果空闲函数想要使用 MAPI、OLE 或其他任何 COM 接口，必须在同一个注册该函数的线程上执行。</span><span class="sxs-lookup"><span data-stu-id="19749-147">Idle function has to execute on the same thread that registered it if it wants to use MAPI, OLE, or any other COM interfaces.</span></span> <span data-ttu-id="19749-148">最简单的方式是使用 MAPI 注册空闲函数，该函数将消息发送到正确的线程，并直接从该线程的消息循环调度"真实"空闲函数。</span><span class="sxs-lookup"><span data-stu-id="19749-148">The most straightforward way is to register an idle function with MAPI that posts a message to the right thread and dispatch the "real" idle function directly from that thread's message loop.</span></span>  <br/> |
   

