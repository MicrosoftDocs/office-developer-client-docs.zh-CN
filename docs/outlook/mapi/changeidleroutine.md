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
ms.openlocfilehash: 49682007946a4c5dda3800751deaebcc0e1e5740
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579450"
---
# <a name="changeidleroutine"></a><span data-ttu-id="3c8e9-103">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="3c8e9-103">ChangeIdleRoutine</span></span>

<span data-ttu-id="3c8e9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3c8e9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3c8e9-105">更改部分或全部[FNIDLE](fnidle.md)基于空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-105">Changes some or all of the characteristics of a [FNIDLE](fnidle.md) based idle routine.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3c8e9-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="3c8e9-106">Header file:</span></span>  <br/> |<span data-ttu-id="3c8e9-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="3c8e9-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="3c8e9-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="3c8e9-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="3c8e9-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="3c8e9-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="3c8e9-110">调用：</span><span class="sxs-lookup"><span data-stu-id="3c8e9-110">Called by:</span></span>  <br/> |<span data-ttu-id="3c8e9-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="3c8e9-111">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="3c8e9-112">参数</span><span class="sxs-lookup"><span data-stu-id="3c8e9-112">Parameters</span></span>

<span data-ttu-id="3c8e9-113">_ftg_</span><span class="sxs-lookup"><span data-stu-id="3c8e9-113">_ftg_</span></span>
  
> <span data-ttu-id="3c8e9-114">[in]标识空闲例程的函数标记。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-114">[in] Function tag that identifies the idle routine.</span></span> 
    
<span data-ttu-id="3c8e9-115">_pfnIdle_</span><span class="sxs-lookup"><span data-stu-id="3c8e9-115">_pfnIdle_</span></span>
  
> <span data-ttu-id="3c8e9-116">[in]指向空闲例程。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-116">[in] Pointer to the idle routine.</span></span> 
    
<span data-ttu-id="3c8e9-117">_pvIdleParam_</span><span class="sxs-lookup"><span data-stu-id="3c8e9-117">_pvIdleParam_</span></span>
  
> <span data-ttu-id="3c8e9-118">[in]对新块的调用实现空闲例程分配内存的指针。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-118">[in] Pointer to a new block of memory that the calling implementation allocates for the idle routine.</span></span> 
    
<span data-ttu-id="3c8e9-119">_priIdle_</span><span class="sxs-lookup"><span data-stu-id="3c8e9-119">_priIdle_</span></span>
  
> <span data-ttu-id="3c8e9-120">[in]表示空闲例程的新优先级值。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-120">[in] Value representing a new priority for the idle routine.</span></span> <span data-ttu-id="3c8e9-121">实现定义例程可能优先级为大于或小于零，而不为零。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-121">Possible priorities for implementation-defined routines are greater than or less than zero, but not zero.</span></span> <span data-ttu-id="3c8e9-122">值为零供用户事件如鼠标单击或 WM_PAINT 消息。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-122">A value of zero is reserved for a user event such as a mouse click or a WM_PAINT message.</span></span> <span data-ttu-id="3c8e9-123">值大于零表示背景任务的优先级高于用户事件的标准 Windows 消息抽取循环一部分调度的优先级。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-123">Values greater than zero represent priorities for background tasks that have a higher priority than user events and are dispatched as part of the standard Windows message pump loop.</span></span> <span data-ttu-id="3c8e9-124">小于零表示空闲只能在消息抽取空闲时间运行的任务的优先级值。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-124">Values less than zero represent priorities for idle tasks that only run during message-pump idle time.</span></span> <span data-ttu-id="3c8e9-125">优先级的示例包括： 前景提交的 1、 电源编辑字符插入 1 和 3 用于下载新邮件。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-125">Examples of priorities are: 1 for foreground submission, 1 for power-edit character insertion, and 3 for downloading new messages.</span></span>
    
<span data-ttu-id="3c8e9-126">_csecIdle_</span><span class="sxs-lookup"><span data-stu-id="3c8e9-126">_csecIdle_</span></span>
  
> <span data-ttu-id="3c8e9-127">[in]中的第二、 要应用于空闲例程形式的新时间。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-127">[in] A new time, in hundredths of a second, to apply to the idle routine.</span></span> <span data-ttu-id="3c8e9-128">初始时间值的含义有所不同，具体取决于_iroIdle_参数中传递的内容。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-128">The meaning of the initial time value varies, depending on what is passed in the  _iroIdle_ parameter.</span></span> <span data-ttu-id="3c8e9-129">它可以是：</span><span class="sxs-lookup"><span data-stu-id="3c8e9-129">It can be:</span></span> 
    
  - <span data-ttu-id="3c8e9-130">用户不采取行动 MAPI 之前必须经过的最小段空闲引擎将调用空闲例程第一次，如果_iroIdle_中设置 FIROWAIT 标志。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-130">The minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time, if the FIROWAIT flag is set in  _iroIdle_.</span></span> <span data-ttu-id="3c8e9-131">超过此时间后，空闲引擎可以根据需要通常调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-131">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
  - <span data-ttu-id="3c8e9-132">调用空闲例程，如果_iroIdle_中设置 FIROINTERVAL 标志之间的最小间隔。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-132">The minimum interval between calls to the idle routine, if the FIROINTERVAL flag is set in  _iroIdle_.</span></span> 
    
<span data-ttu-id="3c8e9-133">_iroIdle_</span><span class="sxs-lookup"><span data-stu-id="3c8e9-133">_iroIdle_</span></span>
  
> <span data-ttu-id="3c8e9-134">[in]指示呼叫处于空闲状态例程的新选项标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-134">[in] Bitmask of flags indicating new options for calling the idle routine.</span></span> <span data-ttu-id="3c8e9-135">必须设置完全以下标志之一：</span><span class="sxs-lookup"><span data-stu-id="3c8e9-135">Exactly one of the following flags must be set:</span></span>
    
  - <span data-ttu-id="3c8e9-136">FIROINTERVAL: _csecIdle_参数指定的时间是连续调用空闲例程之间的最小间隔。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-136">FIROINTERVAL: The time specified by the  _csecIdle_ parameter is the minimum interval between successive calls to the idle routine.</span></span> 
      
  - <span data-ttu-id="3c8e9-137">FIROONCEONLY： 已过时。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-137">FIROONCEONLY: Obsolete.</span></span> <span data-ttu-id="3c8e9-138">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-138">Do not use.</span></span> 
      
  - <span data-ttu-id="3c8e9-139">FIROPERBLOCK： 已过时。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-139">FIROPERBLOCK: Obsolete.</span></span> <span data-ttu-id="3c8e9-140">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-140">Do not use.</span></span> 
      
  - <span data-ttu-id="3c8e9-141">FIROWAIT: _csecIdle_参数指定的时间是用户不采取行动 MAPI 空闲引擎为第一次调用空闲例程之前必须经过的最小期间。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-141">FIROWAIT: The time specified by the  _csecIdle_ parameter is the minimum period of user inaction that must elapse before the MAPI idle engine calls the idle routine for the first time.</span></span> <span data-ttu-id="3c8e9-142">超过此时间后，空闲引擎可以根据需要通常调用空闲例程。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-142">After this time passes, the idle engine can call the idle routine as often as necessary.</span></span> 
    
<span data-ttu-id="3c8e9-143">_ircIdle_</span><span class="sxs-lookup"><span data-stu-id="3c8e9-143">_ircIdle_</span></span>
  
> <span data-ttu-id="3c8e9-144">[in]位掩码用于指示所做的更改的标志对空闲例程。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-144">[in] Bitmask of flags used to indicate the changes to be made to the idle routine.</span></span> <span data-ttu-id="3c8e9-145">以下标志可以设置以任意组合：</span><span class="sxs-lookup"><span data-stu-id="3c8e9-145">The following flags can be set in any combination:</span></span>
    
  - <span data-ttu-id="3c8e9-146">FIRCCSEC： 对空闲例程，也就是说，更改由_csecIdle_参数中传递的值与关联的时间的更改。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-146">FIRCCSEC: A change to the time associated with the idle routine, that is, a change indicated by the value passed in the  _csecIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="3c8e9-147">FIRCIRO： 更改该空闲例程的选项，即更改由值指示在参数中传递_iroIdle_ 。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-147">FIRCIRO: A change to the options for the idle routine, that is, a change indicated by the value passed in the  _iroIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="3c8e9-148">FIRCPFN： 更改为空闲例行指针，也就是说，更改由值指示在参数中传递_pfnIdle_ 。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-148">FIRCPFN: A change to the idle routine pointer, that is, a change indicated by the value passed in the  _pfnIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="3c8e9-149">FIRCPRI： 空闲例程的优先级更改也就是说，更改由值指示在参数中传递_priIdle_ 。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-149">FIRCPRI: A change to the priority of the idle routine, that is, a change indicated by the value passed in the  _priIdle_ parameter.</span></span> 
      
  - <span data-ttu-id="3c8e9-150">FIRCPV： 对空闲例程的内存块的更改，即更改由值指示在参数中传递_pvIdleParam_ 。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-150">FIRCPV: A change to the memory block of the idle routine, that is, a change indicated by the value passed in the  _pvIdleParam_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="3c8e9-151">返回值</span><span class="sxs-lookup"><span data-stu-id="3c8e9-151">Return value</span></span>

<span data-ttu-id="3c8e9-152">无。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-152">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="3c8e9-153">注解</span><span class="sxs-lookup"><span data-stu-id="3c8e9-153">Remarks</span></span>

<span data-ttu-id="3c8e9-154">下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程：</span><span class="sxs-lookup"><span data-stu-id="3c8e9-154">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="3c8e9-155">**空闲例行函数**</span><span class="sxs-lookup"><span data-stu-id="3c8e9-155">**Idle routine function**</span></span>|<span data-ttu-id="3c8e9-156">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="3c8e9-156">**Usage**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c8e9-157">**ChangeIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="3c8e9-157">**ChangeIdleRoutine**</span></span> <br/> |<span data-ttu-id="3c8e9-158">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-158">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="3c8e9-159">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="3c8e9-159">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="3c8e9-160">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-160">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="3c8e9-161">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="3c8e9-161">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="3c8e9-162">禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-162">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="3c8e9-163">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="3c8e9-163">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="3c8e9-164">将一个空闲例程添加到 MAPI 系统，使用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-164">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="3c8e9-165">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="3c8e9-165">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="3c8e9-166">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-166">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="3c8e9-167">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="3c8e9-167">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="3c8e9-168">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-168">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="3c8e9-169">**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**接受作为输入参数的函数标记，则由**FtgRegisterIdleRoutine**返回。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-169">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="3c8e9-170">当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-170">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="3c8e9-171">不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。</span><span class="sxs-lookup"><span data-stu-id="3c8e9-171">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

