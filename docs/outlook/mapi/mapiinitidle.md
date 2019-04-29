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
ms.openlocfilehash: b07c40882c0b9974c71eeb03123e7025b948a75e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432441"
---
# <a name="mapiinitidle"></a><span data-ttu-id="f3fac-103">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="f3fac-103">MAPIInitIdle</span></span>

  
  
<span data-ttu-id="f3fac-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3fac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3fac-105">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="f3fac-105">Initializes the MAPI idle engine for the calling application.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f3fac-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f3fac-106">Header file:</span></span>  <br/> |<span data-ttu-id="f3fac-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="f3fac-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="f3fac-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="f3fac-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="f3fac-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="f3fac-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="f3fac-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="f3fac-110">Called by:</span></span>  <br/> |<span data-ttu-id="f3fac-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="f3fac-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LONG MAPIInitIdle(
  LPVOID lpvReserved
);
```

## <a name="parameters"></a><span data-ttu-id="f3fac-112">参数</span><span class="sxs-lookup"><span data-stu-id="f3fac-112">Parameters</span></span>

 <span data-ttu-id="f3fac-113">_lpvReserved_</span><span class="sxs-lookup"><span data-stu-id="f3fac-113">_lpvReserved_</span></span>
  
> <span data-ttu-id="f3fac-114">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="f3fac-114">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f3fac-115">返回值</span><span class="sxs-lookup"><span data-stu-id="f3fac-115">Return value</span></span>

<span data-ttu-id="f3fac-116">如果初始化成功, 则**MAPIInitIdle**函数返回零, 否则返回1。</span><span class="sxs-lookup"><span data-stu-id="f3fac-116">The **MAPIInitIdle** function returns zero if initialization is successful, and 1 otherwise.</span></span> <span data-ttu-id="f3fac-117">如果多次调用**MAPIInitIdle** , 则所有其他调用都将成功, 但会被忽略, 除非递增引用计数。</span><span class="sxs-lookup"><span data-stu-id="f3fac-117">If **MAPIInitIdle** is called multiple times, all additional calls succeed but are ignored except to increment the reference count.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="f3fac-118">说明</span><span class="sxs-lookup"><span data-stu-id="f3fac-118">Remarks</span></span>

<span data-ttu-id="f3fac-119">在调用任何其他 idle 引擎函数之前, 客户端应用程序或服务提供程序必须调用**MAPIInitIdle** 。</span><span class="sxs-lookup"><span data-stu-id="f3fac-119">A client application or service provider must call **MAPIInitIdle** before calling any other idle engine function.</span></span> 
  
<span data-ttu-id="f3fac-120">每次调用**MAPIInitIdle**时, 都必须通过对[MAPIDeInitIdle](mapideinitidle.md)的后续调用进行匹配, 否则会为调用应用程序保持空闲引擎的运行状态。</span><span class="sxs-lookup"><span data-stu-id="f3fac-120">Every call to **MAPIInitIdle** must be matched by a subsequent call to [MAPIDeInitIdle](mapideinitidle.md), or the idle engine is left running for the calling application.</span></span> 
  
<span data-ttu-id="f3fac-121">以下函数处理 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程:</span><span class="sxs-lookup"><span data-stu-id="f3fac-121">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="f3fac-122">**Idle 例程函数**</span><span class="sxs-lookup"><span data-stu-id="f3fac-122">**Idle routine function**</span></span>|<span data-ttu-id="f3fac-123">**使用**</span><span class="sxs-lookup"><span data-stu-id="f3fac-123">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f3fac-124">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="f3fac-124">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="f3fac-125">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="f3fac-125">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="f3fac-126">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="f3fac-126">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="f3fac-127">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="f3fac-127">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="f3fac-128">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="f3fac-128">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="f3fac-129">禁用或重新启用已注册的空闲例程, 而不将其从 MAPI 系统中删除。</span><span class="sxs-lookup"><span data-stu-id="f3fac-129">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="f3fac-130">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="f3fac-130">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="f3fac-131">将空闲例程添加到 MAPI 系统中 (无论是否启用)。</span><span class="sxs-lookup"><span data-stu-id="f3fac-131">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="f3fac-132">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="f3fac-132">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="f3fac-133">关闭呼叫应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="f3fac-133">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|<span data-ttu-id="f3fac-134">**MAPIInitIdle**</span><span class="sxs-lookup"><span data-stu-id="f3fac-134">**MAPIInitIdle**</span></span> <br/> |<span data-ttu-id="f3fac-135">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="f3fac-135">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="f3fac-136">当平台的所有前台任务都变为空闲时, MAPI 空闲引擎将调用准备执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="f3fac-136">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="f3fac-137">在具有相同优先级的空闲例程之间, 不能保证呼叫顺序。</span><span class="sxs-lookup"><span data-stu-id="f3fac-137">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

