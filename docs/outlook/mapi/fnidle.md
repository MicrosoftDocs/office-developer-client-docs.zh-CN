---
title: FNIDLE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FNIDLE
api_type:
- COM
ms.assetid: f6b31bb4-69dd-43de-b62b-abfa99557641
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cbad4b903592f83fc7d72fde21f149c9835f2e23
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575635"
---
# <a name="fnidle"></a><span data-ttu-id="b34b3-103">FNIDLE</span><span class="sxs-lookup"><span data-stu-id="b34b3-103">FNIDLE</span></span>
 
<span data-ttu-id="b34b3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b34b3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b34b3-105">定义一个空闲例程 MAPI 空闲引擎定期调用根据优先级。</span><span class="sxs-lookup"><span data-stu-id="b34b3-105">Defines an idle routine that the MAPI idle engine calls periodically according to priority.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b34b3-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b34b3-106">Header file:</span></span>  <br/> |<span data-ttu-id="b34b3-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="b34b3-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="b34b3-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="b34b3-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="b34b3-109">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="b34b3-109">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="b34b3-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="b34b3-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="b34b3-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="b34b3-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="b34b3-112">相应的指针类型：</span><span class="sxs-lookup"><span data-stu-id="b34b3-112">Corresponding pointer type:</span></span>  <br/> |<span data-ttu-id="b34b3-113">PFNIDLE</span><span class="sxs-lookup"><span data-stu-id="b34b3-113">PFNIDLE</span></span>  <br/> |
   
```cpp
BOOL (STDAPICALLTYPE FNIDLE)(
  LPVOID lpvContext
);
```

## <a name="parameters"></a><span data-ttu-id="b34b3-114">参数</span><span class="sxs-lookup"><span data-stu-id="b34b3-114">Parameters</span></span>

 <span data-ttu-id="b34b3-115">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="b34b3-115">_lpvContext_</span></span>
  
> <span data-ttu-id="b34b3-116">[in]指向某一内存 MAPI 传递给空闲例程每次调用它。</span><span class="sxs-lookup"><span data-stu-id="b34b3-116">[in] Pointer to a block of memory that MAPI passes to the idle routine each time it calls it.</span></span> <span data-ttu-id="b34b3-117">此指针[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)由传递到 MAPI 空闲引擎_pvIdleParam_参数中。</span><span class="sxs-lookup"><span data-stu-id="b34b3-117">This pointer is passed to the MAPI idle engine in the  _pvIdleParam_ parameter by [FtgRegisterIdleRoutine](ftgregisteridleroutine.md).</span></span> <span data-ttu-id="b34b3-118">内存块中的数据可以提供上下文，用于调用空闲例程，例如，正常工作的对象或冗长的操作的当前状态。</span><span class="sxs-lookup"><span data-stu-id="b34b3-118">The data in the memory block can provide context for the call to the idle routine, such as which object to operate on, or the current state of a lengthy operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b34b3-119">返回值</span><span class="sxs-lookup"><span data-stu-id="b34b3-119">Return value</span></span>

<span data-ttu-id="b34b3-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="b34b3-120">FALSE</span></span> 
  
> <span data-ttu-id="b34b3-121">具有**FNIDLE**原型空闲例程应始终返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="b34b3-121">An idle routine with the **FNIDLE** prototype should always return FALSE.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b34b3-122">注解</span><span class="sxs-lookup"><span data-stu-id="b34b3-122">Remarks</span></span>

<span data-ttu-id="b34b3-123">空闲例程的特定功能由实现客户端应用程序或服务提供商。</span><span class="sxs-lookup"><span data-stu-id="b34b3-123">The specific functionality of the idle routine is determined by the implementing client application or service provider.</span></span> 
  
<span data-ttu-id="b34b3-124">在客户端或提供程序必须限制空闲例程的每个状态的执行时间。</span><span class="sxs-lookup"><span data-stu-id="b34b3-124">The client or provider must limit the execution time of each state of an idle routine.</span></span> <span data-ttu-id="b34b3-125">每个状态应该执行最少的处理，更新所指的_lpvContext_，上下文数据中的当前状态并返回到 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="b34b3-125">Every state should perform a minimum amount of processing, update the current state in the context data pointed to by  _lpvContext_, and return to the MAPI idle engine.</span></span> 
  
<span data-ttu-id="b34b3-126">在客户端或提供程序必须 MAPI 函数[MAPIInitIdle](mapiinitidle.md)之前调用它可以与对[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)函数的调用中注册其自己的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b34b3-126">The client or provider must call the MAPI function [MAPIInitIdle](mapiinitidle.md) before it can register its own idle routine with a call to the [FtgRegisterIdleRoutine](ftgregisteridleroutine.md) function.</span></span> 
  
<span data-ttu-id="b34b3-127">下面的函数处理与 MAPI 空闲引擎和基于 FNIDLE 函数原型的空闲例程：</span><span class="sxs-lookup"><span data-stu-id="b34b3-127">The following functions deal with the MAPI idle engine and with idle routines based on the FNIDLE function prototype:</span></span> 
  
|<span data-ttu-id="b34b3-128">**空闲例行函数**</span><span class="sxs-lookup"><span data-stu-id="b34b3-128">**Idle routine function**</span></span>|<span data-ttu-id="b34b3-129">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="b34b3-129">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b34b3-130">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b34b3-130">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="b34b3-131">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="b34b3-131">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="b34b3-132">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b34b3-132">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="b34b3-133">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b34b3-133">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="b34b3-134">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b34b3-134">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="b34b3-135">禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。</span><span class="sxs-lookup"><span data-stu-id="b34b3-135">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="b34b3-136">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b34b3-136">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="b34b3-137">将一个空闲例程添加到 MAPI 系统，使用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="b34b3-137">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="b34b3-138">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="b34b3-138">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="b34b3-139">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="b34b3-139">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="b34b3-140">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="b34b3-140">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="b34b3-141">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="b34b3-141">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="b34b3-142">**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**接受作为输入参数的函数标记，则由**FtgRegisterIdleRoutine**返回。</span><span class="sxs-lookup"><span data-stu-id="b34b3-142">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="b34b3-143">当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b34b3-143">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="b34b3-144">不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。</span><span class="sxs-lookup"><span data-stu-id="b34b3-144">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

