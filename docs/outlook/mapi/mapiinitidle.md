---
title: MAPIInitIdle
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIInitIdle
api_type:
- COM
ms.assetid: b6de7c6a-f2e7-4248-adea-d354924a8bbf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e4f4cdd1d0ed2e03d49f471e6e91464b7973c920
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776370"
---
# <a name="mapiinitidle"></a><span data-ttu-id="27a8d-103">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="27a8d-103">MAPIInitIdle</span></span>

  
  
<span data-ttu-id="27a8d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="27a8d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="27a8d-105">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="27a8d-105">Initializes the MAPI idle engine for the calling application.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="27a8d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="27a8d-106">Header file:</span></span>  <br/> |<span data-ttu-id="27a8d-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="27a8d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="27a8d-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="27a8d-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="27a8d-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="27a8d-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="27a8d-110">调用：</span><span class="sxs-lookup"><span data-stu-id="27a8d-110">Called by:</span></span>  <br/> |<span data-ttu-id="27a8d-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="27a8d-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LONG MAPIInitIdle(
  LPVOID lpvReserved
);
```

## <a name="parameters"></a><span data-ttu-id="27a8d-112">参数</span><span class="sxs-lookup"><span data-stu-id="27a8d-112">Parameters</span></span>

 <span data-ttu-id="27a8d-113">_lpvReserved_</span><span class="sxs-lookup"><span data-stu-id="27a8d-113">_lpvReserved_</span></span>
  
> <span data-ttu-id="27a8d-114">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="27a8d-114">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="27a8d-115">返回值</span><span class="sxs-lookup"><span data-stu-id="27a8d-115">Return value</span></span>

<span data-ttu-id="27a8d-116">如果初始化成功，和 1 否则，则**MAPIInitIdle**函数将返回零。</span><span class="sxs-lookup"><span data-stu-id="27a8d-116">The **MAPIInitIdle** function returns zero if initialization is successful, and 1 otherwise.</span></span> <span data-ttu-id="27a8d-117">如果多次调用**MAPIInitIdle** ，则所有其他呼叫成功，但会忽略除以增加引用计数。</span><span class="sxs-lookup"><span data-stu-id="27a8d-117">If **MAPIInitIdle** is called multiple times, all additional calls succeed but are ignored except to increment the reference count.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="27a8d-118">说明</span><span class="sxs-lookup"><span data-stu-id="27a8d-118">Remarks</span></span>

<span data-ttu-id="27a8d-119">客户端应用程序或服务提供商必须调用任何其他空闲引擎函数之前调用**MAPIInitIdle** 。</span><span class="sxs-lookup"><span data-stu-id="27a8d-119">A client application or service provider must call **MAPIInitIdle** before calling any other idle engine function.</span></span> 
  
<span data-ttu-id="27a8d-120">每次调用**MAPIInitIdle**必须匹配通过后续调用[MAPIDeInitIdle](mapideinitidle.md)，或空闲引擎仍在运行调用应用程序。</span><span class="sxs-lookup"><span data-stu-id="27a8d-120">Every call to **MAPIInitIdle** must be matched by a subsequent call to [MAPIDeInitIdle](mapideinitidle.md), or the idle engine is left running for the calling application.</span></span> 
  
<span data-ttu-id="27a8d-121">下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程：</span><span class="sxs-lookup"><span data-stu-id="27a8d-121">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="27a8d-122">**空闲例行函数**</span><span class="sxs-lookup"><span data-stu-id="27a8d-122">**Idle routine function**</span></span>|<span data-ttu-id="27a8d-123">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="27a8d-123">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="27a8d-124">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="27a8d-124">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="27a8d-125">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="27a8d-125">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="27a8d-126">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="27a8d-126">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="27a8d-127">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="27a8d-127">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="27a8d-128">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="27a8d-128">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="27a8d-129">禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。</span><span class="sxs-lookup"><span data-stu-id="27a8d-129">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="27a8d-130">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="27a8d-130">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="27a8d-131">将一个空闲例程添加到 MAPI 系统，使用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="27a8d-131">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="27a8d-132">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="27a8d-132">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="27a8d-133">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="27a8d-133">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|<span data-ttu-id="27a8d-134">**MAPIInitIdle**</span><span class="sxs-lookup"><span data-stu-id="27a8d-134">**MAPIInitIdle**</span></span> <br/> |<span data-ttu-id="27a8d-135">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="27a8d-135">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="27a8d-136">当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="27a8d-136">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="27a8d-137">不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。</span><span class="sxs-lookup"><span data-stu-id="27a8d-137">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

