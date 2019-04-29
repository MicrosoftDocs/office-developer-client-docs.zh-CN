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
ms.openlocfilehash: 534f4da15bba5f38bec4cde91206694f8691cbc6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412378"
---
# <a name="fnidle"></a><span data-ttu-id="3b341-103">FNIDLE</span><span class="sxs-lookup"><span data-stu-id="3b341-103">FNIDLE</span></span>
 
<span data-ttu-id="3b341-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b341-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3b341-105">定义 MAPI 空闲引擎根据优先级定期呼叫的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="3b341-105">Defines an idle routine that the MAPI idle engine calls periodically according to priority.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3b341-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3b341-106">Header file:</span></span>  <br/> |<span data-ttu-id="3b341-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="3b341-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="3b341-108">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="3b341-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="3b341-109">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="3b341-109">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="3b341-110">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="3b341-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="3b341-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="3b341-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="3b341-112">相应的指针类型:</span><span class="sxs-lookup"><span data-stu-id="3b341-112">Corresponding pointer type:</span></span>  <br/> |<span data-ttu-id="3b341-113">PFNIDLE</span><span class="sxs-lookup"><span data-stu-id="3b341-113">PFNIDLE</span></span>  <br/> |
   
```cpp
BOOL (STDAPICALLTYPE FNIDLE)(
  LPVOID lpvContext
);
```

## <a name="parameters"></a><span data-ttu-id="3b341-114">参数</span><span class="sxs-lookup"><span data-stu-id="3b341-114">Parameters</span></span>

 <span data-ttu-id="3b341-115">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="3b341-115">_lpvContext_</span></span>
  
> <span data-ttu-id="3b341-116">实时一个指针, 指向 MAPI 在每次呼叫时传递给空闲例程的内存块。</span><span class="sxs-lookup"><span data-stu-id="3b341-116">[in] Pointer to a block of memory that MAPI passes to the idle routine each time it calls it.</span></span> <span data-ttu-id="3b341-117">此指针通过[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)传递给_pvIdleParam_参数中的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="3b341-117">This pointer is passed to the MAPI idle engine in the  _pvIdleParam_ parameter by [FtgRegisterIdleRoutine](ftgregisteridleroutine.md).</span></span> <span data-ttu-id="3b341-118">内存块中的数据可提供对空闲例程 (如要对其执行操作的对象) 或较长操作的当前状态的调用的上下文。</span><span class="sxs-lookup"><span data-stu-id="3b341-118">The data in the memory block can provide context for the call to the idle routine, such as which object to operate on, or the current state of a lengthy operation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="3b341-119">返回值</span><span class="sxs-lookup"><span data-stu-id="3b341-119">Return value</span></span>

<span data-ttu-id="3b341-120">FALSE</span><span class="sxs-lookup"><span data-stu-id="3b341-120">FALSE</span></span> 
  
> <span data-ttu-id="3b341-121">具有**FNIDLE**原型的空闲例程应始终返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="3b341-121">An idle routine with the **FNIDLE** prototype should always return FALSE.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="3b341-122">说明</span><span class="sxs-lookup"><span data-stu-id="3b341-122">Remarks</span></span>

<span data-ttu-id="3b341-123">空闲例程的特定功能由实现客户端应用程序或服务提供程序决定。</span><span class="sxs-lookup"><span data-stu-id="3b341-123">The specific functionality of the idle routine is determined by the implementing client application or service provider.</span></span> 
  
<span data-ttu-id="3b341-124">客户端或提供程序必须限制空闲例程的每个状态的执行时间。</span><span class="sxs-lookup"><span data-stu-id="3b341-124">The client or provider must limit the execution time of each state of an idle routine.</span></span> <span data-ttu-id="3b341-125">每种状态都应执行最少的处理, 更新_lpvContext_指向的上下文数据中的当前状态, 然后返回到 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="3b341-125">Every state should perform a minimum amount of processing, update the current state in the context data pointed to by  _lpvContext_, and return to the MAPI idle engine.</span></span> 
  
<span data-ttu-id="3b341-126">客户端或提供程序必须调用 MAPI 函数[MAPIInitIdle](mapiinitidle.md) , 然后它才能使用对[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)函数的调用注册其自己的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="3b341-126">The client or provider must call the MAPI function [MAPIInitIdle](mapiinitidle.md) before it can register its own idle routine with a call to the [FtgRegisterIdleRoutine](ftgregisteridleroutine.md) function.</span></span> 
  
<span data-ttu-id="3b341-127">以下函数处理 MAPI 空闲引擎和基于 FNIDLE 函数原型的空闲例程:</span><span class="sxs-lookup"><span data-stu-id="3b341-127">The following functions deal with the MAPI idle engine and with idle routines based on the FNIDLE function prototype:</span></span> 
  
|<span data-ttu-id="3b341-128">**Idle 例程函数**</span><span class="sxs-lookup"><span data-stu-id="3b341-128">**Idle routine function**</span></span>|<span data-ttu-id="3b341-129">**使用**</span><span class="sxs-lookup"><span data-stu-id="3b341-129">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3b341-130">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="3b341-130">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="3b341-131">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="3b341-131">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="3b341-132">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="3b341-132">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="3b341-133">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="3b341-133">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="3b341-134">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="3b341-134">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="3b341-135">禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="3b341-135">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="3b341-136">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="3b341-136">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="3b341-137">将空闲例程添加到 MAPI 系统中 (无论是否启用)。</span><span class="sxs-lookup"><span data-stu-id="3b341-137">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="3b341-138">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="3b341-138">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="3b341-139">关闭呼叫应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="3b341-139">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="3b341-140">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="3b341-140">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="3b341-141">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="3b341-141">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="3b341-142">**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**采用**FtgRegisterIdleRoutine**返回的函数标记作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="3b341-142">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="3b341-143">当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="3b341-143">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="3b341-144">在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。</span><span class="sxs-lookup"><span data-stu-id="3b341-144">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

