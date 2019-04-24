---
title: FtgRegisterIdleRoutine
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtgRegisterIdleRoutine
api_type:
- COM
ms.assetid: 8d9557ba-7919-42c6-9e2f-f10214437d53
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b45b80f09efbd4f05aabc2c868d5bd8eb5fa4cce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327991"
---
# <a name="ftgregisteridleroutine"></a><span data-ttu-id="b8914-103">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b8914-103">FtgRegisterIdleRoutine</span></span>

<span data-ttu-id="b8914-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b8914-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b8914-105">向 MAPI 系统添加基于[FNIDLE](fnidle.md)函数的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-105">Adds a [FNIDLE](fnidle.md) function-based idle routine to the MAPI system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b8914-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b8914-106">Header file:</span></span>  <br/> |<span data-ttu-id="b8914-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="b8914-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="b8914-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="b8914-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="b8914-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="b8914-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="b8914-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="b8914-110">Called by:</span></span>  <br/> |<span data-ttu-id="b8914-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="b8914-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FTG FtgRegisterIdleRoutine(
  PFNIDLE pfnIdle,
  LPVOID pvIdleParam,
  short priIdle,
  ULONG csecIdle,
  USHORT iroIdle
);
```

## <a name="parameters"></a><span data-ttu-id="b8914-112">参数</span><span class="sxs-lookup"><span data-stu-id="b8914-112">Parameters</span></span>

<span data-ttu-id="b8914-113">_pfnIdle_</span><span class="sxs-lookup"><span data-stu-id="b8914-113">_pfnIdle_</span></span>
  
> <span data-ttu-id="b8914-114">实时指向空闲例程的指针。</span><span class="sxs-lookup"><span data-stu-id="b8914-114">[in] A pointer to the idle routine.</span></span> 
    
<span data-ttu-id="b8914-115">_pvIdleParam_</span><span class="sxs-lookup"><span data-stu-id="b8914-115">_pvIdleParam_</span></span>
  
> <span data-ttu-id="b8914-116">实时一个指针, 指向空闲引擎在其调用时作为参数传递给空闲例程的内存块。</span><span class="sxs-lookup"><span data-stu-id="b8914-116">[in] A pointer to a block of memory that the idle engine should pass as a parameter to the idle routine when it calls it.</span></span> 
    
<span data-ttu-id="b8914-117">_priIdle_</span><span class="sxs-lookup"><span data-stu-id="b8914-117">_priIdle_</span></span>
  
> <span data-ttu-id="b8914-118">实时空闲例程的初始优先级。</span><span class="sxs-lookup"><span data-stu-id="b8914-118">[in] The initial priority for the idle routine.</span></span> <span data-ttu-id="b8914-119">实现定义的例程的可能优先级大于或小于零, 但不能为零。</span><span class="sxs-lookup"><span data-stu-id="b8914-119">Possible priorities for implementation-defined routines are greater than or less than zero, but not zero.</span></span> <span data-ttu-id="b8914-120">为用户事件 (如鼠标单击或 WM_PAINT 邮件) 保留零优先级。</span><span class="sxs-lookup"><span data-stu-id="b8914-120">The zero priority is reserved for a user event such as a mouse click or a WM_PAINT message.</span></span> <span data-ttu-id="b8914-121">大于零的优先级代表优先级高于用户事件且作为标准 Windows 消息泵循环的一部分进行调度的后台任务。</span><span class="sxs-lookup"><span data-stu-id="b8914-121">Priorities greater than zero represent background tasks that have a higher priority than user events and are dispatched as part of the standard Windows message pump loop.</span></span> <span data-ttu-id="b8914-122">优先级小于零表示仅在消息泵空闲时运行的空闲任务。</span><span class="sxs-lookup"><span data-stu-id="b8914-122">Priorities less than zero represent idle tasks that only run during message pump idle time.</span></span> <span data-ttu-id="b8914-123">优先级如下所示的示例: 1 表示前台提交, 2 表示加电编辑字符插入, 3 用于下载新邮件。</span><span class="sxs-lookup"><span data-stu-id="b8914-123">Examples of priorities are as follows: 1 for foreground submission, 2 for power-edit character insertion, and 3 for downloading new messages.</span></span>
    
<span data-ttu-id="b8914-124">_csecIdle_</span><span class="sxs-lookup"><span data-stu-id="b8914-124">_csecIdle_</span></span>
  
> <span data-ttu-id="b8914-125">实时用于指定空闲例程参数的初始时间值, 以百分之一秒为单位。</span><span class="sxs-lookup"><span data-stu-id="b8914-125">[in] The initial time value, in hundredths of a second, to be used in specifying idle routine parameters.</span></span> <span data-ttu-id="b8914-126">初始时间值的意义各不相同, 具体取决于在_iroIdle_参数中传递的内容。</span><span class="sxs-lookup"><span data-stu-id="b8914-126">The meaning of the initial time value varies, depending on what is passed in the  _iroIdle_ parameter.</span></span> <span data-ttu-id="b8914-127">含义可以是下列之一:</span><span class="sxs-lookup"><span data-stu-id="b8914-127">The meaning can be one of the following:</span></span> 
    
  - <span data-ttu-id="b8914-128">MAPI 空闲引擎首次呼叫空闲例程之前必须经过的最小用户 inaction, 如果_iroIdle_中设置了 FIROWAIT 标志。</span><span class="sxs-lookup"><span data-stu-id="b8914-128">The minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time, if the FIROWAIT flag is set in  _iroIdle_.</span></span> <span data-ttu-id="b8914-129">在此时间过后, 空闲引擎可以根据需要频繁地调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-129">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
  - <span data-ttu-id="b8914-130">如果在_iroIdle_中设置了 FIROINTERVAL 标志, 则调用 idle 例程之间的最小间隔。</span><span class="sxs-lookup"><span data-stu-id="b8914-130">The minimum interval between calls to the idle routine, if the FIROINTERVAL flag is set in  _iroIdle_.</span></span> 
    
<span data-ttu-id="b8914-131">_iroIdle_</span><span class="sxs-lookup"><span data-stu-id="b8914-131">_iroIdle_</span></span>
  
> <span data-ttu-id="b8914-132">实时用于设置空闲例程的初始选项的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="b8914-132">[in] The bitmask of flags used to set initial options for the idle routine.</span></span> <span data-ttu-id="b8914-133">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="b8914-133">The following flags can be set:</span></span>
    
  <span data-ttu-id="b8914-134">FIRONOADJUSTMENT</span><span class="sxs-lookup"><span data-stu-id="b8914-134">FIRONOADJUSTMENT</span></span>
    
  > <span data-ttu-id="b8914-135">使用此标志指定不应为睡眠或恢复调整空闲例程计时器。</span><span class="sxs-lookup"><span data-stu-id="b8914-135">Use this flag to specify that the idle routine timer should not be adjusted for sleep or resume.</span></span> <span data-ttu-id="b8914-136">不带此标志的默认行为是在计算已用时间时排除休眠时间。</span><span class="sxs-lookup"><span data-stu-id="b8914-136">The default behavior without this flag is that sleep time is excluded when calculating the elapsed time.</span></span> <span data-ttu-id="b8914-137">如果传递了 FIRONOADJUSTMENT, 则在计算经过的时间时将包含休眠时间。</span><span class="sxs-lookup"><span data-stu-id="b8914-137">If FIRONOADJUSTMENT is passed then the sleep time is included when calculating elapsed time.</span></span>
      
  <span data-ttu-id="b8914-138">FIRODISABLED</span><span class="sxs-lookup"><span data-stu-id="b8914-138">FIRODISABLED</span></span>
    
  > <span data-ttu-id="b8914-139">应在注册时禁用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-139">The idle routine should be disabled when registered.</span></span> <span data-ttu-id="b8914-140">默认操作是在**FtgRegisterIdleRoutine**注册时启用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-140">The default action is to enable the idle routine when **FtgRegisterIdleRoutine** registers it.</span></span> 
      
  <span data-ttu-id="b8914-141">FIROINTERVAL</span><span class="sxs-lookup"><span data-stu-id="b8914-141">FIROINTERVAL</span></span> 
    
  > <span data-ttu-id="b8914-142">由_csecIdle_参数指定的时间是对 idle 例程的连续调用之间的最小时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b8914-142">The time specified by the  _csecIdle_ parameter is the minimum interval between successive calls to the idle routine.</span></span> 
      
  <span data-ttu-id="b8914-143">FIROONCEONLY</span><span class="sxs-lookup"><span data-stu-id="b8914-143">FIROONCEONLY</span></span> 
    
  > <span data-ttu-id="b8914-144">已过时。</span><span class="sxs-lookup"><span data-stu-id="b8914-144">Obsolete.</span></span> <span data-ttu-id="b8914-145">不得使用。</span><span class="sxs-lookup"><span data-stu-id="b8914-145">Do not use.</span></span> 
      
  <span data-ttu-id="b8914-146">FIROPERBLOCK</span><span class="sxs-lookup"><span data-stu-id="b8914-146">FIROPERBLOCK</span></span> 
    
  > <span data-ttu-id="b8914-147">已过时。</span><span class="sxs-lookup"><span data-stu-id="b8914-147">Obsolete.</span></span> <span data-ttu-id="b8914-148">不得使用。</span><span class="sxs-lookup"><span data-stu-id="b8914-148">Do not use.</span></span> 
      
  <span data-ttu-id="b8914-149">FIROWAIT</span><span class="sxs-lookup"><span data-stu-id="b8914-149">FIROWAIT</span></span> 
    
  > <span data-ttu-id="b8914-150">_csecIdle_参数指定的时间是 MAPI idle engine 首次调用空闲例程之前必须经过的用户 inaction 的最小周期。</span><span class="sxs-lookup"><span data-stu-id="b8914-150">The time specified by the  _csecIdle_ parameter is the minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time.</span></span> <span data-ttu-id="b8914-151">在此时间过后, 空闲引擎可以根据需要频繁地调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-151">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b8914-152">返回值</span><span class="sxs-lookup"><span data-stu-id="b8914-152">Return value</span></span>

<span data-ttu-id="b8914-153">**FtgRegisterIdleRoutine**函数返回一个函数标记, 该标记标识已添加到 MAPI 系统中的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-153">The **FtgRegisterIdleRoutine** function returns a function tag identifying the idle routine that was added to the MAPI system.</span></span> <span data-ttu-id="b8914-154">如果**FtgRegisterIdleRoutine**无法为客户端应用程序或服务提供商注册空闲例程 (例如, 由于内存问题), 它将返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="b8914-154">If **FtgRegisterIdleRoutine** cannot register the idle routine for the client application or service provider, for example because of memory problems, it returns NULL.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="b8914-155">注解</span><span class="sxs-lookup"><span data-stu-id="b8914-155">Remarks</span></span>

<span data-ttu-id="b8914-156">以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-156">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype.</span></span> 
  
|<span data-ttu-id="b8914-157">**Idle 例程函数**</span><span class="sxs-lookup"><span data-stu-id="b8914-157">**Idle routine function**</span></span>|<span data-ttu-id="b8914-158">**使用**</span><span class="sxs-lookup"><span data-stu-id="b8914-158">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b8914-159">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b8914-159">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="b8914-160">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="b8914-160">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="b8914-161">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b8914-161">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="b8914-162">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-162">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="b8914-163">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b8914-163">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="b8914-164">禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="b8914-164">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|<span data-ttu-id="b8914-165">**FtgRegisterIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="b8914-165">**FtgRegisterIdleRoutine**</span></span> <br/> |<span data-ttu-id="b8914-166">将空闲例程添加到 MAPI 系统中 (无论是否启用)。</span><span class="sxs-lookup"><span data-stu-id="b8914-166">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="b8914-167">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="b8914-167">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="b8914-168">关闭呼叫应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="b8914-168">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="b8914-169">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="b8914-169">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="b8914-170">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="b8914-170">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="b8914-171">**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**采用**FtgRegisterIdleRoutine**返回的函数标记作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="b8914-171">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="b8914-172">当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-172">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="b8914-173">在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。</span><span class="sxs-lookup"><span data-stu-id="b8914-173">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  
<span data-ttu-id="b8914-174">以下是在_iroIdle_参数中使用 FIRONOADJUSTMENT 标志的示例。</span><span class="sxs-lookup"><span data-stu-id="b8914-174">The following is an example of using the FIRONOADJUSTMENT flag in the  _iroIdle_ parameter.</span></span> 
  
1. <span data-ttu-id="b8914-175">使用5分钟的延迟注册空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-175">Register an idle routine with a 5 minute delay.</span></span>
    
2. <span data-ttu-id="b8914-176">在1分钟后休眠/睡眠计算机 (计时器剩余4分钟)。</span><span class="sxs-lookup"><span data-stu-id="b8914-176">Hibernate/Sleep the computer after 1 minute (4 minutes left on the timer).</span></span>
    
3. <span data-ttu-id="b8914-177">稍后再将计算机恢复10分钟。</span><span class="sxs-lookup"><span data-stu-id="b8914-177">Resume the computer 10 minutes later.</span></span>
    
<span data-ttu-id="b8914-178">没有 FIRONOADJUSTMENT 的默认行为是, 您仍需要等待4分钟才能运行例程。</span><span class="sxs-lookup"><span data-stu-id="b8914-178">The default behavior, without FIRONOADJUSTMENT, is that you still have to wait 4 more minutes for your routine to run.</span></span> <span data-ttu-id="b8914-179">也就是说, 对计时器进行了调整, 以允许计算机休眠的时间长度。</span><span class="sxs-lookup"><span data-stu-id="b8914-179">That is, your timer was adjusted to allow for how long the computer was asleep.</span></span> <span data-ttu-id="b8914-180">但是, 如果传递 FIRONOADJUSTMENT, 则您的空闲例程将立即运行, 因为实时时间超过5分钟。</span><span class="sxs-lookup"><span data-stu-id="b8914-180">However, if you pass FIRONOADJUSTMENT your idle routine will run immediately because more than 5 minutes of real time have elapsed.</span></span>
  

