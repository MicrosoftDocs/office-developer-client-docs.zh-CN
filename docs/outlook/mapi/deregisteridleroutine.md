---
title: DeregisterIdleRoutine
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DeregisterIdleRoutine
api_type:
- COM
ms.assetid: a8ada6fe-9963-4c25-b4b4-db77f9517368
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 62231a900dbe01ebe1e848355226c0589072cd42
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404559"
---
# <a name="deregisteridleroutine"></a><span data-ttu-id="4ef12-103">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="4ef12-103">DeregisterIdleRoutine</span></span>

  
  
<span data-ttu-id="4ef12-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4ef12-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4ef12-105">从 MAPI 系统中删除基于 [FNIDLE](fnidle.md) 的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="4ef12-105">Removes a [FNIDLE](fnidle.md) based idle routine from the MAPI system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4ef12-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4ef12-106">Header file:</span></span>  <br/> |<span data-ttu-id="4ef12-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="4ef12-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="4ef12-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="4ef12-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="4ef12-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="4ef12-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="4ef12-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="4ef12-110">Called by:</span></span>  <br/> |<span data-ttu-id="4ef12-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="4ef12-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID DeregisterIdleRoutine(
  FTG ftg
);
```

## <a name="parameters"></a><span data-ttu-id="4ef12-112">参数</span><span class="sxs-lookup"><span data-stu-id="4ef12-112">Parameters</span></span>

 <span data-ttu-id="4ef12-113">_ftg_</span><span class="sxs-lookup"><span data-stu-id="4ef12-113">_ftg_</span></span>
  
> <span data-ttu-id="4ef12-114">[in]标识要删除的空闲例程的函数标记。</span><span class="sxs-lookup"><span data-stu-id="4ef12-114">[in] Function tag that identifies the idle routine to be removed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4ef12-115">返回值</span><span class="sxs-lookup"><span data-stu-id="4ef12-115">Return value</span></span>

<span data-ttu-id="4ef12-116">无。</span><span class="sxs-lookup"><span data-stu-id="4ef12-116">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4ef12-117">说明</span><span class="sxs-lookup"><span data-stu-id="4ef12-117">Remarks</span></span>

<span data-ttu-id="4ef12-118">客户端应用程序或服务提供商中的任何任务都可以取消注册其具有有效  _ftg_ 参数的任何空闲例程。</span><span class="sxs-lookup"><span data-stu-id="4ef12-118">Any task in a client application or service provider can deregister any idle routine for which it has a valid  _ftg_ parameter.</span></span> <span data-ttu-id="4ef12-119">特别是，空闲例程可以自行取消注册。</span><span class="sxs-lookup"><span data-stu-id="4ef12-119">In particular, an idle routine can deregister itself.</span></span> 
  
<span data-ttu-id="4ef12-120">以下函数基于 [FNIDLE](fnidle.md) 函数原型处理 MAPI 空闲引擎和空闲例程：</span><span class="sxs-lookup"><span data-stu-id="4ef12-120">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="4ef12-121">**空闲例程函数**</span><span class="sxs-lookup"><span data-stu-id="4ef12-121">**Idle routine function**</span></span>|<span data-ttu-id="4ef12-122">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="4ef12-122">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4ef12-123">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="4ef12-123">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="4ef12-124">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="4ef12-124">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|<span data-ttu-id="4ef12-125">**DeregisterIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="4ef12-125">**DeregisterIdleRoutine**</span></span> <br/> |<span data-ttu-id="4ef12-126">从 MAPI 系统中删除注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="4ef12-126">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="4ef12-127">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="4ef12-127">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="4ef12-128">禁用或重新启用注册的空闲例程，而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="4ef12-128">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="4ef12-129">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="4ef12-129">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="4ef12-130">将空闲例程添加到 MAPI 系统，启用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="4ef12-130">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="4ef12-131">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="4ef12-131">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="4ef12-132">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="4ef12-132">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="4ef12-133">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="4ef12-133">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="4ef12-134">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="4ef12-134">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
 <span data-ttu-id="4ef12-135">ChangeIdleRoutine、DeregisterIdleRoutine 和 **EnableIdleRoutine** 将 **FtgRegisterIdleRoutine** 返回的函数标记作为输入参数。 </span><span class="sxs-lookup"><span data-stu-id="4ef12-135">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="4ef12-136">当平台的所有前台任务变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="4ef12-136">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="4ef12-137">无法保证在优先级相同的空闲例程之间调用顺序。</span><span class="sxs-lookup"><span data-stu-id="4ef12-137">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  
<span data-ttu-id="4ef12-138">在取消注册空闲例程后，空闲引擎不会再次调用它。</span><span class="sxs-lookup"><span data-stu-id="4ef12-138">After the idle routine is deregistered, the idle engine does not call it again.</span></span> <span data-ttu-id="4ef12-139">调用 **DeregisterIdleRoutine** 的任何实现都必须解除分配它向其中传递指针的任何内存块，使空闲引擎在其原始调用 **FtgRegisterIdleRoutine** 函数时可以使用这些内存块。</span><span class="sxs-lookup"><span data-stu-id="4ef12-139">Any implementation that calls **DeregisterIdleRoutine** must deallocate any memory blocks to which it passed pointers for the idle engine to use in its original call to the **FtgRegisterIdleRoutine** function.</span></span> 
  

