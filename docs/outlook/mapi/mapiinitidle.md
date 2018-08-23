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
ms.openlocfilehash: fd9a91b089bb06e6dfe34a1a144245d404adb270
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569223"
---
# <a name="mapiinitidle"></a><span data-ttu-id="1e851-103">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="1e851-103">MAPIInitIdle</span></span>

  
  
<span data-ttu-id="1e851-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1e851-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1e851-105">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="1e851-105">Initializes the MAPI idle engine for the calling application.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1e851-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="1e851-106">Header file:</span></span>  <br/> |<span data-ttu-id="1e851-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="1e851-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="1e851-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="1e851-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="1e851-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="1e851-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="1e851-110">调用：</span><span class="sxs-lookup"><span data-stu-id="1e851-110">Called by:</span></span>  <br/> |<span data-ttu-id="1e851-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="1e851-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
LONG MAPIInitIdle(
  LPVOID lpvReserved
);
```

## <a name="parameters"></a><span data-ttu-id="1e851-112">参数</span><span class="sxs-lookup"><span data-stu-id="1e851-112">Parameters</span></span>

 <span data-ttu-id="1e851-113">_lpvReserved_</span><span class="sxs-lookup"><span data-stu-id="1e851-113">_lpvReserved_</span></span>
  
> <span data-ttu-id="1e851-114">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="1e851-114">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1e851-115">返回值</span><span class="sxs-lookup"><span data-stu-id="1e851-115">Return value</span></span>

<span data-ttu-id="1e851-116">如果初始化成功，和 1 否则，则**MAPIInitIdle**函数将返回零。</span><span class="sxs-lookup"><span data-stu-id="1e851-116">The **MAPIInitIdle** function returns zero if initialization is successful, and 1 otherwise.</span></span> <span data-ttu-id="1e851-117">如果多次调用**MAPIInitIdle** ，则所有其他呼叫成功，但会忽略除以增加引用计数。</span><span class="sxs-lookup"><span data-stu-id="1e851-117">If **MAPIInitIdle** is called multiple times, all additional calls succeed but are ignored except to increment the reference count.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="1e851-118">注解</span><span class="sxs-lookup"><span data-stu-id="1e851-118">Remarks</span></span>

<span data-ttu-id="1e851-119">客户端应用程序或服务提供商必须调用任何其他空闲引擎函数之前调用**MAPIInitIdle** 。</span><span class="sxs-lookup"><span data-stu-id="1e851-119">A client application or service provider must call **MAPIInitIdle** before calling any other idle engine function.</span></span> 
  
<span data-ttu-id="1e851-120">每次调用**MAPIInitIdle**必须匹配通过后续调用[MAPIDeInitIdle](mapideinitidle.md)，或空闲引擎仍在运行调用应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e851-120">Every call to **MAPIInitIdle** must be matched by a subsequent call to [MAPIDeInitIdle](mapideinitidle.md), or the idle engine is left running for the calling application.</span></span> 
  
<span data-ttu-id="1e851-121">下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程：</span><span class="sxs-lookup"><span data-stu-id="1e851-121">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="1e851-122">**空闲例行函数**</span><span class="sxs-lookup"><span data-stu-id="1e851-122">**Idle routine function**</span></span>|<span data-ttu-id="1e851-123">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="1e851-123">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1e851-124">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="1e851-124">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="1e851-125">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="1e851-125">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="1e851-126">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="1e851-126">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="1e851-127">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="1e851-127">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="1e851-128">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="1e851-128">EnableIdleRoutine</span></span>](enableidleroutine.md) <br/> |<span data-ttu-id="1e851-129">禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。</span><span class="sxs-lookup"><span data-stu-id="1e851-129">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="1e851-130">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="1e851-130">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="1e851-131">将一个空闲例程添加到 MAPI 系统，使用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="1e851-131">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="1e851-132">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="1e851-132">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="1e851-133">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="1e851-133">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|<span data-ttu-id="1e851-134">**MAPIInitIdle**</span><span class="sxs-lookup"><span data-stu-id="1e851-134">**MAPIInitIdle**</span></span> <br/> |<span data-ttu-id="1e851-135">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="1e851-135">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
<span data-ttu-id="1e851-136">当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="1e851-136">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="1e851-137">不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。</span><span class="sxs-lookup"><span data-stu-id="1e851-137">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

