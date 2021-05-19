---
title: ChangeIdleRoutine
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ChangeIdleRoutine
api_type:
- HeaderDef
ms.assetid: 0a24fe3b-a1ef-4748-b3b3-3bf747473c9d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cfec9356a866c79b687497c3af007c046a20a75e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418265"
---
# <a name="changeidleroutine"></a><span data-ttu-id="49631-103">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="49631-103">ChangeIdleRoutine</span></span>

<span data-ttu-id="49631-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="49631-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="49631-105">更改基于 [FNIDLE](fnidle.md) 的空闲例程的一些或所有特征。</span><span class="sxs-lookup"><span data-stu-id="49631-105">Changes some or all of the characteristics of a [FNIDLE](fnidle.md) based idle routine.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="49631-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="49631-106">Header file:</span></span>  <br/> |<span data-ttu-id="49631-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="49631-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="49631-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="49631-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="49631-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="49631-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="49631-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="49631-110">Called by:</span></span>  <br/> |<span data-ttu-id="49631-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="49631-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID ChangeIdleRoutine(
  FTG ftg,
  PFNIDLE pfnIdle,
  LPVOID pvIdleParam,
  short priIdle,
  ULONG csecIdle,
  USHORT iroIdle,
  USHORT ircIdle
);
```

## <a name="parameters"></a><span data-ttu-id="49631-112">参数</span><span class="sxs-lookup"><span data-stu-id="49631-112">Parameters</span></span>

<span data-ttu-id="49631-113">_ftg_</span><span class="sxs-lookup"><span data-stu-id="49631-113">_ftg_</span></span>
  
> <span data-ttu-id="49631-114">[in]标识空闲例程的函数标记。</span><span class="sxs-lookup"><span data-stu-id="49631-114">[in] Function tag that identifies the idle routine.</span></span> 
    
<span data-ttu-id="49631-115">_pfnIdle_</span><span class="sxs-lookup"><span data-stu-id="49631-115">_pfnIdle_</span></span>
  
> <span data-ttu-id="49631-116">[in]指向空闲例程的指针。</span><span class="sxs-lookup"><span data-stu-id="49631-116">[in] Pointer to the idle routine.</span></span> 
    
<span data-ttu-id="49631-117">_pvIdleParam_</span><span class="sxs-lookup"><span data-stu-id="49631-117">_pvIdleParam_</span></span>
  
> <span data-ttu-id="49631-118">[in]指向调用实现为空闲例程分配的新内存块的指针。</span><span class="sxs-lookup"><span data-stu-id="49631-118">[in] Pointer to a new block of memory that the calling implementation allocates for the idle routine.</span></span> 
    
<span data-ttu-id="49631-119">_priIdle_</span><span class="sxs-lookup"><span data-stu-id="49631-119">_priIdle_</span></span>
  
> <span data-ttu-id="49631-120">[in]表示空闲例程的新优先级的值。</span><span class="sxs-lookup"><span data-stu-id="49631-120">[in] Value representing a new priority for the idle routine.</span></span> <span data-ttu-id="49631-121">实现定义的例程的可能优先级大于或小于零，但不大于零。</span><span class="sxs-lookup"><span data-stu-id="49631-121">Possible priorities for implementation-defined routines are greater than or less than zero, but not zero.</span></span> <span data-ttu-id="49631-122">为用户事件保留值 0，如鼠标单击或WM_PAINT消息。</span><span class="sxs-lookup"><span data-stu-id="49631-122">A value of zero is reserved for a user event such as a mouse click or a WM_PAINT message.</span></span> <span data-ttu-id="49631-123">大于零的值表示优先级高于用户事件的后台任务的优先级，并作为标准邮件循环循环Windows调度。</span><span class="sxs-lookup"><span data-stu-id="49631-123">Values greater than zero represent priorities for background tasks that have a higher priority than user events and are dispatched as part of the standard Windows message pump loop.</span></span> <span data-ttu-id="49631-124">小于零的值表示仅在消息处理空闲时间期间运行的空闲任务的优先级。</span><span class="sxs-lookup"><span data-stu-id="49631-124">Values less than zero represent priorities for idle tasks that only run during message-pump idle time.</span></span> <span data-ttu-id="49631-125">优先级的示例包括：1 表示前台提交，1 表示 power-edit 字符插入，3 表示下载新邮件。</span><span class="sxs-lookup"><span data-stu-id="49631-125">Examples of priorities are: 1 for foreground submission, 1 for power-edit character insertion, and 3 for downloading new messages.</span></span>
    
<span data-ttu-id="49631-126">_csecIdle_</span><span class="sxs-lookup"><span data-stu-id="49631-126">_csecIdle_</span></span>
  
> <span data-ttu-id="49631-127">[in]应用于空闲例程的新时间（以百分之几秒计）。</span><span class="sxs-lookup"><span data-stu-id="49631-127">[in] A new time, in hundredths of a second, to apply to the idle routine.</span></span> <span data-ttu-id="49631-128">初始时间值的含义会有所不同，具体取决于  _一节参数中传递_ 的值。</span><span class="sxs-lookup"><span data-stu-id="49631-128">The meaning of the initial time value varies, depending on what is passed in the  _iroIdle_ parameter.</span></span> <span data-ttu-id="49631-129">它可以是：</span><span class="sxs-lookup"><span data-stu-id="49631-129">It can be:</span></span> 
    
  - <span data-ttu-id="49631-130">在 MAPI 空闲引擎首次调用空闲例程之前必须经过的最小用户不操作时段（如果 FIROWAIT 标志在  _创建Idle_ 中设置）。</span><span class="sxs-lookup"><span data-stu-id="49631-130">The minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time, if the FIROWAIT flag is set in  _iroIdle_.</span></span> <span data-ttu-id="49631-131">此时间结束后，空闲引擎可以在必要时经常调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="49631-131">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
  - <span data-ttu-id="49631-132">如果 FIROINTERVAL 标志在  _分流Idle_ 中设置，则对空闲例程的调用之间的最小间隔。</span><span class="sxs-lookup"><span data-stu-id="49631-132">The minimum interval between calls to the idle routine, if the FIROINTERVAL flag is set in  _iroIdle_.</span></span> 
    
<span data-ttu-id="49631-133">_一体式_</span><span class="sxs-lookup"><span data-stu-id="49631-133">_iroIdle_</span></span>
  
> <span data-ttu-id="49631-134">[in]指示用于调用空闲例程的新选项的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="49631-134">[in] Bitmask of flags indicating new options for calling the idle routine.</span></span> <span data-ttu-id="49631-135">必须准确设置以下标志之一：</span><span class="sxs-lookup"><span data-stu-id="49631-135">Exactly one of the following flags must be set:</span></span>
    
  - <span data-ttu-id="49631-136">_FIROINTERVAL：csecIdle_ 参数指定的时间是连续调用空闲例程之间的最小间隔。</span><span class="sxs-lookup"><span data-stu-id="49631-136">FIROINTERVAL: The time specified by the  _csecIdle_ parameter is the minimum interval between successive calls to the idle routine.</span></span> 
      
  - <span data-ttu-id="49631-137">FIROONCEONLY：已过时。</span><span class="sxs-lookup"><span data-stu-id="49631-137">FIROONCEONLY: Obsolete.</span></span> <span data-ttu-id="49631-138">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="49631-138">Do not use.</span></span> 
      
  - <span data-ttu-id="49631-139">FIROPERBLOCK：已过时。</span><span class="sxs-lookup"><span data-stu-id="49631-139">FIROPERBLOCK: Obsolete.</span></span> <span data-ttu-id="49631-140">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="49631-140">Do not use.</span></span> 
      
  - <span data-ttu-id="49631-141">_FIROWAIT：csecIdle_ 参数指定的时间是在 MAPI 空闲引擎首次调用空闲例程之前必须经过的最小用户不操作时段。</span><span class="sxs-lookup"><span data-stu-id="49631-141">FIROWAIT: The time specified by the  _csecIdle_ parameter is the minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time.</span></span> <span data-ttu-id="49631-142">此时间结束后，空闲引擎可以在必要时经常调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="49631-142">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
<span data-ttu-id="49631-143">_ircIdle_</span><span class="sxs-lookup"><span data-stu-id="49631-143">_ircIdle_</span></span>
  
> <span data-ttu-id="49631-144">[in]用于指示对空闲例程所做的更改的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="49631-144">[in] Bitmask of flags used to indicate the changes to be made to the idle routine.</span></span> <span data-ttu-id="49631-145">可以任意组合设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="49631-145">The following flags can be set in any combination:</span></span>
    
  - <span data-ttu-id="49631-146">FIRCCSEC：与空闲例程关联的时间更改，即由  _csecIdle_ 参数中传递的值指示的变化。</span><span class="sxs-lookup"><span data-stu-id="49631-146">FIRCCSEC: A change to the time associated with the idle routine, that is, a change indicated by the value passed in the  _csecIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="49631-147">FIRC一：对空闲例程的选项更改，即由  _传入 创建 id 参数的值指示_ 的变化。</span><span class="sxs-lookup"><span data-stu-id="49631-147">FIRCIRO: A change to the options for the idle routine, that is, a change indicated by the value passed in the  _iroIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="49631-148">FIRCPFN：对空闲例程指针的变更，即由  _pfnIdle_ 参数中传递的值指示的变化。</span><span class="sxs-lookup"><span data-stu-id="49631-148">FIRCPFN: A change to the idle routine pointer, that is, a change indicated by the value passed in the  _pfnIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="49631-149">FIRCPRI：对空闲例程的优先级更改，即由  _在 priIdle_ 参数中传递的值指示的变化。</span><span class="sxs-lookup"><span data-stu-id="49631-149">FIRCPRI: A change to the priority of the idle routine, that is, a change indicated by the value passed in the  _priIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="49631-150">FIRCPV：对空闲例程的内存块的变更，即  _由 pvIdleParam_ 参数中传递的值指示的变化。</span><span class="sxs-lookup"><span data-stu-id="49631-150">FIRCPV: A change to the memory block of the idle routine, that is, a change indicated by the value passed in the  _pvIdleParam_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="49631-151">返回值</span><span class="sxs-lookup"><span data-stu-id="49631-151">Return value</span></span>

<span data-ttu-id="49631-152">无。</span><span class="sxs-lookup"><span data-stu-id="49631-152">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="49631-153">说明</span><span class="sxs-lookup"><span data-stu-id="49631-153">Remarks</span></span>

<span data-ttu-id="49631-154">以下函数基于 [FNIDLE](fnidle.md) 函数原型处理 MAPI 空闲引擎和空闲例程：</span><span class="sxs-lookup"><span data-stu-id="49631-154">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="49631-155">**空闲例程函数**</span><span class="sxs-lookup"><span data-stu-id="49631-155">**Idle routine function**</span></span>|<span data-ttu-id="49631-156">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="49631-156">**Usage**</span></span>|
|:-----|:-----|
|<span data-ttu-id="49631-157">**ChangeIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="49631-157">**ChangeIdleRoutine**</span></span> <br/> |<span data-ttu-id="49631-158">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="49631-158">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="49631-159">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="49631-159">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="49631-160">从 MAPI 系统中删除注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="49631-160">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="49631-161">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="49631-161">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="49631-162">禁用或重新启用注册的空闲例程，而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="49631-162">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="49631-163">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="49631-163">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="49631-164">将空闲例程添加到 MAPI 系统，启用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="49631-164">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="49631-165">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="49631-165">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="49631-166">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="49631-166">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="49631-167">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="49631-167">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="49631-168">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="49631-168">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="49631-169">ChangeIdleRoutine、DeregisterIdleRoutine 和 **EnableIdleRoutine** 将 **FtgRegisterIdleRoutine** 返回的函数标记作为输入参数。 </span><span class="sxs-lookup"><span data-stu-id="49631-169">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="49631-170">当平台的所有前台任务变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="49631-170">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="49631-171">无法保证在优先级相同的空闲例程之间调用顺序。</span><span class="sxs-lookup"><span data-stu-id="49631-171">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

