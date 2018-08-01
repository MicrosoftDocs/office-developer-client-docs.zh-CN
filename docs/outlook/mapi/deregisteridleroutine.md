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
ms.openlocfilehash: 85161fb87e798bbb03b267f9760870da1246e48d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774778"
---
# <a name="deregisteridleroutine"></a><span data-ttu-id="b9bf5-103">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b9bf5-103">DeregisterIdleRoutine</span></span>

  
  
<span data-ttu-id="b9bf5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b9bf5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b9bf5-105">删除[FNIDLE](fnidle.md)基于从 MAPI 系统空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-105">Removes a [FNIDLE](fnidle.md) based idle routine from the MAPI system.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b9bf5-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b9bf5-106">Header file:</span></span>  <br/> |<span data-ttu-id="b9bf5-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="b9bf5-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="b9bf5-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="b9bf5-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="b9bf5-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="b9bf5-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="b9bf5-110">调用：</span><span class="sxs-lookup"><span data-stu-id="b9bf5-110">Called by:</span></span>  <br/> |<span data-ttu-id="b9bf5-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="b9bf5-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID DeregisterIdleRoutine(
  FTG ftg
);
```

## <a name="parameters"></a><span data-ttu-id="b9bf5-112">参数</span><span class="sxs-lookup"><span data-stu-id="b9bf5-112">Parameters</span></span>

 <span data-ttu-id="b9bf5-113">_ftg_</span><span class="sxs-lookup"><span data-stu-id="b9bf5-113">_ftg_</span></span>
  
> <span data-ttu-id="b9bf5-114">[in]标识要删除的空闲例程的函数标记。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-114">[in] Function tag that identifies the idle routine to be removed.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b9bf5-115">返回值</span><span class="sxs-lookup"><span data-stu-id="b9bf5-115">Return value</span></span>

<span data-ttu-id="b9bf5-116">无。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-116">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b9bf5-117">说明</span><span class="sxs-lookup"><span data-stu-id="b9bf5-117">Remarks</span></span>

<span data-ttu-id="b9bf5-118">客户端应用程序或服务提供程序中的任何任务可以取消注册它具有有效_ftg_参数为其任何空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-118">Any task in a client application or service provider can deregister any idle routine for which it has a valid  _ftg_ parameter.</span></span> <span data-ttu-id="b9bf5-119">具体而言，空闲例程可以取消注册自身。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-119">In particular, an idle routine can deregister itself.</span></span> 
  
<span data-ttu-id="b9bf5-120">下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程：</span><span class="sxs-lookup"><span data-stu-id="b9bf5-120">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="b9bf5-121">**空闲例行函数**</span><span class="sxs-lookup"><span data-stu-id="b9bf5-121">**Idle routine function**</span></span>|<span data-ttu-id="b9bf5-122">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="b9bf5-122">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b9bf5-123">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b9bf5-123">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="b9bf5-124">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-124">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|<span data-ttu-id="b9bf5-125">**DeregisterIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="b9bf5-125">**DeregisterIdleRoutine**</span></span> <br/> |<span data-ttu-id="b9bf5-126">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-126">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="b9bf5-127">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b9bf5-127">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="b9bf5-128">禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-128">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="b9bf5-129">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="b9bf5-129">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="b9bf5-130">将一个空闲例程添加到 MAPI 系统，使用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-130">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="b9bf5-131">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="b9bf5-131">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="b9bf5-132">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-132">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="b9bf5-133">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="b9bf5-133">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="b9bf5-134">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-134">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
 <span data-ttu-id="b9bf5-135">**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**接受作为输入参数的函数标记，则由**FtgRegisterIdleRoutine**返回。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-135">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="b9bf5-136">当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-136">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="b9bf5-137">不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-137">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  
<span data-ttu-id="b9bf5-138">空闲例程取消注册后，空闲引擎不调用它再次。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-138">After the idle routine is deregistered, the idle engine does not call it again.</span></span> <span data-ttu-id="b9bf5-139">调用**DeregisterIdleRoutine**任何实现必须释放空闲引擎要在其原始调用**FtgRegisterIdleRoutine**函数中使用的指针传送到任何内存块。</span><span class="sxs-lookup"><span data-stu-id="b9bf5-139">Any implementation that calls **DeregisterIdleRoutine** must deallocate any memory blocks to which it passed pointers for the idle engine to use in its original call to the **FtgRegisterIdleRoutine** function.</span></span> 
  

