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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418519"
---
# <a name="ftgregisteridleroutine"></a><span data-ttu-id="15efb-103">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="15efb-103">FtgRegisterIdleRoutine</span></span>

<span data-ttu-id="15efb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="15efb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="15efb-105">将 [基于 FNIDLE](fnidle.md) 函数的空闲例程添加到 MAPI 系统。</span><span class="sxs-lookup"><span data-stu-id="15efb-105">Adds a [FNIDLE](fnidle.md) function-based idle routine to the MAPI system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="15efb-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="15efb-106">Header file:</span></span>  <br/> |<span data-ttu-id="15efb-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="15efb-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="15efb-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="15efb-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="15efb-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="15efb-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="15efb-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="15efb-110">Called by:</span></span>  <br/> |<span data-ttu-id="15efb-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="15efb-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FTG FtgRegisterIdleRoutine(
  PFNIDLE pfnIdle,
  LPVOID pvIdleParam,
  short priIdle,
  ULONG csecIdle,
  USHORT iroIdle
);
```

## <a name="parameters"></a><span data-ttu-id="15efb-112">参数</span><span class="sxs-lookup"><span data-stu-id="15efb-112">Parameters</span></span>

<span data-ttu-id="15efb-113">_pfnIdle_</span><span class="sxs-lookup"><span data-stu-id="15efb-113">_pfnIdle_</span></span>
  
> <span data-ttu-id="15efb-114">[in]指向空闲例程的指针。</span><span class="sxs-lookup"><span data-stu-id="15efb-114">[in] A pointer to the idle routine.</span></span> 
    
<span data-ttu-id="15efb-115">_pvIdleParam_</span><span class="sxs-lookup"><span data-stu-id="15efb-115">_pvIdleParam_</span></span>
  
> <span data-ttu-id="15efb-116">[in]指向空闲引擎在调用空闲例程时应作为参数传递的内存块的指针。</span><span class="sxs-lookup"><span data-stu-id="15efb-116">[in] A pointer to a block of memory that the idle engine should pass as a parameter to the idle routine when it calls it.</span></span> 
    
<span data-ttu-id="15efb-117">_priIdle_</span><span class="sxs-lookup"><span data-stu-id="15efb-117">_priIdle_</span></span>
  
> <span data-ttu-id="15efb-118">[in]空闲例程的初始优先级。</span><span class="sxs-lookup"><span data-stu-id="15efb-118">[in] The initial priority for the idle routine.</span></span> <span data-ttu-id="15efb-119">实现定义的例程的可能优先级大于或小于零，但不大于零。</span><span class="sxs-lookup"><span data-stu-id="15efb-119">Possible priorities for implementation-defined routines are greater than or less than zero, but not zero.</span></span> <span data-ttu-id="15efb-120">为用户事件保留零优先级，如鼠标单击或WM_PAINT消息。</span><span class="sxs-lookup"><span data-stu-id="15efb-120">The zero priority is reserved for a user event such as a mouse click or a WM_PAINT message.</span></span> <span data-ttu-id="15efb-121">大于零的优先级表示优先级高于用户事件的后台任务，并作为标准邮件循环的一Windows调度。</span><span class="sxs-lookup"><span data-stu-id="15efb-121">Priorities greater than zero represent background tasks that have a higher priority than user events and are dispatched as part of the standard Windows message pump loop.</span></span> <span data-ttu-id="15efb-122">小于零的优先级表示仅在邮件空闲时间期间运行的空闲任务。</span><span class="sxs-lookup"><span data-stu-id="15efb-122">Priorities less than zero represent idle tasks that only run during message pump idle time.</span></span> <span data-ttu-id="15efb-123">优先级示例如下：1 表示前台提交，2 表示 power-edit 字符插入，3 表示下载新邮件。</span><span class="sxs-lookup"><span data-stu-id="15efb-123">Examples of priorities are as follows: 1 for foreground submission, 2 for power-edit character insertion, and 3 for downloading new messages.</span></span>
    
<span data-ttu-id="15efb-124">_csecIdle_</span><span class="sxs-lookup"><span data-stu-id="15efb-124">_csecIdle_</span></span>
  
> <span data-ttu-id="15efb-125">[in]指定空闲例程参数时所使用的初始时间值（以百分之几秒表示）。</span><span class="sxs-lookup"><span data-stu-id="15efb-125">[in] The initial time value, in hundredths of a second, to be used in specifying idle routine parameters.</span></span> <span data-ttu-id="15efb-126">初始时间值的含义会有所不同，具体取决于  _一节参数中传递_ 的值。</span><span class="sxs-lookup"><span data-stu-id="15efb-126">The meaning of the initial time value varies, depending on what is passed in the  _iroIdle_ parameter.</span></span> <span data-ttu-id="15efb-127">含义可以是下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="15efb-127">The meaning can be one of the following:</span></span> 
    
  - <span data-ttu-id="15efb-128">在 MAPI 空闲引擎首次调用空闲例程之前必须经过的最小用户不操作时段（如果 FIROWAIT 标志在  _创建Idle_ 中设置）。</span><span class="sxs-lookup"><span data-stu-id="15efb-128">The minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time, if the FIROWAIT flag is set in  _iroIdle_.</span></span> <span data-ttu-id="15efb-129">此时间结束后，空闲引擎可以在必要时经常调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="15efb-129">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
  - <span data-ttu-id="15efb-130">如果 FIROINTERVAL 标志在  _分流Idle_ 中设置，则对空闲例程的调用之间的最小间隔。</span><span class="sxs-lookup"><span data-stu-id="15efb-130">The minimum interval between calls to the idle routine, if the FIROINTERVAL flag is set in  _iroIdle_.</span></span> 
    
<span data-ttu-id="15efb-131">_一体式_</span><span class="sxs-lookup"><span data-stu-id="15efb-131">_iroIdle_</span></span>
  
> <span data-ttu-id="15efb-132">[in]用于设置空闲例程的初始选项的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="15efb-132">[in] The bitmask of flags used to set initial options for the idle routine.</span></span> <span data-ttu-id="15efb-133">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="15efb-133">The following flags can be set:</span></span>
    
  <span data-ttu-id="15efb-134">FIRONOADJUSTMENT</span><span class="sxs-lookup"><span data-stu-id="15efb-134">FIRONOADJUSTMENT</span></span>
    
  > <span data-ttu-id="15efb-135">使用此标志指定不应针对睡眠或恢复调整空闲例程计时器。</span><span class="sxs-lookup"><span data-stu-id="15efb-135">Use this flag to specify that the idle routine timer should not be adjusted for sleep or resume.</span></span> <span data-ttu-id="15efb-136">没有此标志的默认行为是在计算已用时间时排除睡眠时间。</span><span class="sxs-lookup"><span data-stu-id="15efb-136">The default behavior without this flag is that sleep time is excluded when calculating the elapsed time.</span></span> <span data-ttu-id="15efb-137">如果传递 FIRONOADJUSTMENT，则计算已用时间时将包含睡眠时间。</span><span class="sxs-lookup"><span data-stu-id="15efb-137">If FIRONOADJUSTMENT is passed then the sleep time is included when calculating elapsed time.</span></span>
      
  <span data-ttu-id="15efb-138">FIRODISABLED</span><span class="sxs-lookup"><span data-stu-id="15efb-138">FIRODISABLED</span></span>
    
  > <span data-ttu-id="15efb-139">注册时应禁用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="15efb-139">The idle routine should be disabled when registered.</span></span> <span data-ttu-id="15efb-140">默认操作是在 **FtgRegisterIdleRoutine** 注册空闲例程时启用该例程。</span><span class="sxs-lookup"><span data-stu-id="15efb-140">The default action is to enable the idle routine when **FtgRegisterIdleRoutine** registers it.</span></span> 
      
  <span data-ttu-id="15efb-141">FIROINTERVAL</span><span class="sxs-lookup"><span data-stu-id="15efb-141">FIROINTERVAL</span></span> 
    
  > <span data-ttu-id="15efb-142">_csecIdle_ 参数指定的时间是连续调用空闲例程之间的最小间隔。</span><span class="sxs-lookup"><span data-stu-id="15efb-142">The time specified by the  _csecIdle_ parameter is the minimum interval between successive calls to the idle routine.</span></span> 
      
  <span data-ttu-id="15efb-143">FIROONCEONLY</span><span class="sxs-lookup"><span data-stu-id="15efb-143">FIROONCEONLY</span></span> 
    
  > <span data-ttu-id="15efb-p107">已过时。不得使用。 </span><span class="sxs-lookup"><span data-stu-id="15efb-p107">Obsolete. Do not use.</span></span> 
      
  <span data-ttu-id="15efb-146">FIROPERBLOCK</span><span class="sxs-lookup"><span data-stu-id="15efb-146">FIROPERBLOCK</span></span> 
    
  > <span data-ttu-id="15efb-p108">已过时。不得使用。 </span><span class="sxs-lookup"><span data-stu-id="15efb-p108">Obsolete. Do not use.</span></span> 
      
  <span data-ttu-id="15efb-149">FIROWAIT</span><span class="sxs-lookup"><span data-stu-id="15efb-149">FIROWAIT</span></span> 
    
  > <span data-ttu-id="15efb-150">_csecIdle_ 参数指定的时间是在 MAPI 空闲引擎首次调用空闲例程之前必须经过的最小用户不操作时段。</span><span class="sxs-lookup"><span data-stu-id="15efb-150">The time specified by the  _csecIdle_ parameter is the minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time.</span></span> <span data-ttu-id="15efb-151">此时间结束后，空闲引擎可以在必要时经常调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="15efb-151">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="15efb-152">返回值</span><span class="sxs-lookup"><span data-stu-id="15efb-152">Return value</span></span>

<span data-ttu-id="15efb-153">**FtgRegisterIdleRoutine** 函数返回一个函数标记，该标记标识已添加到 MAPI 系统的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="15efb-153">The **FtgRegisterIdleRoutine** function returns a function tag identifying the idle routine that was added to the MAPI system.</span></span> <span data-ttu-id="15efb-154">如果 **FtgRegisterIdleRoutine** 无法注册客户端应用程序或服务提供商的空闲例程，例如，由于内存问题，它将返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="15efb-154">If **FtgRegisterIdleRoutine** cannot register the idle routine for the client application or service provider, for example because of memory problems, it returns NULL.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="15efb-155">备注</span><span class="sxs-lookup"><span data-stu-id="15efb-155">Remarks</span></span>

<span data-ttu-id="15efb-156">以下函数基于 [FNIDLE](fnidle.md) 函数原型处理 MAPI 空闲引擎和空闲例程。</span><span class="sxs-lookup"><span data-stu-id="15efb-156">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype.</span></span> 
  
|<span data-ttu-id="15efb-157">**空闲例程函数**</span><span class="sxs-lookup"><span data-stu-id="15efb-157">**Idle routine function**</span></span>|<span data-ttu-id="15efb-158">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="15efb-158">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="15efb-159">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="15efb-159">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="15efb-160">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="15efb-160">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="15efb-161">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="15efb-161">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="15efb-162">从 MAPI 系统中删除注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="15efb-162">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="15efb-163">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="15efb-163">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="15efb-164">禁用或重新启用注册的空闲例程，而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="15efb-164">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|<span data-ttu-id="15efb-165">**FtgRegisterIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="15efb-165">**FtgRegisterIdleRoutine**</span></span> <br/> |<span data-ttu-id="15efb-166">将空闲例程添加到 MAPI 系统，启用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="15efb-166">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="15efb-167">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="15efb-167">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="15efb-168">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="15efb-168">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="15efb-169">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="15efb-169">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="15efb-170">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="15efb-170">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="15efb-171">ChangeIdleRoutine、DeregisterIdleRoutine 和 **EnableIdleRoutine** 将 **FtgRegisterIdleRoutine** 返回的函数标记作为输入参数。 </span><span class="sxs-lookup"><span data-stu-id="15efb-171">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="15efb-172">当平台的所有前台任务变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="15efb-172">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="15efb-173">无法保证在优先级相同的空闲例程之间调用顺序。</span><span class="sxs-lookup"><span data-stu-id="15efb-173">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  
<span data-ttu-id="15efb-174">下面是在  _一_ 半参数中使用 FIRONOADJUSTMENT 标志的示例。</span><span class="sxs-lookup"><span data-stu-id="15efb-174">The following is an example of using the FIRONOADJUSTMENT flag in the  _iroIdle_ parameter.</span></span> 
  
1. <span data-ttu-id="15efb-175">将空闲例程注册为 5 分钟延迟。</span><span class="sxs-lookup"><span data-stu-id="15efb-175">Register an idle routine with a 5 minute delay.</span></span>
    
2. <span data-ttu-id="15efb-176">休眠/睡眠 1 分钟之后，在计时器 (4 分钟后使计算机) 。</span><span class="sxs-lookup"><span data-stu-id="15efb-176">Hibernate/Sleep the computer after 1 minute (4 minutes left on the timer).</span></span>
    
3. <span data-ttu-id="15efb-177">10 分钟后恢复计算机。</span><span class="sxs-lookup"><span data-stu-id="15efb-177">Resume the computer 10 minutes later.</span></span>
    
<span data-ttu-id="15efb-178">如果没有 FIRONOADJUSTMENT，默认行为是，您仍必须再等待 4 分钟，例程才能运行。</span><span class="sxs-lookup"><span data-stu-id="15efb-178">The default behavior, without FIRONOADJUSTMENT, is that you still have to wait 4 more minutes for your routine to run.</span></span> <span data-ttu-id="15efb-179">即，已调整计时器以允许计算机运行多长。</span><span class="sxs-lookup"><span data-stu-id="15efb-179">That is, your timer was adjusted to allow for how long the computer was asleep.</span></span> <span data-ttu-id="15efb-180">但是，如果你通过 FIRONOADJUSTMENT，你的空闲例程将立即运行，因为经过 5 分钟以上的时间。</span><span class="sxs-lookup"><span data-stu-id="15efb-180">However, if you pass FIRONOADJUSTMENT your idle routine will run immediately because more than 5 minutes of real time have elapsed.</span></span>
  

