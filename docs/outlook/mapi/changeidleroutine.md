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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334431"
---
# <a name="changeidleroutine"></a><span data-ttu-id="23a26-103">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="23a26-103">ChangeIdleRoutine</span></span>

<span data-ttu-id="23a26-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="23a26-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="23a26-105">更改基于[FNIDLE](fnidle.md)的空闲例程的部分或全部特征。</span><span class="sxs-lookup"><span data-stu-id="23a26-105">Changes some or all of the characteristics of a [FNIDLE](fnidle.md) based idle routine.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="23a26-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="23a26-106">Header file:</span></span>  <br/> |<span data-ttu-id="23a26-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="23a26-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="23a26-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="23a26-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="23a26-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="23a26-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="23a26-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="23a26-110">Called by:</span></span>  <br/> |<span data-ttu-id="23a26-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="23a26-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="23a26-112">参数</span><span class="sxs-lookup"><span data-stu-id="23a26-112">Parameters</span></span>

<span data-ttu-id="23a26-113">_ftg_</span><span class="sxs-lookup"><span data-stu-id="23a26-113">_ftg_</span></span>
  
> <span data-ttu-id="23a26-114">实时用于标识空闲例程的 Function 标记。</span><span class="sxs-lookup"><span data-stu-id="23a26-114">[in] Function tag that identifies the idle routine.</span></span> 
    
<span data-ttu-id="23a26-115">_pfnIdle_</span><span class="sxs-lookup"><span data-stu-id="23a26-115">_pfnIdle_</span></span>
  
> <span data-ttu-id="23a26-116">实时指向空闲例程的指针。</span><span class="sxs-lookup"><span data-stu-id="23a26-116">[in] Pointer to the idle routine.</span></span> 
    
<span data-ttu-id="23a26-117">_pvIdleParam_</span><span class="sxs-lookup"><span data-stu-id="23a26-117">_pvIdleParam_</span></span>
  
> <span data-ttu-id="23a26-118">实时指向调用实现为空闲例程分配的新内存块的指针。</span><span class="sxs-lookup"><span data-stu-id="23a26-118">[in] Pointer to a new block of memory that the calling implementation allocates for the idle routine.</span></span> 
    
<span data-ttu-id="23a26-119">_priIdle_</span><span class="sxs-lookup"><span data-stu-id="23a26-119">_priIdle_</span></span>
  
> <span data-ttu-id="23a26-120">实时表示空闲例程的新优先级的值。</span><span class="sxs-lookup"><span data-stu-id="23a26-120">[in] Value representing a new priority for the idle routine.</span></span> <span data-ttu-id="23a26-121">实现定义的例程的可能优先级大于或小于零, 但不能为零。</span><span class="sxs-lookup"><span data-stu-id="23a26-121">Possible priorities for implementation-defined routines are greater than or less than zero, but not zero.</span></span> <span data-ttu-id="23a26-122">值为0时为用户事件 (如鼠标单击或 WM_PAINT 邮件) 保留。</span><span class="sxs-lookup"><span data-stu-id="23a26-122">A value of zero is reserved for a user event such as a mouse click or a WM_PAINT message.</span></span> <span data-ttu-id="23a26-123">大于零的值表示优先级高于用户事件且作为标准 Windows 消息泵循环的一部分进行调度的后台任务的优先级。</span><span class="sxs-lookup"><span data-stu-id="23a26-123">Values greater than zero represent priorities for background tasks that have a higher priority than user events and are dispatched as part of the standard Windows message pump loop.</span></span> <span data-ttu-id="23a26-124">小于零的值表示仅在消息泵空闲时运行的空闲任务的优先级。</span><span class="sxs-lookup"><span data-stu-id="23a26-124">Values less than zero represent priorities for idle tasks that only run during message-pump idle time.</span></span> <span data-ttu-id="23a26-125">优先级的示例为: 1 表示前台提交, 1 表示加电编辑字符插入, 3 用于下载新邮件。</span><span class="sxs-lookup"><span data-stu-id="23a26-125">Examples of priorities are: 1 for foreground submission, 1 for power-edit character insertion, and 3 for downloading new messages.</span></span>
    
<span data-ttu-id="23a26-126">_csecIdle_</span><span class="sxs-lookup"><span data-stu-id="23a26-126">_csecIdle_</span></span>
  
> <span data-ttu-id="23a26-127">实时应用于空闲例程的新时间, 以百分之一秒为单位。</span><span class="sxs-lookup"><span data-stu-id="23a26-127">[in] A new time, in hundredths of a second, to apply to the idle routine.</span></span> <span data-ttu-id="23a26-128">初始时间值的意义各不相同, 具体取决于在_iroIdle_参数中传递的内容。</span><span class="sxs-lookup"><span data-stu-id="23a26-128">The meaning of the initial time value varies, depending on what is passed in the  _iroIdle_ parameter.</span></span> <span data-ttu-id="23a26-129">它可以是:</span><span class="sxs-lookup"><span data-stu-id="23a26-129">It can be:</span></span> 
    
  - <span data-ttu-id="23a26-130">MAPI 空闲引擎首次呼叫空闲例程之前必须经过的最小用户 inaction, 如果_iroIdle_中设置了 FIROWAIT 标志。</span><span class="sxs-lookup"><span data-stu-id="23a26-130">The minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time, if the FIROWAIT flag is set in  _iroIdle_.</span></span> <span data-ttu-id="23a26-131">在此时间过后, 空闲引擎可以根据需要频繁地调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="23a26-131">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
  - <span data-ttu-id="23a26-132">如果在_iroIdle_中设置了 FIROINTERVAL 标志, 则调用 idle 例程之间的最小间隔。</span><span class="sxs-lookup"><span data-stu-id="23a26-132">The minimum interval between calls to the idle routine, if the FIROINTERVAL flag is set in  _iroIdle_.</span></span> 
    
<span data-ttu-id="23a26-133">_iroIdle_</span><span class="sxs-lookup"><span data-stu-id="23a26-133">_iroIdle_</span></span>
  
> <span data-ttu-id="23a26-134">实时指示调用空闲例程的新选项的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="23a26-134">[in] Bitmask of flags indicating new options for calling the idle routine.</span></span> <span data-ttu-id="23a26-135">必须仅设置以下任一标志:</span><span class="sxs-lookup"><span data-stu-id="23a26-135">Exactly one of the following flags must be set:</span></span>
    
  - <span data-ttu-id="23a26-136">FIROINTERVAL: _csecIdle_参数指定的时间是对 idle 例程的连续调用之间的最小时间间隔。</span><span class="sxs-lookup"><span data-stu-id="23a26-136">FIROINTERVAL: The time specified by the  _csecIdle_ parameter is the minimum interval between successive calls to the idle routine.</span></span> 
      
  - <span data-ttu-id="23a26-137">FIROONCEONLY: 已过时。</span><span class="sxs-lookup"><span data-stu-id="23a26-137">FIROONCEONLY: Obsolete.</span></span> <span data-ttu-id="23a26-138">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="23a26-138">Do not use.</span></span> 
      
  - <span data-ttu-id="23a26-139">FIROPERBLOCK: 已过时。</span><span class="sxs-lookup"><span data-stu-id="23a26-139">FIROPERBLOCK: Obsolete.</span></span> <span data-ttu-id="23a26-140">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="23a26-140">Do not use.</span></span> 
      
  - <span data-ttu-id="23a26-141">FIROWAIT: _csecIdle_参数指定的时间是 MAPI idle engine 首次调用空闲例程之前必须经过的用户 inaction 的最小周期。</span><span class="sxs-lookup"><span data-stu-id="23a26-141">FIROWAIT: The time specified by the  _csecIdle_ parameter is the minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time.</span></span> <span data-ttu-id="23a26-142">在此时间过后, 空闲引擎可以根据需要频繁地调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="23a26-142">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
<span data-ttu-id="23a26-143">_ircIdle_</span><span class="sxs-lookup"><span data-stu-id="23a26-143">_ircIdle_</span></span>
  
> <span data-ttu-id="23a26-144">实时标记的位掩码, 用于指示对空闲例程所做的更改。</span><span class="sxs-lookup"><span data-stu-id="23a26-144">[in] Bitmask of flags used to indicate the changes to be made to the idle routine.</span></span> <span data-ttu-id="23a26-145">可以按任意组合设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="23a26-145">The following flags can be set in any combination:</span></span>
    
  - <span data-ttu-id="23a26-146">FIRCCSEC: 与空闲例程关联的时间的更改, 即由_csecIdle_参数中传递的值指示的更改。</span><span class="sxs-lookup"><span data-stu-id="23a26-146">FIRCCSEC: A change to the time associated with the idle routine, that is, a change indicated by the value passed in the  _csecIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="23a26-147">FIRCIRO: 对 idle 例程的选项的更改, 即由_iroIdle_参数中传递的值指示的更改。</span><span class="sxs-lookup"><span data-stu-id="23a26-147">FIRCIRO: A change to the options for the idle routine, that is, a change indicated by the value passed in the  _iroIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="23a26-148">FIRCPFN: 对 idle 例程指针的更改, 即由_pfnIdle_参数中传递的值指示的更改。</span><span class="sxs-lookup"><span data-stu-id="23a26-148">FIRCPFN: A change to the idle routine pointer, that is, a change indicated by the value passed in the  _pfnIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="23a26-149">FIRCPRI: 对 idle 例程的优先级的更改, 即由_priIdle_参数中传递的值指示的更改。</span><span class="sxs-lookup"><span data-stu-id="23a26-149">FIRCPRI: A change to the priority of the idle routine, that is, a change indicated by the value passed in the  _priIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="23a26-150">FIRCPV: 对 idle 例程内存块的更改, 即由_pvIdleParam_参数中传递的值指示的更改。</span><span class="sxs-lookup"><span data-stu-id="23a26-150">FIRCPV: A change to the memory block of the idle routine, that is, a change indicated by the value passed in the  _pvIdleParam_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="23a26-151">返回值</span><span class="sxs-lookup"><span data-stu-id="23a26-151">Return value</span></span>

<span data-ttu-id="23a26-152">无。</span><span class="sxs-lookup"><span data-stu-id="23a26-152">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="23a26-153">注解</span><span class="sxs-lookup"><span data-stu-id="23a26-153">Remarks</span></span>

<span data-ttu-id="23a26-154">以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程:</span><span class="sxs-lookup"><span data-stu-id="23a26-154">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="23a26-155">**Idle 例程函数**</span><span class="sxs-lookup"><span data-stu-id="23a26-155">**Idle routine function**</span></span>|<span data-ttu-id="23a26-156">**使用**</span><span class="sxs-lookup"><span data-stu-id="23a26-156">**Usage**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23a26-157">**ChangeIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="23a26-157">**ChangeIdleRoutine**</span></span> <br/> |<span data-ttu-id="23a26-158">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="23a26-158">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="23a26-159">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="23a26-159">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="23a26-160">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="23a26-160">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="23a26-161">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="23a26-161">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="23a26-162">禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="23a26-162">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="23a26-163">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="23a26-163">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="23a26-164">将空闲例程添加到 MAPI 系统中 (无论是否启用)。</span><span class="sxs-lookup"><span data-stu-id="23a26-164">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="23a26-165">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="23a26-165">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="23a26-166">关闭呼叫应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="23a26-166">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="23a26-167">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="23a26-167">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="23a26-168">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="23a26-168">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="23a26-169">**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**采用**FtgRegisterIdleRoutine**返回的函数标记作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="23a26-169">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="23a26-170">当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="23a26-170">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="23a26-171">在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。</span><span class="sxs-lookup"><span data-stu-id="23a26-171">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

