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
# <a name="deregisteridleroutine"></a><span data-ttu-id="d5506-103">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="d5506-103">DeregisterIdleRoutine</span></span>

  
  
<span data-ttu-id="d5506-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d5506-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d5506-105">从 MAPI 系统中删除基于[FNIDLE](fnidle.md)的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="d5506-105">Removes a [FNIDLE](fnidle.md) based idle routine from the MAPI system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d5506-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d5506-106">Header file:</span></span>  <br/> |<span data-ttu-id="d5506-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="d5506-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="d5506-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="d5506-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="d5506-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="d5506-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="d5506-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="d5506-110">Called by:</span></span>  <br/> |<span data-ttu-id="d5506-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="d5506-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID DeregisterIdleRoutine(
  FTG ftg
);
```

## <a name="parameters"></a><span data-ttu-id="d5506-112">参数</span><span class="sxs-lookup"><span data-stu-id="d5506-112">Parameters</span></span>

 <span data-ttu-id="d5506-113">_ftg_</span><span class="sxs-lookup"><span data-stu-id="d5506-113">_ftg_</span></span>
  
> <span data-ttu-id="d5506-114">实时用于标识要删除的空闲例程的 Function 标记。</span><span class="sxs-lookup"><span data-stu-id="d5506-114">[in] Function tag that identifies the idle routine to be removed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d5506-115">返回值</span><span class="sxs-lookup"><span data-stu-id="d5506-115">Return value</span></span>

<span data-ttu-id="d5506-116">无。</span><span class="sxs-lookup"><span data-stu-id="d5506-116">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d5506-117">说明</span><span class="sxs-lookup"><span data-stu-id="d5506-117">Remarks</span></span>

<span data-ttu-id="d5506-118">客户端应用程序或服务提供程序中的任何任务都可以取消注册其具有有效_ftg_参数的任何空闲例程。</span><span class="sxs-lookup"><span data-stu-id="d5506-118">Any task in a client application or service provider can deregister any idle routine for which it has a valid  _ftg_ parameter.</span></span> <span data-ttu-id="d5506-119">特别是, 空闲例程可以自行取消注册。</span><span class="sxs-lookup"><span data-stu-id="d5506-119">In particular, an idle routine can deregister itself.</span></span> 
  
<span data-ttu-id="d5506-120">以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程:</span><span class="sxs-lookup"><span data-stu-id="d5506-120">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="d5506-121">**Idle 例程函数**</span><span class="sxs-lookup"><span data-stu-id="d5506-121">**Idle routine function**</span></span>|<span data-ttu-id="d5506-122">**使用**</span><span class="sxs-lookup"><span data-stu-id="d5506-122">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d5506-123">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="d5506-123">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="d5506-124">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="d5506-124">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|<span data-ttu-id="d5506-125">**DeregisterIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="d5506-125">**DeregisterIdleRoutine**</span></span> <br/> |<span data-ttu-id="d5506-126">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="d5506-126">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="d5506-127">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="d5506-127">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="d5506-128">禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="d5506-128">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="d5506-129">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="d5506-129">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="d5506-130">将空闲例程添加到 MAPI 系统中 (无论是否启用)。</span><span class="sxs-lookup"><span data-stu-id="d5506-130">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="d5506-131">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="d5506-131">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="d5506-132">关闭呼叫应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="d5506-132">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="d5506-133">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="d5506-133">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="d5506-134">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="d5506-134">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
 <span data-ttu-id="d5506-135">**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**采用**FtgRegisterIdleRoutine**返回的函数标记作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="d5506-135">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="d5506-136">当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="d5506-136">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="d5506-137">在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。</span><span class="sxs-lookup"><span data-stu-id="d5506-137">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  
<span data-ttu-id="d5506-138">在空闲例程取消注册后, 空闲引擎不会再次调用它。</span><span class="sxs-lookup"><span data-stu-id="d5506-138">After the idle routine is deregistered, the idle engine does not call it again.</span></span> <span data-ttu-id="d5506-139">任何调用**DeregisterIdleRoutine**的实现都必须释放其向其传递了空闲引擎的指针的任何内存块, 以便在其对**FtgRegisterIdleRoutine**函数的原始调用中使用。</span><span class="sxs-lookup"><span data-stu-id="d5506-139">Any implementation that calls **DeregisterIdleRoutine** must deallocate any memory blocks to which it passed pointers for the idle engine to use in its original call to the **FtgRegisterIdleRoutine** function.</span></span> 
  

