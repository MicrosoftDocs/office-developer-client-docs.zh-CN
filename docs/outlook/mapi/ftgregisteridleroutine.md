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
ms.openlocfilehash: 0d3f24c41f2cfbd499d92e050c74da904dd4c377
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775008"
---
# <a name="ftgregisteridleroutine"></a><span data-ttu-id="ad1a6-103">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="ad1a6-103">FtgRegisterIdleRoutine</span></span>

<span data-ttu-id="ad1a6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ad1a6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ad1a6-105">向 MAPI 系统[FNIDLE](fnidle.md)基于函数的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-105">Adds a [FNIDLE](fnidle.md) function-based idle routine to the MAPI system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ad1a6-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ad1a6-106">Header file:</span></span>  <br/> |<span data-ttu-id="ad1a6-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="ad1a6-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="ad1a6-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ad1a6-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ad1a6-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ad1a6-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ad1a6-110">调用：</span><span class="sxs-lookup"><span data-stu-id="ad1a6-110">Called by:</span></span>  <br/> |<span data-ttu-id="ad1a6-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="ad1a6-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
FTG FtgRegisterIdleRoutine(
  PFNIDLE pfnIdle,
  LPVOID pvIdleParam,
  short priIdle,
  ULONG csecIdle,
  USHORT iroIdle
);
```

## <a name="parameters"></a><span data-ttu-id="ad1a6-112">参数</span><span class="sxs-lookup"><span data-stu-id="ad1a6-112">Parameters</span></span>

<span data-ttu-id="ad1a6-113">_pfnIdle_</span><span class="sxs-lookup"><span data-stu-id="ad1a6-113">_pfnIdle_</span></span>
  
> <span data-ttu-id="ad1a6-114">[in]指向空闲例程的指针。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-114">[in] A pointer to the idle routine.</span></span> 
    
<span data-ttu-id="ad1a6-115">_pvIdleParam_</span><span class="sxs-lookup"><span data-stu-id="ad1a6-115">_pvIdleParam_</span></span>
  
> <span data-ttu-id="ad1a6-116">[in]一个指向某一空闲引擎应作为参数传递给空闲例程时调用的内存。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-116">[in] A pointer to a block of memory that the idle engine should pass as a parameter to the idle routine when it calls it.</span></span> 
    
<span data-ttu-id="ad1a6-117">_priIdle_</span><span class="sxs-lookup"><span data-stu-id="ad1a6-117">_priIdle_</span></span>
  
> <span data-ttu-id="ad1a6-118">[in]空闲例程初始优先级。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-118">[in] The initial priority for the idle routine.</span></span> <span data-ttu-id="ad1a6-119">实现定义例程可能优先级为大于或小于零，而不为零。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-119">Possible priorities for implementation-defined routines are greater than or less than zero, but not zero.</span></span> <span data-ttu-id="ad1a6-120">零优先级供用户事件如鼠标单击或 WM_PAINT 消息。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-120">The zero priority is reserved for a user event such as a mouse click or a WM_PAINT message.</span></span> <span data-ttu-id="ad1a6-121">优先级大于零表示背景任务的优先级高于用户事件调度标准 Windows 消息抽取循环的一部分。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-121">Priorities greater than zero represent background tasks that have a higher priority than user events and are dispatched as part of the standard Windows message pump loop.</span></span> <span data-ttu-id="ad1a6-122">优先级小于 0 表示空闲只能在消息抽取空闲时间运行的任务。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-122">Priorities less than zero represent idle tasks that only run during message pump idle time.</span></span> <span data-ttu-id="ad1a6-123">优先级的示例如下所示： 前景提交的 1、 电源编辑字符插入 2 和 3 用于下载新邮件。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-123">Examples of priorities are as follows: 1 for foreground submission, 2 for power-edit character insertion, and 3 for downloading new messages.</span></span>
    
<span data-ttu-id="ad1a6-124">_csecIdle_</span><span class="sxs-lookup"><span data-stu-id="ad1a6-124">_csecIdle_</span></span>
  
> <span data-ttu-id="ad1a6-125">[in]中的第二，用于指定空闲例行参数形式的初始时间值。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-125">[in] The initial time value, in hundredths of a second, to be used in specifying idle routine parameters.</span></span> <span data-ttu-id="ad1a6-126">初始时间值的含义有所不同，具体取决于_iroIdle_参数中传递的内容。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-126">The meaning of the initial time value varies, depending on what is passed in the  _iroIdle_ parameter.</span></span> <span data-ttu-id="ad1a6-127">含义可以是下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="ad1a6-127">The meaning can be one of the following:</span></span> 
    
  - <span data-ttu-id="ad1a6-128">用户不采取行动 MAPI 之前必须经过的最小段空闲引擎将调用空闲例程第一次，如果_iroIdle_中设置 FIROWAIT 标志。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-128">The minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time, if the FIROWAIT flag is set in  _iroIdle_.</span></span> <span data-ttu-id="ad1a6-129">超过此时间后，空闲引擎可以根据需要通常调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-129">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
  - <span data-ttu-id="ad1a6-130">调用空闲例程，如果_iroIdle_中设置 FIROINTERVAL 标志之间的最小间隔。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-130">The minimum interval between calls to the idle routine, if the FIROINTERVAL flag is set in  _iroIdle_.</span></span> 
    
<span data-ttu-id="ad1a6-131">_iroIdle_</span><span class="sxs-lookup"><span data-stu-id="ad1a6-131">_iroIdle_</span></span>
  
> <span data-ttu-id="ad1a6-132">[in]用于设置初始选项空闲例程的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-132">[in] The bitmask of flags used to set initial options for the idle routine.</span></span> <span data-ttu-id="ad1a6-133">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ad1a6-133">The following flags can be set:</span></span>
    
  <span data-ttu-id="ad1a6-134">FIRONOADJUSTMENT</span><span class="sxs-lookup"><span data-stu-id="ad1a6-134">FIRONOADJUSTMENT</span></span>
    
  > <span data-ttu-id="ad1a6-135">使用此标志指定空闲例行计时器应不调整为休眠或恢复。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-135">Use this flag to specify that the idle routine timer should not be adjusted for sleep or resume.</span></span> <span data-ttu-id="ad1a6-136">如果没有此标志的默认行为是计算已用时间时，不包括休眠时间。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-136">The default behavior without this flag is that sleep time is excluded when calculating the elapsed time.</span></span> <span data-ttu-id="ad1a6-137">如果传递 FIRONOADJUSTMENT 然后休眠时间时将包括计算经过的时间。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-137">If FIRONOADJUSTMENT is passed then the sleep time is included when calculating elapsed time.</span></span>
      
  <span data-ttu-id="ad1a6-138">FIRODISABLED</span><span class="sxs-lookup"><span data-stu-id="ad1a6-138">FIRODISABLED</span></span>
    
  > <span data-ttu-id="ad1a6-139">注册时，应禁用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-139">The idle routine should be disabled when registered.</span></span> <span data-ttu-id="ad1a6-140">默认操作是**FtgRegisterIdleRoutine**将注册它时启用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-140">The default action is to enable the idle routine when **FtgRegisterIdleRoutine** registers it.</span></span> 
      
  <span data-ttu-id="ad1a6-141">FIROINTERVAL</span><span class="sxs-lookup"><span data-stu-id="ad1a6-141">FIROINTERVAL</span></span> 
    
  > <span data-ttu-id="ad1a6-142">_CsecIdle_参数指定的时间是连续调用空闲例程之间的最小间隔。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-142">The time specified by the  _csecIdle_ parameter is the minimum interval between successive calls to the idle routine.</span></span> 
      
  <span data-ttu-id="ad1a6-143">FIROONCEONLY</span><span class="sxs-lookup"><span data-stu-id="ad1a6-143">FIROONCEONLY</span></span> 
    
  > <span data-ttu-id="ad1a6-p107">已过时。不得使用。 </span><span class="sxs-lookup"><span data-stu-id="ad1a6-p107">Obsolete. Do not use.</span></span> 
      
  <span data-ttu-id="ad1a6-146">FIROPERBLOCK</span><span class="sxs-lookup"><span data-stu-id="ad1a6-146">FIROPERBLOCK</span></span> 
    
  > <span data-ttu-id="ad1a6-p108">已过时。不得使用。 </span><span class="sxs-lookup"><span data-stu-id="ad1a6-p108">Obsolete. Do not use.</span></span> 
      
  <span data-ttu-id="ad1a6-149">FIROWAIT</span><span class="sxs-lookup"><span data-stu-id="ad1a6-149">FIROWAIT</span></span> 
    
  > <span data-ttu-id="ad1a6-150">用户不采取行动 MAPI 空闲引擎为第一次调用空闲例程之前必须经过的最小期间_csecIdle_参数指定的时间。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-150">The time specified by the  _csecIdle_ parameter is the minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time.</span></span> <span data-ttu-id="ad1a6-151">超过此时间后，空闲引擎可以根据需要通常调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-151">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ad1a6-152">返回值</span><span class="sxs-lookup"><span data-stu-id="ad1a6-152">Return value</span></span>

<span data-ttu-id="ad1a6-153">**FtgRegisterIdleRoutine**函数将返回标识已添加到 MAPI 系统空闲例程函数标记。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-153">The **FtgRegisterIdleRoutine** function returns a function tag identifying the idle routine that was added to the MAPI system.</span></span> <span data-ttu-id="ad1a6-154">如果**FtgRegisterIdleRoutine**无法注册的客户端应用程序或服务提供商的空闲例程，例如内存问题，因为它返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-154">If **FtgRegisterIdleRoutine** cannot register the idle routine for the client application or service provider, for example because of memory problems, it returns NULL.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ad1a6-155">说明</span><span class="sxs-lookup"><span data-stu-id="ad1a6-155">Remarks</span></span>

<span data-ttu-id="ad1a6-156">下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-156">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype.</span></span> 
  
|<span data-ttu-id="ad1a6-157">**空闲例行函数**</span><span class="sxs-lookup"><span data-stu-id="ad1a6-157">**Idle routine function**</span></span>|<span data-ttu-id="ad1a6-158">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="ad1a6-158">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ad1a6-159">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="ad1a6-159">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="ad1a6-160">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-160">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="ad1a6-161">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="ad1a6-161">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="ad1a6-162">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-162">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="ad1a6-163">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="ad1a6-163">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="ad1a6-164">禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-164">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|<span data-ttu-id="ad1a6-165">**FtgRegisterIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="ad1a6-165">**FtgRegisterIdleRoutine**</span></span> <br/> |<span data-ttu-id="ad1a6-166">将一个空闲例程添加到 MAPI 系统，使用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-166">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="ad1a6-167">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="ad1a6-167">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="ad1a6-168">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-168">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="ad1a6-169">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="ad1a6-169">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="ad1a6-170">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-170">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="ad1a6-171">**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**接受作为输入参数的函数标记，则由**FtgRegisterIdleRoutine**返回。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-171">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="ad1a6-172">当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-172">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="ad1a6-173">不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-173">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  
<span data-ttu-id="ad1a6-174">下面是使用 FIRONOADJUSTMENT 标志_iroIdle_参数中的示例。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-174">The following is an example of using the FIRONOADJUSTMENT flag in the  _iroIdle_ parameter.</span></span> 
  
1. <span data-ttu-id="ad1a6-175">一个空闲例程注册 5 分钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-175">Register an idle routine with a 5 minute delay.</span></span>
    
2. <span data-ttu-id="ad1a6-176">休眠/休眠计算机后 1 分钟 （保留在计时器 4 分钟）。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-176">Hibernate/Sleep the computer after 1 minute (4 minutes left on the timer).</span></span>
    
3. <span data-ttu-id="ad1a6-177">恢复计算机更高版本 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-177">Resume the computer 10 minutes later.</span></span>
    
<span data-ttu-id="ad1a6-178">默认行为，而 FIRONOADJUSTMENT，不是您仍需要等待 4 的详细分钟，以便您例程，以运行。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-178">The default behavior, without FIRONOADJUSTMENT, is that you still have to wait 4 more minutes for your routine to run.</span></span> <span data-ttu-id="ad1a6-179">即您计时器已被调整以允许计算机已休眠多长时间。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-179">That is, your timer was adjusted to allow for how long the computer was asleep.</span></span> <span data-ttu-id="ad1a6-180">但是，如果传递 FIRONOADJUSTMENT 您空闲例程将立即运行因为已超过 5 分钟的实时。</span><span class="sxs-lookup"><span data-stu-id="ad1a6-180">However, if you pass FIRONOADJUSTMENT your idle routine will run immediately because more than 5 minutes of real time have elapsed.</span></span>
  

