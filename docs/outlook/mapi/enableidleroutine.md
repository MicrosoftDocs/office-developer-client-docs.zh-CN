---
title: EnableIdleRoutine
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.EnableIdleRoutine
api_type:
- COM
ms.assetid: 332ea831-bdf9-4dbd-b9c7-a80f8ba11b3b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c53bd63e60281e999d0d379913b3609e9472a40e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579275"
---
# <a name="enableidleroutine"></a><span data-ttu-id="e7f77-103">EnableIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="e7f77-103">EnableIdleRoutine</span></span>

  
  
<span data-ttu-id="e7f77-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e7f77-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e7f77-105">启用或禁用[FNIDLE](fnidle.md)基于空闲例程。</span><span class="sxs-lookup"><span data-stu-id="e7f77-105">Enables or disables a [FNIDLE](fnidle.md) based idle routine.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e7f77-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="e7f77-106">Header file:</span></span>  <br/> |<span data-ttu-id="e7f77-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="e7f77-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="e7f77-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="e7f77-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="e7f77-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="e7f77-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="e7f77-110">调用：</span><span class="sxs-lookup"><span data-stu-id="e7f77-110">Called by:</span></span>  <br/> |<span data-ttu-id="e7f77-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="e7f77-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID EnableIdleRoutine(
  FTG ftg,
  BOOL fEnable
);
```

## <a name="parameters"></a><span data-ttu-id="e7f77-112">参数</span><span class="sxs-lookup"><span data-stu-id="e7f77-112">Parameters</span></span>

 <span data-ttu-id="e7f77-113">_ftg_</span><span class="sxs-lookup"><span data-stu-id="e7f77-113">_ftg_</span></span>
  
> <span data-ttu-id="e7f77-114">[in]标识非处于空闲状态的例程，以启用或禁用的函数标记。</span><span class="sxs-lookup"><span data-stu-id="e7f77-114">[in] Function tag that identifies the idle routine to be enabled or disabled.</span></span> 
    
 <span data-ttu-id="e7f77-115">_fEnable_</span><span class="sxs-lookup"><span data-stu-id="e7f77-115">_fEnable_</span></span>
  
> <span data-ttu-id="e7f77-116">[in]包含 TRUE，则空闲引擎应启用空闲例程或 FALSE，如果它应禁用。</span><span class="sxs-lookup"><span data-stu-id="e7f77-116">[in] Contains TRUE if the idle engine should enable the idle routine, or FALSE if it should disable it.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e7f77-117">返回值</span><span class="sxs-lookup"><span data-stu-id="e7f77-117">Return value</span></span>

<span data-ttu-id="e7f77-118">无。</span><span class="sxs-lookup"><span data-stu-id="e7f77-118">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e7f77-119">注解</span><span class="sxs-lookup"><span data-stu-id="e7f77-119">Remarks</span></span>

<span data-ttu-id="e7f77-120">下面的函数处理与 MAPI 空闲引擎和基于[FNIDLE](fnidle.md)函数原型的空闲例程：</span><span class="sxs-lookup"><span data-stu-id="e7f77-120">The following functions deal with the MAPI idle engine and with idle routines based on the [FNIDLE](fnidle.md) function prototype:</span></span> 
  
|<span data-ttu-id="e7f77-121">**空闲例行函数**</span><span class="sxs-lookup"><span data-stu-id="e7f77-121">**Idle routine function**</span></span>|<span data-ttu-id="e7f77-122">**使用情况**</span><span class="sxs-lookup"><span data-stu-id="e7f77-122">**Usage**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e7f77-123">ChangeIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="e7f77-123">ChangeIdleRoutine</span></span>](changeidleroutine.md) <br/> |<span data-ttu-id="e7f77-124">更改已注册的空闲例程的特征。</span><span class="sxs-lookup"><span data-stu-id="e7f77-124">Changes the characteristics of a registered idle routine.</span></span>  <br/> |
|[<span data-ttu-id="e7f77-125">DeregisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="e7f77-125">DeregisterIdleRoutine</span></span>](deregisteridleroutine.md) <br/> |<span data-ttu-id="e7f77-126">从 MAPI 系统中删除已注册的空闲例程。</span><span class="sxs-lookup"><span data-stu-id="e7f77-126">Removes a registered idle routine from the MAPI system.</span></span>  <br/> |
|<span data-ttu-id="e7f77-127">**EnableIdleRoutine**</span><span class="sxs-lookup"><span data-stu-id="e7f77-127">**EnableIdleRoutine**</span></span> <br/> |<span data-ttu-id="e7f77-128">禁用或重新启用注册空闲例程，但不从 MAPI 系统中移除它。</span><span class="sxs-lookup"><span data-stu-id="e7f77-128">Disables or re-enables a registered idle routine without removing it from the MAPI system.</span></span>  <br/> |
|[<span data-ttu-id="e7f77-129">FtgRegisterIdleRoutine</span><span class="sxs-lookup"><span data-stu-id="e7f77-129">FtgRegisterIdleRoutine</span></span>](ftgregisteridleroutine.md) <br/> |<span data-ttu-id="e7f77-130">将一个空闲例程添加到 MAPI 系统，使用或不启用它。</span><span class="sxs-lookup"><span data-stu-id="e7f77-130">Adds an idle routine to the MAPI system, with or without enabling it.</span></span>  <br/> |
|[<span data-ttu-id="e7f77-131">MAPIDeInitIdle</span><span class="sxs-lookup"><span data-stu-id="e7f77-131">MAPIDeInitIdle</span></span>](mapideinitidle.md) <br/> |<span data-ttu-id="e7f77-132">关闭调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="e7f77-132">Shuts down the MAPI idle engine for the calling application.</span></span>  <br/> |
|[<span data-ttu-id="e7f77-133">MAPIInitIdle</span><span class="sxs-lookup"><span data-stu-id="e7f77-133">MAPIInitIdle</span></span>](mapiinitidle.md) <br/> |<span data-ttu-id="e7f77-134">初始化调用应用程序的 MAPI 空闲引擎。</span><span class="sxs-lookup"><span data-stu-id="e7f77-134">Initializes the MAPI idle engine for the calling application.</span></span>  <br/> |
   
 <span data-ttu-id="e7f77-135">**ChangeIdleRoutine**、 **DeregisterIdleRoutine**和**EnableIdleRoutine**接受作为输入参数的函数标记，则由**FtgRegisterIdleRoutine**返回。</span><span class="sxs-lookup"><span data-stu-id="e7f77-135">**ChangeIdleRoutine**, **DeregisterIdleRoutine**, and **EnableIdleRoutine** take as an input parameter the function tag returned by **FtgRegisterIdleRoutine**.</span></span> 
  
<span data-ttu-id="e7f77-136">当平台的所有前景任务都变为空闲时，MAPI 空闲引擎将调用已准备好执行的最高优先级空闲例程。</span><span class="sxs-lookup"><span data-stu-id="e7f77-136">When all foreground tasks for the platform become idle, the MAPI idle engine calls the highest priority idle routine that is ready to execute.</span></span> <span data-ttu-id="e7f77-137">不没有呼叫之间空闲例程的相同的优先级顺序不做任何担保。</span><span class="sxs-lookup"><span data-stu-id="e7f77-137">There is no guarantee of calling order among idle routines of the same priority.</span></span> 
  

